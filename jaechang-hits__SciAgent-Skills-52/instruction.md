# Issue

**Title:** [HL1236] annotation 스킬 수정 (허브와 툴 구분)

## Description

## Summary
annotation 스킬을 **허브 스킬(`cell-type-annotation`)**과 **툴 스킬(celltypist / popv / scanpy)**로 역할을 나눔.
- 허브: 어떤 방식으로 annotation할지(Route A~D) 고르고, 수동 마커 방식(Route A) 코드를 직접 가짐
- 툴: 각 도구의 실행 코드만 담당. 공통 인터뷰 질문은 허브와 문구를 통일해 한 번만 묻도록 함

---
## 변경된부분
### `single-cell-annotation-guide` → `cell-type-annotation/SKILL.md` (이름 변경 + 재작성)
guide라는 말이 포함되고 description이 너무 포괄적이어서 annotation해달라고할때 읽지를 않는 현상이 있기 때문

- **Line 2** : `name`을 `single-cell-annotation-guide` → `cell-type-annotation`으로 변경
- **Line 3** : `description`을 "read before any annotation skills"로 시작하도록 변경해 annotation 스킬 중 가장 먼저 읽히게 함. 툴별 코드 위치(celltypist/popv/scvi) 안내 추가
- **Line 9-25** : `## Routes at a Glance` 섹션 신설
  - Route A(마커) / B(CellTypist) / C(popV·scvi) / D(비교)
  - "In default sandbox" 열 추가: Route C는 미설치라 먼저 설치 필요
  - Line 20 : 공간전사체(Xenium/MERFISH/CosMx, Visium)는 대상이 아니므로 각 전용 스킬로 안내
- **Line 35-58** : Key Concepts를 긴 문단 5개에서 짧은 절 4개로 축약
  - Clusters Are Not Cell Types / Marker Evidence / Reference Match and Confidence / Label Vocabulary
- **Line 75-80** : D2 `annotationStrategy` 질문을 A/B/C/D 중 하나를 고르는 형태로 변경, `depends_on` 제거
- **Line 82-104** : D3 `referenceAtlas`, D4 `markerPanel`, D5 `markerValidation`
  - `required` → `optional`
  - 사용자에게 묻지 않고 에이전트가 제안하는 기본값 추가
- **Line 113-118** : D7 `unresolvedClusters`를 `required` → `optional`로 변경
- **Line 120-127** : D8 `doubletHandling`
  - `required` → `optional_conditional`
  - doublet 플래그가 없으면 Scrublet 실행, 상위 QC에 플래그가 있으면 skip
- **Line 129-141** : 인터뷰 설명문 재작성
  - D1, D2, D6은 한 라운드에 같이 질문
  - D3, D4는 질문하지 않고 제안
  - 다른 스킬과 겹치는 질문은 한 번만 묻기
- **Line 143-180** : Decision Framework의 트리와 표를 Tier 표기에서 Route 표기로 변경
- **Line 177-178** : Rare cell types, Fetal 행을 Route D(마커 + transfer 비교)로 재분류
- **Line 245-295** : Route A 실행 코드 추가
  - Line 257 : 예시 PBMC 마커 패널. 데이터에 있는 마커가 2개 이상인 타입만 사용
  - `sc.tl.score_genes`로 클러스터별 점수를 내고 가장 높은 타입을 제안
  - Line 283 : 점수가 0 이하이거나 1·2위 차이가 0.1 미만이면 `"Unresolved"` (D7 연결)
  - dotplot을 보고 매핑을 수정한 뒤 `manual_cell_type`에 저장
- **Line 297, 305** : Route B/C의 코드는 각 툴 스킬(`celltypist-cell-annotation`, `popv-cell-annotation`)에 있다고 명시
- **Line 312-335** : Route D 비교 코드 추가
  - Line 322 : `cluster_summary`로 클러스터별 수동 라벨, 자동 라벨 최빈값, 그 비율 비교
  - Line 334 : 자동 라벨 기준 dotplot으로 해당 타입 마커가 실제로 발현되는지 검증 (D5)

