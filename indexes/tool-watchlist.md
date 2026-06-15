# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: June 15 main-branch work focused on operational reliability after the Surface release: profile gateway supervision no longer lets the reserved default gateway follow sticky `active_profile`, profile gateways can be registered without auto-starting, desired state is persisted, stale log locks are cleared before startup, profile-gateway log parents are made writable, dashboard reroutes are pinned to the machine root, dashboard restarts no longer depend on an `is_container` check, and Windows updates kill Hermes before venv recreation to release locked `_bcrypt.pyd` files.
- Source: https://github.com/NousResearch/hermes-agent

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: June 14 review found `v2.1.177` published, but the GitHub release body exposed no release notes during the check. The previous documented high-signal release remains `2.1.176`: model allowlist enforcement, `/fast` policy handling, Remote Control model-switch correctness, background-agent/session recovery, hook path matching, Bedrock credential caching, and Windows/Linux/tmux reliability fixes.
- Sources: https://github.com/anthropics/claude-code/releases/tag/v2.1.177, https://raw.githubusercontent.com/anthropics/claude-code/main/CHANGELOG.md

### Anthropic Claude Fable 5 / Mythos 5
- Area: frontier model tier for coding agents and long-horizon knowledge work
- Why it matters: affects Claude Code, GitHub Copilot model choice, provider routing, governance, cost, data-retention review, and high-complexity autonomous coding workflows
- Current watch note: Announced June 9, then materially changed on June 12. Anthropic says a US government export-control directive requires suspending access to Fable 5 and Mythos 5 for all customers, while access to other Anthropic models is not affected. This changes the availability picture for Claude Code, Copilot model choice, provider routing, and teams evaluating Mythos-class coding workflows.
- Sources: https://www.anthropic.com/news/claude-fable-5-mythos-5, https://www.anthropic.com/news/fable-mythos-access

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: June 14 review captured active `0.140.0-alpha` repo/release work. `rust-v0.140.0-alpha.19` was published with nearby commits around remote exec-server cwd/shell correctness, native cross-platform path rendering, plugin MCP de-duplication by app declaration name, compact-request turn-state propagation, and bundled SQLite WAL-reset handling. Keep treating this as alpha/infrastructure signal unless reflected in the official Codex product changelog.
- Sources: https://github.com/openai/codex/releases/tag/rust-v0.140.0-alpha.19, https://developers.openai.com/codex/changelog

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: June 13 review captured Copilot code review governance upgrades: organization-level runner configuration for Copilot code review / Copilot cloud agent, support for Copilot content exclusions at repository/org/enterprise scope, and removal of the 4,000-character limit for Copilot code review custom instruction files. June 11 Agentic Workflows public preview and `GITHUB_TOKEN` support remain the strongest infrastructure signal.
- Sources: https://github.com/features/copilot, https://github.blog/changelog/2026-06-12-copilot-code-review-new-configurations-and-controls

### GitHub Copilot SDK
- Area: embeddable agent runtime / developer SDK
- Why it matters: stable programmatic access to Copilot planning, tool invocation, file edits, streaming, multi-turn sessions, custom tools, MCP servers, hooks, tracing, BYOK, and cloud/remote sessions
- Current watch note: General availability was announced on June 2, with SDK support across six language stacks and new Rust/Java availability called out at GA.
- Source: https://github.blog/changelog/2026-06-02-copilot-sdk-is-now-generally-available

### GitHub Agentic Workflows
- Area: GitHub Actions-native agentic engineering automation
- Why it matters: brings reasoning-based agents into governed CI/CD infrastructure for triage, CI failure analysis, documentation updates, security remediation, dependency maintenance, routine change review, reporting, and compliance
- Current watch note: Public preview was announced June 11. Workflows are written in natural-language Markdown, compiled into standard GitHub Actions YAML, run with read-only defaults and sandboxing, and can use `GITHUB_TOKEN` instead of long-lived PATs with organization billing via `copilot-requests: write`.
- Source: https://github.blog/changelog/2026-06-11-github-agentic-workflows-is-now-in-public-preview

### OpenAI Codex Sites
- Area: Codex-hosted app/site canvas
- Why it matters: extends Codex from coding tasks into hosted interactive sites, dashboards, internal tools, lightweight apps, and games that can be shared within a workspace
- Current watch note: Announced as a June 2 preview inside the Codex app alongside role-specific plugins and annotations.
- Source: https://openai.com/index/codex-for-every-role-tool-workflow/

### MCP ecosystem
- Area: protocol / tool interoperability layer
- Why it matters: increasingly central to connecting agents with external tools and services
- Current watch note: June 6 review promoted the MCP 2026-07-28 release candidate as a high-signal interoperability update with breaking changes: stateless HTTP-friendly core, MCP Apps for server-rendered UI, Tasks for long-running work, OAuth/OIDC-aligned authorization, JSON Schema 2020-12 support, and a formal deprecation policy. June 5 also noted an active individual IETF Internet-Draft on MCP security considerations; it has no formal IETF standing but remains a useful risk signal.
- Source: https://modelcontextprotocol.io/

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.
