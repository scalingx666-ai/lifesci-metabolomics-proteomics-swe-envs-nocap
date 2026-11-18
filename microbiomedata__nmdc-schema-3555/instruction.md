# Issue

**Title:** Correct the MIxS release that dropped host_family_relation and soil_text_measure

## Description

## Why

Closes

The comments on `host_family_relation` and `soil_text_measure` said MIxS dropped them in v6.2.2. Both are in the MIxS source schema at the mixs6.1.1 tag and absent at v6.2.0, which I checked in a clone of https://github.com/GenomicsStandardsConsortium/mixs on 2026-10-15. The corrected line moves to `notes` because it records where the slot came from, not how to fill it in. `salinity_meth` got the same fix in

## What changed

`src/schema/nmdc.yaml` only. The `soil_text_measure` comment about its range stays in `comments`. Whether to remove these slots is

## Validation

- `pytest tests/`: 656 passed.
- `linkml-lint`: no problems.

## Documentation impact

None beyond the two slot pages.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e4c7ee3876df`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.