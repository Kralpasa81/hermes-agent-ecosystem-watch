# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: June 9 main-branch work added remote-gateway file attachments via `file.attach`, persisted Nous recommended models to disk with Portal-failure fallback, expanded curated OpenRouter model choices, tightened terminal backend/progress behavior, and improved Photon voice-message / Spectrum-backend handling. A new Desktop/Dashboard MCP discovery issue is also on watch.
- Source: https://github.com/NousResearch/hermes-agent

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: June 9 review of `2.1.169` highlighted `--safe-mode` / `CLAUDE_CODE_SAFE_MODE`, `/cd`, `disableBundledSkills`, stronger enterprise MCP allow/deny enforcement, better background-session state, and restored idle timeout behavior for stalled Vertex/Foundry streams.
- Source: https://raw.githubusercontent.com/anthropics/claude-code/main/CHANGELOG.md

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: June 9 review captured Codex CLI `0.138.0`: `/app` handoff from CLI threads into Codex Desktop on macOS/native Windows, Windows workspace launches into Desktop, improved local/generated image file references, token-usage access for app-server integrations, v2 personal access tokens, richer plugin JSON output, and startup/MCP credential resilience fixes.
- Source: https://developers.openai.com/codex/changelog

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
