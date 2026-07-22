# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: **v0.19.0 / v2026.7.20 — "The Quicksilver Release"** (tagged Jul 20, 2026). This is the first tagged release since v0.18.2 (Jul 8) and the largest in the window tracked by this repo. Headline changes: **~80% cold-start first-token latency cut** (CLI/gateway/TUI/desktop/cron, ~4.3s → ~0.9s) plus reasoning-stream-by-default; **smart approvals** are now on by default (LLM reviewer judges flagged commands, paired with user-defined deny rules and `/deny <reason>`); **Bitwarden and 1Password `SecretSource`** integrations for secrets-from-vault instead of plaintext `.env`; **live subagent transcripts** and durable background-delegation delivery (a completing `delegate_task` result now survives a mid-run restart); the gateway's durable **delivery-obligation ledger** (first tracked Jul 19) ships as part of this release; **/subscription + /topup** in the terminal for managing Nous plans without leaving the keyboard; **profile-based gateway message routing** (one bot token → multiple isolated profiles); new models: GPT-5.6 Sol/Terra/Luna, grok-4.5 GA, kimi-k3, claude-fable-5, claude-sonnet-5; desktop-app speed wave (14× less markdown-splitter CPU, virtualized diff review pane, session-switch without layout thrash); and a major security hardening round. Post-release stabilization (Jul 21–22): `fix(relay)` #68320 closed a total-loss-of-service bug for managed Discord agents' guild replies (Jul 21); `fix(gateway)` #69112 (Jul 22) generalized that same "stranded platform" recovery to every adapter (Discord/Telegram/qqbot/photon) — the gateway now hard-exits if a platform ends up neither reconnected nor queued after a fatal error, so process managers actually restart it; `fix(update)` #69117 stopped one slow gateway unit from aborting a whole fleet restart; a cold-resume session-duplication bug (`/new`/`/resume`/`/branch` right after resume) was fixed; and three related compaction-pipeline correctness fixes landed. Desktop app now supports multi-window (`⌘⇧N` opens a full peer window).
- Sources: https://github.com/NousResearch/hermes-agent/releases/tag/v2026.7.20, https://github.com/NousResearch/hermes-agent/commit/f4df260f26c93f15694698869f3ea8e965eea301, https://github.com/NousResearch/hermes-agent/commit/2ab153218ba401525ec02380305f8c3c4c8b1dc0

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: **`2.1.217`** (Jul 21) adds real anti-runaway-fanout guardrails: a default cap of 20 concurrently-running subagents (`CLAUDE_CODE_MAX_CONCURRENT_SUBAGENTS`), subagents no longer spawn nested subagents by default (`CLAUDE_CODE_MAX_SUBAGENT_SPAWN_DEPTH` to override), and `--max-budget-usd` now actually halts running background subagents once the cap is reached (previously it didn't). Also fixes a memory leak from truncated MCP tool outputs staying fully in memory, and Windows auto-update failures that could leave `claude.exe` missing. **`2.1.216`** (Jul 20) fixes a real long-session performance regression — message normalization cost was growing **quadratically** with turn count, causing multi-second stalls and slow resumes. Also adds `sandbox.filesystem.disabled` (skip filesystem isolation, keep network egress control) and closes a Bash permission-check bypass for compound statements with redirects inside `&&` lists or negations, plus worktree-isolated subagent git-redirect bypass (via `git -C`/`--git-dir`/`GIT_DIR`) and several session/background-agent recovery correctness fixes. **`2.1.215`** (Jul 19) stops Claude from auto-running `/verify` and `/code-review` skills. **`2.1.214`** (Jul 18) closes multiple real permission-check bypasses: nested-directory allow-rule bypass (`Edit(src/**)` wrongly matching any `dir/` in the tree), Windows PowerShell 5.1 bypass, Bash FD-redirect and 10k+ char command blind spots, and an `EndConversation` tool for abusive sessions.
- Sources: https://github.com/anthropics/claude-code/releases/tag/v2.1.217, https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md

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
- Current watch note: **Codex + ChatGPT Work crossed 8M active users** (Jul 14–15) following the GPT-5.6 launch (Jul 9). The surge forced real scaling rollbacks (5-hour cap removed for Plus/Business/Pro, context window cut back on Sol, reasoning-effort changes reverted). On top of that, OpenAI's new **unified ChatGPT/Codex desktop app is drawing widespread freeze reports on Windows after the July 17 update** — multiple independent OpenAI community and Reddit threads describe the app going fully unresponsive on every click ("Not Responding"), with separate reports of banked Codex usage resets disappearing from the UI in the same build. **CLI `0.145.0` shipped stable Jul 21** after two weeks of alpha churn since `0.144.6`: experimental paginated thread history with resume/search/persisted names/memories; `/import` expanded to migrate settings, MCP servers, plugins, sessions, and commands from **Cursor and Claude Code**; experimental Amazon Bedrock login with GPT-5.6 Sol as default Bedrock model; audio inputs/outputs and streaming realtime v3; multi-agent v2 stabilized. Alpha churn resumed immediately (`0.146.0-alpha.1/2`, Jul 22). Net effect: Codex is under real capacity/desktop-stability strain even as its user base and feature set grow fast — track reliability, not just feature velocity, before standardizing workflows on it.
- Sources: https://thenewstack.io/gpt-5-6-codex-user-surge/, https://www.reddit.com/r/codex/comments/1uyqbzl/probleme_lag_last_update/, https://community.openai.com/c/chatgpt/bugs/23, https://github.com/openai/codex/releases/tag/rust-v0.145.0

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: **Gemini 3.6 Flash rolled out July 21** across VS Code, Visual Studio, Copilot CLI, cloud agent, the Copilot app, JetBrains, Xcode, and Eclipse — configurable reasoning effort, parallel tool use, and per-GitHub testing, better task-completion and token efficiency than Gemini 3.5 Flash on coding/agentic workflows; billed at provider list pricing. **July 17 update**: Copilot code review now runs behind a firewall with custom setup steps and independent runner configuration, and reads custom review instructions from the PR's head branch (not just the base) so instruction changes can be tested in the same PR that introduces them. **July 14 update wave**: GitHub Copilot for JetBrains BYOK expansion — custom OpenAI-compatible endpoint support, Claude agent-provider customizations (custom agents/skills/instructions, public preview), local sandboxing settings, built-in Copilot CLI debugger skill; `/security-review` slash command shipped in the Copilot app (public preview, Free/Pro/Business/Enterprise).
- Sources: https://github.blog/changelog/2026-07-21-gemini-3-6-flash-is-now-available-in-github-copilot, https://github.blog/changelog/2026-07-17-copilot-code-review-customization-and-configurability-improvements/, https://github.blog/changelog/2026-07-14-github-copilot-for-jetbrains-expands-byok-capabilities

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