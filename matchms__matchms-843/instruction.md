# Issue

**Title:** Add progress bar option (to allow silencing)

## Description

Added progress bar option to matrix and sparse_array methods.

In some downstream applications (e.g. ms2query) it can be annoying to have progress bars for every tiny .matrix() calculation. So it should be possible to switch this off.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `65d38f76221f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.