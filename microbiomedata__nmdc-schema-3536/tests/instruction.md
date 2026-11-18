# Issue

**Title:** Remove the requests warning suppression from the Makefile

## Description

## Why

Closes
Closes

The Makefile set `PYTHONWARNINGS="ignore:::requests"` on every `uv run` to hide a false `RequestsDependencyWarning` from requests 2.32.5. `uv.lock` now has requests 2.34.2, which doesn't emit it, and the prefix adds noise to every build command, as @eecavanna pointed out on

## What changed

`RUN` in the Makefile is plain `uv run` again, and the comment that pointed at the issue is removed.

## Validation

Tested 2026-10-15 with `python -W default -c 'import requests'` in isolated environments with charset-normalizer 3.5.1 and urllib3 2.8.0:

- requests 2.34.2 with chardet 5.2.0 (main's lock): no warning
- requests 2.34.2 with chardet 7.6.0 (the lock in ): no warning
- requests 2.32.5 with chardet 7.6.0: warns, so the check can see the warning

## Documentation impact

None.

## Scope and complexity

Two lines in the Makefile.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ba3f58f8ae85`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.