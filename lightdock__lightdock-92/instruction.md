# Issue

**Title:** allow passed parser when calling run_simulation

## Description

When a parser is passed into the multiprocessing `run_simulation` it is not actually used.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `17941c591756`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.