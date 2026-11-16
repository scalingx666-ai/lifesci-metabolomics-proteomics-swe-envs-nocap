# Issue

**Title:** fix boxplot header name

## Description

Name was just Height or normalized height, which lead to confusion with the regular height and area columns.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `216cf1f737c3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.