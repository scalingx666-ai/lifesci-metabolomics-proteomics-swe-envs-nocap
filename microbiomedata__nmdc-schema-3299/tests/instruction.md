# Issue

**Title:** DO NOT MERGE until August: docs preview of the objectified-examples PR stack (3276/3277/3278/3292)

## Description

This branch is a integration merge of the four PRs that make changes to the way we store and display examples.

It includes a combined docs preview (although that may require some ongoing maintenance). Each of the feature PRs builds its own preview, but none shows the objectified examples rendered by the new document gnerator all together. This branch does.

We could refine the feature branches and merge then individually or if the reviewers are comfortable, merge this integrated one.

Merged tips:

-  docgen: render object: examples in slot and class docs
-  Remove redundant inline examples from MIxS slot descriptions
-  Objectify wrapper-range example values to match asserted range
-  MIxS units and example discrepancies (deferred slots + documentation)

Review and merge the four PRs individually. This branch will be deleted once the preview has served its purpose.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `258b0aa79663`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.