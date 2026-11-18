# Issue

**Title:** Allow mypy 2.x in the dev dependencies

## Description

The dev dependency `mypy` was capped at `<2.0.0`, which kept the lock on 1.20.2. mypy 2.0.0 was released on 2026-05-06 and 2.3.1 on 2026-08-15 (https://pypi.org/project/mypy/), so 2.x has been out long enough to adopt. Its breaking changes are new defaults, `--local-partial-types` and `--strict-bytes`, and a changed `--allow-redefinition` (https://github.com/python/mypy/blob/master/CHANGELOG.md).

## What changed

The cap is now `<3.0.0`, and `poetry update --lock mypy` changed only three packages: `mypy` 1.20.2 to 2.3.1, `librt` 0.11.0 to 0.15.0, and the new mypy dependency `ast-serialize` 0.11.2.

## Validation

`poetry check --lock` reports "All set!" with Poetry 2.4.3. No Makefile target or workflow runs mypy, so this cannot change the build. The error counts in  Reduce mypy type errors in hand-written Python (scoped), were measured with 1.x and may differ under 2.x defaults.

The same review found `pymdown-extensions` 12.0 behind a similar cap. That release is one day old, so it waits in  Raise the pymdown-extensions cap to 12.x once 12.0 has been out longer.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `6b9f29e9c01a`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.