# Issue

**Title:** Point contributors to the current prod Mongo tunnel doc

## Description

Reaching production NMDC Mongo (to test migrators, verify data questions like #3259, etc.) goes through the jump-dev gateway, documented in `microbiomedata/nmdc-lakehouse/docs/mongodb-connection.md`. Nothing in this repo pointed there, and two things still referenced the retired NERSC/SPIN tunnel, so anyone following them would hit a host or port that no longer applies.

- `.env.example`: added a pointer to the lakehouse doc next to `SOURCE_MONGO_USER`/`SOURCE_MONGO_PASS`.
- `assets/misc/legacy_migration_notes.md`: marked the old recipe superseded, with a link to the current one. Kept for historical reference.
- `nmdc_schema/dump_single_modality.py`: changed the `--mongo-port` default from the retired SPIN port (27777) to the current tunnel port (27124), so the docs, the example env, and the tool all agree on one value.

No secrets are referenced, only variable names and the public doc URL.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9453089c1794`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.