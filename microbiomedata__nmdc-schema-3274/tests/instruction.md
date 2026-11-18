# Issue

**Title:** Document intentional seen_patterns.add() placement in schema_pattern_linting

## Description

GitHub Code Quality AI findings keep suggesting that `seen_patterns.add()` be moved above the `has_unescaped_prefix_dot` check in `src/scripts/schema_pattern_linting.py`. The current placement is intentional and the suggestion does not change output: the set dedups only printed lines, and the check is a pure function of the pattern string, so a skipped pattern can never print later.

This adds a comment at both `add` sites so the next reader, and the next scan, finds the rationale instead of re-triaging it. Comment-only, no behavior change.

Context: https://github.com/microbiomedata/nmdc-schema/discussions/3272

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9fd926a7c6f1`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.