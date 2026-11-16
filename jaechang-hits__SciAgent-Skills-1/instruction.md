# Issue

**Title:** Add 11 more skills

## Description

## Summary                                                                                           
                                                                                                       
  - Add 11 new guide-type skills across 7 categories covering common pitfalls and best practices in    
  bioinformatics, biostatistics, and life science analysis                                             
  - All skills follow the standard Guide template (Key Concepts, Decision Framework, Best Practices,   
  Common Pitfalls, Workflow, Further Reading, Related Skills)                                          
  - Update README to reflect new skill count (74 -> 187) and add Molecular Biology category
                                                                                                       
  ## New Skills                                                                                        
                                                                                                       
  | Skill | Category | Lines |                                                                         
  |-------|----------|-------|                              
  | nan-safe-correlation | biostatistics | 249 |                                                       
  | degenerate-input-filtering | biostatistics | 265 |                                                 
  | single-cell-annotation | cell-biology | 250 |                                                      
  | busco-status-interpretation | genomics-bioinformatics | 291 |                                      
  | depmap-crispr-essentiality | genomics-bioinformatics | 253 |                                       
  | vcf-variant-filtering | genomics-bioinformatics | 254 |                                            
  | western-blot-quantification | lab-automation | 301 |                                               
  | scientific-literature-search | scientific-writing | 420 |                                          
  | sar-analysis | structural-biology-drug-discovery | 293 |                                           
  | kegg-pathway-analysis | systems-biology-multiomics | 303 |                                         
  | omics-analysis-guide | systems-biology-multiomics | 350 |                                          
                                                                                                             

  ## Test plan                                                                                         
  
  - [x] `pixi run validate` passes (registry integrity)                                                
  - [x] `pixi run test` passes (frontmatter, required sections, code block counts)
  - [ ] Spot-check 2-3 skills for section ordering and content completeness

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `cbc4117a17f5`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.