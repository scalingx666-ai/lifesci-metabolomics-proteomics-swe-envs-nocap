# Issue

**Title:** Add load_collection_from_mgf: read mgf files directly into a SpectraCollection

## Description

(mgf part; MSP can follow the same template)

## What this adds

`load_collection_from_mgf(filename, metadata_harmonization=True, *, mz_precision=1e-6, mz_rounding="round") -> SpectraCollection` reads an mgf file straight into a `SpectraCollection`. `load_ms2_dataset` now uses it for `mgf` input, so existing callers get the speed-up without changing code.

The result is the same as `SpectraCollection(load_from_mgf(f))`: same metadata table (columns, order, dtypes, values) and the same CSR fragment array. The difference is how it gets there.

## Why the old path is slow

Profiling `load_ms2_dataset` on a 100k-spectrum mgf (80 MB) on `development`: 120 s wall, 389 MB peak. pyteomics needs about 6 s for the file. Almost all the rest is building 100k `Spectrum` objects that are thrown away right after: the per-spectrum `PickyDict` key harmonization alone is 5.3 M regex calls (~27 s), `Metadata.harmonize_values` re-wraps the dict in a `PickyDict` a second time, and every spectrum gets `Fragments` objects (with sortedness checks and copies) that `CSRFragmentCollection` then concatenates again.

## How the new path works

- pyteomics records are streamed into (a) a list of plain metadata dicts and (b) per-spectrum peak arrays plus lengths. No `Spectrum`, `Metadata`, `PickyDict` or `Fragments` objects are created.
- Metadata keys are harmonized with the existing `harmonize_metadata_column_name`, cached per distinct raw key (so once per column, not once per cell). Key order and duplicate-key handling mirror `PickyDict`: matchms-style keys keep their position, renamed keys follow in file order, an existing value wins over a renamed duplicate unless it is `None`, and a differing duplicate is logged. This is what keeps the column order identical to the old path.
- Metadata values go through the same code as `Spectrum` does: the body of `Metadata.harmonize_values` is lifted into a module-level `harmonize_metadata_values(dict) -> dict` in `matchms.metadata`, and `Metadata.harmonize_values` now calls it. No behaviour change for `Spectrum`.
- Then the usual collection-level `harmonize_metadata_collection_columns` / `harmonize_metadata_types`, exactly as `SpectraCollection._construct_metadata`.
- Fragments are built in one go by a new `CSRFragmentCollection.from_peak_arrays(lengths, mz, intensities, ...)`. `load_from_parquet` now uses this too instead of its private `_build_fragment_collection`.
- The record-to-collection step lives in `matchms/importing/collection_builder.py` (`build_spectra_collection(records, ...)`), so an MSP collection importer only needs to yield `(params, mz, intensities)` tuples from `parse_msp_file`.

## Numbers

Synthetic mgf, 100,000 spectra, 3.2 M peaks, 8 metadata fields per spectrum, 80 MB, laptop:

| | wall time | peak memory (tracemalloc) |
|---|---|---|
| `load_ms2_dataset` before (`SpectraCollection(load_from_mgf(f))`) | 120 s | 389 MB |
| `load_ms2_dataset` now (`load_collection_from_mgf`) | 11.8 s | 329 MB |
| pyteomics parsing alone | 6.2 s | |

So about 10x faster, of which pyteomics is now more than half. Peak memory is dominated by holding the parsed records until the arrays are concatenated; the big win here is time.

## Tests

`tests/importing/test_load_collection_from_mgf.py`:
- for every mgf fixture in `tests/testdata`, with and without `metadata_harmonization`: metadata frame identical (columns, order, dtypes, values via `assert_frame_equal`) and fragment CSR identical (`indptr`, `indices`, `data`) to `SpectraCollection(load_from_mgf(f))`
- row reconstruction gives the same spectra as `load_from_mgf`
- path, string and stream input; missing file; file without spectra; `mz_precision` / `mz_rounding` pass-through, also via `load_ms2_dataset`
- a hand-written mgf with `Precursor_MZ`, `Compound Name`, `RTINSECONDS`, `CHARGE=2+` and `PEPMASS` with intensity, checked against the Spectrum path for key order and duplicate handling
- `harmonize_metadata_values` gives the same dict as `Metadata.harmonize_values`
- `from_peak_arrays` equals the Spectrum-based `CSRFragmentCollection` (including summed duplicate bins and an empty spectrum) and rejects inconsistent input

Empty mgf input keeps raising `ValueError("Spectra must contain at least one Spectrum.")`, the message the CLI relies on to report `empty_spectra`.

Full suite locally (Windows, numba enabled): everything passes except the four ANN tests in `test_base_embedding_similarity.py` / `test_binned_embedding_similarity.py`, which fail identically on a clean `development` checkout here (same as noted in #1017).

## Notes

- Not changed: `load_from_mgf` still returns `Spectrum` objects, as before.
- MSP: `parse_msp_file` already yields dicts, so `load_collection_from_msp` is a small follow-up on top of `build_spectra_collection`. Happy to do it in a second PR once the shape here is OK.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `2a3b6ced302f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.