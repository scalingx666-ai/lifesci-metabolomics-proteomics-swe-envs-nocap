# Issue

**Title:** Align Docker image with CI: Python 3.12 and poetry==2.4.1

## Description

The Docker build generates release artifacts under Python 3.10 and a floating `poetry>=2.3.0`, while the `pypi-publish` workflow that actually publishes uses Python 3.12 and `poetry==2.4.1`. This aligns the image with CI so the documented build path matches the publish path. A test build under 3.10 produced artifacts content-identical to the committed ones (only the generation timestamp differed), so this is consistency hygiene rather than a correctness fix.

- #3206.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `8f1dc97bd80d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.