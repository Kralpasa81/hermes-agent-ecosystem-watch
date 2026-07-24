# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: **v0.19.0 / v2026.7.20 — "The Quicksilver Release"** (tagged Jul 20, 2026) remains the latest tagged release; post-release stabilization continues through Jul 24 with no version bump yet. Headline changes at release: **~80% cold-start first-token latency cut** (CLI/gateway/TUI/desktop/cron, ~4.3s → ~0.9s) plus reasoning-stream-by-default; **smart approvals** on by default; **Bitwarden and 1Password `SecretSource`** integrations; live subagent transcripts and durable background-delegation delivery; gateway **delivery-obligation ledger**; **/subscription + /topup** terminal billing; **profile-based gateway message routing**; new models (GPT-5.6 Sol/Terra/Luna, grok-4.5 GA, kimi-k3, claude-fable-5, claude-sonnet-5); and a major desktop speed/security hardening round. Post-release stabilization (Jul 21–24): gateway stranded-platform recovery generalized to every adapter; clarify-request lifecycle unification (6 PRs) across CLI/TUI/desktop/gateway; desktop multi-profile session-identity fixes; Slack adapter unbounded-cache hardening; and, as of Jul 24, a **production cron reconciliation fix** closing a 20-hour silent-outage class (direct-run/scheduled-fire race left recurring jobs orphaned while `/api/status` stayed green), a **skills system restructure** (the core `hermes-agent` skill shrank from a 51KB monolith to a ~12KB hub + 18 reference files), an **org-skill namespace** (token-gated discovery, fail-loud collisions, provenance), two new optional **context-engine ABC hooks** (`select_context()`, `on_turn_complete()`), and **MoA advisor fan-out fault tolerance** (contained failures, all-failed short-circuit, interrupt handling).
- Sources: https://github.com/NousResearch/hermes-agent/releases/tag/v2026.7.20, https://github.com/NousResearch/hermes-agent/commit/ef6ce56cad, https://github.com/NousResearch/hermes-agent/commit/e3d524b482, https://github.com/NousResearch/hermes-agent/pull/70459, https://github.com/NousResearch/hermes-agent/pull/70281

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: **`2.1.218`** (Jul 22) closes a real security gap: agent frontmatter hooks now require the *agent file's own folder* to have accepted workspace trust before running, not just the invoking session. Also changes `/code-review` to run as a background subagent (keeps stacked slash commands as its target instead of filling the conversation), fixes a fork-session-lineage loss after compaction in headless/SDK sessions, and fixes a resumed session crashing/failing every turn on a malformed history delta. **`2.1.217`** (Jul 21) adds real anti-runaway-fanout guardrails: a default cap of 20 concurrently-running subagents (`CLAUDE_CODE_MAX_CONCURRENT_SUBAGENTS`), subagents no longer spawn nested subagents by default (`CLAUDE_CODE_MAX_SUBAGENT_SPAWN_DEPTH` to override), and `--max-budget-usd` now actually halts running background subagents once the cap is reached (previously it didn't). Also fixes a memory leak from truncated MCP tool outputs staying fully in memory, and Windows auto-update failures that could leave `claude.exe` missing. **`2.1.216`** (Jul 20) fixes a real long-session performance regression — message normalization cost was growing **quadratically** with turn count, causing multi-second stalls and slow resumes. Also adds `sandbox.filesystem.disabled` (skip filesystem isolation, keep network egress control) and closes a Bash permission-check bypass for compound statements with redirects inside `&&` lists or negations, plus worktree-isolated subagent git-redirect bypass (via `git -C`/`--git-dir`/`GIT_DIR`) and several session/background-agent recovery correctness fixes.
- Sources: https://github.com/anthropics/claude-code/releases/tag/v2.1.218, https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md

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
- Current watch note: **OpenAI launched Presence (Jul 22)**, its first managed enterprise product for deploying and governing AI voice/chat agents in production (policies, escalation rules, monitoring, guardrails bundled), in limited availability for eligible enterprise customers — a packaging/maturity signal distinct from CLI feature velocity. **Codex + ChatGPT Work crossed 8M active users** (Jul 14–15) following the GPT-5.6 launch (Jul 9). The surge forced real scaling rollbacks (5-hour cap removed for Plus/Business/Pro, context window cut back on Sol, reasoning-effort changes reverted). On top of that, OpenAI's new **unified ChatGPT/Codex desktop app is drawing widespread freeze reports on Windows after the July 17 update** — multiple independent OpenAI community and Reddit threads describe the app going fully unresponsive on every click ("Not Responding"), with separate reports of banked Codex usage resets disappearing from the UI in the same build. **CLI `0.145.0` shipped stable Jul 21** after two weeks of alpha churn since `0.144.6`: experimental paginated thread history with resume/search/persisted names/memories; `/import` expanded to migrate settings, MCP servers, plugins, sessions, and commands from **Cursor and Claude Code**; experimental Amazon Bedrock login with GPT-5.6 Sol as default Bedrock model; audio inputs/outputs and streaming realtime v3; multi-agent v2 stabilized. Alpha churn continued through Jul 23 (`0.146.0-alpha.1` → `alpha.4`) with no further stable tag and no release-worthy content in those alphas. Net effect: Codex is under real capacity/desktop-stability strain even as its user base, feature set, and enterprise product line grow fast — track reliability, not just feature velocity, before standardizing workflows on it.
- Sources: https://thenewstack.io/gpt-5-6-codex-user-surge/, https://www.reddit.com/r/codex/comments/1uyqbzl/probleme_lag_last_update/, https://community.openai.com/c/chatgpt/bugs/23, https://github.com/openai/codex/releases/tag/rust-v0.145.0, https://openai.com/index/introducing-openai-presence

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: **Jul 23 update wave**: GitHub Issues gets agent-automation controls in public preview — "Approvals" (hold agent-suggested label/type/assign/close changes in a review panel instead of applying), "Confidence" tiers (high auto-applies, medium/low wait for human review), and "Rationale" (audit trail with `has:suggestions` search); and **Copilot cloud agent for Linear reached general availability** — Linear issues can be assigned directly to Copilot's async background agent, which opens a draft PR from its own ephemeral GitHub Actions environment, streams progress to the Linear activity timeline, and supports per-issue model choice, custom agents, base/working-branch control, and mid-session steering via comment mentions. **Gemini 3.6 Flash rolled out July 21** across VS Code, Visual Studio, Copilot CLI, cloud agent, the Copilot app, JetBrains, Xcode, and Eclipse — configurable reasoning effort, parallel tool use, better task-completion and token efficiency than 3.5 Flash. **July 17**: Copilot code review now runs behind a firewall with custom setup and independent runner configuration, and reads custom review instructions from the PR's head branch. **July 14**: JetBrains BYOK expansion (custom OpenAI-compatible endpoints, Claude agent-provider customizations, local sandboxing, built-in CLI debugger skill); `/security-review` slash command in the Copilot app (public preview).
- Sources: https://github.blog/changelog/2026-07-23-agent-automation-controls-in-github-issues-in-public-preview/, https://github.blog/changelog/2026-07-23-copilot-cloud-agent-for-linear-is-now-generally-available/, https://github.blog/changelog/2026-07-21-gemini-3-6-flash-is-now-available-in-github-copilot, https://github.blog/changelog/2026-07-17-copilot-code-review-customization-and-configurability-improvements/

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