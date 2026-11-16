# Issue

**Title:** Fix repair adduct and parent mass not repairing correct parent mass

## Description

Before the repair_adduct_and_parent_mass_from_smiles will always set parent mass to match the smiles. Even if the parent mass is already close to the smiles mass or if no adduct can be found matching it. This results in a processing report with very high repair numbers, while in reality most parent matches already closely match the smiles mass. This PR solves that. 

Somewhat related note:
Now I am looking into this, I am reconsidering the entire filter. It would be more modular to split it into two filters. 
repair_parent_mass_from_smiles: this sets the parent mass to match the smiles if the difference is larger than 0.1 Da.
repair_adduct_based_on_parent_mass: this filter already exists and repairs based on the parent mass. 

The very small difference with this combined filter we have here would be that repair_parent_mass_from_smiles will also repair the parent mass if it cannot be matched to the precursor mz by any available adduct, while the current filter won't do that.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `822892a57737`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.