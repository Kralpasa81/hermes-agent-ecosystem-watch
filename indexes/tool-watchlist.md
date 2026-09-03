# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, changelog-worthy fixes, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: **v0.21.0 "The Pantheon Release" (v2026.8.31)** — Bot Mode (multi-agent group chats built into desktop), `hermes peer` bot-to-bot DMs, cron memory + `continuity=true`, live subagent steering in `delegate_task`, unified MCP command center with `hermes://` deep links, browser agent (Hermes now drives the in-app browser), six new providers (Meta Muse Spark, CommandCode, Tencent TokenPlan, Nebius, Ramp Router, Actual Computer), new model catalog entries, `model_overrides` for custom context/pricing patches. ~5,800 commits, ~2,475 PRs, 760+ contributors since v0.20.0.
- Sources: https://github.com/NousResearch/hermes-agent/releases/tag/v2026.8.31

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows  
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: **Sep 3, 2026** — **MAI-Code-1.1-Flash** (Microsoft AI model with native vision and improved coding) rolling out across Copilot clients; replaces MAI-Code-1-Flash on Sep 10. Copilot CLI now supports **air-gapped GHES environments**. **Claude Fable 5.1** (Anthropic Mythos-class, long-horizon agent coding) GA across all Copilot clients (Sep 1); **Copilot code review can now approve pull requests** (public preview; off by default, configurable). VS Code Aug 2026 (v1.132–v1.135): Agent Host cross-session continuity, side-by-side chats, `/btw` side-chat, Agent Plugins 1.0 standard, experimental `/rubber-duck`, browser element annotation, multi-language dictation.
- Sources: https://github.blog/changelog/ | https://www.neowin.net/news/microsoft-releases-mai-code-11-flash-coding-model-to-better-compete-with-chinese-models/ | https://x.com/GHchangelog

### OpenAI API / Codex
- Area: core models, developer platform, agent tooling
- Why it matters: critical for new capabilities, pricing, and infrastructure shifts that impact agent design and cost management
- Current watch note: **Sep 3, 2026** — **DevDay 2026 confirmed for Sep 29** in San Francisco (global "DevDay Exchange" events planned). **GPT-5.6 Sol price reduction** (Aug 21) of 20%+ for input ($5 → $4 per million tokens) and 33% for output ($30 → $20 per million tokens) extended through Nov 21, 2026. This applies to API, Codex credits, and ChatGPT Work.  
- Sources: https://devday.openai.com/ | https://community.openai.com/t/20-price-reduction-for-gpt-5-6-sol-api-codex-credits-and-chatgpt-work/1391726

### FastFS-MCP
- Area: filesystem access server for AI agents
- Why it matters: provides AI assistants with direct, authenticated access to local filesystems and Git repositories
- Current watch note: **v2.3 released** (2026-08-24) with improved Git operations support and enhanced performance

### Argus
- Area: MCP server exploration and testing
- Why it matters: Postman-like GUI for exploring and testing MCP servers
- Current watch note: **v0.9 reached beta** (2026-08-24) with improved UI and expanded feature set

### NeuralCoreTech Benchmarks
- Area: AI coding agent performance analysis
- Why it matters: tracks relative performance and capabilities of leading AI coding agents
- Current watch note: **August 2026 comprehensive benchmark** released, showing notable improvements in accuracy, speed, and multi-language support across major platforms
- Sources: https://af.net/realtime/best-ai-coding-agents-august-2026-benchmarks-and-guide/

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.