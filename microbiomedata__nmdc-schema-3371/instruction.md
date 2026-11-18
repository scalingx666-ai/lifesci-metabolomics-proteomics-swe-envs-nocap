# Issue

**Title:** Remove internal spreadsheet reference from CreditAssociation

## Description

## Summary

Remove the internal NMDC spreadsheet and tab reference from the public `CreditAssociation` description, as requested in #3300.

The remaining description continues to explain that the class binds associated researchers to studies through a CRediT contributor role and a person value.

.

## Validation

- `make squeaky-clean all test linkml-lint`
- LinkML metamodel validation passed
- 93 Python tests passed
- Example generation and doctests passed
- All LinkML lint checks passed
- `git diff --check`

## Generated artifacts

The clean build exposed unrelated existing drift in tracked generated files under `nmdc_schema/`. Those files are intentionally excluded from this atomic source change, following the policy tracked in #1230. The observed drift was documented there for follow-up.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `385856ec8e0d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.