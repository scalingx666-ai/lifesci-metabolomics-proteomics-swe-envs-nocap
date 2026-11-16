# Issue

**Title:** Adapt the describe_chemical function to the new api

## Description

I simply changed the endpoint. It returns a nested dict containing the response, is this what is expected or shall I generate an object containing all properties?
This should solve #50.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `f05bd1eb3aca`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.