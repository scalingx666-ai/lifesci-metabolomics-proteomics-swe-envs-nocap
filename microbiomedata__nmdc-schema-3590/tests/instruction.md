# Issue

**Title:** Expand QUDT CURIEs to namespaces QUDT still serves

## Description

## Why

This PR closes no issue. Part of:

-

The `qudt` prefix expanded to `http://qudt.org/1.1/schema/qudt#`, which returns 404. It now expands to `http://qudt.org/schema/qudt/`, which the LinkML metamodel's units module and prefixmaps use, and where `Unit` returns 200 (both checked 2026-11-03).

QUDT keeps units and quantity kinds in separate vocabularies, so two prefixes are added under QUDT's own names: `unit:` (`http://qudt.org/vocab/unit/`) and `quantitykind:` (`http://qudt.org/vocab/quantitykind/`). `qudt:DEG_C` on UnitEnum `Cel` becomes `unit:DEG_C`, and the `has_quantity_kind_id` examples become `quantitykind:Temperature` and `quantitykind:MassConcentration`. All three returned 200 on 2026-11-03, and a made-up unit returned 404.

`has_unit` now maps to `qudt:hasUnit`. QUDT deprecated `qudt:unit` in favor of it, and `http://qudt.org/schema/qudt/unit` returns 404 while `http://qudt.org/schema/qudt/hasUnit` returns 200 (checked 2026-11-11).

-

Stored records keep their CURIEs, so there is no migration; only the generated expansions change (JSON-LD context, OWL, RDF).

## What changed

- The `qudt` prefix in `nmdc.yaml`, `core.yaml`, `basic_slots.yaml` and `nmdc_types.yaml`, and two new prefixes in `nmdc.yaml`.
- One mapping and two examples in `attribute_values.yaml`.

## Validation

`make all test` exits 0 with 667 passed after merging main (a7f2dfaec) on 2026-11-03. Generated `nmdc_schema/` files stay uncommitted.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d80bbef07ed9`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.