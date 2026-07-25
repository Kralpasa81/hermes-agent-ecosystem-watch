# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: **v0.19.0 / v2026.7.20 — "The Quicksilver Release"** (tagged Jul 20, 2026) remains the latest tagged release; post-release stabilization continues through Jul 25 with no version bump yet. Headline changes at release: **~80% cold-start first-token latency cut** (CLI/gateway/TUI/desktop/cron, ~4.3s → ~0.9s) plus reasoning-stream-by-default; **smart approvals** on by default; **Bitwarden and 1Password `SecretSource`** integrations; live subagent transcripts and durable background-delegation delivery; gateway **delivery-obligation ledger**; **/subscription + /topup** terminal billing; **profile-based gateway message routing**; new models (GPT-5.6 Sol/Terra/Luna, grok-4.5 GA, kimi-k3, claude-fable-5, claude-sonnet-5); and a major desktop speed/security hardening round. Post-release stabilization (Jul 21–24): gateway stranded-platform recovery generalized to every adapter; clarify-request lifecycle unification (6 PRs) across CLI/TUI/desktop/gateway; desktop multi-profile session-identity fixes; Slack adapter unbounded-cache hardening; a production cron reconciliation fix closing a 20-hour silent-outage class; a skills system restructure (51KB monolith → ~12KB hub + 18 reference files); an org-skill namespace; two new context-engine ABC hooks; and MoA advisor fan-out fault tolerance. **Jul 25**: two real cross-session isolation bugs closed (a desktop background-queue drain that could deliver a message into the wrong session; a shared terminal bash snapshot that could leak one session's `HERMES_SESSION_ID` into another); a **crash-survivable in-flight turn journal** ships for desktop (streamed turn content now survives an app/machine crash); a gateway fix stops a slow cold-start build from silently discarding the user's first message; `hermes update` no longer stalls for minutes on large `state.db` files (measured 143.5s → 0.001s on a 30GB DB); and two state-recovery data-loss paths closed (cross-process quarantine race, oversized-DB pruning gap).
- Sources: https://github.com/NousResearch/hermes-agent/releases/tag/v2026.7.20, https://github.com/NousResearch/hermes-agent/commit/ef6ce56cad, https://github.com/NousResearch/hermes-agent/commit/062d261955, https://github.com/NousResearch/hermes-agent/commit/f2e32ceead, https://github.com/NousResearch/hermes-agent/commit/8d8d1d61fe, https://github.com/NousResearch/hermes-agent/commit/60c8fc6290, https://github.com/NousResearch/hermes-agent/commit/01232e8e21

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: **`2.1.219`** (Jul 24) sets **Claude Opus 5** as the default Opus model — 1M context, fast mode at $10/$50 per Mtok (Opus 4.7 removed from fast mode) — same day GitHub Copilot shipped Opus 5 across nine surfaces, making this a genuine cross-vendor model-launch event rather than a routine bump. Also in `2.1.219`: default nested-subagent spawn depth raised to 3 (from 1, override via `CLAUDE_CODE_MAX_SUBAGENT_SPAWN_DEPTH=1`), a new `sandbox.network.strictAllowlist` setting (deny non-allowlisted hosts for sandboxed commands without prompting), a `DirectoryAdded` hook firing after `/add-dir`, and MCP config validation now surfaces skipped-server errors in headless stream-json and `/mcp`. **`2.1.220`** (Jul 25) is bug-fix/reliability only. **`2.1.218`** (Jul 22) closed a real security gap: agent frontmatter hooks now require the *agent file's own folder* to have accepted workspace trust before running, not just the invoking session. **`2.1.217`** (Jul 21) added anti-runaway-fanout guardrails: a default cap of 20 concurrently-running subagents, no nested subagent spawning by default (superseded by `2.1.219`'s depth-3 default), and a working `--max-budget-usd` halt for background subagents.
- Sources: https://github.com/anthropics/claude-code/releases/tag/v2.1.219, https://github.com/anthropics/claude-code/releases/tag/v2.1.218, https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md

