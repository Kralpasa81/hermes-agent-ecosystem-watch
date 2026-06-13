# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: June 13 main-branch work focused on Desktop/TUI reliability after the Surface release: honoring `provider_routing` config in the Desktop/TUI backend, recovering queued prompts across transient `session busy` and backend-bounce states, improving streaming/rendering performance, preserving recent turns during context compression, hardening profile update/gateway restart behavior, and expanding messaging/tool support for Telegram rich messages, Teams attachments, Yuanbao forwarded WeChat messages, binary-file errors, and `/credits`.
- Source: https://github.com/NousResearch/hermes-agent

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: June 13 review captured Claude Code `2.1.176`: alias model picks can no longer redirect to disallowed models via `ANTHROPIC_DEFAULT_*_MODEL`, `/fast` refuses switches outside allowlists, auto mode falls back when Fable 5 is unavailable for an organization, Remote Control no longer silently switches a session model, background-agent/session recovery improved, hook path matching was fixed, Bedrock credential caching now respects expiration, and several Windows/Linux/tmux reliability issues were addressed.
- Source: https://raw.githubusercontent.com/anthropics/claude-code/main/CHANGELOG.md

### Anthropic Claude Fable 5 / Mythos 5
- Area: frontier model tier for coding agents and long-horizon knowledge work
- Why it matters: affects Claude Code, GitHub Copilot model choice, provider routing, governance, cost, data-retention review, and high-complexity autonomous coding workflows
- Current watch note: Announced June 9, then materially changed on June 12. Anthropic says a US government export-control directive requires suspending access to Fable 5 and Mythos 5 for all customers, while access to other Anthropic models is not affected. This changes the availability picture for Claude Code, Copilot model choice, provider routing, and teams evaluating Mythos-class coding workflows.
- Sources: https://www.anthropic.com/news/claude-fable-5-mythos-5, https://www.anthropic.com/news/fable-mythos-access

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: June 12 review captured Codex app `26.609`: Developer mode for Browser use with controlled Chrome DevTools Protocol access, up to 2x faster browser use via CDP and DOM snapshot optimizations, `/init` in the app composer, expanded Computer Use availability/access controls, better plugin management, improved usage-limit errors, and scheduled automations honoring selected approval mode.
- Source: https://developers.openai.com/codex/changelog

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
