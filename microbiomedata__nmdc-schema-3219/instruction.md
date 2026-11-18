# Issue

**Title:** Refactor function to invoke recently-introduced helper function

## Description

On this branch, I refactored a function so it used a recently-introduced helper function, rather than "re-implementing" the same thing locally.

Here's a screenshot showing the before (left) and after (right) of the schema docs web page that is downstream from the modified script. By design, there is no difference. Note: These are two different web browsers:

<img width="1462" height="820" alt="image" src="https://github.com/user-attachments/assets/df3487fa-7122-4f0f-ae31-8814ccb951fe" />

It can be previewed at: http://microbiomedata.github.io/nmdc-schema/pr-preview/pr-3219/typecode-to-class-map/

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e4b86a6b523e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.