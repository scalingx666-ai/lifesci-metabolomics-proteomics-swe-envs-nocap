# Issue

**Title:** Migrate/python 313

## Description

This adds support for python 3.13 as mentioned in #728 and #803 and bumps some dependencies:
* numPy `>1.24` ->` >=2.0.0` (numPy 1 support is dropped!)
* scipy `^1.14.1` -> `^1.15.3`
* lxml `^4.9.3` -> `^5.4.0`
* numba `^0.60.0` -> `^0.61.0`
* sparsestack `>=0.6.0` -> `>=0.7.0` (needs to be released )

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d8386466767e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.