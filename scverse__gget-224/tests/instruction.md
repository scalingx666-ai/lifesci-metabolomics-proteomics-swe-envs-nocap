# Issue

**Title:** feat(bgee): identify gget in outbound Bgee API requests

## Description

## Summary
- Sends `User-Agent: gget/<version> (+https://github.com/scverse/gget)` on every Bgee API call from `gget.bgee`, so upstream traffic is attributable to gget rather than the default `python-requests/...` UA.
- Version is resolved at import via `importlib.metadata.version("gget")`, falling back to `"unknown"` if the package isn't installed (same pattern as `gget/__init__.py`).

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `b955901a860f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.