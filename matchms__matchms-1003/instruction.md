# Issue

**Title:** Add "sirius" export style for mgf files

## Description

## What

Adds `export_style="sirius"` to `save_as_mgf` (and therefore `save_spectra`, `Spectrum.metadata_dict` / `to_dict`). It is a new column in `matchms/data/export_key_conversions.csv`, so it follows the same mechanism as the existing `gnps`, `nist`, ... styles.

Following @florian-huber's comment on the issue, this translates the matchms keys back to SIRIUS terms on export rather than attempting a passthrough of the original keys.

## Which keys

I took the key list from SIRIUS's own mgf parser ([`MgfParser.java`](https://github.com/sirius-ms/sirius/blob/4a749a8b010205bd6240bd2e9619d95600dfd855/io/src/main/java/de/unijena/bioinf/babelms/mgf/MgfParser.java#L140-L255)) and writer, not from memory:

| matchms | sirius | note |
|---|---|---|
| `precursor_mz` | `PEPMASS` | |
| `charge` | `CHARGE` | SIRIUS's `CHARGE_PATTERN` accepts `-1`, `1-` and `1+` |
| `ms_level` | `MSLEVEL` | |
| `retention_time` | `RTINSECONDS` | no unit conversion is done; documented in the docstring |
| `adduct` | `ION` | what SIRIUS's own writer emits |
| `feature_id` | `FEATURE_ID` | new matchms row, only the sirius style exports it; keeps the feature id of files that came from SIRIUS/MZmine |
| `compound_name` / `title` / `scans` | `NAME` / `TITLE` / `SCANS` | SIRIUS uses these as the feature name |
| `smiles`, `inchi`, `inchikey`, `formula` | same, upper case | |
| `instrument_type` | `SOURCE_INSTRUMENT` | same as the gnps style |

**Deliberately left out: `ionmode`.** In the SIRIUS parser every keyword that *starts with* `ION` goes through the adduct branch; `IONMODE=positive`/`negative` is handled, but a value such as `n/a` (common in GNPS exports, e.g. `tests/testdata/testdata.mgf`) raises `Unknown ion 'n/a'` and aborts the import of that spectrum. SIRIUS takes the polarity from `CHARGE` anyway.

## Tests

- `tests/test_key_conversion.py`: three `sirius` cases (key renaming, `FEATURE_ID`/`ION`, and that `ionmode` is not exported).
- `tests/exporting/test_save_as_mgf.py`: `sirius` added to the parametrized export-style test, plus `test_save_as_mgf_sirius_style` which writes a spectrum with the sirius style, checks the exact lines in the file (`PEPMASS=`, `CHARGE=-1`, `MSLEVEL=2`, `RTINSECONDS=61.2`, `ION=[M-H]-`, `NAME=`, `FEATURE_ID=`, `SMILES=`), checks that no matchms-only key leaks into the file, and reads it back with `load_from_mgf`.

```
$ pytest tests/test_key_conversion.py tests/exporting tests/test_metadata.py tests/test_spectrum.py tests/importing/test_load_from_mgf.py -q
153 passed in 5.71s
```

`ruff check` reports no new findings on the changed files (only the pre-existing ones that `master` also has).

Also updated: the export-style lists in the docstrings of `save_as_mgf`, `save_as_json`, `save_as_msp`, `save_spectra` and `Spectrum`, and `CHANGELOG.md`.

I have not run the exported file through SIRIUS itself (no SIRIUS install here), only checked against the parser source. If someone with SIRIUS at hand can confirm the import works, that would be a good last check.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7d960b001e52`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.