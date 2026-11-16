# Issue

**Title:** fix basic search requests

## Description

Fixes 

Best I can tell, this package has malformed queries for basic searches. A basic search should have `query.type.service = "full_text"` (not "text").

See the Search API docs for more info: https://search.rcsb.org/index.html#return-type

This PR fixes the broken unit tests and demo notebook.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `6bef095fa776`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.