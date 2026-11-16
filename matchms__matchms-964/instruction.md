# Issue

**Title:** make `default_filters` accept a SpectraCollection

## Description

The functions called in `default_filters` already support SpectraCollection, so this just updates the type hints and docstring to match.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `591b1486e6d0`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.