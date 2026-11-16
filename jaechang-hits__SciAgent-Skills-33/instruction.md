# Issue

**Title:** refactor: regroup literature databases under scientific-writing

## Description

## Summary
Literature/citation databases were scattered:
- `pubmed-database` lived in `genomics-bioinformatics`
- `biorxiv-database` and `openalex-database` already sat in `scientific-writing`

PubMed's primary user-facing task is literature search (systematic reviews, citation matching, abstract mining), not NGS or variant analysis. Move it next to the other literature DBs and tag all three for cross-cutting discovery.

### Changes
- `pubmed-database`: `genomics-bioinformatics` → `scientific-writing` (path + category updated; SKILL.md and `references/` moved via `git mv`)
- All three literature DBs tagged with `["databases", "literature"]` to surface them under cross-cutting "databases" and "literature" lenses without duplicating files

### First PR to exercise the optional `tags` schema from #27
| Entry | New tags |
|---|---|
| `pubmed-database` | `["databases", "literature"]` |
| `openalex-database` | `["databases", "literature"]` |
| `biorxiv-database` | `["databases", "literature"]` |

### Cross-references
Other SKILL.md files (`clinicaltrials-database-search`, `geo-database`, `clinvar-database`, `ena-database`, `biorxiv-database`, `scientific-literature-search`, `openalex-database`, `hypogenic-hypothesis-generation`, `transformers-bio-nlp`) all refer to `pubmed-database` by name — not by path. No edits needed there.

### Category counts after
- `genomics-bioinformatics` -1 (pubmed leaves)
- `scientific-writing` +1 (pubmed arrives)

## Test plan
- [x] `pixi run test` passes (4096 tests, includes `test_category_matches_directory` and `test_path_matches_category`)
- [x] tag schema validated by `TestTagsField` (kebab-case, list-of-strings, no dupes)
- [x] reviewer confirms PubMed's discovery shouldn't also surface under a future `genomics` tag (e.g., for users searching genomics literature)
- [x] reviewer confirms the tag values `databases` and `literature` (vs `database`/`papers`/`citations`) — these are the first cross-cutting tag names in the registry, so they set precedent

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `2c26efbcce94`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.