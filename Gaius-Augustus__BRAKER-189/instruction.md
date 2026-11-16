# Issue

**Title:** Reproducible filter genemark

## Description

Use a fixed random seed for random selection of single-exon genes in `filterGenemark.pl` in order to make BRAKER runs reproducible.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `825cb5662f28`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.