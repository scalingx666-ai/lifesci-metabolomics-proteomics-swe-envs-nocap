# Issue

**Title:** Keep five descriptions to the definition and move the rest to comments

## Description

Closes  (LLM-generated slot description appears on Data Portal UI).

The Data Portal shows the `badges` description in a tooltip, and @eecavanna reported that it reads as machine-written. Most of that description wasn't a definition. It explained how badges are awarded and what happens to them afterward.

Each of these five elements now has a one-sentence description that says what it is. The rest of the old text moved to `comments`, and the NcbiTaxon example CURIE moved to `examples` on its `id`:

- the `badges` slot
- `MetadataBadgeEnum`
- the `jgi_isolate` subset
- `NcbiTaxon`
- `Organism`

Where an existing comment already said the same thing, as both of the `Organism` points did, I didn't add it again. No other field changes.

## Validation

- `linkml-lint`: no problems.
- `pytest tests/`: 501 passed and 1 failed. The failure is `test_all_valid_examples`, which fails the same way on `main` ( fixed in ).
- A local Codex review compared both files with `main` after removing `description` and `comments` (it ran before the `examples` move), found them identical, and found no problems.

Other descriptions that mix in usage notes or examples are listed in follow-up issues.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `03ba5a2bec0c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.