# Issue

**Title:** Show subset membership and slot_group on slot doc pages

## Description

Show a slot's `in_subset` (linked to its subset page) and `slot_group` on its generated documentation page, added to the Properties section of `slot.md.jinja2`.

Class pages are intentionally left unchanged (option 1 from the issue discussion): each slot row already links to its slot page, which now carries this, so the class Slots table stays uncluttered.

`Slot Group` renders as a link when its value names a real slot, and otherwise shows the label, since this schema uses `slot_group` as a free-form group name (for example `JGI-Metagenomics`). Both lines are guarded, so slots with neither are unchanged.

Independent of the badge PRs (#3230, #3232, #3233). It improves `jgi_isolate` and `slot_group` display today, and the badge subset pages once those merge.

Verified by generating docs from the source schema: `strain_name` shows `In Subsets: JgiIsolate`, `dna_concentration` shows `Slot Group: JGI-Metagenomics`, and a plain slot like `md5_checksum` is unchanged.

Closes

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1e86e5b382f6`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.