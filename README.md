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
Latest daily note: [2026-11-10](daily/2026-11-10.md)

- **Latest Hermes signal:** [v0.23.1](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.1) (patch, Nov 9/10) — fixes a silent plugin-install regression (the live plugin catalog exceeded the 2 MiB client cap, so installs fell back to the shipped catalog; cap raised to 16 MiB) and exposes a broader plugin API (session-scoped env, plugin JSON-RPC, `llm.oneshot`, `on_session_open`/`post_curator_run` hooks) ahead of the v0.24.0 curated notes.
- **Latest ecosystem signal:** the broader ecosystem was quiet on Nov 10 — nothing strong from Codex, Claude Code, Copilot, or MCP. Only a minor Anthropic [usage-policy update](https://www.anthropic.com/news/2026-usage-policy-update) (effective Nov 12).
- **Tool watchlist:** [indexes/tool-watchlist.md](indexes/tool-watchlist.md)
- **Starred highlights:** [highlights/starred-highlights.md](highlights/starred-highlights.md)
- **Last update:** 2026-11-10

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
