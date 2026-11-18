# Issue

**Title:** Clean up make_typecode_to_class_map.py (AI code-quality findings)

## Description

## Why

Addresses the three AI code-quality findings on `src/scripts/make_typecode_to_class_map.py`:

- **Import-time global.** `SchemaView` was built at module import. Moved behind a lazy `get_schema_view()` so importing the module is cheap and side-effect-free (helps testing), and the schema loads only when needed.
- **`len(typecodes) > 0`** simplified to `typecodes` (an empty list is falsy).
- **Unchecked `slot_definition.range`.** Guard against a slot with no range before calling `class_descendants()`.

Scoped to the three findings; the identical `len(...) > 0` idiom at line 107 is left alone to keep this 1:1 with the findings.

## Verification

Module doctests pass (11/11), including the `get_collection_names_for_class_name` cases that exercise the lazy `SchemaView` and the range path.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `14ddcdc051ab`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.