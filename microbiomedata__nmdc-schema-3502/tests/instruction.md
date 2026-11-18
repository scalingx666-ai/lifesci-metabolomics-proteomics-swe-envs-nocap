# Issue

**Title:** Pin the three owlgen options whose defaults will change

## Description

## Why

Closes  linkml warns on every build that three OWL generator defaults will change from `false` to `true`. If that happens, about 1,900 of the roughly 3,100 restrictions in `nmdc.owl.ttl` would be dropped or merged without anyone choosing it. Setting all three to `false` in `gen-project-config.yaml` keeps today's output and stops the warnings. Adopting the new defaults later is then a deliberate one-line change.

linkml 1.12.0rc2 still defaults all three to `false` and still warns, so this isn't urgent for the 1.12 upgrade (), but nothing in rc2 removes the need for it.

`src/docs/owl-generation.md` said the config had no OWL settings; it now shows them and lists the three options.

## Validation

With linkml 1.11.1 on 2026-10-08, I ran `linkml generate project --include owl` with `main`'s config and with this branch's:

- The three "will change" warnings appear with `main`'s config and not with this branch's.
- The restriction counts are identical: 3,196 restrictions, 941 `owl:minCardinality 0`, 1,085 `owl:allValuesFrom`, 916 `owl:maxCardinality`. The Turtle isn't byte-stable even between two runs of the same config, so I compared counts rather than bytes; the issue records an isomorphism check with these settings on 2026-09-15.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `971c2eae3405`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.