# Issue

**Title:** Refactor Entropy computations

## Description

This fixes a formerly overlooked bug (the `neutral_losses` matching mode was not fully correct for the Entropy computation).

It further add functionalities:
- `Entropy` and `EntropyGreedy` now work for three different "matching modes" (`fragment`, `neutral_losses`, `hybrid` with the default being `fragment`)
- `FlashEntropy` not computes the `neutral_losses` mode correctly.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `8a769c8c0727`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.