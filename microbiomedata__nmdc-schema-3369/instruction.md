# Issue

**Title:** Constrain md5_checksum to a 32-character hex digest

## Description

Closes

`md5_checksum` was `range: string` with nothing else, so a `DataObject` could carry a URL, a SHA, or a sentence and every validator in this repo passed it. That is not hypothetical: the isolate sequencing example merged in  held `md5_checksum: https://example.com/read2.fastq` on two records, and only a review comment caught it.

The shape is already enforced one repo upstream. submission-schema patterns its three checksum slots as `^[a-fA-F0-9]{32}(?:\s*;\s*[a-fA-F0-9]{32})*$`, and `nmdc_runtime/site/translation/submission_portal_translator.py` splits those semicolon-separated values and writes one per DataObject. So the constraint survived the submission form and the translator, then got dropped at the destination. This closes that gap with the single-value form.

**No migrator needed, and this is measured rather than assumed.** Zero of the 290,640 `data_object_set` records in production fail the pattern:

```bash
curl -s -G "https://api.microbiomedata.org/nmdcschema/data_object_set" \
  --data-urlencode 'filter={"md5_checksum":{"$exists":true,"$not":{"$regex":"^[a-fA-F0-9]{32}$"}}}'
# {"resources":[]}
```

Controls were run so an empty result is not mistaken for an ignored filter: `$not` over a regex matching nothing returns records, `$not` over `.` returns none, and a 31-hex variant returns the 32-character values. Every database valid under the old schema is still valid under the new one, which is the conformance test `nmdc_schema/migrators/README.md` sets for whether a migration is required.

Two deliberate choices:

- **Case-insensitive.** Nothing normalizes case anywhere in the pipeline and the existing corpus mixes both (`3EFB4966125DFA9329ADE5B18EADDA8E` next to `dfd5515ee4b31c563d0f07cca9d52ed6`).
- **Still optional.** The `SRA toolkit-accessible sequence data` objects legitimately carry no checksum, and production has many. Only present values are constrained.

`url` is left alone on purpose. submission-schema patterns its URL slots too, but this repo's `url` carries a note that it clashes with the MIxS field, so it deserves its own decision rather than a bundled change.

Verified: the examples runner passes all 161 valid files and correctly fails the new counter-example. I confirmed the counter-example check actually fires by temporarily making that file valid, which produced `Counter example ... succeeded validation` and exit 1. Full pytest suite green against a locally regenerated artifact; the artifact itself is restored from `main` per the repo's no-generated-files-in-feature-PRs policy, so CI regenerates it.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `2a6caf293471`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.