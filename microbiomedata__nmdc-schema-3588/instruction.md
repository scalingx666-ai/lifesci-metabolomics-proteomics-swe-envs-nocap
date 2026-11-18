# Issue

**Title:** Use static version in pyproject.toml with release coordination script

## Description

Supports  (new `package.json` file here)

These changes replace the dynamic versioning (via `uv-dynamic-versioning`) with static versioning. The source of truth for the version in various generated artifacts is now `pyproject.toml`. Even though the version number is now explicitly listed in `pyproject.toml`, it is **not** intended to be modified manually. There is a new release script which keeps everything (`pyproject.toml`, the new `package.json` file, LinkML-generated artifacts, git tags, GitHub Releases, etc) in sync.

The new release script is in `src/scripts/release.py` and is invoked via the `make release` target. The target takes a `BUMP` argument that controls what the next version number is. It follows the same semantic of `uv version --bump` (https://docs.astral.sh/uv/reference/cli/#uv-version--bump) except only `major`, `minor`, `patch`, `stable`, and `rc` are allowed.

A corresponding update to the `infra-admin` release instructions is here:

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a7f2dfaec37c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.