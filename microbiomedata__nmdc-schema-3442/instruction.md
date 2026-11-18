# Issue

**Title:** Drop the mod_date re-evaluation claim from the badges description

## Description

Closes

The `badges` description said badges are recalculated when `ProvenanceMetadata.mod_date` changes. That trigger can't work (`mod_date` is one constant on 10,689 NCBI-ingested biosamples, ), and the squad decided on 2026-09-16 that awarding is additive and not driven by dates (). The description now states that instead. The test module docstring made the same claim about the subset dates and is corrected too.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c2ee3fc2d472`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.