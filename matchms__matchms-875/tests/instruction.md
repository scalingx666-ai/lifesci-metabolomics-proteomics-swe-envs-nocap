# Issue

**Title:** Linear cosine

## Description

- Adds `LinearCosine`, a linear-time cosine similarity from the SIRIUS framework. After a one-time peak merge that enforces well-separated m/z gaps (> 2× tolerance), scoring runs in `O(n+m)` via a two-pointer sweep, versus O(n³) for `CosineHungarian`.
- Adds a `pytest-benchmark` suite comparing `matrix()` performance of `CosineHungarian`, `CosineGreedy`, `LinearCosine`, and `FlashSimilarity` on synthetic spectra (sizes 50 / 100 / 200).

## Algorithm

The algorithm has two phases, both implemented as Numba-jitted functions for decent performance.

**Phase 1: Merge close peaks** (`sirius_merge_close_peaks`):
Processes peaks in descending intensity order. Each unconsumed peak adopts its own m/z and sums the intensities of all unconsumed neighbors within a 2× tolerance window. The result is guaranteed to have consecutive m/z gaps > 2× tolerance, meaning each peak can match at most one partner in the other spectrum. Ask @Adafede why this is a good idea in practice. @oolonek might have a different opinion.

**Phase 2: Two-pointer cosine** (`linear_cosine_score`):
Walks both sorted spectra. Matching peaks (|Δm/z| ≤ tolerance) contribute `mz^mz_power · intensity^intensity_power` products to the cosine numerator. Single pass, O(n+m).

The `matrix()` override pre-merges all spectra once (N+M calls) instead of redundantly merging during each of the N×M pairwise comparisons, and exploits `is_symmetric=True` to halve work for all-vs-all comparisons.

## Testing

Reference data in `tests/linear_cosine_reference.json` covers **6 real compounds** (aspirin, cocaine, glucose, hydroxy-cholesterol, phenylalanine, salicin) across **4 parameter sets** (varying tolerance, mz_power, intensity_power), obtained from the Rust impl.

## Benchmarks

Added `pytest-benchmark` as a dev dependency with `addopts = "--benchmark-disable"` so normal test runs are unaffected. Run with:

```bash
uv run pytest tests/similarity/test_bench_matrix.py --benchmark-enable -v
```

Results (single-threaded, `is_symmetric=True`, synthetic spectra with ~18 overlapping peaks per pair):

| Function | 50 spectra | 100 spectra | 200 spectra |
|---|---|---|---|
| **FlashSimilarity** | 4.9 ms | 11.9 ms | 33 ms |
| **LinearCosine** | 7.2 ms | 27 ms | 108 ms |
| **CosineGreedy** | 42 ms | 166 ms | 666 ms |
| **CosineHungarian** | 114 ms | 451 ms | 1,777 ms |

I was expecting the new LinearCosine to be faster than FlashSimilarity, so maybe there is space for improvement.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3ecc41aa0a16`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.