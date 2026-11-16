# Issue

**Title:** docs: adopt AGENTS.md as canonical guidance

## Description

## Summary

- Move the skill authoring workflow from `CLAUDE.md` to canonical `AGENTS.md`.
- Keep `CLAUDE.md` as an `@AGENTS.md` compatibility shim.
- Update templates, contributor docs, and validation references.
- Document the two-file integration pattern for external Claude Code projects.

## Dependency / merge note

This PR can be merged independently. After merge, `hyperlab-agent` must bump the `SciAgent-Skills` gitlink to the commit that actually lands on `main`.

## Checklist

- [ ] `pixi run test` passes locally
- [x] Registry and template references use canonical `AGENTS.md`.
- [x] Claude Code compatibility shim is documented.
- [x] Required authoring guidance remains present.
- [x] Ran migration invariant checks and `git diff --check`.

## Skill(s) added or modified

No scientific skill content changed; this is repository guidance migration only.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `02745ef6988d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.