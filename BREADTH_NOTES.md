# Build notes - Metabolomics & Proteomics

Repo2RLEnv pr_diff (v0.9.6), Harbor-format output. Domain: metabolomics-proteomics.

## Funnel

| Stage | Count |
|---|---|
| Domain candidates (deduped) | 321 |
| After active+star+noise filter | 113 |
| Final target list (cap unlimited) | 113 |
| Repos with >=1 task | 9 |
| Repos with 0 tasks | 91 |
| Total tasks (unlimited (no per-repo cap)) | 422 |

## Generation

- Shared task bank: each repo generated once (pr_diff, limit=3,
  max_files_per_pr=15, min_loc_changed=2), 4-way concurrency,
  rate-limit-aware with .done checkpoint resume.
- Per-domain consolidation: rank by reward_calibration.loc_changed desc,
  keep ALL qualifying tasks (no per-repo cap). Zero-yield repos are NOT fabricated.
- Overlap with the 3 published cancer editions is allowed (user decision);
  domains are independent selections, not a partition of one repo set.

## Zero-yield repos (informational, 91)

- zhoushengisnoob/DeepClustering
- 52CV/CV-Surveys
- opencog/atomspace
- tseemann/prokka
- BioContainers/containers
- mahmoodlab/UNI
- bioMate-AI/biomate-bioconductor-kb
- YinLiLin/CMplot
- OpenMS/OpenMS
- MannLabs/CKG
- mikeroyal/Neuromorphic-Computing-Guide
- maduc7/Histopathology-Datasets
- mahmoodlab/CONCH
- Misterursw/web_wsi_viewer_with_all_format
- halsay/ASR-TTS-paper-daily
- imteekay/machine-learning-research
- prov-gigatime/GigaTIME
- giotto-suite/Giotto
- allenai/codescientist
- broadinstitute/ssGSEA2.0
- xiaolei-lab/rMVP
- tariqdaouda/pyGeno
- Nesvilab/FragPipe
- ProteoWizard/pwiz
- lazear/sage
- heise3/ExtremaRank
- tomtommyyuan/spmind
- refresh-bio/FAMSA
- graphia-app/graphia
- jiabowang/GAPIT
- celltype/celltype-agent
- bgruening/docker-galaxy
- sneumann/xcms
- zdk123/SpiecEasi
- allenai/discoveryworld
- pymzml/pymzML
- MannLabs/alphapept
- lgatto/TeachingMaterial
- soedinglab/plass
- bittremieuxlab/spectrum_utils
- lgatto/MSnbase
- OpenChrom/openchrom
- Nesvilab/MSFragger
- Nesvilab/philosopher
- MassBank/MassBank-data
- MannLabs/alphadia
- bigbio/proteomics-sample-metadata
- lgatto/RforProteomics
- MannLabs/alphatims
- MannLabs/alphamap
- MannLabs/alphapeptstats
- bigbio/quantms
- iomega/spec2vec
- rickhelmus/patRoon
- CompOmics/DeepLC
- cgohlke/molmass
- xieguigang/mzkit
- EMSL-Computing/CoreMS
- wheretrue/exon
- saezlab/cosmosR
- michaelwitting/RepoRT
- BioGenies/peptide-prediction-list
- CCMS-UCSD/GNPS_Workflows
- shuzhao-li-lab/asari
- fraenkel-lab/OmicsIntegrator2
- wenbostar/PDV
- CompOmics/ms2rescore
- BiRG/pyopls
- pnnl/isicle
- Sanofi-Public/MIPHEI-ViT
- MannLabs/directlfq
- griquelme/tidyms
- fgcz/rawrr
- metaspace2020/metaspace
- MannLabs/alphabase
- wilhelm-lab/koina
- ethanbass/chromConverter
- enveda/computational-metabolomics-review
- CompOmics/peptide-shaker
- AutoFlowResearch/SmartPeak
- BAMeScience/fiora
- mahmoodlab/3DCPath-datasets
- LiChenPU/NetID
- rusteomics/mzcore
- microbiomedata/nmdc-schema
- Functional-Metabolomics-Lab/FBMN-STATS
- CompOmics/ms2pip
- qcxms/QCxMS
- pmartR/pmartR
- nf-core/mhcquant
- the-omics-os/lobster

## Caveats

- Static validation only; real grading needs an LLM judge key + Docker.
- inline_dockerfile mode skips image build (no Docker daemon needed to publish).
- Provider secrets in upstream diffs were redacted before public release.
