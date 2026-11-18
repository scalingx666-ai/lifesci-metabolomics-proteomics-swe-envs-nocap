# Issue

**Title:** Give each schema module its own copy of the settings its patterns use

## Description

Closes  (Give each schema module its own settings so its patterns resolve on linkml 1.12).

linkml-runtime 1.12 interpolates a `structured_pattern` only with the `settings:` of the module that defines it (). All our settings are in `nmdc.yaml`, so on 1.12 the patterns in the other six modules keep literal placeholders like `{id_nmdc_prefix}`, and 20 of 57 class id patterns don't resolve when the source schema is loaded with SchemaView.

`src/scripts/sync_module_settings.py` copies exactly the keys each module uses from `nmdc.yaml` into a marked block at the end of that module. `nmdc.yaml` stays the one place to edit a value. The MIxS regeneration still deletes the MIxS source settings () and then runs the script, so a regenerated `mixs.yaml` keeps its copy.

## Validation

- `tests/test_module_settings.py`: 39 tests. 14 fail on `main` and all pass here, on the locked linkml-runtime 1.11.1 and on 1.12.1.
- On linkml-runtime 1.12.1, SchemaView on `src/schema/nmdc.yaml`: unresolved induced patterns go from 330 of 522 to 0, and unresolved class id patterns from 20 of 57 to 0. On 1.11.1 both counts are 0 before and after.
- `make squeaky-clean all test` passes (549 passed, 1 skipped). Generated `nmdc_schema/` files are not committed.
- Not run: `make src/schema/mixs.yaml`, the network-dependent MIxS regeneration. The new Makefile line was run by hand on the committed `mixs.yaml`.

## Documentation impact

Comments in `nmdc.yaml`, `makefiles/mixs.Makefile` and `assets/yq-for-mixs-dematerialize.yq` now say where the copies come from.

The long-term fix is upstream:  asks whether an imported module should fall back to the importing schema's settings. If linkml does that, these copies can be removed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `72628b33bd01`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.