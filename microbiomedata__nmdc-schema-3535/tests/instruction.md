# Issue

**Title:** Generate release artifacts for nmdc-schema 11.25.0rc1

## Description

## Why

Release artifacts for the 11.25.0 pre-release, tag `v11.25.0-rc.1`, published as a GitHub pre-release only. It's the first release built and published with uv, so it tests the publish workflow's upload step, which only runs on a release:

-

Built with linkml and linkml-runtime 1.11.1. The linkml 1.12 change is not in this release:

-

The one change since 11.24.1 that can invalidate existing data is the removal of `collection_time_inc` from Biosample, and the 11.24.1 to 11.25.0 migrator already checks for it.

## What changed

The six generated files under `nmdc_schema/`, rebuilt from `main` at bd88357cd with `make squeaky-clean all test` (passed locally).

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `bd88357cd17c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.