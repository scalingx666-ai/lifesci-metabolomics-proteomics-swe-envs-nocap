# Issue

**Title:** Allow pressure compensation for bruker tdf data

## Description

Allow pressure compeensation for ims tdf data
main fix is sorting of the mobility ranges before indexing them
add parameters to preferences + vendor options + mapping for old parameter sets

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7312cf2c419f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.