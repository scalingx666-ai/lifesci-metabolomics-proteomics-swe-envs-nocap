# Issue

**Title:** refactor: decouple skills from biomni package

## Description

## Summary

- Replace all 7 `from biomni.tool.literature import ...` blocks in `skills/scientific-writing/scientific-literature-search/SKILL.md` with standard open-source equivalents (`Bio.Entrez`, `arxiv`, `scholarly`, `duckduckgo-search`, `trafilatura`, `pypdf`, Crossref API) and the Anthropic SDK `web_search_20250305` server-side tool. Code blocks are now runnable without the third-party `biomni` package.
- Update prose mentions of the biomni-named functions accordingly (Tier 1 / Tier 2 / Tier 3 description lines).
- Append a Biomni attribution block to `LICENSE` following the existing K-Dense-AI reference pattern (Apache-2.0 for the codebase + CC BY 4.0 for the adapted sgRNA Design Guide content).

The Biomni attribution line in `skills/molecular-biology/sgrna-design-guide/SKILL.md` is intentionally kept (CC BY 4.0 acknowledgment).

## Function → Replacement Mapping

| Biomni function | Replacement |
|---|---|
| `query_pubmed` | `Bio.Entrez` (Biopython) |
| `query_arxiv` | `arxiv` package |
| `query_scholar` | `scholarly` package |
| `search_google` | `duckduckgo-search` |
| `advanced_web_search_claude` | Anthropic SDK with `web_search_20250305` tool |
| `extract_url_content` | `trafilatura` |
| `extract_pdf_content` | `requests` + `pypdf` |
| `fetch_supplementary_info_from_doi` | `requests` + Crossref API |

## Test plan

- [x] `rg -ni "biomni" skills/` — only the kept attribution line in `sgrna-design-guide/SKILL.md` remains
- [x] `rg -n "from\s+(biomni\.)?tool[\.\s]" skills/` — no `biomni.tool` / `tool.*` imports remain
- [x] `rg -n "Biomni" LICENSE` — attribution block present
- [x] `pixi run test` — 4093 passed

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1ce3fc5b261f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.