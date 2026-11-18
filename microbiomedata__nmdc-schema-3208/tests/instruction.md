# Issue

**Title:** Make yq download architechure-aware and version-pinned

## Description

On Apple Silicon the build container is arm64, so the hardcoded `yq_linux_amd64` ran only under emulation. This fetches the architecture-matching binary via `dpkg --print-architecture` and pins the release (v4.53.3, what `latest` resolved to during testing) so the build no longer depends on emulation being available or on `latest` drifting.

.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `8f1dc97bd80d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.