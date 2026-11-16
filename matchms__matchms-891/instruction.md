# Issue

**Title:** Ignore mass shifts < tolerance for Flash-style computations

## Description

Recently, a small change was added to `ModifiedCosineGreedy` and `ModifiedCosineHungarian` to ignore precursor-m/z shifts when they are `< tolerance`  because that would often lead to undesired results.

This is now also implemented for the `FlashCosine` similarity implementation.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `350f43a3df05`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.