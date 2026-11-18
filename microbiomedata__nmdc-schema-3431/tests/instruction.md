# Issue

**Title:** Document schema consumers and compatibility rollout

## Description

Schema consumers currently have no shared inventory connecting their package dependencies, compatibility checks, and release-update work. Add a nine-consumer registry and a developer guide that identifies repository ownership, links the implementation issues, and explains the source-schema / derived-artifact / data-migration sequence.

The registry explicitly distinguishes planned integrations from discovery. It does not dispatch workflows or claim compatibility has been tested. This is the inventory/documentation foundation for #3427; candidate orchestration (#3428) and release-update automation (#3429) remain separate implementation tasks. The guide is linked from the developer FAQ and documentation navigation.

Validation: parsed the registry and checked unique consumers, dependency declarations, statuses, tracking links, and navigation; verified the new GitHub issue bodies and parent links; rendered the two authored documentation pages with MkDocs and the project's theme/Markdown extensions; `git diff --check` passed. The focused render emitted only three expected warnings for existing FAQ links whose pages were omitted from that two-page preview. No schema or runtime code changed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `135349819d0b`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.