# Issue

**Title:** fix: add K-Dense-AI attribution to LICENSE

## Description

## Summary
- Add K-Dense-AI/claude-scientific-skills (MIT License) copyright notice to LICENSE file
- Remove residual "Promotional K-Dense section stripped" and similar migration notes from 9 skill files

## Test plan
- [x] `pixi run validate` passes (197 entries)
- [x] `grep -ri "K-Dense" skills/` returns no matches
- [x] `grep -ri "promotional" skills/` returns no matches

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7e822f2ce084`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.