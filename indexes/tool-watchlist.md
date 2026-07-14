# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: `v0.18.2` / `v2026.7.7.2` remains the latest tagged release; curated v0.19.0 release notes for the post-v0.18.0 window are still pending. Nous Research (Hermes' maker) is reportedly in talks for a new funding round at a **$1.5B valuation** (≥$75M, led by Robot Ventures with USV participating) per TechCrunch — unconfirmed by Nous but the first major funding signal since the company's prior $70M raise. On `main`, recent fixes address real cross-platform correctness bugs: the Desktop Memory Provider dropdown silently disappearing after v0.18.1 (fixed by restoring `memory.provider` to the config schema), Windows non-login Git Bash shells missing coreutils on PATH (causing silent write failures and exit 127s), and Desktop cross-platform builds staging the wrong-architecture `node-pty` binary. Use `hermes update` or `pip install -U hermes-agent` to pick up tagged releases.
- Sources: https://github.com/NousResearch/hermes-agent/releases/tag/v2026.7.7.2, https://techcrunch.com/2026/07/13/hermes-agent-maker-nous-research-in-talks-for-new-funding-at-1-5b-valuation/, https://github.com/NousResearch/hermes-agent/commit/861d69c7bba8d2ea6a1cd170e989c901c74d32d1, https://github.com/NousResearch/hermes-agent/commit/4a58e22e997ec56802fa93d4ca503a3767a02c4a

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: **`2.1.208`** (first seen July 11–14) shipped a large reliability/performance pass: opt-in screen reader mode, vim insert-mode remaps, and multiple long-session memory-leak fixes (MCP stdio stderr capped, LSP documents LRU-capped at 50 docs, unbounded headless/SDK tool-result growth fixed); tool-heavy sessions get up to **7x faster tool rounds** via cached tool-pool assembly, and transcripts shrink up to 79x in edit-heavy sessions. `2.1.209` followed with a quick fix reverting an overly broad dialog-blocking guard in background sessions. Earlier: `2.1.207` made auto mode default on Bedrock/Vertex AI/Foundry (Opus 4.8 default), and Week 28 (July 6–10) added a built-in sandboxed Desktop browser and upgraded `/doctor` into a full setup checkup.
- Sources: https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md, https://releasebot.io/updates/anthropic/claude-code

### Claude Tag
- Area: team agent surface / Slack-based delegated work
- Why it matters: moves Claude-style coding and knowledge work into shared channels with selected tool, data, and codebase access; useful as a mainstream signal for multiplayer, proactive, asynchronous agents
- Current watch note: Introduced June 23 in beta for Claude Team and Enterprise customers. Claude Tag starts in Slack, replaces the existing Claude in Slack app, lets teams tag `@Claude`, and is framed by Anthropic as an evolution of Claude Code toward proactive team workflows.
- Source: https://www.anthropic.com/news/introducing-claude-tag

### Anthropic Claude Fable 5 / Mythos 5
- Area: frontier model tier for coding agents and long-horizon knowledge work
- Why it matters: affects Claude Code, GitHub Copilot model choice, provider routing, governance, cost, data-retention review, and high-complexity autonomous coding workflows
- Current watch note: Export controls were lifted June 30 and global access restored July 1 with a plan-included promo window on Pro/Max/Team/eligible Enterprise plans (up to 50% of weekly usage limits at no extra cost, same pool as other models). That promo window has now been extended **twice** at the wire: original July 7 cutoff → moved to July 12 (announced July 7) → moved again to **July 19** (announced early July 13, after the July 12 deadline had already passed). Claude Code's 50% higher weekly rate limits extend alongside each Fable 5 extension. No forward commitment exists past July 19 — teams standardizing workflows on Fable 5 should not assume a stable cutoff date. Post-promo rate is $10/$50 per M tokens in/out on usage credits.
- Sources: https://www.anthropic.com/news/redeploying-fable-5, https://www.anthropic.com/news/fable-mythos-access, https://support.claude.com (help center, updated Jul 13)

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: **Codex joined the ChatGPT desktop app** (Jul 9) on macOS/Windows — existing Codex app users keep projects/settings; adds inline Markdown/code editing, in-app GitHub PR review, and multi-repo project support. CLI catch-up through the week: `0.143.0` (Jul 7–8) enabled remote plugins by default with npm marketplace sources, added macOS/Windows system-proxy routing (PAC/WPAD) for auth and Responses API traffic, brought Bedrock GPT-5.6 Sol/Terra/Luna with `max` reasoning effort, and made MCP tool search the default; `0.144.0` (Jul 9) added a `writes` app-approval mode (auto-allow read-only actions, prompt only on writes), interactive MCP auth without an experimental flag, and Ultra-reasoning concurrency-cost warnings; `0.144.1`/`0.144.2` (Jul 9–13) were installer-reliability and Guardian auto-review-regression-revert patches.
- Sources: https://developers.openai.com/codex/changelog, https://github.com/openai/codex/releases

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: **July 7–9 update wave**: Copilot app opened to all users (July 7); Kimi K2.7 became available for Business/Enterprise (July 7); **GPT-5.6 Sol, Terra, and Luna rolled out** (July 9) — three-tier model family (Sol: highest reasoning, Pro+/Max/Business/Enterprise; Terra: balanced default, all plans ≥ Pro; Luna: lightweight/cost-efficient, all plans ≥ Pro); "Ask Copilot for a repository overview" added (July 9). The **VS Code June 2026 release bundle** (v1.123–v1.127, posted July 8) includes: agentic browser tools GA, parallel agent sessions with multi-chat, full session cost visibility (total + subagent credits), model provider discovery from Marketplace, Autopilot improvements (better task completion judgment), session sync and history across machines, 1M context for Anthropic/OpenAI models, MCP OAuth credential storage, enterprise MDM-managed settings. Earlier: June 17–July 2 wave (Copilot app GA + BYOK, Agent Finder/ARD, MAI-Code-1-Flash GA, redesigned CLI, Copilot for Jira GA, `managed-settings.json` GA, Kimi K2.7 Code GA, Copilot vision GA, agent session streaming preview).
- Sources: https://github.blog/changelog/2026-07-09-openais-gpt-5-6-sol-terra-and-luna-are-now-available-in-github-copilot/, https://github.blog/changelog/2026-07-08-github-copilot-in-visual-studio-code-june-2026-releases/, https://github.blog/changelog/2026-07-07-github-copilot-app-available-to-all

