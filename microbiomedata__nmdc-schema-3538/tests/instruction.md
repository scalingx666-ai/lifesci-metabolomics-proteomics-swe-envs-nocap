# Issue

**Title:** Generate release artifacts for nmdc-schema 11.25.0rc2

## Description

## Why

Release artifacts for the 11.25.0 pre-release, tag `v11.25.0-rc.2`, published as a GitHub pre-release only. It is rc1 rebuilt with linkml and linkml-runtime 1.12.1, so NMDC consumers, and nmdc-runtime's minter change in particular, can test against a 1.12-built package:

-
-

The schema source is unchanged since rc1, so no new migration is needed.

## What changed

The six generated files under `nmdc_schema/`, rebuilt from `main` at 311f7276f with the full rebuild (`make squeaky-clean`, `mixs-yaml-clean`, `src/schema/mixs.yaml`, then `squeaky-clean all test`, 563 passed). The regenerated `mixs.yaml` was identical to the committed one.

The diff is large because of the linkml 1.12 output, checked in these files:

- the 40 `nmdc:` id patterns are wrapped as `^(?:...)$`
- 85 `type` enums also list the full class URI ()
- 191 class-slot pairs, on 125 slots, newly accept `null`
- `nmdc.py` has no unfilled `{...}` placeholders

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `311f7276f902`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.