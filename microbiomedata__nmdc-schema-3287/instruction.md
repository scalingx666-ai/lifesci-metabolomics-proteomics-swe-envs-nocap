# Issue

**Title:** Deprecate `collection_date_inc`

## Description

Related to 
- 

Per the issue, with new modeling and the expected field to lab schema expansions for NMDC, we no longer need this slot. Rather, the individual samples are modeled separately. The field collection date of the incubation sample can be informed by looking at the original biosample, following some process, and the incubation sample's collection date is just `collection_date` no longer needing `incubation_collection_date`

This PR adds the initial steps for deprecation.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `258b0aa79663`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.