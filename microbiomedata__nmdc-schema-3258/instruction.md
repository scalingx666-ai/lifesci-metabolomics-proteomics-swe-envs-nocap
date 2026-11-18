# Issue

**Title:** Run CodeQL as advanced setup so generated-file exclusions apply

## Description

## Why

`.github/codeql/codeql-config.yml` already lists path exclusions for the generated model modules (`nmdc_schema/nmdc.py`, `nmdc_schema/nmdc_pydantic.py`) and the frozen partial migrators. But CodeQL runs here as *default setup*, which does not read that config file, so those exclusions have never applied.

Because of that, the code quality queries report hundreds of findings in generated files that must not be hand-edited. Example: `py/not-named-self` fires on every generated pydantic v2 `@field_validator` method, which takes `cls` by convention. These are false positives on correct generated code. A local reproduction of the rule finds it only in `nmdc_pydantic.py` (506) and `nmdc.py` (2); no authored file is affected.

This adds an advanced-setup workflow that references the existing config file, using the `security-and-quality` suite so the exclusions apply to both the security and quality queries. Security queries reported 0 open alerts under default setup, so that coverage is unchanged; quality coverage stays on authored code.

## Required settings change

Advanced setup and default setup cannot coexist. CodeQL default setup must be disabled in Settings > Security and analysis > Code scanning before this workflow can run.

## Validation

`actionlint` (with shellcheck on PATH) and `zizmor` at default and pedantic personas: all clean.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `14ddcdc051ab`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.