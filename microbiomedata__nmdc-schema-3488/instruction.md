# Issue

**Title:** Allow Python 3.14 and test it in CI

## Description

## Why

Closes  nmdc-schema couldn't be installed on Python 3.14. A library should not exclude a released Python it works on, and adding 3.14 to the CI matrix makes sure it keeps working.

The lock picks networkx 3.4.2 on Python 3.14, because networkx 3.6.1 declares `!=3.14.1`. Python 3.10 already uses that version. CLAUDE.md's note on supported Pythons is updated to match.

## Validation

Locally on Python 3.14.8: `poetry install` succeeds and `make squeaky-clean all test` passes (431 tests). The regenerated artifacts match `main` except for the generation timestamp.

This PR and  both change `poetry.lock`, so whichever merges second needs a `poetry lock` on top.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `b6926b73faa0`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.