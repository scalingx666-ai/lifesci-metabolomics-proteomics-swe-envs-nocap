# Issue

**Title:** Prepare `get_typecode_for_future_ids` for LinkML v1.12 and add associated test

## Description

With LinkMl 1.12, the `get_typecode_for_future_ids` function would return None for several classes.  This will break the minter if not resolved. This MR fixes that functionality under both LinkML 1.12 and 1.11 and adds a test so it is covered by CI/CD in the future.

First I added a test to ensure that all classes that are descendant of `NamedThing` but not descendants of `OntologyClass` resolve proper typecodes using the `get_typecode_for_future_ids`.  This test passes with linkML 1.11. Commit c0865223c49405647f54ba47a0fb607f731281d9

Next I bumped the poetry.lock to show that with LinkML 1.12 the new test fails. Commit 393fe9775e232d73265f7979f1482c22aa78f6eb

Then I fixed the failing test with some updated regex. Commit 84576d671d32bed1b2cb2388f29c1b96edd3bc88.

Finally, I "unbumped" the poetry.lock to revert back to LinkML 1.11. Commit 7f7aeae55d72a36a86af31794b4de6a0cf475b5a

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a1bcc01f9d18`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.