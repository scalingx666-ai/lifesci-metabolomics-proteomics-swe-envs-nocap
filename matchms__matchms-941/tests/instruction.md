# Issue

**Title:** Add central entropy implementations

## Description

Adds:
- new `EntropyGreedy` class for a (codewise-) simpler Entropy computation
- new `Entropy` class as main go-to-option --> this uses `EntropyGreedy` for individual pair computations, but defaults to the faster `FlashEntropy` solution adapted from the Fiehn group when `matrix()` is called. 

Addresses #940

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e93899d07052`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.