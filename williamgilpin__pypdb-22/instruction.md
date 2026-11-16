# Issue

**Title:** [RCSB Search] - Added support for "terminal" node queries against the Text search service

## Description

## Implemented Basic RCSB Text Search

This goes a ways towards implementing fully-featured search, in my estimation.
The other RCSB search services are much simpler than the text one.

For example usages, see: `pypdb/clients/search/EXAMPLES.md`.

All of those example searches worked for me locally. Try them out yourself if you like!

#### Also I accidentally added some files that will contain the graphql API...

I figure there's no harm in these existing in the `pypdb` repo. 
(I'm a little bit too lazy to split them out of the pull request, unless you want me to.)

## Tests

All tests pass, run using `pytest` in the `setup.py` directory.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `22f00af7cb18`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.