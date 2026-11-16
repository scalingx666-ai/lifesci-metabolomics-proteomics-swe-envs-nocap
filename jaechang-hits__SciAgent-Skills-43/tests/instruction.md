# Issue

**Title:** HL-354/612: [Agent][SKills] plot 모아서 하나의 pdf 파일로 만들기 & Volcanoplot 개선

## Description

## Summary
**HL-354 : Volcano plot 을 만들때 잦은 확률로 유전자 라벨이나 디자인(색깔과 모양)이 일반적이지 않음.**

(1) down (blue) top (red) 기본 양식을 따르도록 
(2) plot 격자무늬 없도록 
(3) 라벨 겹치지 않도록 
(4) 채팅이 달라져도 일관되고 질좋은 산출물을 위한 SKILL 개선 
(5) 더불어 barplot, boxplot, MAplot, correlationplot, survival plot도 마찬가지로 작성해둠. 

**HL-612 : 논문제출시 필요한 figure 모음 pdf 파일 제작하기 위한 SKILL**

(1) pdf안에 선별한 figure들의 left top에 a, b, c / A, B, C만 붙이기 (제목 x figure x ) → 논문형식
(2) figure size 스스로 조절해서(python_execute로 plot 재구성) 구조 맞추고 빈여백 없애기 
(3) 글씨와 plot 제목, label, color, legend 위치 등 가독성 있게 
(4) 채팅이 바뀌어도 통일감 있게 규정 

이 두가지 skill을 **registry.yaml**에도 추가함 
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

**`skills/data-visualization/omics-plotting/SKILL.md`
`skills/data-visualization/multipanel/SKILL.md`**

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e698250153e8`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.