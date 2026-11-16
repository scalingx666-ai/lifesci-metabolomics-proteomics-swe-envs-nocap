# Issue

**Title:** Make mysql-connector-python an optional dependency

## Description

mysql-connector-python is GPL-2.0 licensed, and requiring it as a core dependency effectively imposes GPL terms on the BSD-2-Clause gget package.

- Move it to a new `search` extra (`pip install gget[search]`)
- Import it lazily inside `gget.search()` and raise a clear ImportError with install instructions before any network calls if it is missing
- Add "search" to `gget setup` (Python and CLI)
- Install the `search` feature in all hatch-test environments so CI keeps testing gget search
- Document the new install step in the search and setup docs (en/es)




Claude-Session: https://claude.ai/code/session_01LxcykXY8HzhM48o1Rx2LLc

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ce325296c74f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.