# Issue

**Title:** wizard: always add ms1 mobility scan mass detection step

## Description

when importing an ims imaging file manually but then running the wizard on it, the batch would fail because the ims file did not have mass detection run on ims scans, because the wizard assumed the mass lists were present due to the advanced import

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3117ae2f4d75`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.