# Issue

**Title:** Standardize QUDT prefix (qud to qudt)

## Description

## Why

The schema declared the prefix `qud` for QUDT and used `qud:` in three mapping CURIEs, but the `description` prose already used the community-standard `qudt:` (for example `qudt:QuantityKind`), and [bioregistry](https://bioregistry.io/qudt) records `qudt` as the preferred prefix. That left the schema internally inconsistent (`qud` in declarations and CURIEs, `qudt` in prose) and externally non-standard on the prefix name.

This renames the prefix token `qud` to `qudt` in the four prefix declarations, the three mapping CURIEs (`qudt:unit`, `qudt:quantityValue`, `qudt:DEG_C`), and CLAUDE.md.

## Scope: prefix name only

The namespace URI is unchanged (`http://qudt.org/1.1/schema/qudt#`), so no CURIE changes what it resolves to. This is deliberately a pure rename.

The namespace-URI modernization and per-term IRI correctness are a separate topic, tracked in  (QUDT prefix: schema uses non-standard `qud` + deprecated 1.1 namespace). Verification for that follow-up found two things worth a real decision: QUDT's own current schema namespace uses a slash (`http://qudt.org/schema/qudt/`), which conflicts with bioregistry's hash form; and `DEG_C` is canonically `http://qudt.org/vocab/unit/DEG_C` (the QUDT unit vocabulary), not the schema namespace. Those are kept out of this PR.

## Verification

`SchemaView("src/schema/nmdc.yaml")` loads (80 classes, 874 slots); `qudt` resolves to the declared namespace, `qud` is gone, and the three CURIEs expand. Generated `nmdc_schema/` artifacts are intentionally not included; they are regenerated at release.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `14ddcdc051ab`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.