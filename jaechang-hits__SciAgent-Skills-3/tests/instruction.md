# Issue

**Title:** feat: add statistical significance annotation guide skill

## Description

## Summary
- Add new guide-type skill for annotating statistical significance (p-value asterisk notation) on comparison plots
- Covers standard notation conventions (ns, *, **, ***, ****), decision framework for when to annotate, and reusable matplotlib helper functions
- Includes integration examples with seaborn box/violin/bar plots

## Test plan
- [ ] Verify `registry.yaml` entry is valid
- [ ] Verify SKILL.md follows guide template structure
- [ ] Run `pixi run validate` to check registry integrity
- [ ] Test skill discovery via OmicsSkillsMiddleware

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `0ae721311419`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.