### GitHub Copilot SDK
- Area: embeddable agent runtime / developer SDK
- Why it matters: stable programmatic access to Copilot planning, tool invocation, file edits, streaming, multi-turn sessions, custom tools, MCP servers, hooks, tracing, BYOK, and cloud/remote sessions
- Current watch note: General availability was announced on June 2, with SDK support across six language stacks and new Rust/Java availability called out at GA.
- Source: https://github.blog/changelog/2026-06-02-copilot-sdk-is-now-generally-available

### GitHub Agentic Workflows
- Area: GitHub Actions-native agentic engineering automation
- Why it matters: brings reasoning-based agents into governed CI/CD infrastructure for triage, CI failure analysis, documentation updates, security remediation, dependency maintenance, routine change review, reporting, and compliance
- Current watch note: Public preview was announced June 11. Workflows are written in natural-language Markdown, compiled into standard GitHub Actions YAML, run with read-only defaults and sandboxing, and can use `GITHUB_TOKEN` instead of long-lived PATs with organization billing via `copilot-requests: write`. Also watch the June 16 GitHub Actions Node 24 default-runtime migration because agentic workflows and their third-party JavaScript actions inherit the underlying Actions runtime behavior.
- Sources: https://github.blog/changelog/2026-06-11-github-agentic-workflows-is-now-in-public-preview, https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners

### GitHub Agent Finder / Agentic Resource Discovery (ARD)
- Area: agent resource discovery / registry-based tool and skill selection
- Why it matters: reduces context-window bloat and manual pre-wiring by letting agents discover approved MCP servers, skills, canvases, agents, and tools on demand from a public or private registry
- Current watch note: GitHub Agent Finder became available across Copilot plans on June 17. It uses the open Agentic Resource Discovery specification and can point at GitHub's curated catalog or an internal registry while respecting enterprise governance and avoiding silent auto-installation.
- Sources: https://github.blog/changelog/2026-06-17-agent-finder-for-github-copilot-now-available/, https://github.com/agentfinder

### OpenAI Codex Sites
- Area: Codex-hosted app/site canvas
- Why it matters: extends Codex from coding tasks into hosted interactive sites, dashboards, internal tools, lightweight apps, and games that can be shared within a workspace
- Current watch note: Announced as a June 2 preview inside the Codex app alongside role-specific plugins and annotations.
- Source: https://openai.com/index/codex-for-every-role-tool-workflow/

### MCP ecosystem
- Area: protocol / tool interoperability layer
- Why it matters: increasingly central to connecting agents with external tools and services
- Current watch note: The **MCP 2026-07-28 release candidate** is the largest spec revision since launch and is now in its validation window (RC locked May 21; final ships **July 28, 2026**). Key changes: stateless HTTP core (removes `initialize`/`initialized` handshake and `Mcp-Session-Id` — any server instance can handle any request); MCP Apps (server-rendered UIs via a new extension); Tasks extension now first-class; OAuth/OIDC-aligned authorization; JSON Schema 2020-12 support for tool schemas; W3C Trace Context propagation standardized; `ttlMs`/`cacheScope` on list results; formal deprecation policy (12-month window minimum). Impact: this is a **breaking change** for existing MCP implementations. Tier 1 SDKs are expected to ship support before July 28. Enterprise-Managed Authorization (centralizing MCP server access through an IdP) is also now stable.
- Sources: https://modelcontextprotocol.io/, https://blog.modelcontextprotocol.io/posts/2026-07-28-release-candidate/, https://blog.modelcontextprotocol.io/posts/enterprise-managed-auth/

### Skills Over MCP
- Area: MCP-based agent skill discovery / portability
- Why it matters: connects portable agent skills with MCP registry, spec, SDK, and client behavior instead of leaving skills locked to individual hosts
- Current watch note: A June 30 MCP Working Session focuses on how "agent skills" can be discovered and consumed through MCP, with SEP-2640 called out as the near-term focus through June 2026.
- Source: https://meet.modelcontextprotocol.io/2026/06/skills-over-mcp-working-session-bi-weekly--WrKrEDAM75hr

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.