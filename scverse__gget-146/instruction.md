# Issue

**Title:** cbio: fix support for pre-2.1.0 pandas

## Description

Fix support for pre-2.1.0 pandas by automatically aliasing `pd.DataFrame.map` to be `pd.DataFrame.applymap` when `pd.DataFrame.map` is not found

Also allows plotting even for studies that do not contain `cna` or `sv` data

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `eea4fd7fbf48`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.