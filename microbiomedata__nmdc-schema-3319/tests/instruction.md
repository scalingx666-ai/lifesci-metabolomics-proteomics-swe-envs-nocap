# Issue

**Title:** Fail CI if uv.lock is tracked

## Description

uv.lock has been committed and reverted twice (5c415c17a, 16b10a8e2). `.gitignore` catches the accidental case but not `git add -f`, and not a file that is already tracked, which is how both earlier occurrences got in.

The check is its own job rather than a step inside `ruff`, so it needs no Python and gets a distinct check name. That name is the thing worth adding to main's required status checks: main currently requires zero checks and `enforce_admins` is false, so a red job does not block a merge on its own.

`git ls-files` rather than `test -f`, because the rule is about the file being tracked. The same check then works locally without firing on a contributor's git-ignored copy.

Delete this job if  lands and uv becomes the lock tool. The job comment says so.

actionlint and zizmor are both clean on the edited workflow.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c05a302ffa2b`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.