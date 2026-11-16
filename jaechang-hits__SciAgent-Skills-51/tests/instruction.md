# Issue

**Title:** Feat/HL1281 spatial transcriptomics 공간전사체 skills 추가

## Description

## Summary
공간전사체 분석 스킬 추가 PR입니다.

총 9개의 스킬 추가
spatial-transcriptomics-cell-cell-communication
multimodal-omics-integration
spatial-domain-detection
spatial-mapping-tangram
spatial-panel-design
spatial-transcriptomics-analysis-squidpy
spatial-transcriptomics-cell-type-annotation
spatial-transcriptomics-deconvolution-cell2location
+
trajectory-inference 스킬 추가
+
registry.yaml 수정

license 4.0 (MIT)

## Checklist

- [ ] `pixi run test` passes locally
- [ ] `registry.yaml` updated with the new entry
- [ ] Skill type is correctly set: pipeline / toolkit / database / guide
- [ ] `description` field is ≤ 1024 characters
- [ ] Frontmatter has `name`, `description`, `license`
- [ ] Required sections present in correct order (see `AGENTS.md`)
- [ ] Code blocks are runnable with sample data or clear placeholders
- [ ] Troubleshooting table has 5+ rows
- [ ] Key Parameters table has 5+ rows

## Skill(s) added or modified

List the skill paths, e.g. `skills/genomics-bioinformatics/salmon-rna-quantification/SKILL.md`

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e08614515b62`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.