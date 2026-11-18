# Issue

**Title:** Generate release artifacts for `nmdc-schema` version `11.23.0`

## Description

On this branch, I did two things:
1. I generated the release artifacts for `nmdc-schema` version `11.23.0` (by running `$ docker compose run --rm -it --name nmdc-schema-builder app sh -c 'poetry install && make squeaky-clean all test'`)
2. I added a "no op" migrator between schema versions `11.22.0` and `11.23.0`

---

Note that step 1 took 21 minutes and 32 seconds. The majority of that was spent installing Python packages via `poetry install`. There were 247 packages to install.

<img width="980" height="124" alt="image" src="https://github.com/user-attachments/assets/bdc6e104-17df-4702-b2ec-afbe98ffd9bd" />

[...]

<img width="759" height="140" alt="image" src="https://github.com/user-attachments/assets/f66c6c8a-49b5-4cbb-bedb-c212b145f3a2" />

[...]

<img width="948" height="256" alt="image" src="https://github.com/user-attachments/assets/b735254e-ed94-4fba-8a2a-78f17a0be75b" />

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c9dd3e50bad3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.