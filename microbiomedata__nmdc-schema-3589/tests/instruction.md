# Issue

**Title:** Remove the unused id_locus setting

## Description

## Why

Closes

`id_locus` is defined under `settings` in `src/schema/nmdc.yaml` and no structured pattern uses it: `{id_locus}` appears nowhere in `src/schema`. @sujaypatil96, I asked in the issue whether it has a use I'm missing; if so, please say so here and I'll close this PR.

A GitHub code search across microbiomedata (2026-11-03) found `id_locus` outside nmdc-schema only in the nmdc-runtime minter, which has its own `id_locus_pattern` regex and does not read the schema setting (read from source, not run):

- https://github.com/microbiomedata/nmdc-runtime/blob/b46768c46/nmdc_runtime/minter/domain/model.py#L103

No pattern changes, so there is no migration. The frozen migrator `migrator_from_10_3_0_to_10_4_0.py` quotes `{id_locus}` in a string and is unaffected.

## What changed

- The `id_locus` setting is removed from `src/schema/nmdc.yaml`.
- `tests/test_structured_pattern_anchors.py` now checks every `id_*` setting for anchors instead of naming two.

## Validation

`make all test` exits 0 with 667 passed after merging main (a7f2dfaec) on 2026-11-03. The committed `nmdc_schema/` files keep `id_locus` until the release regenerates them; the regenerated copies stay uncommitted.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3e992c458a46`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.