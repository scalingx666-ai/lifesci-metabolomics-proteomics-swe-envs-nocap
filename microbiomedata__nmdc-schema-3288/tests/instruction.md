# Issue

**Title:** Firm up collection_date_inc deprecation metadata and add a validated example

## Description

Builds on the upstream `collection_date_inc` deprecation: it firms up the deprecation metadata and adds a validated example of the replacement pattern, for James and Montana to review. The rationale and open questions are in a comment below.

Two changes:

1. Corrects the `collection_date_inc` deprecation metadata:
   - removes the stray trailing quote in the `deprecated` text (also flagged by Copilot)
   - sets `last_updated_on` to the deprecation date rather than the 2022 slot-creation date (also flagged by Copilot)
   - keeps `modified_by` as a single ORCID CURIE (James Tessmer, who authored the deprecation) and adds `contributors` crediting both James Tessmer and Mark Miller, matching how every `contributors` value is written

2. Adds a validated example (`src/data/valid/Database-incubation-as-culturing.yaml`) showing the replacement pattern: a `MaterialProcessing` links an input sample to an output sample, the output carries its own `collection_date` (the harvest date), and the process carries `start_date`/`end_date` (the window). It uses `Culturing` as a `MaterialProcessing` subclass compatible with the pattern, and validates against the `Database` target class. Rationale, the full slot mapping, and open questions are in a PR comment below.

Scope: only `collection_date_inc` is deprecated. The three sibling slots (`collection_time_inc`, `start_date_inc`, `start_time_inc`) are not touched here; whether they should also be deprecated is proposed separately (see the list below).

On migrators: this PR only adds the `deprecated` annotation. The slot still exists and all data stays valid, so no migrator is required yet. A migrator becomes relevant only when the slot is moved into the deprecation file (`src/schema/deprecated.yaml`) a release later, per the completion criteria in the deprecation issue. Because `collection_date_inc` is empty in production (0 of 27,352 `biosample_set` documents, checked 2026-07-21), that later migrator will be a no-op, recorded with its reason per the repo convention.

Related issues and PRs:

-  (the collection_date_inc deprecation PR this builds on)
-  (the deprecation issue)
-  (should the three sibling `_inc` slots also be deprecated?)
-  (modified_by/created_by should be ORCID CURIEs or URLs)
-  (implement no-op migrators for recent releases)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `8a552af06c67`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.