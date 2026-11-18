# Issue

**Title:** Remove the yq lines that create an empty `internal_standard` slot

## Description

Closes  (A yq customization creates an empty `internal_standard` slot).

Commit 08ce09a7c, part of the SIP work, removed `internal_standard` from `assets/import_mixs_slots_regardless.tsv` and deleted its examples line. Two other customizations for that slot stayed: one sets its range and one deletes its `structured_pattern`. A yq update on a missing path creates it, so `src/schema/mixs.yaml` kept an `internal_standard` slot with only `range: Protocol`, which no class uses. `internal_standard_method` in `nmdc.yaml`, mapped to the same MIxS ID (MIXS:0001351), is the slot that is actually used.

This removes the two lines and regenerates `mixs.yaml`, which drops the stub and changes nothing else.

`tests/test_mixs_customization_targets.py` fails when an active customization line targets a slot that isn't imported, injected from `assets/other_mixs_yaml_files/`, or created by a rename line such as `samp_collec_device`. On `main` it reports `internal_standard` and nothing else.

This also moves `internal_standard_method` from `PENDING_METHOD_SLOTS` to `PROCESS_METHOD_SLOTS` in `tests/test_method_for_annotations.py`, added by  With the stub gone, there's no `internal_standard` slot to pair it with.

## Validation

- `make src/schema/mixs.yaml`: the diff is the two stub lines only.
- `pytest` with a locally regenerated `nmdc_materialized_patterns.yaml`, which isn't committed: 501 passed.
- Negative control: the new test, run against `main`'s customization file, reports `internal_standard`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `cd2e4a8b272e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.