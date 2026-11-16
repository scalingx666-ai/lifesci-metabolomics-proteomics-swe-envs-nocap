# Issue

**Title:** Fix saving bug

## Description

Saving with spectrum processor had a bug introduced in #651 
When a spectrum is set to None it would still try to save it resulting in the pipeline breaking.

Maybe we should also add the ability to handle None values in the general save functions, but for now a quick fix.

@tornikeo fyi

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7b7fe7e24f87`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.