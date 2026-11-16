# Issue

**Title:** Issues/721

## Description

## Describe your changes
I added pre-commit functionality that runs ruff for linting and pytest.

## Issue ticket number and link


## Checklist before requesting a review
- [x] I have performed a self-review of my code
- [x] I have added thorough tests to see if it is a core feature.

## Known Issues

Although I tested it, I am unsure if pytest runs smoothly (there was no error, but that's often a good thing).

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d46de7649a36`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.