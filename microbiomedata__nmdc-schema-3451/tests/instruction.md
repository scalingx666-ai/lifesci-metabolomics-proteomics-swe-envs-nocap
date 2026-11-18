# Issue

**Title:** Add titles to Biosample slots that lacked one

## Description

## Why

Part of  The Data Portal's sample page labels each Biosample field with the slot's top-level `title` (`formatSlotLabel` in nmdc-server) and otherwise capitalizes each word of the slot name, so `ncbi_taxonomy_name` shows as "Ncbi Taxonomy Name". This adds titles to the 35 Biosample slots that had none, and a test so new Biosample slots can't arrive without one.

Titles use Title Case to match the portal's existing labels and the existing identifier titles (e.g. "GOLD Study Identifiers"). Where the portal already hard-codes a label (`Ecosystem Category`, `Specific Ecosystem`, etc.) the title matches it.

Points for review:

- `id` and `name` are shared by every class, so they get `ID` and `Name`, not the portal's Biosample-specific "Sample ID" and "Sample Name".
- `badges` gets `Metadata Quality Badges`; the portal's facet label is "Metadata Quality".
- `proport_woa_temperature` and `soluble_iron_micromol` have no description, so their titles (`Proport WOA Temperature`, `Soluble Iron (micromol)`) only restate the name with capitalization. Better titles need someone who knows what these fields hold.

## Validation

`make squeaky-clean all`, `make test` and `make linkml-lint` pass locally. The new test fails against the committed 11.24.0 materialized schema and passes after the rebuild. Generated artifacts are not committed, per the release process.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `6fea28e893a8`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.