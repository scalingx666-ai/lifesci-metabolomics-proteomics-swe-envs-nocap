# Issue

**Title:** feat: add 9 figure guide skills (including journal-specific skills)

## Description

## Summary
- Add 9 new figure preparation guide skills under `scientific-writing/`
- 8 journal-specific guides: Nature, Cell, Science, PNAS, Cancer Research, The Lancet, NEJM, and eLife — covering resolution, format, font, panel labeling, and image integrity requirements per journal
- 1 general figure quality guide extracted from the Image Quality Check prompt in `a1_hits_multiagent.py` — covering visual inspection (overlapping labels, clipped text, missing axes/legends, empty areas, overcrowded data), resolution/format best practices, and color accessibility
- All 9 guides include required sections: Key Concepts, Decision Framework, Best Practices, Common Pitfalls
- Register all entries in registry.yaml

## Test plan
- [x] `pixi run test` passes (4074 tests)
- [ ] Spot-check 2-3 guides against official journal submission guidelines

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e20fcb25bdde`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.