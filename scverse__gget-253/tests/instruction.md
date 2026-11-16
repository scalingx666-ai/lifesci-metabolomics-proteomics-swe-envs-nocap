# Issue

**Title:** fix(types): allow tuple request timeouts in http_json

## Description

## Summary
- Allow `http_json(timeout=...)` to accept requests-style `(connect_timeout, read_timeout)` tuples.
- Match the existing `DEFAULT_REQUESTS_TIMEOUT = (10, 60)` value used by `http_json` callers.

## Validation
- Ran `pre-commit run mypy --files gget/utils.py gget/gget_opentargets.py`.
- Confirmed the previous timeout-related mypy errors are gone.
- Remaining mypy failures are pre-existing errors in `gget/utils.py`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `5506537f52e3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.