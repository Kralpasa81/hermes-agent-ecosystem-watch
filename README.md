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
Latest daily note: [2026-11-02](daily/2026-11-02.md)

- **Latest Hermes signal:** [approval-prompt display hardening](https://github.com/NousResearch/hermes-agent/commit/3f5612cde62556d0b73558230f4acb0e98279d83) — mainline commits now surface hidden/zero-width, bidi-override, and ANSI-escape characters before a human approves a command, so the approved command is the one that actually runs.
- **Latest ecosystem signal:** [GitHub Copilot Fusion GA](https://github.blog/news-insights/company-news/github-universe-2026-evolving-every-layer-of-the-stack/) — Copilot's multi-model orchestration layer reached general availability at Universe 2026, alongside the new Copilot app and Copilot projects.
- **Tool watchlist:** [indexes/tool-watchlist.md](indexes/tool-watchlist.md)
- **Starred highlights:** [highlights/starred-highlights.md](highlights/starred-highlights.md)
- **Last update:** 2026-11-02

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