# Issue

**Title:** fix(wizard): handle unset numeric values and report batch creation errors

## Description

Comparing a populated numeric parameter with an unset parameter throws a `NullPointerException`. Separately, the wizard reads and validates controls before entering its batch-creation error handler, so a readback failure can leave **Create batch** appearing to do nothing.

Handle missing values symmetrically in `Parameter.valueEquals` and move the existing wizard readback, validation, and batch-parameter lookup inside its error handler. Preserve the existing batch creation and execution flow. Add regression tests for numeric comparisons and visible reporting of readback failures.

This PR targets community `master` and includes only the fix and tests. It does not introduce the MCP-specific wizard readback present on `mmm-features` or change dependency versions/build workflows.

Validation: both new regression tests fail on unmodified master (`14cf429f13738f64cd5ece7e05929f6e8e9b11c4`); all 33 focused tests pass with the fix on macOS / Java 26:

```sh
./gradlew :mzmine-community:test --tests io.github.mzmine.modules.tools.batchwizard.BatchWizardBatchCreationTest --tests io.github.mzmine.parameters.StandardParameterTest
```

The JavaFX test is skipped on Linux. This validates the failure handling in tests, not an installed application on every OS.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `14cf429f1373`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.