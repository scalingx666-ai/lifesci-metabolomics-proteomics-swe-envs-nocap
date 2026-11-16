# Issue

**Title:** replace guava range map with SimpleDoubleRangeMap

## Description

2.6-4.6x speed up during spectra merging

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ea6ee5e46409`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.