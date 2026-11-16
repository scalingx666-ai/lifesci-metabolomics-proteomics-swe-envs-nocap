# Issue

**Title:** Fix version update in pyproject.toml

## Description

This reduces the need to update the version in `pyproject.toml` and `__version__.py`

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `8a839cdd92e3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.