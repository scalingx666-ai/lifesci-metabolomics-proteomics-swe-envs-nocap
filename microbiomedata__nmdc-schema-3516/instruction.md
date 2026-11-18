# Issue

**Title:** Record structured alias origins in source, not contexts

## Description

Closes  (14 structured aliases record their origin in contexts instead of source).

In the LinkML StructuredAlias metamodel, `source` is where an alias comes from and `contexts` is where it applies. `CLAUDE.md` asks for `source`, but 14 aliases put their origin in `contexts`.

- Nine GOLD aliases on `InstrumentModelEnum` values now have `source: https://gold.jgi.doe.gov/`, the same URL they listed under `contexts`.
- Five aliases from the JGI Analysis Tracker (JAT) pointed at a macro file in a Bitbucket repository that needs a login. Following the `CLAUDE.md` rule for restricted sources, `source` is now the public nmdc_automation README that explains JAT, and a note gives the Bitbucket URL. The same pattern is already used for the JGI isolate form aliases.

`tests/test_structured_alias_source.py` fails if a structured alias in any `src/schema/*.yaml` file has no `source` or uses `contexts`. That includes `src/schema/mixs.yaml`: it is generated, but its aliases are written by NMDC in `assets/yq-for-mixs-customizations.txt`, so a fix goes there.

## Validation

- `linkml-lint` reports no problems, and the new test passes.
- `pytest tests/`: 502 passed. `test_all_valid_examples` fails the same way on `main`, because the committed `nmdc_materialized_patterns.yaml` predates the SIP slots in `src/data/valid/Database-sip-lifecycle.yaml`. This branch changes nothing under `nmdc_schema/` or `src/data/`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ecfb8c72f3ab`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.