# Issue

**Title:** Show member subsets and a subset's own in_subset on subset pages

## Description

Makes subset grouping visible on subset pages, in both directions. Fixes

`subset.md.jinja2` collected classes, slots and enums and nothing else, so a subset whose members are other subsets rendered with an empty body. `badge_topic` is that case: its two members are the `biogeochemistry` and `host_information` subsets, and https://microbiomedata.github.io/nmdc-schema/BadgeTopic/ listed neither.

Two additions:

**Subsets in subset.** A member-subset table, collected the same way the other three kinds are. `BadgeTopic` now renders:

| Subset | Description |
| --- | --- |
| Biogeochemistry | Biosample slots holding measured biogeochemical analytes: nitrogen,... |
| HostInformation | Biosample slots describing the host organism a sample was taken from or... |

**Member of.** A subset's own `in_subset`, so the grouping is reachable from the member as well as from the group. `Biogeochemistry` now shows `Member of: BadgeTopic`.

Rendered output for all four subsets, confirming each section appears only where it applies:

| page | slots in subset | subsets in subset | member of |
| --- | --- | --- | --- |
| `JgiIsolate` | yes | no | no |
| `Biogeochemistry` | yes | no | yes |
| `HostInformation` | yes | no | yes |
| `BadgeTopic` | no | yes | no |

`JgiIsolate` is unchanged, which is the regression check that matters: it is the one subset predating this work.

Full test suite passes (87 tests).

Note these pages are also affected by the frontmatter collapse in  The two changes touch different parts of the same template and do not conflict, but subset pages will not read correctly until both are merged.

Closes

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `84651fe32b2e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.