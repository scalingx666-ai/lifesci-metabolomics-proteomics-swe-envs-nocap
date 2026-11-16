# Issue

**Title:** feat(utils): retry transient upstream errors in rest_query/post_query

## Description

### Scope

`rest_query` / `post_query` in `gget/utils.py` are the shared entry points for every Ensembl-backed module (`seq`, `ref`, `search`, `info`, `blat`, and `enrichr` with `ensembl=True`). They currently issue a single request, so any transient hiccup from the upstream service fails the whole call. Ensembl REST in particular returns intermittent `500/502/503/504` or `429` under load, and occasionally drops the connection — which shows up as flaky failures in CI and for users.

### Change

Add a small `_query_with_retry` helper and route both functions through it:

- **Retries** on `429` and `5xx` (500/502/503/504) and on connection/timeout errors, with linear backoff (2s, 4s, 6s; 4 attempts total).
- **Honors `Retry-After`** when the server sends one (capped at 30s).
- **Does not retry `4xx`** client errors (e.g. `404`) — returned to the caller unchanged, so existing error handling (`if not r.ok: raise ...`) is preserved.
- After exhausting retries, returns the last response (or re-raises the last connection error), so callers behave exactly as before in the terminal-failure case.

No public API or return types change — this only adds resilience underneath the existing functions.

### Tests

Offline unit tests (`tests/test_utils.py::TestQueryRetry`, mocked `requests`/`sleep` — no network) cover: success after retry, connection-error retry, no-retry on `404`, retry exhaustion, and `Retry-After` handling.

### Notes

`utils.py` already has an `http_json` retry helper, but it always parses JSON and raises on non-JSON bodies. `rest_query` can return either text or JSON and needs the raw `Response`, so this helper returns the `Response` object and leaves body handling to the existing call sites.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ccd734296c4c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.