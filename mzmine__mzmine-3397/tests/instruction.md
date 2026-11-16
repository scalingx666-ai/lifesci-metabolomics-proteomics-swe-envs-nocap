# Issue

**Title:** fix mzml parsing for "inf" precursor

## Description

fix parsing in case "inf" is the value of the precursor mz.
Als add toString methods so we get better error info

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `644a28e697ae`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.