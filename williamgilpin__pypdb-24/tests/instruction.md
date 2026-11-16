# Issue

**Title:** [RCSB Search API] - Added support for `NOT_EQUAL` comparison type

## Description

## Feature Description

I implemented a `NOT_EQUAL` `ComparisonType` for the `ComparisonOperator` within the Text Search Service.

This contributes incrementally towards .

## Rationale

I know I said earlier I would support negation for the RCSB Search API ([it's briefly mentioned here](http://search.rcsb.org/#field-queries)) but I cannot think of a good reason it is useful beyond wanting to query something being 'not equal' to some other value.

So, to keep the API wrapper "sparking joy" (=> not loaded with unnecessary arguments), I implemented a `NOT_EQUAL` comparison type that should do the trick just fine. So, downstream users need not know what this negation thing is.

## Tests + `mypy`

All tests pass using `pytest`, all files pass `mypy` inpection using `mypy --namespace-packages path/to/file.py`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `83c9f7fdd7ea`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.