### Claude Tag
- Area: team agent surface / Slack-based delegated work
- Why it matters: moves Claude-style coding and knowledge work into shared channels with selected tool, data, and codebase access; useful as a mainstream signal for multiplayer, proactive, asynchronous agents
- Current watch note: Introduced June 23 in beta for Claude Team and Enterprise customers. Claude Tag starts in Slack, replaces the existing Claude in Slack app, lets teams tag `@Claude`, and is framed by Anthropic as an evolution of Claude Code toward proactive team workflows.
- Source: https://www.anthropic.com/news/introducing-claude-tag

### Claude Opus 5
- Area: frontier model tier for coding agents and long-horizon knowledge work
- Why it matters: affects Claude Code default model choice, GitHub Copilot model picker, provider routing, pricing, and high-complexity autonomous coding workflows
- Current watch note: Launched **Jul 24** and immediately set as Claude Code's default Opus model (`2.1.219`) — 1M context, fast mode at $10/$50 per Mtok, with Opus 4.7 removed from fast mode. Shipped **same day** in GitHub Copilot across nine surfaces (VS Code, Visual Studio, Copilot CLI, cloud agent, Copilot app, JetBrains, Xcode, Eclipse, github.com) for Pro+/Max/Business/Enterprise plans, billed at provider list price, with added safeguards on high-harm cyber-related requests. A genuine cross-vendor day-one launch rather than a staggered rollout.
- Sources: https://github.com/anthropics/claude-code/releases/tag/v2.1.219, https://github.blog/changelog/2026-07-24-claude-opus-5-is-now-available-in-github-copilot

