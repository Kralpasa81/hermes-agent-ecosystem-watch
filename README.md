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
Latest daily note: [2026-11-08](daily/2026-11-08.md)

- **Latest Hermes signal:** [Arete-27B](https://nousresearch.com/arete) (Nov 6) — Nous Research post-trained Alibaba's Qwen3.8-27B to reinforce Western values, cutting propaganda-framed answers 22% → 1% and raising the fact score 2.32 → 2.98 with no Hermes Bench or Terminal-Bench regression; weights, eval (`Propaganda_Eval`), and training data are all open. Hermes Agent v0.23.0 ("The Hearth Release", Nov 5) remains the latest stable tag.
- **Latest ecosystem signal:** [DeepSeek open-sources "Super-agent"](https://github.com/deepseek-ai/dsh-superagent-prototype) (announced Oct 31, reported Nov 1) — an MIT-licensed prototype autonomous coding agent that watches developer group chats and fixes bugs proactively, aimed at Claude Code. Perplexity also launched always-on [Teammates](https://www.perplexity.ai/hub/blog/teammates-are-agents-for-complex-ongoing-work) (Nov 6), and OpenAI released GPT-6 Cyber (Nov 5).
- **Tool watchlist:** [indexes/tool-watchlist.md](indexes/tool-watchlist.md)
- **Starred highlights:** [highlights/starred-highlights.md](highlights/starred-highlights.md)
- **Last update:** 2026-11-08

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
