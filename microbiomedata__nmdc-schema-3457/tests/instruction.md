# Issue

**Title:** Remove unused psycopg2-binary from the dev group

## Description

## Why

`psycopg2-binary` is in the dev group, but nothing on `main` imports it, including scripts, notebooks and docs. It came in on 2025-04-16 for notebook-only dependencies, and those notebooks are gone. Removing it saves every dev install one compiled package.

No runtime dependencies change. This came out of a dependency review prompted by https://github.com/microbiomedata/nmdc-schema/security/dependabot/55, which I dismissed as tolerable risk (see ). Whether pymongo should stay a runtime dependency is a separate question, tracked in

## Validation

- The lock diff removes only the psycopg2-binary entry and updates the content hash.
- `poetry check --lock` passes under 2.4.3 (the CI pin) and 2.5.1.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ab582f1b3745`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.