# Issue

**Title:** Raise the pymdown-extensions cap to <13.0.0

## Description

## Why

Closes  The issue waited for 12.x to settle. As of 2026-10-08, 12.0 has been out 23 days (2026-09-15), it's had two follow-up releases (12.0.1 the same day, 12.1 on 2026-09-23), and no advisory covers any 12.x version. The one open upstream bug filed since 12.0 ( magiclink does not support multi-level repositories) concerns nested GitLab project paths and is a long-standing limit, not a 12.x regression. Dependabot can't make this change, because `versioning-strategy: lockfile-only` stays inside the caps.

The `>=11.0.1` security floor is unchanged.

## Validation

- `poetry update --lock pymdown-extensions` changed only that package, from 11.0.2 to 12.1, and `poetry check --lock` reports "All set!".
- `mkdocs.yml` enables only `pymdownx.magiclink` from this package. Rendering all of `src/docs/*.md` with `magiclink`, `attr_list`, `md_in_html`, `tables` and `fenced_code` gave byte-identical HTML under 11.0.2 and 12.1.
- The "Build and deploy docs preview" check builds the full site with 12.1.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `971c2eae3405`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.