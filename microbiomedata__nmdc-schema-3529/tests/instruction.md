# Issue

**Title:** Lock linkml 1.12.1 by overriding pronto's chardet cap in uv.lock

## Description

## Why

Part of  Stacked on  it targets that branch, not `main`.

We couldn't lock linkml 1.12 because pyshexc 0.10.3 (needed by linkml 1.12) requires `chardet>=7.4.1`, while pronto 2.7.3 (needed by oaklib, in our dev group) requires `chardet~=5.0`. Poetry can't override that, but uv can. `override-dependencies = ["chardet>=7.4.1,<8.0.0"]` affects only `uv.lock`, not the package metadata consumers install from, and no `pyproject.toml` specifier changes. pronto worked the same under chardet 7.6.0 when we tried it on 2026-10-08 (see the comment on ). The override can come out once this is released:

-

This is the one PR that moves nmdc-schema to linkml 1.12. It moves linkml and linkml-runtime together, and removes the dev-group hold that keeps linkml-runtime below 1.12 on main and in

## What changed

The `[tool.uv]` override, removal of the `linkml-runtime<1.12` dev-group hold, plus `uv lock --upgrade-package linkml --upgrade-package linkml-runtime`. linkml and linkml-runtime go from 1.11.1 to 1.12.1, chardet from 5.2.0 to 7.6.0, and pyshexc from 0.9.1 to 0.10.3.post1, along with the other packages linkml 1.12 needs.

## Before merging

Wait for nmdc-runtime. Release artifacts built with linkml-runtime 1.12 wrap every structured id pattern as `^(?:...)$`, which linkml intends (). nmdc-schema's own helper already handles that. nmdc-runtime's minter does not, so this PR must not merge until this is deployed:

-

## What consumers see

Consumers keep their own linkml: `[project.dependencies]` still allows linkml and linkml-runtime `>=1.9.0,<2.0.0`. They see linkml 1.12 only through the files we ship. An 11.25.0rc1 wheel built from this branch was installed into each consumer at its main commit, without changing their linkml pins, and compared with 11.24.1 (2026-10-14):

- nmdc-runtime (linkml 1.10.0): with  the minter finds 40 typecodes; without it, 0.
- nmdc-server (linkml 1.10.0): the enums it imports are unchanged; its test suite needs Postgres and was not run.
- submission-schema (linkml 1.9.6): `make all` and its 44 tests pass; its build re-materializes patterns with its own runtime, so its output patterns are unchanged.
- ontology-loader (linkml 1.9.2): 131 passed, 16 skipped, the same as 11.24.1.
- sample-annotator: same results as 11.24.1; only imports are exercised.
- nmdc-lakehouse (linkml 1.11.1): with a flat schema regenerated from the candidate, 1061 passed; the same 11 tests fail as on 11.24.1. Its version check only accepts X.Y.Z, so an rc version needs a scratch change to install there.
- nmdc-lakehouse-schema (linkml 1.11.1): the generator writes 62 tables and `--check` passes; two tests that expect 61 fail because of the new isotopolog table. Its 59 patterns are unchanged, and it doesn't read the JSON Schema.
- nmdc_automation (linkml 1.10.0): 235 of 235 pass, the same as 11.24.1.
- nmdc-ingest-agent (linkml 1.9.3): fails the same way on 11.24.1 because it still uses `TargetGeneEnum`, renamed in 11.22.0; with that name fixed, 133 pass on both.
- nmdc_mass_spectrometry_metadata_generation and nmdc-mass-spec-automation: pass on the candidate; their current failures come from installing linkml 1.12 against nmdc-schema 11.24.x, which mints `nmdc:None-...` ids.

Changes in the shipped JSON Schema beyond the `^(?:...)$` wrapping: 191 optional slots ranged on enums or classes now accept null, and every `type` enum also accepts the full class URI (for example `https://w3id.org/nmdc/Study`). nmdc-runtime parses `type` as a CURIE, so the URI form needs a decision before release. 1733 sampled production records validate against the new JSON Schema, as they do against 11.24.1.

linkml 1.12.1's `gen-python` fills a class's id pattern (for example `slots.Biosample_id`) with the settings of the module that defines the base `id` slot, `basic_slots.yaml`, which had none, so 41 compiled patterns in `nmdc_schema/nmdc.py` kept `{id_nmdc_prefix}`. This PR gives `basic_slots.yaml` those settings through `sync_module_settings.py`, and a new test fails if `nmdc.py` compiles a pattern that still holds a placeholder. Regenerated from this branch, `nmdc.py` has 0 such patterns (41 before). No consumer read these patterns: the only one importing `nmdc.slots`, sample-annotator, reads `.name`.

The `^`/`$` inside our own structured pattern `syntax` values are left as they are on purpose. Dropping them, so LinkML adds the anchors, is a planned follow-up after this merges.

## Validation

- CI passes on Python 3.10, 3.13 and 3.14.
- `test_named_thing_classes_have_a_future_typecode` fails locally for `ChromatographicSeparationProcess`, `Manifest` and `MixingProcess` when run against the committed `nmdc_materialized_patterns.yaml`, and passes once that file is regenerated (tested 2026-10-14). The committed file was built for 11.24.1, before  added `interpolated: true` to those three id patterns, and linkml-runtime 1.12 treats a pattern without it as literal text. CI regenerates the artifacts, so it is not affected, and the next release regenerates the committed file.
- All production ids for those three classes match the interpolated patterns: 90 Manifest and 3237 ChromatographicSeparationProcess records, 0 failures; there are no MixingProcess records (public API, 2026-10-14).

## Documentation impact

The comment on the override in `pyproject.toml` explains it and when to remove it.

## Scope and complexity

`pyproject.toml` (the override added, the dev-group hold removed), `uv.lock`, a settings block in `src/schema/basic_slots.yaml`, `src/scripts/sync_module_settings.py`, and two tests.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ba3f58f8ae85`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.