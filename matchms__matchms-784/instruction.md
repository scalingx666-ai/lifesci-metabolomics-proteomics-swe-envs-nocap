# Issue

**Title:** Remove custom chain method

## Description

Importing load_spectra used a custom chain method, which is not necessary.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `0569be08cc80`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.