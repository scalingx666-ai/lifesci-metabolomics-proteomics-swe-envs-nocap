# Issue

**Title:** Record created_on, last_updated_on and modified_by on the badge subsets

## Description

Closes

Adds `created_on`, `last_updated_on` and `modified_by` to the two badge-topic subsets, with a test that fails when a badge subset lacks one.

Both dates are 2026-08-13 because `git blame` shows nothing has changed either subset since they were created. Today's date would be false, and it would make the first re-evaluation run think both subsets had just changed.

The test checks presence only. linkml refuses to generate the schema when a datetime metaslot holds a value it cannot parse, so a format check here could never fail.

Two things that will trip a reviewer. A fresh checkout fails the new test until `nmdc_schema/nmdc_materialized_patterns.yaml` is regenerated, because the tests read that file and feature branches do not commit it. CI regenerates, so CI is fine. And the values render nowhere on subset pages:

 proposes versioning badges instead, which would remove the rationale  gives. The metaslots still stand as element attribution, and `last_updated_on` with `modified_by` is the pair `src/docs/schema_element_deprecation_guide.md` already requires.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a4fff7dcf2a8`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.