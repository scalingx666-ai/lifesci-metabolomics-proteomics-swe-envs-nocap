# Issue

**Title:** Handle fragment precision

## Description

- rename `bin_size` to `mz_precision`
- `CSRFragmentCollection` now supports two `mz_rounding` modes: `round` (default) or `floor`
- the new rounding to set precision also avoids more decimals than the precision delivers in the final file exports

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `360bdcf4df1f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.