---

### `celltypist-cell-annotation/SKILL.md`

- **Line 3** : `description` 끝에 "read cell-type-annotation first" 추가
- **Line 27-30** : Prerequisites의 `pip install` 블록 삭제, "pre-installed in the runtime"으로 명시. 선택한 모델만 다운로드하라는 항목 추가
- **Line 38-81** : D1~D6 질문 문구를 허브와 동일하게 통일
  - D1 `default` → `null`
  - D3 `model`, D4 `markerValidation`, D5 `markerPanel`은 `required` → `optional`
  - D5 param 이름 변경: `validationMarkerPanel` → `markerPanel`
- **Line 83-113** : D7~D10 질문 문구 간결화 (의미는 그대로)
- **Line 116** : 설명문을 "D1-D6은 허브와 문구가 같으니 한 번만 묻는다"로 축약
- **Line 133** : Quick Start에 `download_models(model="Immune_All_Low.pkl")` 추가해 필요한 모델만 다운로드
- **Line 151-160** : Step 1
  - 전체 모델 다운로드(약 2GB) 삭제, 버전 확인으로 대체
  - `models_description()`은 인덱스만 읽는다는 주석 추가
- **Line 197-202** : Step 3
  - 조직명으로 모델 카탈로그를 검색하는 예시(breast)
  - 선택한 모델만 다운로드
- **Line 205** : 종양 데이터 주의사항 추가
  - 정상 조직 모델을 쓰면 악성 세포도 정상 상피로 라벨링됨
  - 이런 클러스터는 "epithelial (malignancy not resolved)"로 보고
- **Line 212-217** : 모델 표의 셀 타입 수 정정, `Cells_Adult_Breast.pkl` 행 추가
  - `Immune_All_High` 30 → 32
  - `Pan_Fetal_Human` 139 → 138
  - `Developing_Human_Brain` 51 → 129
  - `Human_Colorectal_Cancer` 62 → 36
- **Line 376** : 커스텀 모델을 `"./custom_tissue_model.pkl"` 경로로 지정 (이름만 주면 전체 모델 다운로드가 일어남)
- **Line 391** : 여러 모델 비교 레시피에서 후보 모델만 먼저 다운로드
- **Line 455-456** : Troubleshooting
  - "Model not found" 해결책을 모델 단위 다운로드로 변경
  - "첫 `annotate()`가 모든 모델을 다운로드함" 행 추가

---

### `popv-cell-annotation/SKILL.md`

- **Line 3** : `description` 끝에 "read cell-type-annotation first" 안내 추가
- **Line 128** : 참조를 `single-cell-annotation-guide` → `cell-type-annotation`으로 변경

---

### `scanpy-scrna-seq/SKILL.md`

- **Line 87-92** : D6b `annotationStrategy`를 허브와 같은 A~D 질문으로 변경, 기본값 "manual" → `null`
- **Line 94-100** : D6c `markerPanel`
  - `required` → `optional`, `depends_on` 제거
  - 기본값: 에이전트가 만든 패널
  - `skip_if`: "label transfer only"
- **Line 127-128** : "D6b, D6c는 `cell-type-annotation`의 D2, D4와 같은 질문이니 한 번만 묻는다" 추가

---

### `registry.yaml`

- **Line 1220-1225** : 엔트리의 `name`, `path`, `description`을 `cell-type-annotation`으로 변경

올리기 전에 고치면 좋을 오타 2개:
- cell-type-annotation/SKILL.md:3와 registry.yaml의 같은 description에 있는 "validate one against other"는 "against the other"로 고쳐야 합니다.
- celltypist-cell-annotation/SKILL.md:30의 "Loading a model by name, so download the chosen one first"는 문장이 끊겨 있습니다. 예를 들어 "Loading a model by

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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `82c862c094a4`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.