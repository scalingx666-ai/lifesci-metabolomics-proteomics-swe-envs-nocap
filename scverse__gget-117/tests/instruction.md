# Issue

**Title:** Add module to COSMIC database

## Description

Add module to COSMIC database #112
    """
    COSMIC, the Catalogue Of Somatic Mutations In Cancer, 
    is the world's largest and most comprehensive resource 
    for exploring the impact of somatic mutations in human cancer.
    Start using COSMIC by searching for a gene, cancer type, mutation, etc. below. 
    (https://cancer.sanger.ac.uk/cosmic/).

    Args:
    - name      by searching for a gene, cancer type, mutation, etc. below.
    - limit     Number of rows to return (default: 100).
    - types      'mutations' (default) or 'pubmed', 'genes','studies','samples'.
    - json          If True, returns results in json format instead of data frame. Default: False.
    - save          True/False whether to save the results in the local directory.
    - verbose        True/False whether to print progress information. Default True.

    Returns a data frame with the requested results.
    """

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `651855609354`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.