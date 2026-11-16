# Issue

**Title:** fix(ci): repair archs4 + ELM live-data test failures

## Description

Scoped to the ARCHS4 + ELM CI-stability fixes only. The opentargets parts of this PR have been moved to #256 per maintainer preference for one-module-per-PR review.

## ARCHS4 — graceful missing-`color` column + deterministic order

**Bug**: ARCHS4 intermittently omits the `color` column from its tissue-expression CSV response. The previous `tissue_exp_df.drop(["color"], axis=1)` raises `KeyError: ['color'] not found in axis` when this happens, so `gget archs4 -w tissue ...` crashes for users on those requests.

**Fix**: `drop(columns=["color"], errors="ignore")` — drops if present, no-op if absent. The `color` column was never used by `gget archs4` (only ARCHS4's own plotting needs it).

**Secondary improvement**: sort key changed from `"median"` to `["median", "id"]` (descending median, ascending id) so equal-median tissues no longer flip order between requests. Test fixtures refreshed for the deterministic ordering.

**New regression tests** (network-free, mocked):
- `TestArchs4MissingColor.test_tissue_missing_color_does_not_crash` — main regression guard for the `errors="ignore"` fix
- `TestArchs4MissingColor.test_tissue_with_color_still_dropped` — paired companion confirming the column still gets dropped when present

## ELM — retry transient setup download

`gget_setup(module="elm")` downloads ELM database files from elm.eu.org. Cold-cache or transient network blips occasionally fail the download and break test collection (the call happens at module-import time, before any test runs). Wrap in a 3-attempt retry with a 30s sleep between attempts so transient failures don't kill the whole opentargets/ELM suite.

## Out of scope (moved or punted)

- **OpenTargets** synonyms HTTP 400 fix + fixture drift + expression-tests-skip: .
- **`baselineExpression` migration** (): separate PR (or rebased version of #248).

## Test plan

- [x] `python -m pytest tests/test_archs4.py -v` locally — all pass (including the new `TestArchs4MissingColor` cases)
- [x] `python -m pytest tests/test_elm.py -v` locally — passes (ELM setup either succeeds first try or after a retry)
- [ ] CI green on this PR

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `5506537f52e3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.