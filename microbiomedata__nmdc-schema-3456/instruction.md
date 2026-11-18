# Issue

**Title:** Add titles to MetadataBadgeEnum values

## Description

## Why

The Data Portal shows badge names by converting the snake_case value (`snakeToSentenceCase`).  proposes reading schema titles instead, and the `MetadataBadgeEnum` values had none. This adds them, matching what the portal displays today, so switching over changes nothing on screen:

- `biogeochemistry`: Biogeochemistry
- `host_information`: Host Information
- `expert_curation`: Expert Curation

`test_badge_subset_sync.py` gains a check that every badge value has a title, so new badges arrive with one.

Related:

## Validation

`make squeaky-clean all`, `make test` and `make linkml-lint` pass locally. The new test fails before the change and passes after it.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ab582f1b3745`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.