### Anthropic Claude Fable 5 / Mythos 5
- Area: frontier model tier for coding agents and long-horizon knowledge work
- Why it matters: affects Claude Code, GitHub Copilot model choice, provider routing, governance, cost, data-retention review, and high-complexity autonomous coding workflows
- Current watch note: Export controls were lifted June 30 and global access restored July 1 with a plan-included promo window on Pro/Max/Team/eligible Enterprise plans (up to 50% of weekly usage limits at no extra cost, same pool as other models). That promo window has now been extended **twice** at the wire: original July 7 cutoff → moved to July 12 (announced July 7) → moved again to **July 19** (announced early July 13, after the July 12 deadline had already passed). Claude Code's 50% higher weekly rate limits extend alongside each Fable 5 extension. No forward commitment exists past July 19 — teams standardizing workflows on Fable 5 should not assume a stable cutoff date. Post-promo rate is $10/$50 per M tokens in/out on usage credits.
- Sources: https://www.anthropic.com/news/redeploying-fable-5, https://www.anthropic.com/news/fable-mythos-access, https://support.claude.com (help center, updated Jul 13)

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: **OpenAI launched Presence (Jul 22)**, its first managed enterprise product for deploying and governing AI voice/chat agents in production (policies, escalation rules, monitoring, guardrails bundled), in limited availability for eligible enterprise customers — a packaging/maturity signal distinct from CLI feature velocity. **Codex + ChatGPT Work crossed 8M active users** (Jul 14–15) following the GPT-5.6 launch (Jul 9). The surge forced real scaling rollbacks (5-hour cap removed for Plus/Business/Pro, context window cut back on Sol, reasoning-effort changes reverted). On top of that, OpenAI's new **unified ChatGPT/Codex desktop app is drawing widespread freeze reports on Windows after the July 17 update** — multiple independent OpenAI community and Reddit threads describe the app going fully unresponsive on every click ("Not Responding"), with separate reports of banked Codex usage resets disappearing from the UI in the same build. **CLI `0.145.0` shipped stable Jul 21** after two weeks of alpha churn since `0.144.6`: experimental paginated thread history with resume/search/persisted names/memories; `/import` expanded to migrate settings, MCP servers, plugins, sessions, and commands from **Cursor and Claude Code**; experimental Amazon Bedrock login with GPT-5.6 Sol as default Bedrock model; audio inputs/outputs and streaming realtime v3; multi-agent v2 stabilized. Alpha churn continued through Jul 23 (`0.146.0-alpha.1` → `alpha.4`) with no further stable tag and no release-worthy content in those alphas. Net effect: Codex is under real capacity/desktop-stability strain even as its user base, feature set, and enterprise product line grow fast — track reliability, not just feature velocity, before standardizing workflows on it.
- Sources: https://thenewstack.io/gpt-5-6-codex-user-surge/, https://www.reddit.com/r/codex/comments/1uyqbzl/probleme_lag_last_update/, https://community.openai.com/c/chatgpt/bugs/23, https://github.com/openai/codex/releases/tag/rust-v0.145.0, https://openai.com/index/introducing-openai-presence

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: **Jul 24**: **Claude Opus 5 shipped day-one** across VS Code, Visual Studio, Copilot CLI, cloud agent, the Copilot app, JetBrains, Xcode, and Eclipse (Pro+/Max/Business/Enterprise, gradual rollout, provider-list-price billing, with added safeguards on high-harm cyber content) — same-day as Opus 5 becoming Claude Code's default Opus. **Jul 23 update wave**: GitHub Issues gets agent-automation controls in public preview — "Approvals" (hold agent-suggested label/type/assign/close changes in a review panel instead of applying), "Confidence" tiers (high auto-applies, medium/low wait for human review), and "Rationale" (audit trail with `has:suggestions` search); and **Copilot cloud agent for Linear reached general availability** — Linear issues can be assigned directly to Copilot's async background agent, which opens a draft PR from its own ephemeral GitHub Actions environment, streams progress to the Linear activity timeline, and supports per-issue model choice, custom agents, base/working-branch control, and mid-session steering via comment mentions. **Gemini 3.6 Flash rolled out July 21** across VS Code, Visual Studio, Copilot CLI, cloud agent, the Copilot app, JetBrains, Xcode, and Eclipse — configurable reasoning effort, parallel tool use, better task-completion and token efficiency than 3.5 Flash.
- Sources: https://github.blog/changelog/2026-07-24-claude-opus-5-is-now-available-in-github-copilot, https://github.blog/changelog/2026-07-23-agent-automation-controls-in-github-issues-in-public-preview/, https://github.blog/changelog/2026-07-23-copilot-cloud-agent-for-linear-is-now-generally-available/, https://github.blog/changelog/2026-07-21-gemini-3-6-flash-is-now-available-in-github-copilot

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
- Current watch note: The **MCP 2026-07-28 release candidate** is the largest spec revision since launch and remains in its validation window (RC locked May 21; final ships **July 28, 2026** — unchanged). Key changes: stateless HTTP core (removes `initialize`/`initialized` handshake and `Mcp-Session-Id` — any server instance can handle any request); MCP Apps (server-rendered UIs via a new extension); Tasks extension now first-class; OAuth/OIDC-aligned authorization; JSON Schema 2020-12 support for tool schemas; W3C Trace Context propagation standardized; `ttlMs`/`cacheScope` on list results; formal deprecation policy (12-month window minimum). Impact: this is a **breaking change** for existing MCP implementations. **Jul 23 update: GitHub MCP Server shipped concrete stateless-core support ahead of the deadline** — Redis-backed sessions removed entirely (no DB writes on `initialize`, no DB reads per call), deep packet inspection replaced with guaranteed HTTP-header fields for logging/secret-scanning, and its stdio elicitation flow upgraded to the new multi-round-trip HTTP elicitation with a Go SDK compatibility wrapper for old/new clients. Tier 1 SDKs have all shipped backward-compatible beta support; official conformance tests were also added. Enterprise-Managed Authorization (centralizing MCP server access through an IdP) remains stable.
- Sources: https://modelcontextprotocol.io/, https://blog.modelcontextprotocol.io/posts/2026-07-28-release-candidate/, https://github.blog/changelog/2026-07-23-github-mcp-server-supports-the-next-mcp-specification/

### Skills Over MCP
- Area: MCP-based agent skill discovery / portability
- Why it matters: connects portable agent skills with MCP registry, spec, SDK, and client behavior instead of leaving skills locked to individual hosts
- Current watch note: A June 30 MCP Working Session focuses on how "agent skills" can be discovered and consumed through MCP, with SEP-2640 called out as the near-term focus through June 2026.
- Source: https://meet.modelcontextprotocol.io/2026/06/skills-over-mcp-working-session-bi-weekly--WrKrEDAM75hr

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.