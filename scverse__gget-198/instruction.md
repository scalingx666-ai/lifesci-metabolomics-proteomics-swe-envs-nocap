# Issue

**Title:** Rename 'gget 8cubedb' module to 'gget 8cube'

## Description

## Summary

- Rename the `gget 8cubedb` module to `gget 8cube` for a shorter, cleaner command name
- Update all source files, tests, fixtures, and documentation (English and Spanish)
- All import statements and CLI command references updated across the codebase

## Files Changed

- **Source**: `gget/gget_8cubedb.py` → `gget/gget_8cube.py`
- **Tests**: `tests/test_8cubedb.py` → `tests/test_8cube.py`
- **Fixtures**: `tests/fixtures/test_8cubedb.json` → `tests/fixtures/test_8cube.json`
- **Docs (EN)**: `docs/src/en/8cubedb.md` → `docs/src/en/8cube.md`
- **Docs (ES)**: `docs/src/es/8cubedb.md` → `docs/src/es/8cube.md`
- Updated references in `gget/__init__.py`, `gget/main.py`, `docs/src/SUMMARY.md`, and `updates.md` files

## Test plan

- [ ] Run existing 8cube tests to verify functionality
- [ ] Test CLI commands: `gget 8cube specificity`, `gget 8cube psi_block`, `gget 8cube expression`
- [ ] Verify Python imports: `from gget import specificity, psi_block, gene_expression`
- [ ] Check documentation renders correctly

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d067b8f2bba3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.