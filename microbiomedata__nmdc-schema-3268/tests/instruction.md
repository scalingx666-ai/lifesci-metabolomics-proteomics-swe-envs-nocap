# Issue

**Title:** Fix AttributeValue description

## Description

## Summary

- fix the grammar in `AttributeValue`'s description
- remove the incorrect sample-only scope so the description matches the class's use across NMDC entities
- keep the change in the hand-maintained source schema; generated artifacts are intentionally not committed

.

## Root cause

The source description in `src/schema/attribute_values.yaml` combined a grammatical error ("a attribute") with wording that described only samples, even though `AttributeValue` is the abstract base for values used by multiple NMDC entity types.

## Validation

- `linkml validate src/schema/*.yaml`
- full `linkml generate project` test-schema generation into a disposable directory
- configured `linkml lint` across every non-deprecated source schema module and the materialized schema
- exact `SchemaView` assertion for the materialized `AttributeValue.description`
- `pytest tests -q -p no:cacheprovider` — 68 passed
- the three repository doctest commands
- `ruff check .`
- `deptry nmdc_schema --known-first-party nmdc_schema`
- `python src/scripts/schema_pattern_linting.py --schema-file src/schema/nmdc.yaml`
- `git diff --check`

## Validation limitations

The repository's Unix `make` wrapper was not available on this Windows host, so I ran its relevant underlying LinkML, pytest, doctest, Ruff, Deptry, and pattern-lint commands directly. The Docker path was also unavailable after the Docker Hub base-image request ended with an EOF, so validation used the project dependencies in a Poetry 2.4.1 environment on Python 3.13.12. The OAK-backed test used the public OBI SQLite artifact in a task-local `PYSTOW_HOME` cache.

## Automation disclosure

This draft pull request was prepared autonomously by OpenAI Codex. Codex rechecked the issue and contribution policy, made the source-only edit, ran the validations listed above, pushed the branch, and opened this draft. No issue comment, claim, or pre-announcement was made. Human maintainer review is required before merge.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9453089c1794`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.