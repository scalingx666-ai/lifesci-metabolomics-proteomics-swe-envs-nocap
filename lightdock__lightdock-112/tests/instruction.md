# Issue

**Title:** cast PyObject to PyArrayObject for python 3.13 support

## Description

previously lightdock wouldn't build on python 3.13.5 (debian 13.1), so i've added a simple cast to the numpy C variables to fix the compiler error.

i've based this on 1.0.0-pre2, so i'm PRing against that branch.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `56f273a1e0ee`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.