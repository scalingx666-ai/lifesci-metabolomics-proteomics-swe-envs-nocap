# Issue

**Title:** Report files under assets/ that nothing uses, and fail CI on new ones

## Description

## Why

Closes

When a schema element is deprecated, mapping files and reports under `assets/` keep naming it, and the deprecation guide said nothing about them. Nothing stopped new files from being added to `assets/` with no consumer either. This was raised at the 2026-08-26 NMDC Schema and Metadata meeting over `assets/misc/neon_nmdc_term_mapping.tsv`, which was deleted in  (Finalize Deprecation of `collection_date_inc`).

## What changed

- `make report-asset-usage` (`src/scripts/report_asset_usage.py`) lists tracked files under `assets/` that no other committed file names, files that name an element in `src/schema/deprecated.yaml`, and the overlap. A finding is a candidate for review, not proof that nothing uses the file.
- `tests/test_no_new_unreferenced_assets.py` fails CI when a new unreferenced asset appears, or when an allowlisted one becomes referenced. It allows the 24 that exist today, grouped with a reason and a tracking issue. 10 of the 24 also name a deprecated element; 8 of those 10 are false positives tracked in  (Asset usage report flags files that use a retired subset or type name as an ordinary word).
- `src/docs/asset-lifecycle.md` describes how to retire an asset, including checking other repositories. `src/docs/schema_element_deprecation_guide.md` now covers files under `assets/` and consumer repositories such as submission-schema, whose build fails with `ValueError: Slot 'collection_date_inc' not found in source schema.` when an imported slot is removed.

## Validation

33 tests in `tests/test_report_asset_usage.py` and `tests/test_no_new_unreferenced_assets.py` pass locally on Python 3.13. The tests for whole-name matching, unquoted non-ASCII paths and the generic-filename denylist each fail against the previous version of the detector. Ruff check and format pass.

## Scope

The report only searches this repository. A search across the microbiomedata organization was proposed in  (closed) and is tracked in  (Find and clean up mentions of retired schema elements in files nothing checks).

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a1bcc01f9d18`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.