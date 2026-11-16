# Issue

**Title:** Standard compound normalizer modes and IS selection based on alignment rate

## Description

- prefer IS rows with highest number of detections across all reference samples
- ties are resolved by highest sum intensity and then by score derived from distance

reasoning is that the user provided RT and mz are often far from measured value and then FT ringing or other interferences might be picked instead if its only distance based.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9f386b2a0687`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.