# Issue

**Title:** Test the installed wheel weekly with the newest allowed dependencies

## Description

## Why

Closes  CI installs from `poetry.lock`, but `pip install nmdc-schema` gets the newest versions `pyproject.toml` allows, so the linkml-runtime 1.12 typecode break () reached users without failing CI.

The new workflow builds the wheel the way the release does, installs it into a fresh environment with pip and no lock, and runs the tests against that. It runs weekly and on demand, so it never blocks a PR. Whether it should also run on PRs is left for later.

## Which tests run

Measured locally on 2026-10-13 with Python 3.13, where pip resolved linkml and linkml-runtime 1.12.1:

- 28 of 37 test files run against the installed wheel and pass (420 tests), plus the doctests in `nmdc_schema/id_helpers.py` and `nmdc_schema/nmdc_data.py`.
- Two of the 28 import dev-only packages, so the job installs `fastjsonschema` and `ucumvert` alongside pytest.
- 9 are skipped because they import repo code that isn't in the wheel: 7 import `src.scripts`, and 2 import `nmdc_schema/*.py` files as top-level modules (`from nmdc_data import ...`), which only works with Poetry's editable install.

`--import-mode=importlib` keeps the checkout off `sys.path`, so `nmdc_schema` comes from the installed wheel. I confirmed that with a probe test.

## Validation

- With the regex from before  patched into the installed wheel, `tests/test_id_helpers.py` fails, so this job would have caught the 3510 break.
- `actionlint` and `zizmor --persona pedantic` report nothing on the new workflow. `tests/test_poetry_version_pins.py` passes.
- I repeated the run with the wheel built by the release's own steps (`poetry dynamic-versioning`, then `make -C units fast`), versioned `11.24.1.post157.dev0+e02e17487`, with the same results.
- Python 3.10 has not been run locally. The first manual run after merge will cover it.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3c5307539403`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.