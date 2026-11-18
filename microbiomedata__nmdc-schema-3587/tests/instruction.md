# Issue

**Title:** Set partial_match on the MIxS patterns that linkml-runtime 1.12 would anchor twice

## Description

## Why

This handles `cult_root_med` and `genetic_mod` from  That issue stays open for `salinity_meth`, which keeps its doubled anchors until submission-schema builds with linkml 1.12.

linkml-runtime 1.12.1 wraps each resolved pattern as `^(?:...)$` unless the structured pattern sets `partial_match: true`. MIxS anchors its own syntax values, and of the 212 anchored patterns in `src/schema/mixs.yaml` on main, 210 set `partial_match: true`. `cult_root_med` and `genetic_mod` leave it unset, as MIxS v7.0.1 does, so they resolve to `^(?:^...$)$`. The doubled anchors were redundant, so both patterns match the same values as before and no migrator is needed.

`salinity_meth` is defined in `nmdc.yaml` and keeps its doubled anchors on purpose: submission-schema imports it and still builds with linkml-runtime 1.9.5, which adds no anchors. It stays in `KEEP_ANCHORS` until submission-schema builds with linkml 1.12.

## What changed

`assets/yq-for-mixs-dematerialize.yq` sets `partial_match: true` on a MIxS structured pattern that carries its own `^...$` anchors and leaves `partial_match` unset. That matches the other 210 anchored MIxS patterns, so linkml 1.12 adds no wrapper and the MIxS anchors still require a full match. An earlier version of this PR stripped the anchors instead, which left both slots unanchored in submission-schema, because it builds with linkml-runtime 1.9.5. `src/schema/mixs.yaml` is generated and committed. I applied the new rule to it directly, without a fresh MIxS download, and checked that on main's `mixs.yaml` the rule selects only `cult_root_med` and `genetic_mod` and selects nothing after the edit. `tests/test_structured_pattern_anchors.py` now covers `mixs.yaml`, and a new test resolves every pattern, imports included, with `SchemaView.resolve_pattern` and fails on any doubled anchor. It resolves from source because `nmdc_materialized_patterns.yaml` is only regenerated at release.

## Validation

`make all test` exits 0 with 742 passed after merging current main (2026-11-10). In the regenerated `nmdc_materialized_patterns.yaml`, `^(?:^` patterns drop from 3 to 1 (`salinity_meth`). Built against this branch, submission-schema's `make all` and `make test` (44 passed) succeed, and its `cult_root_med` and `genetic_mod` patterns are identical to those on its main, so `genetic_mod` still rejects `deleted the lacZ gene, see doi:10.1234/abc`. Generated `nmdc_schema/` files stay uncommitted.

## Documentation impact

None beyond comments in the yq file and the test docstring.

## Scope and complexity

One yq step, two generated lines in `mixs.yaml`, and tests.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3e992c458a46`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.