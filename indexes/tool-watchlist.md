# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: June 6 brought Hermes Agent v0.16.0 / `v2026.6.5` (“The Surface Release”): native desktop app, remote gateway auth, concurrent multi-profile desktop sessions, browser admin panel, Quick Setup via Nous Portal, fuzzy model picker, `/undo`, a leaner default skill set, NVIDIA/skills trusted tap, and security/reliability hardening. Post-release main branch added usage-aware credits, custom profile aliases, desktop auxiliary-provider warnings, delegate content-block fixes, and ntfy target handling.
- Source: https://github.com/NousResearch/hermes-agent

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: June 6 review of the latest changelog highlighted `fallbackModel` support, cross-session messaging hardening, managed version-range settings, MCP/session environment handling, and terminal / remote-session reliability fixes.
- Source: https://www.anthropic.com/claude-code

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: June 4 Codex CLI 0.137.0 added cloud-managed config, monthly credit-limit visibility, remote-control grant APIs, JSON plugin listing, hosted web/image tools in more code-mode flows, and multi-agent v2 refinements. June 2 product updates also introduced role-specific plugins, annotations, Codex Sites preview, and OpenAI framed Codex as expanding beyond developers into knowledge-worker productivity with more than 5M weekly active users.
- Source: https://developers.openai.com/codex

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: June 5 review captured June 4/June 2 Copilot agent moves: Agent tasks REST API public preview for Pro/Pro+/Max, one-million-token context windows, configurable reasoning levels, code review MCP + custom agent skills support, and deeper Medium review tier.
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
- Current watch note: June 6 review promoted the MCP 2026-07-28 release candidate as a high-signal interoperability update with breaking changes: stateless HTTP-friendly core, MCP Apps for server-rendered UI, Tasks for long-running work, OAuth/OIDC-aligned authorization, JSON Schema 2020-12 support, and a formal deprecation policy. June 5 also noted an active individual IETF Internet-Draft on MCP security considerations; it has no formal IETF standing but remains a useful risk signal.
- Source: https://modelcontextprotocol.io/

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.
