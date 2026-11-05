# Starred Highlights

Only the strongest signals are kept here.

## Highlight rule
Use this page for developments that meaningfully change:
- capabilities
- reliability
- workflow speed
- limits/access
- ecosystem interoperability

## Current starred items

### 2026-11-05
- ⭐ **Hermes hardens MCP consent rows (mainline):** Each MCP consent row in Desktop now shows a scrubbed `launch` line — what the server runs or contacts (e.g. `Runs: npx -y ...`, `Connects to: https://...`) — before the user installs/enables/authorizes it, with secret flags, credential params, and URL userinfo redacted. A targeted MCP approval-surface transparency change; not yet in a stable release. ([commit](https://github.com/NousResearch/hermes-agent/commit/3dbb1303fe3d3cb69615a7b3a811ee9ecfe13446))
- ⭐ **GitHub Copilot reaches Xcode's native coding assistant (public preview):** Copilot is now usable inside Apple's built-in Xcode assistant (Xcode 27.3 beta, macOS Tahoe 26.6+), a meaningful interoperability/access expansion beyond the standalone extension and VS Code. ([changelog](https://github.blog/changelog/2026-11-04-github-copilot-is-now-available-in-xcodes-coding-assistant))

### 2026-11-04
- ⭐ **Hermes ships two back-to-back patch releases (v0.22.6 → v0.22.7):** Rolling ~950 PRs since v0.22.5, the pair adds a webapp served from the gateway's own listener (`hermes webapp`, plus a Desktop Web Access pane and Desktop plugins in a browser tab), `/model reset`, per-skill locks against autonomous writes, opt-in prepared compaction (`compression.prepare_ahead`), `hermes cron cancel` with a per-job missed-run policy and a Stop button, a `pre_llm_call` hook that can block a turn before inference, `hermes migrate`, and opt-in OS-keychain vault-key storage. Directly changes capability, workflow, and reliability for Hermes users; full curated notes ship with v0.23.0. ([v0.22.7](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.7), [v0.22.6](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.6))
- ⭐ **Mistral Large 4 (Le Chonk) open weights:** A 1-trillion-parameter multimodal model is now fully open-weight, leading open-weight agentic-coding benchmarks (Terminal-Bench 4.0: 41%) while using ~47% fewer tokens per task than the previous open leader. A meaningful limits/access shift for self-hosted and sovereign agentic-coding deployments. ([Mistral](https://mistral.ai/news/mistral-large-4-oss/))

### 2026-11-01
- ⭐ **Hermes hardens approval prompts against hidden-character spoofing:** A cluster of mainline commits makes dangerous invisible content — zero-width and bidi-override characters, ANSI/OSC escapes, carriage returns, and padding — visible as explicit escapes before a human approves, and pages long approval commands so every line is reviewable. This prevents approving a command other than what actually runs. Display-only; the executed command is unchanged. ([Source](https://github.com/NousResearch/hermes-agent/commit/3f5612cde62556d0b73558230f4acb0e98279d83))
- ⭐ **GitHub Copilot Fusion reaches GA (Universe 2026):** Copilot's multi-model routing/orchestration layer is now generally available; Fusion Max posted within two points of Claude Code + Opus 5.5 Max on the Artificial Analysis Coding Agent Index at roughly half the cost and ~40% less time per task. ([Source](https://github.blog/news-insights/company-news/github-universe-2026-evolving-every-layer-of-the-stack/))

### 2026-10-27
- ⭐ **OpenAI releases GPT-6.1 Terra for computer-use agents:** Available in Codex, ChatGPT Work, and the API, Terra pairs visual reasoning and UI action with substantially lower standard pricing than the prior Terra generation. It is a meaningful new routing option for high-volume multimodal automation. ([Source](https://openai.com/index/introducing-gpt-6-1-terra/))

### 2026-10-26
- ⭐ **Hermes splits GitHub Copilot into a Labs provider plugin:** A merged mainline refactor removes Copilot-specific core logic in favor of generic provider-profile hooks. Existing Copilot profiles are designed to receive an automatic plugin migration, while non-Copilot profiles stop touching incidental GitHub credentials. This is an important modularity and operational-safety shift, pending its next release cut. ([Source](https://github.com/NousResearch/hermes-agent/pull/144788))
- ⭐ **MCP reference servers v2.1.0 fixes eight vulnerabilities:** Update the filesystem and everything packages to `2.0.1`, and `mcp-server-fetch` to `2026.10.24`. The fixes matter directly to agent deployments that expose local files or web-fetch capabilities. ([Source](https://github.com/modelcontextprotocol/servers/releases/tag/v2.1.0))

### 2026-10-25
- ⭐ **Hermes cron MCP allowlist safety fix:** Scheduled jobs that explicitly named one MCP server could incorrectly receive every enabled server. The fixed matching preserves the requested scope (including `no_mcp`), restoring least-privilege behavior for automation. ([Source](https://github.com/NousResearch/hermes-agent/commit/11cebb30dafd478c7f30818715ba248f24e44212))

### 2026-10-23
- ⭐ **Hermes Agent v0.22.5:** The latest stable patch rolls the post-v0.22.4 work into every main distribution channel. Explicitly named improvements span pluggable delegation, agent import/migration, MCP serving, sign-in, update/gateway recovery, and experimental MCP events; full curated notes are planned for v0.23.0. ([Source](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.5))
- ⭐ **OpenAI Decisions API GA:** A dedicated GPT-6 Luna endpoint for structured probabilities, choices, and scores makes fast routing and control decisions a first-class agent building block; it also supports GPT-Live, caching, images, and JSON inputs. ([Source](https://openai.com/index/decisions-api/))

### 2026-10-22
- ⭐ **Hermes Agent v0.22.4:** The October 21 patch improves Desktop and plugin-install reliability, fixes WhatsApp re-pairing, and adds `mcp-serve` to the catalog—a direct Hermes-as-MCP-server interoperability path. ([Source](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.4))

### 2026-10-02
- ⭐ **Hermes Agent v0.21.0 - The Pantheon Release & v0.21.5 Stable:** The "Pantheon Release" (v0.21.0, Aug 31, 2026) introduced transformative features including **Bot Mode** for multi-agent societies, **`hermes peer`** for direct bot-to-bot DMs, **Persistent Cron Jobs** with memory and `continuity=true`, **Live Subagent Orchestration** for real-time control, an **Enhanced MCP Command Center**, and **Agent-Driven Desktop Browser** capabilities. This release, followed by the latest stable v0.21.5 (Sep 24, 2026), significantly elevates Hermes's multi-agent workflow, task reliability, and ecosystem integration. ([Source](https://github.com/NousResearch/hermes-agent/releases))
- ⭐ **Anthropic Claude Opus 4.6 - 1M Token Context, Agent Teams, Adaptive Thinking, Enhanced Coding:** (Feb 05, 2026) Marks a substantial leap in Claude's intelligence and agentic potential, offering a 1M token context window (beta), agent teams in Claude Code, adaptive thinking, and advanced coding capabilities. This expands its utility for complex, long-running agentic tasks. ([Source](https://www.anthropic.com/news/claude-opus-4-6))
- ⭐ **GitHub Integrates Claude Code & OpenAI Codex in Public Preview:** (Feb 02, 2026) A pivotal move embedding leading AI coding agents directly into mainstream developer workflows on GitHub and VS Code for Copilot Pro+ and Enterprise users. This enables direct assignment of agent tasks to major models within the GitHub ecosystem. ([Source](https://github.com/orgs/community/discussions/186179))

### 2026-09-29
- ⭐ **Anthropic Claude Sonnet 5.5 Release:** (Sep 28, 2026) Anthropic announced Claude Sonnet 5.5, offering 30% faster performance and up to 30% cost reduction, now the default Sonnet model on the Anthropic API. This upgrade significantly enhances capabilities for AI-assisted development. [[Source](https://www.anthropic.com/news/claude-sonnet-5-5)]
- ⭐ **OpenAI DevDay 2026 — GPT-6.1 Sol and Dots:** GPT-6.1 Sol delivers near-Astra agentic-coding, computer-use, and professional-work capability at one-fifth of Astra's price ($2/M input, $0.10/M cached, $10/M output), a major step down in the cost of capable agents. DevDay also introduced **Dots** (always-on agents inside ChatGPT) and **Agents API computer use**, extending hosted agent execution beyond chat. ([GPT-6.1 Sol](https://openai.com/index/introducing-gpt-6-1-sol/), [Dots](https://openai.com/index/introducing-dots/), [Recap](https://openai.com/index/devday-2026-recap/))

### 2026-09-22
- ⭐ **Anthropic Claude Opus 5.5 — flagship 5.5-family model:** Leads agentic coding and knowledge work, performs at the level of Claude Fable 5.1 for most tasks, and costs 40% less to run than Opus 5 on typical workloads. Recorded retroactively on 2026-11-02 after being missed. ([Source](https://www.anthropic.com/claude-opus-5-5))

### 2026-09-17
- ⭐ **OpenAI GPT-6 Astra Launch:** OpenAI's new model brings stronger biological reasoning to its API.
- ⭐ **Anthropic Claude 4 New API Capabilities & Claude Code Beta:** Introduces code execution, MCP connector, Files API, prompt caching, and IDE integrations for Claude Code.

### 2026-09-15
- ⭐ **AI Agent Security Exploits and Detections:** The CrowdStrike demo and Claude cookie exploit reports highlight a rapidly evolving threat landscape for AI agents, pushing the need for advanced security measures and monitoring.
- ⭐ **GitHub Copilot Expands Model Support with GPT-6 Astra and Gemini 3.8 Flash:** The integration of these cutting-edge models significantly enhances Copilot's capabilities, offering developers more powerful and diverse AI assistance directly within their workflow.

### 2026-09-14
- ⭐ **OpenAI Launches Managed Agents API**: Significant for enterprise AI agent development, simplifying deployment and management in corporate environments. (Source: [InfoWorld](https://www.infoworld.com/article/4221163/openai-launches-managed-agents-api-to-simplify-enterprise-ai-agent-development.html))
- ⭐ **GitHub Copilot CLI: HydraFusion Live**: Introduces multi-model orchestration for advanced coding assistance, enhancing code generation. (Source: [GitHub Community Discussions](https://github.com/orgs/community/discussions/206492))
- ⭐ **Anthropic Fable 5.1 and Mythos 5.1 Released**: Anthropic's most advanced models for coding and knowledge work, enhancing efficiency and capability. (Source: [Anthropic News](https://www.anthropic.com/))

### 2026-09-09
- ⭐ **Hermes Agent OAuth Live:** Nous Research launched OAuth for Hermes Agent, enabling 1-click connection to Honcho from Hermes Desktop and the CLI. This significantly streamlines user authentication and integration workflows. (Source: Facebook Group post by Nous Research)

### 2026-09-08
- ⭐ **Anthropic Claude Opus 5 Released:** Major performance and cost efficiency improvements, more than doubling Opus 4.8 on Frontier-Bench v0.1. Crucial for advanced agent task execution.  
  Source: https://thenewstack.io/best-ai-coding-agents-2026-ranked/
- ⭐ **OpenAI GPT-5.6 Family (Sol, Terra, Luna) & Sol Ultra Integration:** New flagship models generally available, with Sol Ultra integrating into the Codex client for cooperative subagents.  
  Source: https://thenewstack.io/best-ai-coding-agents-2026-ranked/
- ⭐ **Claude & OpenAI Codex Agents on GitHub Copilot (Public Preview):** Deep integration into GitHub and VS Code for Pro+ and Enterprise users, enabling direct assignment of agent tasks to major models within development workflows.  
  Source: https://github.blog/news-insights/company-news/pick-your-agent-use-claude-and-codex-on-agent-hq/

### 2026-09-03
- ⭐ **MAI-Code-1.1-Flash rolling out in GitHub Copilot**  
  Microsoft's updated coding model with native vision support (image understanding) and improved performance rolling out across Copilot clients. Replaces MAI-Code-1-Flash on Sep 10.  
  Source: https://www.neowin.net/news/microsoft-releases-mai-code-11-flash-coding-model-to-better-compete-with-chinese-models/
- ⭐ **Claude Fable 5.1 and Mythos 5.1 launched (Sep 1, 2026)**  
  Anthropic's most advanced models for coding and knowledge work now generally available in Claude API, Claude Code, and GitHub Copilot (Fable 5.1).  
  Source: https://www.anthropic.com/claude-fable-and-mythos-5-1

### 2026-09-02
- ⭐ **Copilot code review can approve pull requests — public preview (Sep 1)**  
  Copilot can now submit a counted PR approval against required-approvals rules. Off by default; configurable at enterprise / org / repo level, with per-path controls. Approval dismissed on new commits. First meaningful step toward AI-backed merge gates in GitHub-native workflows.  
  Source: https://github.blog/changelog/2026-09-01-copilot-code-review-can-now-approve-pull-requests

### 2026-08-27
- ⭐ **Anthropic's Model Hardware Standard (MHS) Research Preview:** A significant step towards standardized, safe operation of AI agents with physical devices, broadening the scope of agentic AI.

### 2026-08-24
- ⭐ **MCP Security Alert** — CSA Research published bulletin on MCP auto-execution risks with coding assistants.
- ⭐ **DeepSeek V4-Pro general availability** — Adaptive reasoning profiles, tiered pricing, and API compatibility now widely available.

### 2026-08-11
- ⭐ **Hermes Agent v0.20.0 "The Herald Release" (Aug 3, 2026)**  
  Autonomous functions, flexible Python evaluation, improved safety/conversion tools. Foundation for v0.21.0.  
  Source: https://github.com/NousResearch/hermes-agent/releases/tag/v2026.8.3

### 2026-08-09
- ⭐ **Claude Code Auto Mode becomes default (Aug 14, 2026)**  
  Significant shift toward greater agent autonomy in coding workflows. Auto mode catching 89% of harmful actions vs 13.6% from human review.  
  Source: https://techcrunch.com/2026/08/09/anthropic-is-turning-claude-codes-auto-mode-on-by-default/

### 2026-07 (ongoing)
- ⭐ **MCP specification 2026-07-28** — Stateless protocol (no handshake/sessions), HTTP-native, routable/cacheable/traceable. Updated TypeScript, Python, Go, C# SDKs. Now fully adopted by Cloudflare, Google, and major MCP client implementors.  
  Source: https://blog.modelcontextprotocol.io/posts/2026-07-28/
- ⭐ **Claude Sonnet 5** — Significant performance leap for coding and agent workflows.
- ⭐ **Hermes Desktop public preview (Jun 2, 2026)** — Hermes Agent as a native app for macOS/Windows/Linux.
