# Issue

**Title:** Change rdkit version constraint to minimum

## Description

Currently rdkit is restricted to <2025 (which is not ideal).

--> Maybe we should also allow newer versions of other dependencies?

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `2508b1e245ed`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.