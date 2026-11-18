# Issue

**Title:** Add a report for slot_usage that restates inherited values

## Description

has two checkboxes. This implements the first and explains why the second no longer applies.

**"does the usage alter a parent class' attribute value? reverting to the global usage?"** A `slot_usage` that asserts a value the class already inherits leaves the induced slot unchanged, so it reads as intent without being any. The cost shows up later: an edit to the global slot stops reaching every class that restated the old value, and nothing says so.

The comparison is against what the class actually inherits, not against the global slot. For a class with a parent that means the parent's induced slot, which already folds in the parent's own refinements. This is the distinction the issue was pointing at: a `slot_usage` that restores the global value *after a parent narrowed it* is a genuine refinement, and comparing against the global slot alone would report it as redundant.

Reports rather than edits. Some restatements are deliberate, including the re-declared `range: uriorcurie` that `src/docs/maintaining-the-schema.md` describes as belt-and-suspenders, so a human decides what comes out.

It currently finds 69 assertions. A sample, verified by hand against the YAML:

```
ChromatographicSeparationProcess:
  has_input.range = 'Sample'   [same as is_a MaterialProcessing]
  id.required = True           [same as is_a MaterialProcessing]
```

`MaterialProcessing.slot_usage` sets `has_input.range: Sample` at `src/schema/core.yaml:1305`, and `ChromatographicSeparationProcess` restates it at `src/schema/nmdc.yaml:823`. The same class's `id.structured_pattern` carrying the `cspro` typecode is correctly *not* flagged, because that one refines.

**The second checkbox, agreement with the sheets_and_friends Google sheet, is obsolete.** That sheet drives `submission-schema`, not this repo's `slot_usage`.

**Unset booleans count as false.** LinkML stores an unset boolean metaslot as `None`, which looks the same as having nothing to compare against, so an early version never reported `required: false` written over a slot that is already optional. That assertion leaves the induced slot unchanged and belongs in the report. Only the metaslots where unset really does mean false are treated this way; `inlined` and `inlined_as_list` are left out, because their effective value depends on whether the range class has an identifier. The one case this adds today is `PropertyAssertion.has_unit` in `src/schema/attribute_values.yaml`, and the report labels its baseline "unset so false" so a reader can see the assertion was never inherited from anywhere.

Run it with `make assets/redundant-slot-usage.txt`, or directly for TSV. The output is not committed, matching `assets/usages-report.txt` and the other reports next to it.

Ten tests cover both directions, since a checker that reports refinements as redundant would be worse than none: restating the global value, restating an inherited value, restating an unset boolean, a genuine refinement, dropping an inherited requirement, a class with no `slot_usage`, and TSV well-formedness. That last one matters because LinkML object reprs span multiple lines and would otherwise break the columns.

Fixes  "boolean usage script overlooks"

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `aa47a1030eab`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.