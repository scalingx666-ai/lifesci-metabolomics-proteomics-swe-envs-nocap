# Issue

**Title:** Switch to `uv`

## Description

@florian-huber as discussed:

- pyproject.toml: remove poetry-bumpversion dep and its config section, add [tool.uv] with package=true and default-groups=["dev"]
- .gitignore: un-ignore uv.lock, add .venv/
- CI workflows: use astral-sh/setup-uv@v5, uv sync --frozen, uv run for all commands, uv build + uv publish for publishing
- .readthedocs.yml: switch to uv install method with docs group
- .pre-commit-config.yaml: add uv-lock hook from astral-sh/uv-pre-commit
- README.rst & CONTRIBUTING.md: uv-first installation instructions, uv version --bump for releases, uv run for dev commands
- Regenerate uv.lock and dev-requirements.txt with uv
- Remove poetry.toml and readthedocs/requirements.txt

Also renames test_with_conda job to test_docs and updates SonarCloud artifact name from sonarcloud-data-conda to sonarcloud-data-docs.

(I'll mark it as draft for now)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `2e814060bcd2`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.