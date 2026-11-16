# Issue

**Title:** fix(gui): restore dialog padding and error icons

## Description

Messages shown through the desktop API could touch the dialog's left edge, and errors used the blue information icon. Apply default padding to unpadded TextFlow content in the shared alert builder, preserve custom padding, and route desktop errors through the existing error-alert helper.

Validation:
- Latest master: `./gradlew :javafx-framework:test :mzmine-community:compileJava` passed.
- Local Community/Pro composite: `./gradlew :mzmine3:javafx-framework:test :mzminepro:compileJava` passed.
- A temporary JavaFX smoke check exercised the actual desktop error and hyperlink-message paths, checked alert styles and default/custom padding, and captured both dialogs for visual inspection.

This PR changes only the shared alert helper and desktop error routing.

<img width="1198" height="410" alt="grafik" src="https://github.com/user-attachments/assets/6f974ec7-9dca-40a2-8f5a-402ee258a619" />

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d8dcef0b1eed`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.