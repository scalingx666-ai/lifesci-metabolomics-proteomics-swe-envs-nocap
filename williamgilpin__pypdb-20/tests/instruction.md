# Issue

**Title:** [API Refactor / Update] - Factored out HTTP Methods into separate file, added tests

## Description

I factored the HTTP methods out of `pypdb.py`, so they can be reused in API implementations.

I also added tests to verify behaviour is as expected, using the `unittest` and `mock` python standard libraries.

Also, apologies for the insignificant whitespace changes; I formatted `pypdb.py` to conform to PEP8 by accident.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `63903cbad572`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.