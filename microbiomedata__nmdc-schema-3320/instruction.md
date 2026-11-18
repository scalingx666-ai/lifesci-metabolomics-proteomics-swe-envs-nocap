# Issue

**Title:** Scope pymdown-extensions to dev and drop its ceiling

## Description

`pymdown-extensions` was in `[project.dependencies]` only as a security floor for a transitive package. The only two things that require it are `mkdocs-material` and `mkdocs-mermaid2-plugin`, both dev-only. So every consumer of the published package (submission-schema, nmdc-runtime, nmdc-server) installed a Markdown extension pack for a docs build they never run, and inherited a `<11.0.0` cap on it.

That cap then blocked the fix it existed to deliver. The open advisories are fixed in 11.0.0 and 11.0.1, which `<11.0.0` puts out of reach, so Dependabot could not open a PR and reported nothing. Two of the twelve open alerts are this.

Moved to the `dev` group and made floor-only. A pin whose whole purpose is "at least the patched version" should not carry a ceiling; the upper-bound policy in CLAUDE.md makes sense for dependencies we actually import, but works against us for security floors.

Also dropped `pymdown-extensions` from the `DEP002` ignore list, since it is no longer a declared-but-unused runtime dependency.

Verification:

- `poetry lock` resolves `pymdown-extensions` to 11.0.1
- `poetry check` passes
- `make check-dependencies` (what CI runs, scoped to `nmdc_schema`) is clean
- repo-wide `deptry` finds the same 11 pre-existing issues before and after

`idna` and `urllib3` are left alone. They are genuine runtime transitives via `requests`, so they are correctly scoped; only their ceilings are arguable, and that is a separate conversation.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `86dee32c85df`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.