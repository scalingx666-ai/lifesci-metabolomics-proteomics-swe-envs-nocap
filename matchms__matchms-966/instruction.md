# Issue

**Title:** Speedup filters

## Description

Add SpectraCollection-optimized implementations for important filter functions:
- `remove_peaks_relative_to_precursor_mz`
- `remove_profiled_spectra`
- `require_precursor_mz`

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `591b1486e6d0`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.