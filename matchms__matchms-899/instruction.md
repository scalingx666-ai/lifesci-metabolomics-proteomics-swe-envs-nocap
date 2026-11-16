# Issue

**Title:** Add support for Python 3.14

## Description

Adds Python 3.14 to the supported versions for matchms.

`pynndescent`  so this is no longer a blocker for `matchms`. The next blocker turned out to be `sparsestack==0.7.0`, which pins `numba>=0.61.0,<0.62.0` and `numba` 0.61.x ships no Python 3.14 wheels (and `llvmlite` 0.44.0 fails to build from source on 3.14 due to the distutils.spawn(dry_run=...) removal).

  Changes

  - pyproject.toml
    - Widened `requires-python to >=3.10,<3.15` and added the 3.14 trove classifier.
    - Bumped `scipy>=1.15.3,<1.16` → `scipy>=1.15.3,<1.17`. scipy 1.15.x has no 3.14 wheels; 3.14 support starts in 1.16.
    - Added `[tool.uv.sources]` pointing sparsestack at [BioGeek/sparsestack@python3.14 ](https://github.com/BioGeek/sparsestack/tree/python3.14) as a temporary workaround. I will revert this block once  is merged and a new sparsestack release is published on PyPI.
  - uv.lock: refreshed. Notable upgrades on the 3.14 fork: `numba` 0.61.2 → 0.65.1, `llvmlite` 0.44.0 → 0.47.0, `scipy` 1.15.3 → 1.16.3.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d5b0c4fe2ae1`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.