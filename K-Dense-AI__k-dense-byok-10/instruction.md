# Issue

**Title:** feat: add Exa AI-powered search tool

## Description

## Summary

- Registers the Exa hosted MCP server as a new optional built-in, gated on `EXA_API_KEY` — same shape as the existing `PARALLEL_API_KEY`-gated Parallel registration. Neither key is required; users set whichever provider(s) they want.
- Minimal footprint: the change is additive. No existing behavior changes when `EXA_API_KEY` is unset.
- Main-agent instructions are updated so the orchestrator knows both Parallel Search MCP and Exa Search MCP are valid open-web search surfaces, and so the `exa-search` skill name gets passed through alongside `parallel-web` when users reference it.

## How it works

When a user puts an Exa API key in `.env`, BYOK connects to `https://mcp.exa.ai/mcp` over streamable HTTP. Auth uses the `x-api-key` header per Exa's MCP spec. An `x-exa-integration: k-dense-byok` header is also sent so Exa can attribute MCP usage to this integration.

```python
# kady_agent/mcps.py
if os.getenv("EXA_API_KEY"):
    exa_search_mcp = ResilientMcpToolset(
        McpToolset(
            connection_params=StreamableHTTPConnectionParams(
                url="https://mcp.exa.ai/mcp",
                headers={
                    "x-api-key": os.getenv("EXA_API_KEY"),
                    "x-exa-integration": "k-dense-byok",
                },
                timeout=600,
            ),
        ),
        label="Exa Search MCP",
    )
    all_mcps.append(exa_search_mcp)
```

## Files changed

- `kady_agent/mcps.py` — register Exa Search MCP alongside Parallel, conditional on `EXA_API_KEY`
- `kady_agent/manifest.py` — include `exa-search` in the per-turn MCP server snapshot so provenance / replay captures it
- `kady_agent/agent.py` — expose `EXA_API_KEY` module constant (parallels `PARALLEL_API_KEY`)
- `kady_agent/env.example` — add `EXA_API_KEY=` under **Highly Recommended**
- `kady_agent/instructions/main_agent.md` — update Tool Preferences and Proactive Skill Matching sections so the orchestrator handles both providers; references `exa-search` as a sibling skill to `parallel-web`
- `README.md` — add Exa row to the "What you'll need" table, update the web-search feature bullet, and mention Exa in the env-keys walkthrough
- `docs/custom-mcp-servers.md` — update the built-in-defaults descriptions to list both providers
- `tests/test_manifest.py` — 4 new tests covering `_mcp_servers_snapshot` behavior across the neither / only-parallel / only-exa / both combinations

## Design notes

- **Additive, not a replacement.** Parallel stays exactly as it was. Users who have only `PARALLEL_API_KEY` get unchanged behavior.
- **Integration attribution.** The `x-exa-integration: k-dense-byok` header lets Exa see how much MCP traffic is coming from BYOK, without changing what the user sees in their dashboard.
- **Manifest/replay stays correct.** Because `_mcp_servers_snapshot` now includes `exa-search` when enabled, the per-turn manifest pins the full set of built-in MCPs active at the time of the turn, matching the existing guarantee for Parallel.

## Test plan

- [x] `uv run pytest` → **190 passed, 0 failed** on this branch
- [x] Targeted run: `uv run pytest tests/test_mcps.py tests/test_manifest.py` → 20 passed (4 new)
- [x] Syntax checked all modified files
- [ ] Manual smoke test: set `EXA_API_KEY=…`, start the app, confirm `web_search` / `get_contents` tools from the Exa MCP show up in the expert and return results
- [ ] Manual smoke test: set both `PARALLEL_API_KEY` and `EXA_API_KEY`, confirm both MCPs load side-by-side

## Draft status

Opening as a **draft** to leave room for review and iteration before it lands. Happy to adjust scope, naming, or wording (e.g. the main_agent.md phrasing on default provider selection) based on maintainer preferences.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `13ba4ad833f8`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.