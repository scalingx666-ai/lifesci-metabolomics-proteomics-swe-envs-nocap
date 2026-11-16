# Issue

**Title:** Allow peaks with many floating types

## Description

A tiny quality-of-life addition: I've relaxed the assertion check for `Fragments.mz` and `Fragments.intensitities` dtypes. Now, any "floaty" type is acceptable - including `np.float16`, `np.float32` and `np.float64`. Added tests for this too.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `904457b2a2ef`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.