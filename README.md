# Hermes Agent Ecosystem Watch

A curated GitHub watch repo for **Hermes Agent**, Hermes-adjacent tooling, and the wider **AI agent / coding assistant / MCP / automation** ecosystem.

## What this repo tracks
- **Hermes-first signals**: releases, docs, changelog-worthy fixes, gateway/tool/provider/MCP changes
- **Hermes-adjacent developments**: Nous Research news or ecosystem moves that can affect real Hermes usage
- **Broader agent ecosystem**: Codex, Claude Code, Copilot, MCP infrastructure, coding agents, agent tooling
- **Practical watch items**: not hype alone, but changes that may affect real workflows

## Repository map
- `daily/` — daily dated notes
- `indexes/daily-index.md` — chronological archive index
- `indexes/tool-watchlist.md` — tracked tools, programs, and platforms worth watching
- `highlights/starred-highlights.md` — highest-signal developments only

## Current snapshot
Latest daily note: [2026-11-27](daily/2026-11-27.md)

- **Latest Hermes signal:** **Hermes Agent v0.23.4** (Nov 24) — latest stable, rolling ~229 PRs since v0.23.3 into the CLI/installers, Microsoft Store, Docker, and Hermes Cloud (headline: Gemini 4 Hydrogen / Neon / Carbon on Nous Portal, OpenRouter, and Vertex; `hermes gateway migrate --backends`; `hermes plugins config`). Today's canary (`canary.20261127T064803Z-v0.23.4`) rolls ~641 commits: mostly plugin-catalog growth, plus gateway stop/restart reliability hardening, a new `turn_origin` plugin API, Google Gemini/Solstice consolidation into a bundled `google` plugin, and macOS Desktop move-to-Applications — canary-only, not yet stable. ([release](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.4), [canary](https://github.com/NousResearch/hermes-agent/releases/tag/canary.20261127T064803Z-v0.23.4))
- **Latest ecosystem signal:** **Claude Code engineer Thariq Shihipar joins OpenAI** (Nov 25) — one of Anthropic's most visible Claude Code engineers (skills system, context engineering, `AskUserQuestion`, Agent SDK) announced he has joined OpenAI, following Cat Wu's earlier move to the Codex team. A talent/competitive signal, not a product change. ([ChipDispatch](https://chipdispatch.com/articles/thariq-shihipar-leaves-anthropics-claude-code-for-openai))
- **Tool watchlist:** [indexes/tool-watchlist.md](indexes/tool-watchlist.md)
- **Starred highlights:** [highlights/starred-highlights.md](highlights/starred-highlights.md)
- **Last update:** 2026-11-27

## How updates are written
1. Hermes Agent and Hermes-adjacent changes are checked first.
2. Then broader AI agent ecosystem developments are reviewed.  
3. Only meaningful updates are promoted into highlights or the tool watchlist.
4. A daily file is still committed even on quiet days, so the history stays continuous.

## Signal rules
- **High signal** = directly changes workflows, capabilities, packaging, reliability, limits, or integration options.
- **Medium signal** = interesting platform/tool movement worth tracking.
- **Low signal** = ignored unless it clearly matters for practical use.

## Why this repo exists
This repo is a clean public record of useful Hermes and AI agent ecosystem changes. Instead of losing important updates in chats, release feeds, and scattered bookmarks, the signal is collected here in a searchable structure.
