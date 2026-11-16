# Issue

**Title:** chore: add optional registry tags schema

## Description

## Summary
Introduce an optional `tags: []` field on registry entries for cross-cutting secondary discovery. Useful when an entry meaningfully belongs to more than one category — e.g., literature databases that live in `scientific-writing` but should also surface under a `databases` lens, or ML libraries that span `scientific-computing` and a future `medical-informatics`.

### Schema rules (enforced by validator + tests)
- `tags` is **optional** — absence is normal
- When present, must be a list of unique strings
- Each tag matches `^[a-z0-9][a-z0-9-]*$` (lowercase kebab-case)
- `tags` does **not** replace `category` — primary home stays in `category`

### Changes
- `registry.yaml` header comment documents the full schema, including `tags`
- `scripts/validate_registry.py`: validate type, item type, pattern, uniqueness
- `tests/test_registry.py`: new `TestTagsField` (4 tests)

## Test plan
- [x] `pixi run test` passes (4135 → 4139)
- [x] reviewer confirms schema rules (kebab-case, list of strings, optional)
- [x] reviewer confirms naming convention (`tags` vs `secondary_categories` vs `topics`)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ca3bcfdf5ec4`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.