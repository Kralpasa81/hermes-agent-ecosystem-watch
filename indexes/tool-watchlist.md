# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, changelog-worthy fixes, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: **v0.21.3 (v2026.9.14)** released on September 14, 2026. This patch addresses critical remote dashboard session expiry issues and prevents long-lived processes from leaking duplicate `state.db` writer handles. (Source: [https://github.com/NousResearch/hermes-agent/releases/tag/v2026.9.14](https://github.com/NousResearch/hermes-agent/releases/tag/v2026.9.14))
- Sources: https://github.com/NousResearch/hermes-agent/releases

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows  
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: **Sep 15, 2026** — **GPT-6 Astra** and **Gemini 3.8 Flash** models are now generally available in GitHub Copilot, expanding its coding assistant capabilities (Sources: [GPT-6 Astra](https://github.blog/changelog/2026-09-04-gpt-6-astra-is-generally-available-in-github-copilot), [Gemini 3.8 Flash](https://github.blog/changelog/2026-09-03-gemini-3-8-flash-is-now-available-in-github-copilot)). **Sep 8, 2026** — **Enterprise-managed sandbox** now available in Copilot for JetBrains, enhancing security for corporate users (Source: [JetBrains Sandbox](https://github.blog/changelog/2026-09-08-enterprise-managed-sandbox-in-copilot-for-jetbrains)). Previous updates: **Sep 14, 2026** — **GitHub Copilot CLI** now features **HydraFusion** (Research Preview). **Sep 12, 2026** — **GitHub Agent HQ** launched, enabling Claude and Codex agents directly within GitHub. **GitHub Copilot desktop app** is in public preview; **MAI-Code-1.1-Flash** rollout continues; Copilot CLI supports **air-gapped GHES environments**; **Claude Fable 5.1** is GA; Copilot code review can **approve pull requests** (public preview). (Source: [GitHub Community Discussions](https://github.com/orgs/community/discussions/206492))
- Sources: https://github.blog/changelog/ | https://www.neowin.net/news/microsoft-releases-mai-code-11-flash-coding-model-to-better-compete-with-chinese-models/ | https://x.com/GHchangelog

### OpenAI API / Codex
- Area: core models, developer platform, agent tooling
- Why it matters: critical for new capabilities, pricing, and infrastructure shifts that impact agent design and cost management
- Current watch note: **Sep 14, 2026** — OpenAI launched a new **Managed Agents API** to simplify enterprise AI agent development. **Sep 12, 2026** — OpenAI relaunched Codex (May 2025) as a cloud-based, autonomous coding agent (now GPT-5.5 based), capable of end-to-end task execution. OpenAI introduced **Codex Security** (March 2026) for automated vulnerability detection and remediation. **Anthropic Claude Opus 5** and **OpenAI GPT-5.6 family (Sol, Terra, Luna)** with Sol Ultra in Codex client announced (Sep 8, 2026). **DevDay 2026 confirmed for Sep 29**. **GPT-5.6 Sol price reduction** (Aug 21) extended. (Source: [InfoWorld](https://www.infoworld.com/article/4221163/openai-launches-managed-agents-api-to-simplify-enterprise-ai-agent-development.html))
- Sources: https://devday.openai.com/ | https://community.openai.com/t/20-price-reduction-for-gpt-5-6-sol-api-codex-credits-and-chatgpt-work/1391726 | https://thenewstack.io/best-ai-coding-agents-2026-ranked/

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

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.