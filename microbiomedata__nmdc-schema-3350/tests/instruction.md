# Issue

**Title:** Stop the doc frontmatter fence collapsing onto the next line

## Description

Fixes the frontmatter collapse described in

Measured by regenerating the full documentation set before and after:

| | malformed frontmatter |
| --- | --- |
| before | 178 of 1164 pages |
| after | 0 (2 pages have no frontmatter by design: `index.md` and `NMDC.md`) |

Nothing was newly broken by the change.

The cause is whitespace control. When the construct after the closing `---` opens with `{%-`, the strip eats the newline after the fence and the fence lands on the following line, so mkdocs stops recognizing the block and renders it as body text. Affected pages opened with `search: boost: 1.0 ---# Subset: ...` and their search boost never took effect.

Three changes:

**The four local templates** (`subset`, `enum`, `class`, `slot`) now put a blank line after the fence and use a non-stripping `{% from %}`. `class` and `slot` were rendering correctly before, but only by accident: the construct after their fence happened to emit a newline. They are now explicit rather than lucky.

**`type.md.jinja2` is vendored** into `src/doc-templates/` with the same fix. This accounts for 25 of the 178 pages. LinkML 1.11.1's built-in type template has the identical defect, and there was no local override, so those pages could not be fixed any other way. The repository already vendors eight templates, so this follows existing practice. Upstream report to follow.

**A regression test** (`tests/test_doc_template_frontmatter.py`) asserts that no template's closing fence is followed by a whitespace-stripping tag or by a heading with no blank line between. It is a string check on the templates, so it runs in milliseconds and needs no generated artifact. Verified it fails when the defect is reintroduced.

The test is deliberately stricter than the bug: it forbids the risky construct rather than trying to predict which templates survive it by luck. That is what made `class` and `slot` fragile in the first place.

Closes

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `84651fe32b2e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.