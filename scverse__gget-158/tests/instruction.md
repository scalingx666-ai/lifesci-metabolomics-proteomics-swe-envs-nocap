# Issue

**Title:** gget_setup.py: Several fixes

## Description

Fixes a few warnings that pop up when building `gget` from source on modern python versions (>=3.12).

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `4c8c2568102e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.