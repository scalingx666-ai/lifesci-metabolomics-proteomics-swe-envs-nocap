# Issue

**Title:** fix: normalize plotly-interactive-plots skill name for spec compliance

## Description

## Summary
- Renamed `name` field in `plotly-interactive-plots/SKILL.md` frontmatter from `"Plotly Interactive Plots"` to `"plotly-interactive-plots"` to comply with the spec requirement that names must be lowercase alphanumeric with single hyphens only.

## Test plan
- [ ] Verify `name` field matches the lowercase-alphanumeric-with-hyphens pattern
- [ ] Run `pixi run validate` to confirm registry integrity

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `82d0c87b4839`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.