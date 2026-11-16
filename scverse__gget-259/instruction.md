# Issue

**Title:** docs(archs4): clarify legacy endpoint vs archs4.org data source

## Description

Addresses #254.

## Context

#254 asks about migrating `gget archs4` off the legacy `maayanlab.cloud` ARCHS4 endpoints now that ARCHS4 has moved to [archs4.org](https://archs4.org). I investigated the feasibility:

- The **legacy endpoints still work** (verified live) and are lightweight HTTP — the right fit for gget's quick single-gene queries.
- **archs4.org has no equivalent lightweight HTTP API** (POSTs to the old paths return `405`). Its programmatic access is **only** via [`archs4py`](https://github.com/MaayanLab/archs4py) + multi-GB HDF5 downloads.

A full migration would replace an instant query with a tens-of-GB download + heavy dependency — a major UX regression that contradicts gget's design. So rather than migrate, this PR **documents the situation** so users understand the data source and their options.

## Changes (docs-only, no code)

- `docs/src/en/archs4.md`: added a note explaining that `gget archs4` uses the legacy `maayanlab.cloud` endpoints, that archs4.org's newer/larger dataset is only reachable via `archs4py`/HDF5, and that users who need the newest data should use `archs4py` directly. Links the tracking issue.
- `docs/src/en/updates.md`: brief 0.30.8 entry.

## Note on the issue

This **addresses** but does not fully close #254 — the "evaluate migration" tracker should stay open in case archs4.org later exposes a lightweight API. I used "Addresses" (not "Resolves") so it won't auto-close.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `4b586a391bf2`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.