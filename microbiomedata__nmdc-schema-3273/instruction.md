# Issue

**Title:** Move inline examples into the examples metaslot (batch 1)

## Description

## Why

Example values belong in the LinkML `examples` metaslot, not embedded in `description` or `comments`. Keeping them there makes them machine-readable, lets docgen render them consistently, and lets validation check them against the slot range. This is the convention Montana, Mark, and others already follow, and the narrow case in #2466 (`samp_store_temp`) is one instance of it.

## What this PR contains

1. **Convention doc.** A new Modeling Best Practice bullet in `CONTRIBUTING.md` defining where example values belong and how to tell a misplaced example from legitimate explanatory prose (the "would the parenthetical be a valid value of the slot?" test), the `value:`/`description:` gloss pattern, and the MIxS yq-asset path.
2. **Batch 1 of edits.** Relocates canonical example values for four `PropertyAssertion` slots in `src/schema/attribute_values.yaml` (`has_attribute_label`, `has_attribute_id`, `has_quantity_kind_id`, `has_value_term_id`) from `description`/`comments` into `examples`. Explanatory prose stays in `comments`, and source/type hints (`MIxS label or ENVO term label`, `qudt:QuantityKind`) are kept in the descriptions as plain statements rather than `e.g.` examples. Scoped to `string`/`uriorcurie` ranges so relocated examples cannot fail range validation (the range-matching concern is #2950).

## Scope of the whole effort

An audit of the hand-maintained sources (excluding generated `mixs.yaml`) finds about 57 occurrences of `e.g.`/`i.e.`/`for example`/`such as` across `description`/`comments`/`notes`, plus "Examples include ..." phrasings the keyword scan misses. A large share are genuine explanatory prose (unit glosses, usage guidance, the `OntologyRelation` walkthrough, GOLD ecosystem definitions) that should stay as prose, so this is a judgment call per case, not a mechanical sweep.

**Native sources** are handled here in reviewable batches (this is batch 1).

**MIxS-derived slots** (about 55 with inline examples in their descriptions, 19 with no `examples` block) will be a **separate PR**: they must be changed through `assets/yq-for-mixs-customizations.txt` and require regenerating the committed `src/schema/mixs.yaml`, they touch upstream GSC text (a policy question), and they overlap the consolidation tracked in #2947. Keeping them apart keeps each PR's review surface and build footprint clean. `samp_store_temp` is already handled by #3267.

Draft until the batching plan is agreed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9fd926a7c6f1`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.