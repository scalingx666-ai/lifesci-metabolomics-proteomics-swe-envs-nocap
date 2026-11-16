# Issue

**Title:** Add ensembl plants to search

## Description

This PR adds the ability to search the ensembl plants database.

Main changes:

- switch database server to the EBI one, which includes all organisms
- add a database argument to the gget_species_options function

The resulting ensemble IDs are retrievable with e.g. seq, so no changes to other subcommands appear to be needed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `261e037232cc`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.