# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: June 4 main-branch activity focused on dashboard auth, self-hosted OAuth registration, OAuth-aware remote gateway handling, desktop provider/account UX, attachment/IME/streaming reliability, Docker/Matrix deployment fixes, memory setup fallback behavior, and Windows path handling. Latest tag remains v2026.5.29.2.
- Source: https://github.com/NousResearch/hermes-agent

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Source: https://www.anthropic.com/claude-code

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: June 4 Codex CLI 0.137.0 added cloud-managed config, monthly credit-limit visibility, remote-control grant APIs, JSON plugin listing, hosted web/image tools in more code-mode flows, and multi-agent v2 refinements. June 2 product updates also introduced role-specific plugins, annotations, and Codex Sites preview.
- Source: https://developers.openai.com/codex

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: June 3 VS Code Copilot updates moved the Agents window into Stable preview and emphasized remote agents over SSH/Dev Tunnels, session sync, `/chronicle`, BYOK including air-gapped environments, and terminal safety. June 2 Copilot announcements also included Copilot SDK GA, sandboxes, cloud-agent automations, agent apps, and CLI updates.
- Source: https://github.com/features/copilot

### GitHub Copilot SDK
- Area: embeddable agent runtime / developer SDK
- Why it matters: stable programmatic access to Copilot planning, tool invocation, file edits, streaming, multi-turn sessions, custom tools, MCP servers, hooks, tracing, BYOK, and cloud/remote sessions
- Current watch note: General availability was announced on June 2, with SDK support across six language stacks and new Rust/Java availability called out at GA.
- Source: https://github.blog/changelog/2026-06-02-copilot-sdk-is-now-generally-available

### OpenAI Codex Sites
- Area: Codex-hosted app/site canvas
- Why it matters: extends Codex from coding tasks into hosted interactive sites, dashboards, internal tools, lightweight apps, and games that can be shared within a workspace
- Current watch note: Announced as a June 2 preview inside the Codex app alongside role-specific plugins and annotations.
- Source: https://openai.com/index/codex-for-every-role-tool-workflow/

### MCP ecosystem
- Area: protocol / tool interoperability layer
- Why it matters: increasingly central to connecting agents with external tools and services
- Source: https://modelcontextprotocol.io/

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.
