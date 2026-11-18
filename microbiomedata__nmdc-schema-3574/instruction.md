# Issue

**Title:** Remove the chardet override now that pronto 2.7.4 allows chardet 7

## Description

## Why

-

nmdc-schema carried a uv override forcing chardet 7, because every pronto release capped chardet at ~=5.0 while linkml 1.12 needs chardet>=7.4.1 through pyshexc. pronto 2.7.4, released 2026-10-19, allows chardet>=5.0,<8.0, so the override is no longer needed.

This does not close the issue above, which still lists two linkml 1.12 breaks.

-

## What changed

The override and its comment are removed from `pyproject.toml`. In `uv.lock` the override entry is removed and pronto moves from 2.7.3 to 2.7.4. chardet stays at 7.6.0, and linkml and linkml-runtime stay at 1.12.1.

## Validation

`uv lock --check` passes. `make squeaky-clean all test` exits 0 on Python 3.13.13 with 660 tests passed, and it leaves no generated file changed. A from-scratch rebuild that also regenerated `src/schema/mixs.yaml` (`make squeaky-clean mixs-yaml-clean && make src/schema/mixs.yaml && make squeaky-clean all test`) left no file changed either.

## Documentation impact

None.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1a20c2753395`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.