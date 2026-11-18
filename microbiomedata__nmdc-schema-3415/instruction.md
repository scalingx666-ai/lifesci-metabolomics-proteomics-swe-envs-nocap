# Issue

**Title:** Use Poetry 2.4.3 everywhere, in CI and in the docs

## Description

Allow Poetry 2.4.3 alongside the pinned 2.4.1 in `CLAUDE.md`, left the docs recommending two Poetry versions while CI stayed on 2.4.1. Poetry 2.4.3 is the latest release (published 2026-09-05, https://pypi.org/project/poetry/), and Homebrew installs 2.4.3. Naming one version in CI and in the docs is simpler than naming two.

## What changed

All 7 workflows install `poetry==2.4.3`. `CLAUDE.md` and `DEVELOPMENT.md` name 2.4.3 only, and `DEVELOPMENT.md` shows `pipx install --force poetry==2.4.3` instead of `pipx upgrade poetry`, which would move past the pin.

## Validation

With Poetry 2.4.3 on `main` at 340cc5162 on 2026-09-15, `poetry check --lock` reports "All set!" and `poetry lock` leaves `poetry.lock` byte-identical (compared with `cmp`). CI on this PR runs every workflow with the new pin.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `340cc51622cc`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.