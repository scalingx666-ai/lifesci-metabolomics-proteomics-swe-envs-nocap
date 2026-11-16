# Issue

**Title:** Irems updates

## Description

Hello, I intend this to be the first in a serious of contributions that would get the data submodule functional. This is sort of an early PR to make sure I'm moving in a direction that would be compatible with your vision. (And to make sure I did not break any  installation recipes).

Briefly:
- minor fixes including updating some dead RSCB links, clearing out the empty cells in the demo, and removing a redundant entry in .gitignore (and adding a .vscode entry because I use vscode as a code editor)
- added extremely basic functionality to graphql, where passing in json arguments as a dict returns the results as a dict. Updated `test_graphql.py` with a simple test.
- added `pypdb.clients.data.graphql` to `modules_list` in `setup.py`
- `setup.py` didn't work for me, and I realized an `__init__.py` was missing in `pypdb/clients/search/operators/`. I'm not sure how the installation with `pip` worked before this, so I may have missed something.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c2f0f7bf646c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.