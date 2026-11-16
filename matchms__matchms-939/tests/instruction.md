# Issue

**Title:** Adjust matchms default filter execution order

## Description

- Adjust the filter order --> Now `normalize_intensities` is at the end
- Remove default `select_by_mz` from `CLEAN_PEAKS` because I would consider removing peaks above 1000 Da as too optinionated/not general enough.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `66af954b4658`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.