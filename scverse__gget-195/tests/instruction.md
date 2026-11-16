# Issue

**Title:** Remove shell=True from subprocess calls for security

## Description

## Summary
This PR addresses security concerns by replacing `shell=True` subprocess calls with list-based arguments in high-risk files that handle user input (file paths).

### Changes
- **gget_muscle.py**: Convert `chmod` and muscle alignment commands to list-based subprocess
- **gget_diamond.py**: Split chained `&&` commands into separate subprocess calls for version check, makedb, and alignment
- **gget_setup.py**: Convert `_install()` pip commands to list-based subprocess

## Why this matters
Using `shell=True` with f-strings is a security risk because:
- Shell metacharacters in user-provided paths could be interpreted as commands
- Paths with special characters (spaces, quotes, semicolons) could cause command injection

Using list-based arguments:
- Prevents shell metacharacter interpretation
- Safely handles paths with spaces without manual quoting
- Follows Python security best practices

## Note
There are additional `shell=True` instances in `gget_setup.py` (ELM download, AlphaFold setup) and other files that use complex shell features (`&&` chaining, `|` pipes). These would require more extensive refactoring and are lower risk since they don't process user-provided paths directly.

## Test plan
- [ ] Run `gget muscle` with various FASTA inputs
- [ ] Run `gget diamond` with query and reference files
- [ ] Run `gget setup elm` to test package installation

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `36148f8a599c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.