# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: June 10 main-branch work improved Skills Hub browsing with live per-source progress and bounded ClawHub catalog walks, added/clarified memory + skill write approvals, continued Desktop/remote-session polish, hardened gateway/container restart and dashboard-auth behavior, and updated provider/model metadata for Claude Fable 5 and MiniMax M3.
- Source: https://github.com/NousResearch/hermes-agent

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: June 10 review captured Claude Code `2.1.170`, which adds access to Claude Fable 5 and fixes transcript saving for sessions launched from VS Code integrated terminals or inherited Claude Code shells. The June 9 `2.1.169` safe-mode, `/cd`, bundled-skill hiding, and enterprise MCP policy fixes remain important.
- Source: https://raw.githubusercontent.com/anthropics/claude-code/main/CHANGELOG.md

### Anthropic Claude Fable 5 / Mythos 5
- Area: frontier model tier for coding agents and long-horizon knowledge work
- Why it matters: affects Claude Code, GitHub Copilot model choice, provider routing, governance, cost, data-retention review, and high-complexity autonomous coding workflows
- Current watch note: Announced June 9. Fable 5 is the generally available Mythos-class model; Mythos 5 is the trusted-access version for selected high-risk domains. Fable 5 is available in Claude Code `2.1.170` and GitHub Copilot, where Business/Enterprise admins must explicitly enable it and accept the model-specific retention requirement.
- Source: https://www.anthropic.com/news/claude-fable-5-mythos-5

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: June 10 review captured ChatGPT for iOS `1.2026.153` Codex Mobile updates: branch selection, worktree creation, environment setup scripts for new threads, Codex usage/token activity, `/goal`, inline review comments, side chat from transcript selections, latest-prompt editing, better Windows-host attachments, and inline skills/plugins in the composer. June 9 CLI `0.138.0` Desktop handoff and plugin JSON improvements remain relevant.
- Source: https://developers.openai.com/codex/changelog

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: June 10 review captured two June 9 high-signal changes: Claude Fable 5 became available across Copilot surfaces with admin enablement and retention caveats, and security validation for third-party coding agents became generally available, extending CodeQL, dependency, and secret-scanning checks to agents such as Claude and OpenAI Codex.
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
