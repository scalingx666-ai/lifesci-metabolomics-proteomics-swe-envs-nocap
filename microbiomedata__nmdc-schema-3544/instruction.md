# Issue

**Title:** Keep the base id slot's MAG example out of every class's id

## Description

## Why

Built with linkml 1.12, the JSON Schema carries slot examples, and every class's `id` showed the base slot's MAG id `nmdc:mgmag-00-x012.1_7_c1`. That example fails the class's own id pattern for 40 of 57 classes, so a reader looking at Biosample for a sample id got a MAG id. 11.24.1 had no id examples in its JSON Schema.

Fixes

## What changed

- `src/schema/basic_slots.yaml`: the base `id` slot loses its example, and a note in its `notes` says why and that id examples belong in each class's `slot_usage`. NcbiTaxon's own `id` example (`NCBITaxon:511145`) is unchanged.
- `tests/test_id_examples_match_class_patterns.py`: every example on a class's induced `id` slot must match that class's induced `id` pattern.

## Validation

- Built `nmdc_materialized_patterns.schema.json` the way the Makefile does, on linkml 1.12.1. On main: 57 classes with an `id`, 57 with id examples, 40 examples failing their class pattern. With this PR: 1 class with an id example (NcbiTaxon), 0 failing.
- The new test fails on main (40 failed, 18 passed) and passes with the fix.
- `uv run pytest tests`: 565 passed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `41da3b4a7a9d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.