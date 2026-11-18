# Issue

**Title:** Hold our lock at linkml-runtime 1.11 until nmdc-runtime can read wrapped id patterns

## Description

## Why

 moved our lock to linkml-runtime 1.12.1 (linkml stayed at 1.11.1). linkml-runtime 1.12 wraps induced id patterns as `^(?:...)$`, which linkml intends:

-

A release built from that lock would ship a JSON Schema whose id patterns nmdc-runtime's minter can't read, because the minter skips any pattern that doesn't start with `^(nmdc):`. That stays true until this is deployed:

-

This puts the lock back on linkml-runtime 1.11.1. linkml 1.12 will come in through its own PR, together with linkml-runtime 1.12, once nmdc-runtime is ready:

-

## What changed

`linkml-runtime>=1.9.0,<1.12.0` is added to the `dev` dependency group. Dependency groups aren't part of the published package metadata, so this holds our lock (and stops Dependabot's lock-only updates from moving it) without changing what consumers can install. `[project.dependencies]` still says `linkml-runtime>=1.9.0,<2.0.0`.

`poetry lock` (Poetry 2.5.1) moved only two packages: linkml-runtime 1.12.1 to 1.11.1, and pyoxigraph 0.5.11 (a linkml-runtime 1.12 dependency) is removed.

## Validation

Built `nmdc_materialized_patterns.yaml` and the JSON Schema from this branch's `src/schema` (2026-10-14), counting the 40 NMDC `id` patterns:

| linkml | linkml-runtime | wrapped | start with `^(nmdc):` |
|---|---|---|---|
| 1.11.1 | 1.11.1 (this PR) | 0 | 40 |
| 1.11.1 | 1.12.1 (main now) | 40 | 0 |

`poetry check --lock` passes.

## Documentation impact

The comment on the new constraint says why it's there and when to remove it.

## Scope and complexity

`pyproject.toml` (one constraint and its comment) and `poetry.lock`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ca17a32db88d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.