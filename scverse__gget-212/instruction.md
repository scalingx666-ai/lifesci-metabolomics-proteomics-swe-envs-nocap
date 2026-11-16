# Issue

**Title:** Fix blat tests: surface UCSC errors, retry transients, tighten negative tests

## Description

## Summary

The CI run on 2026-06-08 (`tests/pytest_results_py3.12.txt`) had 5 blat tests failing where `gget.blat()` returned `None` instead of a result. The cause was UCSC's BLAT endpoint returning an HTML error / throttle page to the GitHub Actions runner; `gget_blat.py` caught the resulting `JSONDecodeError` silently and printed a generic "sequence too short / assembly invalid" message that hid the real cause. Nothing in this repo had changed — the previous CI run on 2026-06-04 passed all 390 tests against the same code.

Four commits, applied in order:

- **`0029f02e` gget_blat: surface real error response on JSON decode failure** — read the response body, log a preview, and catch `HTTPError`/`URLError` so the real failure (HTML body, 4xx/5xx, network blip) is visible instead of a misleading message.
- **`d1f45d6a` gget_blat: retry transient UCSC failures with exponential backoff** — retry up to 4 times (1.5s → 3s → 6s) for 429 / 5xx / network errors / non-JSON 200 responses. 4xx other than 429 still fail immediately.
- **`5ad41afd` tests: gate assert_none on a happy-path log substring** — six negative blat tests used `assert_none` and would pass even when the API call broke (`None` is `None`). Added an optional `expected_log` field to `_assert_none` in `tests/from_json.py`; each negative blat test now declares the specific log it expects ("No matches were found" for clean empty responses, "failed after N attempts" for the retry-exhaustion path). Backward compatible — tests that don't set `expected_log` behave exactly as before.
- **`32664225` docs: document blat resilience fixes in updates.md** — entry added under "Version ≥ 0.30.6 (Jun 08, 2026)". Note: `setup.cfg` version bump intentionally left for the release commit.

## Why this targets `dev`

Changes the `gget.blat()` module itself (new retry behavior, new helper functions, new exception class). Warrants a version bump on release, so merging into `dev` rather than `main`.

## Test plan

- [x] `python -m pytest tests/test_blat.py -v` — all 17 tests pass locally (~24s wall-clock)
- [x] All 5 originally-failing tests (`test_blat_aa`, `test_blat_aa_protein`, `test_blat_nt`, `test_blat_nt_DNA`, `test_blat_nt_fasta`) are now green
- [x] Negative tests verified to take the expected code path via the new `expected_log` assertion
- [x] `python -m pytest tests/test_archs4.py` — confirmed `assert_none` tests in another module still pass (4 pre-existing assert_equal failures there are unrelated data-drift, not introduced by this PR)
- [ ] CI green on this PR — please confirm in the Actions tab

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9e22b98e1090`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.