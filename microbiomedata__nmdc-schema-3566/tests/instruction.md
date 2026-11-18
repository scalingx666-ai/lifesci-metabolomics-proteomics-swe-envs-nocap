# Issue

**Title:** Generate release artifacts for nmdc-schema 11.25.0rc3

## Description

## Why

Release artifacts for the 11.25.0 pre-release, tag `v11.25.0-rc.3`, published as a GitHub pre-release only. Since rc2 it adds the MIxS v7.0.1 import, our structured patterns leaving anchoring to linkml, per-class id examples, structured alias sources and two MIxS history corrections:

-
-
-
-
-
-

No new migrator: 3501 leaves every record valid (its JSON Schema comparison), and 3549 changes pattern text but not what matches. I checked 3549's patterns against production MongoDB on 2026-10-15: 0 of 1,902,502 patterned values and 0 of 51,744,347 functional_annotation_agg documents fail.

This PR closes no issue. Part of:

-

## What changed

The six generated files under `nmdc_schema/`, rebuilt from `main` at a92840ab7 with the full rebuild (`make squeaky-clean mixs-yaml-clean`, `make src/schema/mixs.yaml`, then `make squeaky-clean all test`, 660 passed). The regenerated `mixs.yaml` was identical to the committed one.

Checked in these files:

- all 40 `nmdc:` id patterns have the form `^(?:(nmdc):...)$`; 3 patterns are still doubled (`salinity_meth` on purpose, and the MIxS slots `cult_root_med` and `genetic_mod`)
- 45 classes carry an `id` example
- 83 `type` enums also list the full class URI ()
- `nmdc.py` has no unfilled `{id_...}` placeholders

nmdc-runtime needs  (now expecting the single-anchored form) in the same change that moves it to 11.25.0.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a92840ab7a60`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.