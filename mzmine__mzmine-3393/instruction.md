# Issue

**Title:** baf: fix spectrum type availability check

## Description

null from the sql is mapped to 0 in mzmine, fix the spectrum type availability check for mixed cases

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `235cc9e48201`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.