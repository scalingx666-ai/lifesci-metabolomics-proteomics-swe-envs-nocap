# Issue

**Title:** Require a term on isotopolog and add hetero_isotopolog for labeled inputs with no PubChem compound

## Description

Implements what we decided on 2026-09-15 (): `isotopolog` takes a `ControlledIdentifiedTermValue`, and a labeled input with no PubChem compound identifier goes in a new `hetero_isotopolog` slot with a string range.

Why two slots rather than a term-less `ControlledTermValue`: a value with only `has_raw_value` cannot be told apart from a value nobody identified, and it treats an organism such as T4 phages as a molecular entity. `hetero_isotopolog` is the column the MISIP supplementary tables use for these cases (Simpson et al. 2024, https://doi.org/10.1093/gigascience/giae071). It is not in MIxS 7.0.1;  asks for it upstream, and the slot carries that link in `see_also` so it can become an import later.

Two rules on `IsotopeMetadata` make the pair exclusive: if `isotopolog` is absent then `hetero_isotopolog` is required, and if `isotopolog` is present then `hetero_isotopolog` must be absent. They compile to `if`/`then` in the JSON Schema the same way the existing rules on `DataObject`, `WorkflowExecution` and `MassSpectrometry` do. Because the rules sit on the entry class, a process with one labeled input and a process with several are validated the same way.

The PubChem-only pattern on `term.id` is unchanged. Which namespaces `isotopolog` accepts is the open thread with @sierra-moxon and is not decided here.

Also in this PR: the provisional markers from  are removed, `IsotopeLabelingProcess-isotopolog-multiple.yaml` had `type` twice in one entry, and the CID 0 counter-example was failing for two reasons because its term lacked `type`.

Validation: `make test` passes locally (95 tests) and `linkml-lint` reports no problems. Against the generated JSON Schema, each of the six counter-examples produces exactly one validation error and each of the six valid SIP examples produces none. Generated artifacts under `nmdc_schema/` are not committed, per the repo convention.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `5eb1afce2d81`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.