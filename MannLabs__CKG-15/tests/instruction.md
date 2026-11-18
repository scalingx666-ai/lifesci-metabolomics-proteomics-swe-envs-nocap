# Issue

**Title:** filenaming issue with wget in dockerfile

## Description

Dockerfile would create the file /var/lib/neo4j/data/backup/ckg_080520.dump?dl=1 not /var/lib/neo4j/data/backup/ckg_080520.dump so the loading command would file

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `57ee21804a8a`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.