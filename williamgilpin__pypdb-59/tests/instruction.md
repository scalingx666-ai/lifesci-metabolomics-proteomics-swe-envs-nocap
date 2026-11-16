# Issue

**Title:** Change 'is' to '==', RangeOperator now functioning

## Description

I deleted my earlier pull request as there were bugs with `RangeOperator`. From the [RCSB API changelog](https://search.rcsb.org/index.html#changelog):

> [2.0.0] - 2022-04-13
> Breaking Changes
> The range_closed operator is deprecated (RO-3091)
> The range operator no longer accepts an array of values as an input (RO-3091)

Hence the format required to perform `RangeOperator` searches is now a dict rather than a list as before. The demo wouldn't compile without error without this being updated and the pull request changes appears to work and the demo compiles. I will add further pull requests about verbosity later on. There were also

> \pypdb\pypdb.py:498: SyntaxWarning: "is" with a literal. Did you mean "=="?

warnings so the `is`'s were changed to `==`. There were also markdown warnings about space before/after headers `##` and the backtick language not specified so that was added. Added the verbosity changes, accidentally included a `___scratch.py` file I was using for tests as well as the demos so the scratch file was deleted.

The demos work fine, verbosity options are added and included in examples, minor other changes from warnings I got from VS Code.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `544ab339be40`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.