# Issue

**Title:** Batch fix step duplication

## Description

- Remove hashCode and equals implementation of MZmineProcessingStepImpl
  - this fixes not working duplication and subsequent movement in the batch dialog
- Add test for RawDataSavingUtils

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `729d46c5cb74`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.