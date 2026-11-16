# Issue

**Title:** Ensure >= 4000 training genes

## Description

Check whether the number of "good" training genes selected from GeneMark is at least 4000. If not, add additional randomly selected genes to the set to ensure at least 4000 training genes.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `8c27e799f02d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.