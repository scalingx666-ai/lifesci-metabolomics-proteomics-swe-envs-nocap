# Issue

**Title:** Fix license classifier

## Description

The license changed from MIT to BSD in 5e8a7d7c85005bc4992ba95b0756cccff249189a but this one string was missed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `f7b895a82ed6`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.