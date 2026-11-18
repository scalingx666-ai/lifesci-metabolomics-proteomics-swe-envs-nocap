# Issue

**Title:** Map QuantityValue to schema:QuantitativeValue, which schema.org defines

## Description

## Why

This PR closes no issue.

`QuantityValue` carried `schema:QuantityValue` in its generic `mappings`, and schema.org defines no such type: https://schema.org/QuantityValue returns 404 and https://schema.org/QuantitativeValue returns 200 (checked 2026-11-03). `QuantitativeValue` has `value`, `minValue`, `maxValue` and `unitCode`, which line up with `has_numeric_value` (already mapped to `schema:value`), `has_minimum_numeric_value`, `has_maximum_numeric_value` and `has_unit` (already mapped to `schema:unitCode`).

Only the mapping changes. `class_uri` stays `nmdc:QuantityValue`, so the `rdf:type` of instances and the JSON-LD context are unchanged, and in the OWL output one `skos:mappingRelation` object changes. It stays in generic `mappings` because `src/docs/maintaining-the-schema.md` reserves that metaslot for the existing schema.org, QUDT and PROV alignments.

## What changed

One line in `src/schema/attribute_values.yaml`.

## Validation

`make all test` exits 0 with 667 passed after merging main (a7f2dfaec) on 2026-11-03. Generated `nmdc_schema/` files stay uncommitted, as this repo does for development PRs.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d80bbef07ed9`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.