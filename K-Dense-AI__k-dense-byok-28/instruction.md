# Issue

**Title:** fix(server): honor HTTP_PROXY/HTTPS_PROXY for outbound requests

## Description

Fixes the gap behind #26.

## Problem

Node's built-in `fetch` ignores `HTTP_PROXY` / `HTTPS_PROXY` / `NO_PROXY` unless the process is started with `NODE_USE_ENV_PROXY`, which only exists on Node ≥ 24 — `start.mjs` supports ≥ 22.19.

Pi's own CLI handles this: `configureHttpDispatcher()` installs undici's `EnvHttpProxyAgent` at startup (`main.js:378`, `rpc-entry.js:8`). So the child `pi` processes that run **subagents already honored a proxy**. But the lead agent embeds the SDK rather than spawning the CLI, and `configureHttpDispatcher` isn't in pi-coding-agent's public exports (`.` and `./rpc-entry` only) — so nothing installed it in-process.

On a proxied network that split is invisible until it isn't: subagents work, while the lead agent, Fusion, and speech transcription dial providers directly and get whatever the network's filtering appliance answers with. In #26 that's a `403 "Access denied by security policy."` — a body shaped `{"error": "<string>"}`, which is not OpenRouter's error schema, and which the reporter also got from an unrelated gateway.

## Change

`server/src/http-proxy.ts` installs the same dispatcher Pi does, called first in the `index.ts` boot block. **It is a no-op unless a proxy variable is set**, so anyone on a direct connection keeps Node's own dispatcher untouched.

Two details are carried over from Pi's implementation deliberately:

- the swallowed dispatcher `"error"` listener — undici emits an internal Client error while tearing down a fetch body mid-stream, which happens on every stopped run;
- `undici.install()`, which keeps `fetch` and the dispatcher on one undici copy. Node bundles a different copy, and mismatching them breaks response decompression on Node 26.0.

Proxy credentials are redacted from the boot log line. `undici` is added as a direct dependency pinned to `8.5.0`, matching pi-coding-agent's pin so the tree dedupes to one copy.

## Tests

`server/test/http-proxy.test.ts` (9 tests) drives the real mechanism rather than the config parsing: a local **CONNECT** proxy tunnels to a local origin server, and the request target is an unresolvable `.invalid` host — so a 200 is only reachable *through* the proxy, and the `NO_PROXY` case is confirmed by the DNS failure. Writing it surfaced something worth knowing: undici tunnels with CONNECT even for `http://` targets, so a plain request-handler proxy never sees the traffic.

Full backend suite passes (419 passed, 1 skipped); typecheck clean.

## Caveat

This is a real bug on its own merits — the lead/subagent split is wrong regardless. Whether it is *the* cause of #26 is unconfirmed: the reporter hasn't yet said they use a proxy, and I've asked them for `env | grep -i proxy` plus a direct `curl` to discriminate a provider 403 from a middlebox one.

## Docs

`.env.example` gains the three variables, and `docs/installation.md` gains a troubleshooting entry for "works in other apps, 403 in Kady" with the `curl` one-liner.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `30d0815aeda4`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.