# Issue

**Title:** fix(types): annotate pdb URL fallback list

## Description

## Summary
- Add an explicit type annotation for the PDB URL fallback list.
- Fix the remaining mypy list item errors in `gget_pdb.py`.
- No runtime behavior changes.

## Validation
- Ran `pre-commit run mypy --files gget/gget_pdb.py`.

Part of #216.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `5506537f52e3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.