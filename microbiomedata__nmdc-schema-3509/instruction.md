# Issue

**Title:** Remove assets/mongodb_queries

## Description

Closes  Closes

Replaces  where @aclum pointed out that `linked_instances` does these traversals better and the files aren't needed:

For traversals, see `get_linked_instances` in https://github.com/microbiomedata/nmdc-client; for reference checks, https://github.com/microbiomedata/refscan.

The only other reference in the repo was this directory's `.gitattributes` line, removed here. No other microbiomedata repo references these files.

 allowlists these files in its unreferenced-assets test, so whichever PR merges second must drop those entries.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d4bd09426685`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.