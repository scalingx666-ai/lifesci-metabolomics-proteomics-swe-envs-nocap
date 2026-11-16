# Issue

**Title:** mspepsearch: fix discovery and library path

## Description

It was assumed that MsPepSearch is in the NIST26 directory, which is not the case. the installer puts it into NIST26/MSSEARCH. Cover both cases even though i dont know how it would end up in NIST26 in the first place

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `befbfb48b161`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.