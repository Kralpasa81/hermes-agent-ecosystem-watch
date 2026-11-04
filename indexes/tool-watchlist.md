# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, changelog-worthy fixes, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: **Nov 3, 2026** — **v0.22.7** (Nov 3) and **v0.22.6** (Nov 2) shipped back-to-back, rolling ~174 + ~776 PRs since v0.22.5. Shipped features include the webapp served from the gateway listener (`hermes webapp`, a Desktop Web Access pane, Desktop plugins in a browser tab), `/model reset`, per-skill locks against autonomous writes, `compression.prepare_ahead`, `hermes cron cancel` + a per-job missed-run policy + a Stop button, `/delegation` persistence, `hermes migrate`, opt-in OS-keychain vault-key storage, `requires_hermes` enforcement, agent-picked ElevenLabs voices, a `pre_llm_call` hook, Desktop group-chat controls, Telegram video notes, Slack emoji reactions, resumable downloads, Desktop lead routing + cron-to-group-chat, `$$TeX$$`/mermaid via Pele, and a Daybreak switch for catalog-listed ChatGPT subscription models. Full curated notes ship with v0.23.0. ([v0.22.7](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.7), [v0.22.6](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.6)) **Nov 1, 2026** — mainline approval-prompt display hardening: hidden/zero-width and bidi-override characters, ANSI/OSC escapes, carriage returns, and runs of padding are now rendered as explicit `\uXXXX`/`\xNN` escapes at every approval surface, and the TUI pages long approval commands so every line is reviewable. Display-only; the executed command and allowlist keys are unchanged. **Oct 28, 2026** — mainline web-app hardening now treats a corrupt desktop-half timestamp as stale metadata instead of an outage, avoiding a false-offline state. This is a targeted reliability fix and has not yet shipped in a stable release. **Oct 26** — a merged refactor moves GitHub Copilot (`copilot` and `copilot-acp`) out of core and into the Nous-maintained `github-copilot` Labs plugin. Generic provider-profile hooks remain in core; profiles configured for Copilot are intended to auto-install the plugin, while `gh`-only users are explicitly directed to `hermes auth add copilot`. **Oct 25** — a fix restored per-job MCP least privilege: naming one server in a cron allowlist no longer broadens access to every enabled MCP server. Latest stable is **v0.22.7** (Nov 3). ([Approval hardening](https://github.com/NousResearch/hermes-agent/commit/3f5612cde62556d0b73558230f4acb0e98279d83), [Web-app fix](https://github.com/NousResearch/hermes-agent/commit/07f075c291ba), [Copilot migration PR](https://github.com/NousResearch/hermes-agent/pull/144788), [Cron fix](https://github.com/NousResearch/hermes-agent/commit/11cebb30dafd478c7f30818715ba248f24e44212), [v0.22.5](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.5))
- Sources: https://github.com/NousResearch/hermes-agent/releases

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows  
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: **Oct 28, 2026** — **GitHub Universe 2026**: Copilot Fusion (multi-model routing/orchestration) reached general availability; Fusion Max scored within two points of Claude Code + Opus 5.5 Max on the Artificial Analysis Coding Agent Index at roughly half the cost and ~40% less time per task. Also shipped: the new GitHub Copilot app (an agentic issue-to-merge surface), Copilot projects (goal-based, multi-repo parallel agent sessions, public preview), and Copilot code review Max. ([GitHub](https://github.blog/news-insights/company-news/github-universe-2026-evolving-every-layer-of-the-stack/), [unite.ai](https://www.unite.ai/github-makes-copilot-fusion-generally-available-at-universe-2026/)) **Oct 22, 2026** — the usage metrics API now identifies configured custom skills, agents, MCP servers, slash commands, and plugins (up to 25 named entries per category), making organizational customization adoption measurable. ([Source](https://github.blog/changelog/2026-10-22-custom-skills-agents-and-mcp-servers-in-usage-metrics-api)) Previous: **Sep 17, 2026** — **GitHub Copilot pricing go-live delayed to October 2026**, allowing continued free usage until then (Source: [AI coding assistants - What's new](https://docs.developer.tech.gov.sg/docs/ai-coding-assistants/whats-new)). **Sep 15, 2026** — **GPT-6 Astra** and **Gemini 3.8 Flash** models are now generally available in GitHub Copilot, expanding its coding assistant capabilities (Sources: [GPT-6 Astra](https://github.blog/changelog/2026-09-04-gpt-6-astra-is-generally-available-in-github-copilot), [Gemini 3.8 Flash](https://github.blog/changelog/2026-09-03-gemini-3-8-flash-is-now-available-in-github-copilot)). **Sep 8, 2026** — **Enterprise-managed sandbox** now available in Copilot for JetBrains, enhancing security for corporate users (Source: [JetBrains Sandbox](https://github.blog/changelog/2026-09-08-enterprise-managed-sandbox-in-copilot-for-jetbrains)). Previous updates: **Sep 14, 2026** — **GitHub Copilot CLI** now features **HydraFusion** (Research Preview). **Sep 12, 2026** — **GitHub Agent HQ** launched, enabling Claude and Codex agents directly within GitHub. **GitHub Copilot desktop app** is in public preview; **MAI-Code-1.1-Flash** rollout continues; Copilot CLI supports **air-gapped GHES environments**; **Claude Fable 5.1** is GA; Copilot code review can **approve pull requests** (public preview). (Source: [GitHub Community Discussions](https://github.com/orgs/community/discussions/206492))
- Sources: https://github.blog/changelog/ | https://www.neowin.net/news/microsoft-releases-mai-code-11-flash-coding-model-to-better-compete-with-chinese-models/ | https://x.com/GHchangelog

### OpenAI API / Codex
- Area: core models, developer platform, agent tooling
- Why it matters: critical for new capabilities, pricing, and infrastructure shifts that impact agent design and cost management
- Current watch note: **Oct 27, 2026** — **GPT-6.1 Terra** is now available in ChatGPT Work, Codex, and the API as `gpt-6.1-terra`. It targets high-volume computer use, visual reasoning, and coding, with standard pricing of $1/M input, $0.05/M cached input, and $5/M output tokens—an important routing option where cost and latency matter. ([Announcement](https://openai.com/index/introducing-gpt-6-1-terra/)) **Sep 29** — **DevDay 2026**: **GPT-6.1 Sol** launched — near-Astra agentic-coding / computer-use capability at one-fifth of Astra's price ($2/M input, $0.10/M cached, $10/M output, API id `gpt-6.1-sol`). Also announced: **Dots** (always-on agents in ChatGPT, Pro/Business Premium), **Agents API computer use** (plus Codex multi-agent, tool search, context compaction), **Codex in the cloud**, a refreshed **Codex CLI**, and a **Decisions API** preview (now GA). ([GPT-6.1 Sol](https://openai.com/index/introducing-gpt-6-1-sol/), [DevDay recap](https://openai.com/index/devday-2026-recap/), [Dots](https://openai.com/index/introducing-dots/)) **Sep 17** — **OpenAI GPT-6 Astra** launched with stronger biological reasoning capabilities. **Sep 14** — OpenAI launched a new **Managed Agents API** to simplify enterprise AI agent development. **Sep 8** — the **GPT-5.6 family (Sol, Terra, Luna)** and Sol Ultra-in-Codex were announced.
- Sources: https://devday.openai.com/ | https://community.openai.com/t/20-price-reduction-for-gpt-5-6-sol-api-codex-credits-and-chatgpt-work/1391726 | https://thenewstack.io/best-ai-coding-agents-2026-ranked/

### Anthropic Claude Code
- Area: AI coding assistant, IDE extensions
- Why it matters: directly integrates Claude's coding capabilities into developer workflows, supporting agentic development and code generation/review. Significant for MCP ecosystem with new API capabilities.
- Current watch note: **Nov 2, 2026 (retroactive)** — **Claude Opus 5.5** (announced Sep 22, 2026) recorded after being missed: the first and flagship model in the Claude 5.5 family, it leads agentic coding and knowledge work, performs at the level of Claude Fable 5.1 for most tasks, and costs 40% less to run than Opus 5. ([Source](https://www.anthropic.com/claude-opus-5-5)) **Sep 29, 2026** — Anthropic introduced **Claude Sonnet 5.5** (Sep 28, 2026), a significant upgrade to Sonnet 5 with 30% faster performance and up to 30% cost reduction, now the default Sonnet model on the Anthropic API. The Bedrock default Sonnet model has also been updated to `global.anthropic.claude-sonnet-4-5-20250929-v1:0`. Previous updates: **Sep 17, 2026** — New beta extensions for VS Code and JetBrains integrate Claude Code directly into IDEs. Claude Code on GitHub also launched in beta. Claude 4 also introduces new API capabilities: code execution tool, MCP connector, Files API, and prompt caching. **Feb 05, 2026** — **Claude Opus 4.6** introduced with significant enhancements in coding skills, agentic task capabilities, a 1M token context window (beta), and new features like agent teams in Claude Code, context compaction, adaptive thinking, and effort controls. It also includes improved Claude in Excel and a research preview for PowerPoint. (Source: [https://www.anthropic.com/news/claude-opus-4-6](https://www.anthropic.com/news/claude-opus-4-6))
- Sources: https://www.anthropic.com/news/claude-4

### Mistral Large 4 (Le Chonk)
- Area: open-weight foundation model for agentic coding / cybersecurity
- Why it matters: frontier-level agentic-coding performance with fully open weights enables sovereign, self-hosted agents — a real alternative to closed coding models for local/Hermes-adjacent automation.
- Current watch note: **Oct 29, 2026** — Mistral released open weights for Le Chonk (1T params, multimodal). Leads open-weight agentic-coding benchmarks (Terminal-Bench 4.0: 41% vs GLM-5.3's 40%) while using ~47% fewer tokens per task; three reasoning modes; European-trained. Weights on Hugging Face, deployable via vLLM/SGLang. ([Mistral](https://mistral.ai/news/mistral-large-4-oss/))
- Sources: https://mistral.ai/news/

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

### System Initiative
- Area: Infrastructure automation with AI agents
- Why it matters: Integrates autonomous AI agents with digital twins of IT infrastructure for proposing and executing changes, optimizing workflows, and discovering hidden relationships.
- Current watch note: **September 2026** - Added autonomous AI agents to its platform.
- Sources: https://devops.com/system-initiative-adds-ai-agents-to-infrastructure-automation-platform/

### Dynatrace AI Coding Agent Monitoring
- Area: AI agent observability, performance, cost, and governance
- Why it matters: provides unified monitoring for various AI coding agents (Claude Code, Google Gemini CLI, OpenAI Codex CLI, OpenCode, GitHub Copilot SDK) across development and production workflows. Crucial for understanding agent behavior and operational impact.
- Current watch note: **April 2026** - Expanded monitoring capabilities launched, offering insights into agent activity, token consumption, costs, and tool interactions through a unified Dynatrace platform. (Source: [https://www.dynatrace.com/news/blog/dynatrace-expands-ai-coding-agent-monitoring/](https://www.dynatrace.com/news/blog/dynatrace-expands-ai-coding-agent-monitoring/))


## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.