# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: June 19 main-branch work was high-signal for hosted operation and multimodal/tool capability: hosted relay self-provisioning now keys off relay config rather than package-manager `is_managed()` state and was verified with an end-to-end Discord round-trip; a bundled dependency-free `html-artifact` skill replaced overlapping diagram/sketch skills; `image_generate` gained image-to-image/editing inputs across providers; Desktop model picker gained `Refresh Models`; dashboard chat, upload cleanup, Slack setup validation, read-only WebUI Docker installs, worktree locking, session-store warnings, gateway lifecycle safety, and FTS fallback behavior were hardened.
- Source: https://github.com/NousResearch/hermes-agent

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: `v2.1.183` strengthens auto-mode safety by blocking destructive git and infrastructure-destroy commands unless explicitly requested, warning on deprecated/auto-updated models, adding `attribution.sessionUrl` and `/config --help`, and fixing subagent/WebSearch behavior, thinking-only turns, MCP auth-stub exposure in headless/SDK mode, tmux teammate panes, background tasks, and scheduled/webhook trigger classification.
- Source: https://github.com/anthropics/claude-code/releases/tag/v2.1.183

### Anthropic Claude Fable 5 / Mythos 5
- Area: frontier model tier for coding agents and long-horizon knowledge work
- Why it matters: affects Claude Code, GitHub Copilot model choice, provider routing, governance, cost, data-retention review, and high-complexity autonomous coding workflows
- Current watch note: Announced June 9, then materially changed on June 12. Anthropic says a US government export-control directive requires suspending access to Fable 5 and Mythos 5 for all customers, while access to other Anthropic models is not affected. This changes the availability picture for Claude Code, Copilot model choice, provider routing, and teams evaluating Mythos-class coding workflows.
- Sources: https://www.anthropic.com/news/claude-fable-5-mythos-5, https://www.anthropic.com/news/fable-mythos-access

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: Codex CLI `0.141.0` remains the latest stable CLI release and is high-signal for secure remote execution, plugin/MCP activation, app-server APIs, and reliability. Codex app `26.616` added macOS Record & Replay, turning a demonstrated workflow into a reusable skill, plus bulk automation-history actions and Browser Use routing/annotation improvements.
- Sources: https://developers.openai.com/codex/changelog, https://github.com/openai/codex/releases/tag/rust-v0.141.0

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: June 17-18 was a major Copilot agent wave: the Copilot app is GA; Agent Finder / Agentic Resource Discovery is available across Copilot plans; Copilot Chat auto mode is available for all users; Copilot code review now uses root-level `AGENTS.md`; MAI-Code-1-Flash is rolling out to more Copilot surfaces; and Opus 4.6 (fast) is scheduled for Copilot deprecation on June 29, 2026.
- Sources: https://github.blog/changelog/2026-06-17-github-copilot-app-generally-available/, https://github.blog/changelog/2026-06-17-agent-finder-for-github-copilot-now-available/, https://github.blog/changelog/2026-06-17-auto-mode-in-copilot-chat-available-for-all-users/, https://github.blog/changelog/2026-06-18-copilot-code-review-agents-md-support-and-ui-improvements, https://github.blog/changelog/2026-06-18-mai-code-1-flash-available-on-more-copilot-surfaces, https://github.blog/changelog/2026-06-18-upcoming-deprecation-of-opus-4-6-fast

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
- Current watch note: June 6 review promoted the MCP 2026-07-28 release candidate as a high-signal interoperability update with breaking changes: stateless HTTP-friendly core, MCP Apps for server-rendered UI, Tasks for long-running work, OAuth/OIDC-aligned authorization, JSON Schema 2020-12 support, and a formal deprecation policy. June 5 also noted an active individual IETF Internet-Draft on MCP security considerations; it has no formal IETF standing but remains a useful risk signal.
- Source: https://modelcontextprotocol.io/

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.
