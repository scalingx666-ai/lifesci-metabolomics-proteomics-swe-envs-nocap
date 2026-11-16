# Issue

**Title:** Add central similarity score default parameters

## Description

Many of the matchms similarity scores have overlapping parameters. This PR now add a `default_parameters.py` file were central parameters can be set. This is to avoid setting slightly different defaults in different methods (which could lead to unintended variation/mistakes).

This will fix #876

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `66af954b4658`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.