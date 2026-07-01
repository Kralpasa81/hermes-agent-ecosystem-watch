# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: `v0.17.0` / `v2026.6.19` (“The Reach Release”) remains the current public release baseline. June 21-July 1 main-branch follow-up is high-signal for unattended operation, gateway trust, messaging surfaces, provider fallback, operator UX, and Desktop/runtime separation: cron heartbeat/stalled-status reporting, prompt-cache reuse for recurring cron jobs, continuable cron thread/session mirroring, external-provider cron status correctness for Chronos-style schedulers, cron pre-run script timeout expansion, cron BSM secret re-resolution per run, compression lock/cooldown/resume reliability, post-compression context sentinel clamping, stale `sessions.json` gateway-route self-healing, CDP/browser-control URL token redaction consolidation, relay-delivery authorization hardening, multi-platform relay identity work, Photon/iMessage stabilization, dashboard OIDC redirect handling, content-filter / transport fallback recovery, Telegram bot-auth policy, WhatsApp send serialization, Matrix media delivery through the live gateway adapter, symlinked-`HERMES_HOME` cache-media delivery, Desktop/TUI freeze and launch hardening, shared WebSocket / JSON-RPC extraction around `hermes serve`, Desktop terminal tab/scrollback persistence, strict skills path containment, context-reference concurrency, bounded `web_extract` full-text handling, per-platform typing indicators, `/usage` context breakdowns, and redaction / credential / proxy correctness fixes.
- Sources: https://github.com/NousResearch/hermes-agent/releases/tag/v2026.6.19, https://github.com/NousResearch/hermes-agent/commit/6e4e5967f73483ad32568e0684c02390fae8bdad, https://github.com/NousResearch/hermes-agent/commit/85e084d60d57b8e0fdbddaa73cb3b59950297c37, https://github.com/NousResearch/hermes-agent/commit/56cf517ccd4c28cf0815a27403dee680dc36ca6e, https://github.com/NousResearch/hermes-agent/commit/0b7128582fad94d9bb5e9b36de4f937162fab7f2, https://github.com/NousResearch/hermes-agent/commit/68680db10d1744bcff4fd2fbc519cccc8447e0e3, https://github.com/NousResearch/hermes-agent/commit/5636c22828b0be1eadaf8968c7033efb27f705fa, https://github.com/NousResearch/hermes-agent/commit/fbf748b2824703f11a55bcf4b5ba7a5909c00865, https://github.com/NousResearch/hermes-agent/commit/578e3989, https://github.com/NousResearch/hermes-agent/commit/c9df4bc0, https://github.com/NousResearch/hermes-agent/commit/fc70d023, https://github.com/NousResearch/hermes-agent/commit/c393a8e5, https://github.com/NousResearch/hermes-agent/commit/a7fd62d8, https://github.com/NousResearch/hermes-agent/commit/f3aaba7f, https://github.com/NousResearch/hermes-agent/commit/674e16e7, https://github.com/NousResearch/hermes-agent/commit/388268ecde085a22c15474fea1723db161a930da, https://github.com/NousResearch/hermes-agent/commit/fb0644fbc2a56d7b76f0f2856cca989314a05e2a, https://github.com/NousResearch/hermes-agent/commit/0943e2a2720fd2b7eb5aee19c3bad0d495e5450a, https://github.com/NousResearch/hermes-agent/commit/313a8c68332e126e6b5b831877da3d8c2dd3f72f, https://github.com/NousResearch/hermes-agent/commit/58d8e25e671ead6d3ae4f30d6fa2f193bab44059, https://github.com/NousResearch/hermes-agent/commit/643b0dc67849, https://github.com/NousResearch/hermes-agent/commit/3a83b6bc5dc8, https://github.com/NousResearch/hermes-agent/commit/c1b9de73f566, https://github.com/NousResearch/hermes-agent/commit/c9269fbfb689, https://github.com/NousResearch/hermes-agent/commit/c626dde, https://github.com/NousResearch/hermes-agent/commit/265da9c, https://github.com/NousResearch/hermes-agent/commit/e09ff88, https://github.com/NousResearch/hermes-agent/commit/836732f, https://github.com/NousResearch/hermes-agent/commit/b6d8fc4, https://github.com/NousResearch/hermes-agent/commit/8db6ed7

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: `2.1.197` makes Claude Sonnet 5 the default model in Claude Code, with a native 1M-token context window and promotional pricing of $2/$10 per million tokens through August 31. `2.1.196` remains high-signal for organization default models, readable session names, clickable attachments, background-agent durability, Remote-session crash recovery, MCP OAuth scope handling for enterprise IdPs, safer MCP listing in untrusted workspaces, default-on streaming idle watchdog behavior, PowerShell search/diff parity, and reduced `/code-review` token usage.
- Source: https://docs.anthropic.com/en/release-notes/claude-code

### Claude Tag
- Area: team agent surface / Slack-based delegated work
- Why it matters: moves Claude-style coding and knowledge work into shared channels with selected tool, data, and codebase access; useful as a mainstream signal for multiplayer, proactive, asynchronous agents
- Current watch note: Introduced June 23 in beta for Claude Team and Enterprise customers. Claude Tag starts in Slack, replaces the existing Claude in Slack app, lets teams tag `@Claude`, and is framed by Anthropic as an evolution of Claude Code toward proactive team workflows.
- Source: https://www.anthropic.com/news/introducing-claude-tag

