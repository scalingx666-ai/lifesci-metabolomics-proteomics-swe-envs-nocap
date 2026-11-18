# Issue

**Title:** Generate release artifacts for `nmdc-schema` version `11.22.0`

## Description

On this branch, I generated the usual 6 schema release artifacts by running the command:

```shell
docker compose run --rm -it --name nmdc-schema-builder app sh -c \
  'poetry install && make squeaky-clean all test'
```

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9bfa5334b3ea`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.