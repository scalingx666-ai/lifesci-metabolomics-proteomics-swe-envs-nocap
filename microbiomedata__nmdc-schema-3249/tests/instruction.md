# Issue

**Title:** Stop docgen truncating slot/class descriptions mid-word

## Description

Fixes the mid-word truncation reported in 
- 

The class, slot, enum, index, and subset doc templates ran each table-cell description through linkml docgen's `enshorten` filter, which splits on the first period. Abbreviations like "i.e." and "e.g." were treated as sentence ends, so `has_raw_value` rendered as "...raw form, i" and `language` as "...code e".

This replaces `enshorten` with a local `shorten` macro (`src/doc-templates/_macros.jinja2`) that caps length at a word boundary without splitting on periods, and collapses newlines and escapes pipes for table safety. Regenerating the docs confirms `has_raw_value` and `language` now show their full first sentence.

Docs-build only: no schema or generated artifacts change. The upstream fix to `enshorten` itself is tracked in  this is the local stopgap.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `84b930399cb6`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.