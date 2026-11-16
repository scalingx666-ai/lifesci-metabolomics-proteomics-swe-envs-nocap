# Issue

**Title:** fix baseline corrector

## Description

if a trace had no detected peaks, the buffer arrays were reassigned leading to data corruption

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `0bbf119cfddf`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.