### Anthropic Claude Fable 5 / Mythos 5
- Area: frontier model tier for coding agents and long-horizon knowledge work
- Why it matters: affects Claude Code, GitHub Copilot model choice, provider routing, governance, cost, data-retention review, and high-complexity autonomous coding workflows
- Current watch note: Announced June 9, then materially changed on June 12. Anthropic says a US government export-control directive requires suspending access to Fable 5 and Mythos 5 for all customers, while access to other Anthropic models is not affected. This changes the availability picture for Claude Code, Copilot model choice, provider routing, and teams evaluating Mythos-class coding workflows.
- Sources: https://www.anthropic.com/news/claude-fable-5-mythos-5, https://www.anthropic.com/news/fable-mythos-access

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: Codex Remote reached GA on June 25, enabling ChatGPT mobile to start or continue work on a connected Mac or Windows host with authenticated one-to-one QR pairing. The same changelog also notes a new DigitalOcean plugin for provisioning a Droplet and connecting it to Codex App as a remote workspace. Codex CLI `0.142.5` is a privacy/security maintenance release that prevents full Responses WebSocket request payloads from being written to trace logs; the broader functional baseline remains `0.142.2` for MCP tool-search, proxy-aware auth, remote MCP, Bedrock recovery, and PowerShell approval behavior changes.
- Sources: https://developers.openai.com/codex/changelog, https://github.com/openai/codex/releases/tag/rust-v0.142.5, https://github.com/openai/codex/releases/tag/rust-v0.142.2

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: June 17-26 is a major Copilot agent/governance wave: the Copilot app is GA and now supports BYOK model providers; Agent Finder / Agentic Resource Discovery is available across Copilot plans; Copilot Chat auto mode is available for all users; Copilot code review uses root-level `AGENTS.md` and now has file-exploration-backed analysis-depth / efficiency updates; MAI-Code-1-Flash is generally available for Copilot Business / Enterprise behind admin policy controls and usage-based pricing; Opus 4.6 (fast) is scheduled for Copilot deprecation on June 29, 2026; the Copilot usage metrics API exposes per-user daily `ai_credits_used` plus `total_pull_requests_merged` by AI adoption phase; the redesigned Copilot CLI terminal interface is GA with guided MCP / skills / plugin configuration; Copilot for Jira is GA with real-time agent progress and post-session steering from Jira; Free / Student plans now use Copilot auto model selection as the only model-selection experience; and enterprise-managed settings now support `strictKnownMarketplaces` for plugin marketplace governance in VS Code and Copilot CLI.
- Sources: https://github.blog/changelog/2026-06-17-github-copilot-app-generally-available/, https://github.blog/changelog/2026-06-17-agent-finder-for-github-copilot-now-available/, https://github.blog/changelog/2026-06-17-auto-mode-in-copilot-chat-available-for-all-users/, https://github.blog/changelog/2026-06-18-copilot-code-review-agents-md-support-and-ui-improvements, https://github.blog/changelog/2026-06-18-mai-code-1-flash-available-on-more-copilot-surfaces, https://github.blog/changelog/2026-06-18-upcoming-deprecation-of-opus-4-6-fast, https://github.blog/changelog/2026-06-19-ai-credits-consumed-per-user-now-in-the-copilot-usage-metrics-api/, https://github.blog/changelog/2026-06-23-github-copilot-app-support-for-byok, https://github.blog/changelog/2026-06-23-copilot-cli-new-terminal-interface-is-generally-available/, https://github.blog/changelog/2026-06-24-changes-to-model-selection-for-free-and-student-plans/, https://github.blog/changelog/2026-06-25-copilot-code-review-analysis-depth-and-efficiency-updates, https://github.blog/changelog/2026-06-25-enterprise-managed-settings-now-support-strictknownmarketplaces-in-vs-code-and-the-cli, https://github.blog/changelog/2026-06-25-github-copilot-for-jira-is-now-generally-available, https://github.blog/changelog/2026-06-26-mai-code-1-flash-for-copilot-business-and-copilot-enterprise, https://github.blog/changelog/2026-06-26-track-total-merges-by-adoption-phase-in-enterprise-and-organization-reports

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
- Current watch note: June review promoted two high-signal MCP interoperability items: the MCP 2026-07-28 release candidate, with stateless HTTP-friendly core, MCP Apps, Tasks, OAuth/OIDC-aligned authorization, JSON Schema 2020-12 support, and formal deprecation policy; and stable Enterprise-Managed Authorization, which lets organizations centrally authorize MCP server access through an IdP and reduce repeated per-server OAuth prompts. June 5 also noted an active individual IETF Internet-Draft on MCP security considerations; it has no formal IETF standing but remains a useful risk signal.
- Sources: https://modelcontextprotocol.io/, https://blog.modelcontextprotocol.io/posts/2026-07-28-release-candidate/, https://blog.modelcontextprotocol.io/posts/enterprise-managed-auth/

### Skills Over MCP
- Area: MCP-based agent skill discovery / portability
- Why it matters: connects portable agent skills with MCP registry, spec, SDK, and client behavior instead of leaving skills locked to individual hosts
- Current watch note: A June 30 MCP Working Session focuses on how “agent skills” can be discovered and consumed through MCP, with SEP-2640 called out as the near-term focus through June 2026.
- Source: https://meet.modelcontextprotocol.io/2026/06/skills-over-mcp-working-session-bi-weekly--WrKrEDAM75hr

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.
