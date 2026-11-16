# Issue

**Title:** Get rid of `SearchService` and `QueryNode` concepts in Public Search API

## Description

## Changes

Got rid of `SearchService` and `QueryNode` objects in the public API. They were unnecessary and added bloat, when all necessary information can be inferred just using the search operator.

## Example

Whereas before we might have:
```
from pypdb.clients.search.search_client import perform_search
from pypdb.clients.search.search_client import SearchService, ReturnType
from pypdb.clients.search.operators import text_operators

search_service = SearchService.TEXT
search_operator = text_operators.DefaultOperator(value="ribosome")
results = perform_search(search_service, search_operator,  ReturnType.POLYMER_ENTITY)
```

We can now have:
```
from pypdb.clients.search.search_client import perform_search
from pypdb.clients.search.search_client import ReturnType
from pypdb.clients.search.operators import text_operators

results = perform_search(text_operators.DefaultOperator(value="ribosome"), ReturnType.POLYMER_ENTITY)
```

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `786c204734e2`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.