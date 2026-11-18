# Issue

**Title:** Retarget the post-11.20.2 no-op migrator to 11.21.0

## Description

The next release is a minor bump to **11.21.0**, not a patch (11.20.3), because it adds new modeling (library-preparation slots and enums in #3214, plus a conditional DataObject rule in #3215).

#3216 added a no-op migrator named `migrator_from_11_20_2_to_11_20_3`. This renames it to `migrator_from_11_20_2_to_11_21_0` and sets `_to_version = "11.21.0"` so the chain link matches the version that will actually be released. The two backfill migrators (11.20.0 to 11.20.1, 11.20.1 to 11.20.2) are unchanged.

Still a no-op: every change from 11.20.2 to 11.21.0 is additive, so no data valid under 11.20.2 becomes invalid. Should merge before the v11.21.0 release so no phantom 11.20.3 migrator remains on main.

sorry about that, @eecavanna

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e85d43bc1241`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.