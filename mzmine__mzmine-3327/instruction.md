# Issue

**Title:** charts: default visible for value marker

## Description

earlier the chart theme always made markers visible, now they were missing in the pca/volcano plot. make them visible by default, but this way the chart theme does not always make them visible if they were turned off before.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d9e2d529cfc6`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.