# Issue

**Title:** Require Python3 for all of BRAKER

## Description

A Python script is now a part of Augustus training set preparation, and it is expected that more Python scripts will be added into BRAKER in the future.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `15dcca5a3654`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.