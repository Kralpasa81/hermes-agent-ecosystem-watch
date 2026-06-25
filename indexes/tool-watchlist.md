# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: `v0.17.0` / `v2026.6.19` (“The Reach Release”) remains the current public release baseline. June 21-25 main-branch follow-up is also high-signal for unattended operation and embedding: cron heartbeat/stalled-status reporting, live-adapter delivery confirmation fixes, per-profile cron storage restoration, structured `project.facts` and `llm.oneshot` gateway RPCs, Honcho OAuth memory connect flows, browser-tool runnable validation, Anthropic OAuth token-host repair, prompt-cache reuse for recurring cron jobs, continuable cron thread/session mirroring, relay-delivery authorization hardening, coding verification evidence/status, provider setup resilience, and `/learn` alignment with skill standards.
- Sources: https://github.com/NousResearch/hermes-agent/releases/tag/v2026.6.19, https://github.com/NousResearch/hermes-agent/commit/7a65800fed6f7b3f87c264018b7456b250e150ac, https://github.com/NousResearch/hermes-agent/commit/b693bee100bd163bd9e18e3c2c68179190bdc4ae, https://github.com/NousResearch/hermes-agent/commit/b177d4ee4891aeb3bf8a908f6e5def846a55c180, https://github.com/NousResearch/hermes-agent/commit/72ae163250dbd40d39ccf8b412835711bafd9c13, https://github.com/NousResearch/hermes-agent/commit/fcbdf3c3568bc0563c0af5b444c6e5bd6842bf02, https://github.com/NousResearch/hermes-agent/commit/7ef0f360d0cee8ffb512f372d1e2271afb6c5324, https://github.com/NousResearch/hermes-agent/commit/6f2b2a1f34d1dbeaf67a02e7212485f0f77ed116, https://github.com/NousResearch/hermes-agent/commit/e62afaca6259278ef08d23cb178abf477597f986

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: `v2.1.191` is the latest stable release found today and is a meaningful reliability update: permanent stop semantics for background agents, MCP capability-discovery retries, MCP OAuth retry/headless login improvements, clearer MCP 404 diagnostics, session-remembered sandbox network host approvals, `/rewind` recovery after `/clear`, managed-settings refresh fixes, and multiple terminal/UI correctness fixes.
- Source: https://github.com/anthropics/claude-code/releases/tag/v2.1.191

### Anthropic Claude Fable 5 / Mythos 5
- Area: frontier model tier for coding agents and long-horizon knowledge work
- Why it matters: affects Claude Code, GitHub Copilot model choice, provider routing, governance, cost, data-retention review, and high-complexity autonomous coding workflows
- Current watch note: Announced June 9, then materially changed on June 12. Anthropic says a US government export-control directive requires suspending access to Fable 5 and Mythos 5 for all customers, while access to other Anthropic models is not affected. This changes the availability picture for Claude Code, Copilot model choice, provider routing, and teams evaluating Mythos-class coding workflows.
- Sources: https://www.anthropic.com/news/claude-fable-5-mythos-5, https://www.anthropic.com/news/fable-mythos-access

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: Codex CLI `0.142.2` is the latest stable CLI release and is high-signal for MCP tool search by default when supported, macOS auth clients respecting system proxy / PAC / WPAD settings, remote stdio MCP path handling, clearer remote image-input validation, actionable expired Bedrock credential guidance, and stricter PowerShell approval behavior when safety classification cannot inspect executable AST regions. OpenAI also updated Codex team pricing on June 24: new pay-as-you-go Codex seats are no longer available for Business plans, while existing seats are not affected.
- Sources: https://github.com/openai/codex/releases/tag/rust-v0.142.2, https://openai.com/index/codex-flexible-pricing-for-teams/

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: June 17-24 was a major Copilot agent/governance wave: the Copilot app is GA and now supports BYOK model providers; Agent Finder / Agentic Resource Discovery is available across Copilot plans; Copilot Chat auto mode is available for all users; Copilot code review now uses root-level `AGENTS.md`; MAI-Code-1-Flash is rolling out to more Copilot surfaces; Opus 4.6 (fast) is scheduled for Copilot deprecation on June 29, 2026; the Copilot usage metrics API now exposes per-user daily `ai_credits_used`; the redesigned Copilot CLI terminal interface is GA with guided MCP / skills / plugin configuration; and Free / Student plans now use Copilot auto model selection as the only model-selection experience.
- Sources: https://github.blog/changelog/2026-06-17-github-copilot-app-generally-available/, https://github.blog/changelog/2026-06-17-agent-finder-for-github-copilot-now-available/, https://github.blog/changelog/2026-06-17-auto-mode-in-copilot-chat-available-for-all-users/, https://github.blog/changelog/2026-06-18-copilot-code-review-agents-md-support-and-ui-improvements, https://github.blog/changelog/2026-06-18-mai-code-1-flash-available-on-more-copilot-surfaces, https://github.blog/changelog/2026-06-18-upcoming-deprecation-of-opus-4-6-fast, https://github.blog/changelog/2026-06-19-ai-credits-consumed-per-user-now-in-the-copilot-usage-metrics-api/, https://github.blog/changelog/2026-06-23-github-copilot-app-support-for-byok, https://github.blog/changelog/2026-06-23-copilot-cli-new-terminal-interface-is-generally-available/, https://github.blog/changelog/2026-06-24-changes-to-model-selection-for-free-and-student-plans/

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

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.
