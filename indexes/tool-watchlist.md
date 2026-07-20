# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: `v0.18.2` / `v2026.7.7.2` remains the latest tagged release; curated v0.19.0 release notes for the post-v0.18.0 window are still pending. On `main`, the gateway gained a **durable delivery-obligation ledger** for final responses (#67181, Jul 19): a response generated but not yet confirmed-delivered was previously the one artifact a gateway crash or planned restart could lose without a trace, forcing an expensive full-turn re-run on resume. `gateway/delivery_ledger.py` records every outbound final response in `state.db` before the first send attempt, sweeps dead-owner rows on startup, and redelivers with an explicit "♻️ Recovered reply — may be a duplicate" label rather than silently retrying. A same-day-plus-one follow-up (Jul 20) closed a real gap in that ledger: `sweep_recoverable()` incremented the capped `attempts` counter on every claim even when the target platform's adapter wasn't connected this boot, so a platform that was down at startup could burn all 3 redelivery attempts with zero actual sends and get permanently abandoned — exactly the loss the ledger exists to prevent. The fix lets callers declare which platforms can actually send this boot, skipping claims for the rest. Also on Jul 20: a streaming fix now catches text-only stream drops that end with HTTP 200 and no `finish_reason` (previously silently treated as complete), and an MCP auto-reload opt-out toggle (`mcp.auto_reload_on_config_change`) landed after two same-day relocations to the correct config section. Use `hermes update` or `pip install -U hermes-agent` to pick up tagged releases.
- Sources: https://github.com/NousResearch/hermes-agent/releases/tag/v2026.7.7.2, https://github.com/NousResearch/hermes-agent/commit/5854aad8b5, https://github.com/NousResearch/hermes-agent/commit/371ee065fd, https://github.com/NousResearch/hermes-agent/commit/65bb16c8ce

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: **`2.1.215`** (Jul 19) stops Claude from auto-running the `/verify` and `/code-review` skills on its own — they now require explicit invocation. **`2.1.214`** (Jul 18) closes several real permission-check bypasses: single-segment `dir/**` allow rules (e.g. `Edit(src/**)`) were auto-approving writes to any nested `dir/` anywhere in the tree instead of only `<cwd>/dir`; a Windows PowerShell 5.1 permission-check bypass; Bash checks now fail closed on file-descriptor redirect forms parsed differently by bash than the analyzer; commands over 10,000 characters now always prompt; zsh variable subscripts/modifiers in `[[ ]]` were being treated as inert text (now prompt); certain `help`/`man` invocations could auto-approve unsafe options (now fixed). Also adds an `EndConversation` tool for abusive/jailbreak sessions. **`2.1.212`** (Jul 17) added a session-wide WebSearch call cap (default 200, `CLAUDE_CODE_MAX_WEB_SEARCHES_PER_SESSION`) and a per-session subagent-spawn cap (default 200, `CLAUDE_CODE_MAX_SUBAGENTS_PER_SESSION`) to stop runaway search/delegation loops; MCP tool calls running over 2 minutes now auto-background so the session stays usable; `/fork` now copies a conversation into a real background session instead of an in-session subagent (that role moves to `/subtask`). **`2.1.210`** (Jul 15) closed a worktree-isolation bypass for subagents and hardened the Agent tool against indirect prompt injection. Weekly rate limits were raised 50% through the Claude Fable 5 promo window (through July 19; no further extension confirmed as of writing).
- Sources: https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md, https://github.com/anthropics/claude-code/releases

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
- Current watch note: **Codex + ChatGPT Work crossed 8M active users** (Jul 14–15) following the GPT-5.6 launch (Jul 9). The surge forced real scaling rollbacks (5-hour cap removed for Plus/Business/Pro, context window cut back on Sol, reasoning-effort changes reverted). On top of that, OpenAI's new **unified ChatGPT/Codex desktop app is drawing widespread freeze reports on Windows after the July 17 update** — multiple independent OpenAI community and Reddit threads describe the app going fully unresponsive on every click ("Not Responding"), with separate reports of banked Codex usage resets disappearing from the UI in the same build. CLI: `0.144.6` (Jul 18) was a targeted backport correcting bundled instructions and context windows (272,000 tokens) for GPT-5.6 Sol/Terra/Luna; `0.145.0` remains in alpha (24+ pre-release tags, no stable cut yet). Net effect: Codex is under real capacity and desktop-stability strain even as its user base grows fast — track reliability, not just feature velocity, before standardizing workflows on it.
- Sources: https://thenewstack.io/gpt-5-6-codex-user-surge/, https://www.reddit.com/r/codex/comments/1uyqbzl/probleme_lag_last_update/, https://community.openai.com/c/chatgpt/bugs/23, https://github.com/openai/codex/releases/tag/rust-v0.144.6

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: **July 17 update**: Copilot code review now runs behind a firewall with custom setup steps and independent runner configuration, and reads custom review instructions from the PR's head branch (not just the base) so instruction changes can be tested in the same PR that introduces them. **July 14 update wave**: GitHub Copilot for JetBrains BYOK expansion — custom OpenAI-compatible endpoint support, Claude agent-provider customizations (custom agents/skills/instructions, public preview), local sandboxing settings, built-in Copilot CLI debugger skill; `/security-review` slash command shipped in the Copilot app (public preview, Free/Pro/Business/Enterprise). Earlier **July 7–9 wave**: Copilot app opened to all users; Kimi K2.7 for Business/Enterprise; GPT-5.6 Sol, Terra, and Luna rolled out across all major surfaces. The **VS Code June 2026 release bundle** (v1.123–v1.127) added agentic browser tools GA, parallel agent sessions, full session cost visibility, 1M context for Anthropic/OpenAI models, and MCP OAuth credential storage.
- Sources: https://github.blog/changelog/2026-07-17-copilot-code-review-customization-and-configurability-improvements/, https://github.blog/changelog/2026-07-14-github-copilot-for-jetbrains-expands-byok-capabilities, https://github.blog/changelog/2026-07-14-security-reviews-now-available-in-the-github-copilot-app

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