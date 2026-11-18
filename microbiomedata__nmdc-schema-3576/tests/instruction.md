# Issue

**Title:** Updates to ProcessingInstitutionEnum permissible values

## Description

This PR adds permissible values to ProcessingInstitutionEnum to account for DataGeneration records in mongo which do not have an assigned processing_institution.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `884b28002529`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.