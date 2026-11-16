# Issue

**Title:** fix: use bundled Inter for macOS UI text

## Description

JavaFX 26 renders the macOS system font with cramped spacing in mzmine. Use bundled static Inter 4.1 regular, bold, italic, and bold-italic faces for macOS UI text while keeping the existing theme sizes and styles.

The fonts and SIL Open Font License are published as an optional `macos-fonts` artifact on every build host. macOS Community runs include that artifact; Windows and Linux retain their existing font and runtime contents. Pro consumes the same artifact in the companion PR: 

Validation on macOS ARM64 with JavaFX 26:
- Built the Community artifact and regenerated the 4.10.117 Gradle module metadata.
- Verified a standalone Gradle consumer resolves both the main JAR and the optional font variant; the main JAR contains no Inter resources.
- Verified all four font faces across the existing themes, and actual Pro GUI startup on the matching 4.10.117 sources with Inter active.
- Checked upstream font hashes and bundled license.

Merge into `feat/auto-mcp`, then publish the updated Community package before building the companion Pro change. Windows/Linux execution and signed installer builds were not run for this change.

Before:
<img width="841" height="513" alt="Bildschirmfoto 2026-10-30 um 09 33 08" src="https://github.com/user-attachments/assets/9da60f6d-ae39-4644-8e20-e942c12d0ea4" />
After:
<img width="953" height="515" alt="Bildschirmfoto 2026-10-30 um 09 34 00" src="https://github.com/user-attachments/assets/b1f96e1b-d017-4906-a2eb-1231a69df8f9" />
Before:
<img width="437" height="89" alt="Bildschirmfoto 2026-10-30 um 06 56 39" src="https://github.com/user-attachments/assets/5555db52-5fb0-4a74-91ce-21f72bbdcbbe" />
After:
<img width="972" height="603" alt="Bildschirmfoto 2026-10-30 um 09 35 58" src="https://github.com/user-attachments/assets/ce4ae5eb-b456-4563-a5f0-3b80f7cd04ed" />

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `0437541d303b`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.