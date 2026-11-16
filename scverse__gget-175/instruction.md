# Issue

**Title:** [muscle] remove temp fasta even if output is not specified

## Description

Removal of `abs_fast_path` should not depend on whether or not `out` is `None`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `07afc3ff34cd`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.