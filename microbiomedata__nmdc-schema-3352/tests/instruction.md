# Issue

**Title:** Remove see_also links that point at closed issues

## Description

Removes the 19 `see_also` entries listed in  all of which pointed at closed issues or pull requests.

Distinct GitHub references in the merged schema go from 19 to 8. Ten `see_also` keys had no surviving items and were dropped with them. All edits are in hand-maintained source files; none of these references lived in the generated `mixs.yaml`, so no customization lines or regeneration were involved.

**The `type` slot's reasoning is preserved rather than deleted.** Its three links ( deprecate type slot,  all classes should have a required type-designating slot,  MVP polymorphic planned_process_set) were together the only record of why the slot exists in its current form. That is now a comment on the slot:

> Deprecating this slot was proposed and rejected: without it, a document read back from a polymorphic MongoDB collection cannot be resolved to the class it instantiates. It is required on every class for that reason, rather than as a convention inherited from LinkML.

**One entry was deliberately kept and needs a reviewer's opinion.** `emsl_project_identifiers` has:

```yaml
see_also:
  -
```

The issue is closed, so the rule as stated would remove it, but this is a deep link to a specific comment rather than to a thread, and that comment is where the reasoning for the identifier pattern actually lives. Deleting it loses content with nowhere else to point. Happy to remove it if reviewers prefer the rule applied uniformly; it is a one-line change.

Three closed-issue references remain in the schema and are out of scope, because they sit in prose rather than in `see_also`: two in class comments and one inside a `description`. Those read as narrative context and are not presented to a user as a link to follow.

Verification: every file in `src/schema/` parses, the schema regenerates, and the full test suite passes (87 tests).

Closes

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `71d7a28a4a07`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.