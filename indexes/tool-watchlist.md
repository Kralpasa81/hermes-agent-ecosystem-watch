# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: `v0.18.0` / `v2026.7.1` (“The Judgment Release”) is now the public release baseline. The release is high-signal for first-class Mixture-of-Agents model selection, visible reference-model reasoning with streamed aggregation, evidence-based completion verification, `/goal` completion contracts, `/learn` + `/journey` improvements, gateway scale-to-zero and drain coordination, Desktop coding projects, memory-graph work, background subagent fan-out, and the reported zero-open-P0/P1 clean sweep. The July 2 post-release stale-runtime issue (`#56717`) for non-default profile gateways/dashboards remains open with multiple hardening PRs in flight, and is linked to two related open bugs about profile deletion and stale dashboard process accumulation. On July 6, main-branch commits fixed a real cross-profile leak where secondary-profile replies were routed through the default profile's bot token across all messaging platforms, plus fail-closed adapter resolution and per-profile config env isolation. The earlier-tracked OpenAI Codex `NoneType` crash report (`#33932`) was confirmed closed as a duplicate with the fix already on `main`; it is not an open regression.
- Sources: https://github.com/NousResearch/hermes-agent/releases/tag/v2026.7.1, https://github.com/NousResearch/hermes-agent/issues/56717, https://github.com/NousResearch/hermes-agent/commit/8a9bc38c2e72a20ed1e8b081917b6a0dd8891573

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: `2.1.197` made Claude Sonnet 5 the default model in Claude Code, with a native 1M-token context window and promotional pricing of $2/$10 per million tokens through August 31. `2.1.199`–`2.1.201` (July 2–3) shipped a reliability/safety wave: the default permission mode changed from "default" to **"Manual"** across CLI, VS Code, and JetBrains; `AskUserQuestion` dialogs no longer auto-continue by default; several background-agent daemon bugs were fixed (Linux daemon self-killing every ~50s after unclean shutdown, stale `daemon.lock` PID reuse blocking restarts); TLS/SSL certificate errors now fail immediately with actionable guidance; and subagents cut off by a rate limit now return partial work instead of failing silently.
- Source: https://code.claude.com/docs/en/changelog

### Claude Tag
- Area: team agent surface / Slack-based delegated work
- Why it matters: moves Claude-style coding and knowledge work into shared channels with selected tool, data, and codebase access; useful as a mainstream signal for multiplayer, proactive, asynchronous agents
- Current watch note: Introduced June 23 in beta for Claude Team and Enterprise customers. Claude Tag starts in Slack, replaces the existing Claude in Slack app, lets teams tag `@Claude`, and is framed by Anthropic as an evolution of Claude Code toward proactive team workflows.
- Source: https://www.anthropic.com/news/introducing-claude-tag

### Anthropic Claude Fable 5 / Mythos 5
- Area: frontier model tier for coding agents and long-horizon knowledge work
- Why it matters: affects Claude Code, GitHub Copilot model choice, provider routing, governance, cost, data-retention review, and high-complexity autonomous coding workflows
- Current watch note: Announced June 9, then materially changed on June 12. Anthropic says a US government export-control directive requires suspending access to Fable 5 and Mythos 5 for all customers, while access to other Anthropic models is not affected. This changes the availability picture for Claude Code, Copilot model choice, provider routing, and teams evaluating Mythos-class coding workflows.
- Sources: https://www.anthropic.com/news/claude-fable-5-mythos-5, https://www.anthropic.com/news/fable-mythos-access

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: Codex Remote reached GA on June 25, enabling ChatGPT mobile to start or continue work on a connected Mac or Windows host with authenticated one-to-one QR pairing. The same changelog also notes a new DigitalOcean plugin for provisioning a Droplet and connecting it to Codex App as a remote workspace. Codex CLI `0.142.5` is a privacy/security maintenance release that prevents full Responses WebSocket request payloads from being written to trace logs; the broader functional baseline remains `0.142.2` for MCP tool-search, proxy-aware auth, remote MCP, Bedrock recovery, and PowerShell approval behavior changes.
- Sources: https://developers.openai.com/codex/changelog, https://github.com/openai/codex/releases/tag/rust-v0.142.5, https://github.com/openai/codex/releases/tag/rust-v0.142.2

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: June 17-26 was a major Copilot agent/governance wave (Copilot app GA + BYOK, Agent Finder / ARD, Copilot Chat auto mode for all users, `AGENTS.md`-aware code review, MAI-Code-1-Flash GA, redesigned Copilot CLI terminal, Copilot for Jira GA, `strictKnownMarketplaces` governance). July 1-2 added a further GA wave: Copilot CLI no longer needs a personal access token in GitHub Actions; Enterprise `managed-settings.json` reached GA; enterprises can default users to auto model selection; Kimi K2.7 Code and Copilot vision both reached GA; and Copilot agent session streaming entered public preview.
- Sources: https://github.blog/changelog/2026-06-17-github-copilot-app-generally-available/, https://github.blog/changelog/2026-06-23-copilot-cli-new-terminal-interface-is-generally-available/, https://github.blog/changelog/2026-07-01-enterprise-managed-settings-json-is-generally-available, https://github.blog/changelog/2026-07-01-copilot-vision-is-generally-available, https://github.blog/changelog/2026-07-02-copilot-agent-session-streaming-is-now-in-public-preview, https://github.blog/changelog/2026-07-02-copilot-cli-no-longer-needs-a-personal-access-token-in-github-actions

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
- Current watch note: June review promoted two high-signal MCP interoperability items: the MCP 2026-07-28 release candidate, with stateless HTTP-friendly core, MCP Apps, Tasks, OAuth/OIDC-aligned authorization, JSON Schema 2020-12 support, and formal deprecation policy; and stable Enterprise-Managed Authorization, which lets organizations centrally authorize MCP server access through an IdP and reduce repeated per-server OAuth prompts. June 5 also noted an active individual IETF Internet-Draft on MCP security considerations; it has no formal IETF standing but remains a useful risk signal.
- Sources: https://modelcontextprotocol.io/, https://blog.modelcontextprotocol.io/posts/2026-07-28-release-candidate/, https://blog.modelcontextprotocol.io/posts/enterprise-managed-auth/

### Skills Over MCP
- Area: MCP-based agent skill discovery / portability
- Why it matters: connects portable agent skills with MCP registry, spec, SDK, and client behavior instead of leaving skills locked to individual hosts
- Current watch note: A June 30 MCP Working Session focuses on how “agent skills” can be discovered and consumed through MCP, with SEP-2640 called out as the near-term focus through June 2026.
- Source: https://meet.modelcontextprotocol.io/2026/06/skills-over-mcp-working-session-bi-weekly--WrKrEDAM75hr

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.
