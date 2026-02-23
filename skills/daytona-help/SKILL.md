---
name: daytona-help
description: Use when the user asks about Daytona installation, configuration, providers, runners/regions, or SDK usage and the answer should be grounded in the bundled Daytona reference docs shipped with this skill.
---

# Daytona Help

## Overview

Answer Daytona questions by searching the bundled Daytona reference docs that ship with this skill, quoting what you find, and citing exact file paths.

**Core principle:** If it is not in the bundled docs, say so. Do not fill gaps from memory or the public internet.

## Docs Scope

Only use the docs bundled with this skill:

- `daytona-docs/` (relative to this `SKILL.md`)

Common locations you may see in practice:

- Repo checkout: `skills/daytona-help/daytona-docs/`
- Global install: `~/.config/opencode/skills/daytona-help/daytona-docs/`

## Workflow

1. Identify 3-6 query keywords (product area + object + verb).
2. Search only within the docs scope (do a scoped search immediately; do not answer from memory).
3. Read the 1-3 most relevant files (and any file they reference).
4. Answer with:
   - The concrete steps / config / commands from the docs
   - Minimal paraphrase
   - Citations to the file paths you used

## Evidence Rule

For anything that is easy to get wrong (exact env var names, CLI flags, install commands, file locations):

- Quote the smallest relevant line(s) or code block from the doc, then cite the path.

## Quick Reference

Common search terms:

- Install: `install`, `brew`, `linux`, `docker`, `compose`, `getting-started`
- OSS deploy: `oss`, `deployment`, `docker-compose`, `dex`, `oidc`, `auth0`
- Providers: `provider`, `github`, `aws`, `s3`
- SDK config: `DAYTONA_API_URL`, `DAYTONA_API_KEY`, `.env`, `DaytonaConfig`
- Runners/regions: `runner`, `region`, `limits`, `network`, `vpn`

Citation format:

- Prefer inline path mentions like: "See `skills/daytona-help/daytona-docs/docs/oss-deployment.mdx`."

## Handling Missing Information

If you cannot find it after searching and reading:

"I could not find information about <topic> within the bundled Daytona docs (`daytona-docs/`)."

Then offer the nearest related doc you did find (with citations), or ask for a narrower target (e.g., "Dex GitHub connector" vs "linking GitHub account").

## Common Mistakes

- Answering from memory under time pressure (especially install steps and env vars).
- Searching the whole repo and picking up unrelated references.
- Citing a file you did not actually read.
- Reading only `index.mdx` and missing deep docs under `docs/`, `guides/`, or SDK subfolders.

## Red Flags - Stop And Search

- "I already know this" / "I can answer quickly"
- You are about to write an exact command or env var name without quoting it from docs
- You cited a file path but cannot point to the line/block you used

## Rationalizations To Reject

| Excuse | Reality |
| --- | --- |
| "Time pressure: I will avoid file reads." | Install/config answers drift quickly; do a scoped search anyway. |
| "I remember the env vars; I will just list them." | One wrong variable breaks setups; quote from docs. |
| "I can cite a plausible file path without opening it." | A citation is only valid if you read and extracted the relevant lines. |
