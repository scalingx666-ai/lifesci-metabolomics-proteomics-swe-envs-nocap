# Issue

**Title:** fix: clear remaining ruff baseline errors on main

## Description

## Summary

After  cleared the bulk of the ruff baseline, **7 unfixable errors remained** — the same set PR #222 also addresses. This PR applies the fixes on main so the baseline is at zero independent of PR #222's merge order.

After this PR, `ruff check gget/` reports **0 errors**.

## What was wrong

- 1× `D205` in `gget/gget_g2p.py:22` — multi-line docstring summary without the required blank line before the description body.
- 6× `E402` in `gget/main.py:33,42–46` — module-level imports for `g2p`, `ref`, `search`, `seq`, `setup`, `virus` without the `# noqa: E402` comment that the surrounding imports carry. `main.py` has executable code (`dt_string = datetime.now()`) above the import block, so every later import needs the noqa.

## What changed

- `gget/gget_g2p.py`: collapsed the multi-line summary into one line + paragraph break.
- `gget/main.py`: added `# noqa: E402` to the 6 imports; dropped the now-stale `# Module functions` comment that was splitting one alphabetical list into two.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c72cc560a381`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.