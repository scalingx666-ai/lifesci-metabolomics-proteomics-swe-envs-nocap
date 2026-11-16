# Issue

**Title:** [RCSB SeqMotif Search] - Implemented SeqMotif Search

## Description

## Pull Request Notes

Implemented searching using SeqMotifs, similar to the other search functions I implemented.

## Testing

Tests pass using `pytest`.
Typing passes with `mypy --namespace-packages pypdb/path/to/file.py`, for all changed files.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d235c363c302`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.