# Issue

**Title:** Add badge subsets, MetadataBadgeEnum, and the badges slot

## Description

Defines the schema terminology for biosample metadata-quality badges: the badge subsets, the enum, the `badges` slot, its attachment to `Biosample`, and a valid example. It does not compute badges; award logic belongs in the runtime.

Revised 2026-08-13 to match the metadata quality squad decisions of 2026-08-05 and 2026-08-12 and @bmeluch's review, so it no longer resembles its original description:

- Badges are boolean. The silver and gold levels are gone.
- Ships the three badges scoped for this quarter: `biogeochemistry`, `host_information`, `expert_curation`. `land_use_and_vegetation` and the other candidate axes move to a follow-up.
- `biogeochemistry` (44 slots) and `host_information` (37 slots) are completeness badges, each declared as a subset carrying a `badge_minimum_slots` annotation of 2. Membership is the squad's Badge Subsets Scratchpad supersets, each slot verified as a `Biosample` slot. Twelve members are NMDC-native and carry `in_subset` in their own definitions, since the yq customization file only rewrites `mixs.yaml`.
- `expert_curation` is awarded from `ProvenanceMetadata.source_system_of_record`, not from slot completeness, so it has an enum value but no subset and no bar. The sync test exempts it through an explicit list rather than a silent gap.

The bar is an absolute count of populated slots and never a proportion of subset size, so adding a slot to a subset can only make a badge easier to earn. Without that property a subset that grows would revoke badges records already display, which users would read as a badge vanishing for no reason.

`badges` is attached to `Biosample` only. Study badges are out of scope for this quarter, so the `Study` attachment from the original plan is deliberately absent.

Three decisions are recorded as issues rather than settled here, because they are squad calls and none of them blocks the terminology:

-  whether required slots belong in badge subsets. Two `host_information` members are `required: true` in submission-schema's `PlantAssociatedInterface`.
-  the bar of 2 needs a per-biosample distribution against these subset sizes.
-  `src/schema/subsets.md` is maintainer-facing, so it sits outside `src/docs/` to stay off the published site.

Closes  (Define slot groups (subsets) that badge criteria are evaluated against)

Closes  (Add valid example data showing badges on a Biosample)

Closes  (Record each badge subset's qualifying bar as an annotation on the subset)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e30e0b2b109a`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.