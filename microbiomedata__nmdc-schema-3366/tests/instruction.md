# Issue

**Title:** Validate example data structurally, not just unit alignment

## Description

Closes

`CLAUDE.md` has warned since May that "the pytest validation plugin can be more permissive, so this can pass unit tests and still fail the build at the examples step" (b3f57735e). This is the cause of that, and the fix.

`Validator(schema=..., validation_plugins=[...])` **replaces** linkml's default `JsonschemaValidationPlugin` rather than adding to it. `test_all_valid_examples` was built that way, so despite its name it checked QuantityValue unit alignment and nothing else. Measured against a file merged yesterday, one mutation at a time:

| planted defect | before | after |
|---|---|---|
| `has_output` set to a non-CURIE string | passes | fails |
| `id` violating the class id pattern | passes | fails |
| required `type` or `analyte_category` removed | passes | fails |
| invented slot added | passes | fails |

`make test` was never fooled, because the examples runner does full validation, so nothing bad reached `main` through this. The cost was local: `pytest tests/` reported green on 161 files it had barely inspected, and anyone iterating that way got no signal until CI.

The two tests that unit-test the plugin keep the plugin-only validator, since folding jsonschema results into them would make `test_invalid_instance`'s single-result assertion a statement about two different checkers. The corpus test gets a second fixture that runs both.

Along the way this exposed that `minimal_biosample` set `has_value` on a QuantityValue. That slot does not exist (it is `has_numeric_value`, which `CLAUDE.md` documents), and the fixture also omitted the required `name`. So the shared fixture described an instance shape that could never occur in real data, and nothing noticed because it was only ever run through the validator that does not check structure.

`test_structural_defects_need_the_jsonschema_plugin` asserts both halves: the plugin-only validator stays silent on a broken instance, the full one does not. Dropping the plugin again fails that test rather than quietly widening what passes.

**Unrelated one-comment fix in the same PR**, at Mark's request rather than as a drive-by: the Mongo tunnel instructions in `project.Makefile` pointed at `mongo-loadbalancer.nmdc.production.svc.spin.nersc.org` through a NERSC login node. Production Mongo is reached through the `jump-dev.microbiomedata.org` cloud gateway now, so anyone following those lines was aiming at a decommissioned host.

Verified: full suite 93 passed. A defect planted in a valid example fails the corpus test now and passed it before.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `2a6caf293471`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.