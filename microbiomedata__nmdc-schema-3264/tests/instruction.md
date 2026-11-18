# Issue

**Title:** Simplify schema_pattern_linting.py (AI code-quality findings)

## Description

## Why

Applies the two AI code-quality findings on `src/scripts/schema_pattern_linting.py`, both behavior-preserving simplifications:

- **Character-class stripping:** replace the two-pass `re.sub(r'\[\]', ...)` + `re.sub(r'\[[^\]]+\]', ...)` with a single `re.sub(r'\[[^\]]*\]', ...)`, which matches both empty and non-empty classes. (The original two-pass code was correct, so this is a cleanup, not a bug fix.)
- **Duplicate iteration:** merge the two consecutive `for slot in induced_slots` loops into one. The second loop only appends to `dangling_slot_group_messages` (printed later under its own header), so merging does not change any output.

## Verification

`schema_pattern_linting.py --schema-file src/schema/nmdc.yaml` produces byte-identical output before and after (147 lines, `diff` empty).

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `14ddcdc051ab`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.