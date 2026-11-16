# Issue

**Title:** Make OpenRouter base URL configurable via OPENROUTER_BASE_URL

## Description

## What

The OpenRouter provider in `server/src/agent/models.ts` hardcodes `https://openrouter.ai/api/v1`. Since it's just an OpenAI-compatible endpoint, this makes the base URL overridable via `OPENROUTER_BASE_URL` (defaulting to OpenRouter), mirroring how `OLLAMA_BASE_URL` is already env-driven one section away.

That lets users point the existing OpenRouter provider at any OpenAI-compatible gateway while keeping `OPENROUTER_API_KEY` for that gateway's key — for example [Requesty](https://requesty.ai) (`OPENROUTER_BASE_URL=https://router.requesty.ai/v1`), which uses the same `vendor/model` ids and Bearer auth.

- `server/src/agent/models.ts`: `OPENROUTER_BASE_URL = process.env.OPENROUTER_BASE_URL ?? "https://openrouter.ai/api/v1"`
- `.env.example`: document the override with a Requesty example

No new provider, no behavior change when the env var is unset.

## Tested

- `cd server && npm run typecheck` — passes
- With `OPENROUTER_BASE_URL=https://router.requesty.ai/v1`, verified the resolution logic produces the Requesty endpoint and a live chat completion (`openai/gpt-4o-mini`) returns HTTP 200 correctly.

Note: I couldn't get a clean `npm test` (vitest) run locally — `rolldown`'s native binding fails to load on my machine (a `MODULE_NOT_FOUND` from the install, unrelated to this one-line change). Typecheck is clean and the change is config-only.

## Disclosure

I work at Requesty. This is a small config-flexibility change (one env var + a docs example). Happy to drop the Requesty example, reword, or close if it's not a fit.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `74832a84e830`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.