# Starred Highlights

Only the strongest signals are kept here.

## Highlight rule
Use this page for developments that meaningfully change:
- capabilities
- reliability
- workflow speed
- limits/access
- ecosystem interoperability

## Current starred items

### 2026-06-07
- **Hermes cron jobs becoming first-class Desktop/dashboard entities** is high-signal because scheduled-agent work is easier to inspect, trigger, and manage when it has dedicated sidebar/session treatment.
- **Hermes GUI tool-backend configuration and Skills Hub browser improvements** matter because setup, tool operations, skill discovery, previews, and security scanning are moving into polished admin surfaces rather than staying CLI-only.
- **Hermes post-release security/reliability hardening** is worth keeping because Windows gateway behavior, installer/bootstrap edges, path traversal, zip-slip prevention, memory-tool shadowing, and migration correctness directly affect unattended operation.
- **OpenAI Codex macOS certificate cutoff** is a practical access/reliability item because Codex App / CLI users on macOS have a June 12 update deadline before older signed versions may stop launching or updating.

### 2026-06-06
- **Hermes Agent v0.16.0 “The Surface Release”** is the week’s strongest Hermes signal because a native desktop app and expanded web dashboard move Hermes from primarily CLI/TUI operation toward polished graphical, admin-friendly workflows.
- **Hermes remote gateway + multi-profile desktop support** matters because users can run a thin local GUI against a remote Hermes runtime while keeping profile-specific sessions and authentication practical.
- **Hermes onboarding, skill-surface, and security hardening** are high-signal because Nous Portal setup, fuzzy model selection, a leaner default skill set, NVIDIA/skills as a trusted tap, CVE pinning, SSRF hardening, and credential stripping all affect real adoption and unattended reliability.
- **MCP 2026-07-28 release candidate** is an interoperability signal because stateless HTTP scaling, MCP Apps, Tasks, OAuth/OIDC alignment, JSON Schema 2020-12 support, and breaking-change/deprecation policy can shape how future agent tools expose UI, long-running work, and remote authorization.

### 2026-06-05
- **Hermes Agent operational safety fixes** are high-signal because cron listing, updater cleanup, Docker update checks, gateway status parsing, terminal CWD handling, WAL growth, MCP shutdown, and approval checks directly affect unattended-agent reliability.
- **Hermes Desktop multi-profile and remote-gateway maturity** matters because concurrent profile sockets, live WebSocket validation, OAuth-ticket checks, and flexible provider onboarding make multi-profile desktop operation more practical.
- **GitHub Copilot Agent tasks REST API** is a workflow signal because Copilot cloud-agent tasks can now be launched and tracked from scripts, internal portals, and recurring automation systems.
- **Copilot code review MCP + skills support** is an interoperability signal because mainstream AI review can now pull approved organization context from internal tools, docs, issue systems, and service catalogs.

### 2026-06-04
- **Hermes Agent dashboard auth and remote-gateway access work** is high-signal because a bundled username/password auth plugin, self-hosted OAuth registration, OAuth-aware gateway connection handling, and safer WebSocket ticket behavior directly affect secure self-hosted operation.
- **Hermes Agent desktop provider/reliability wave** matters because provider-account settings, background needs-input visibility, attachment/IME fixes, streaming scroll improvements, atomic config writes, and fetch error handling all reduce practical desktop friction.
- **OpenAI Codex CLI 0.137.0** is a workflow signal because cloud-managed config, remote-control grant APIs, machine-readable plugin listing, hosted web/image tools, and multi-agent v2 refinements expand Codex as an automatable agent surface.
- **VS Code Agents window in Stable preview** matters because persistent, remote-capable, multi-session, BYOK-friendly agent workflows are moving into mainstream developer tooling.

### 2026-06-03
- **Hermes Agent desktop/dashboard/runtime reliability wave** matters because session isolation, queued-turn interrupts, WebSocket auth/origin handling, gateway reconnect cleanup, Docker bootstrap behavior, setup defaults, and cron skill-bundle expansion all affect practical Hermes operability.
- **GitHub Copilot SDK GA** is a major interoperability signal because Copilot's agent runtime can now be embedded through a stable API with custom tools, MCP, hooks, tracing, BYOK, and cloud/remote sessions.
- **GitHub Copilot sandboxes and cloud-agent automations** matter because safer execution boundaries plus scheduled/event-driven agent runs are core infrastructure for production coding-agent workflows.

### 2026-06-02
- **Hermes Agent dashboard Channels + admin panel work** is high-signal because gateway setup, MCP catalog management, hook creation, and system stats moved further into browser-operable surfaces.
- **Hermes Agent structured gateway stream/event and formatting work** matters because reliable cross-channel delivery is core infrastructure for messaging-driven agent workflows.
- **GitHub Copilot AI-adoption cohorts in the usage metrics API** matter because enterprises can distinguish completion/chat usage from real agentic surfaces like cloud agent, code review, CLI, and the Copilot app.

### 2026-06-01
- **Hermes Agent gateway/media cleanup on main** matters because preserving code blocks, blockquotes, and JSON-embedded `MEDIA:` text directly affects tool-output fidelity in messaging workflows.
- **GitHub Copilot code review billing changed on June 1** because private-repo agentic reviews now carry both Copilot AI Credit and GitHub Actions minute implications.

### 2026-05-31
- **Hermes Agent main-branch gateway and MCP reliability work** is worth watching because watcher recovery, plugin/bundle error logging, config re-reading, and MCP auth reconnect behavior affect real agent stability ahead of the next tagged release.
- **OpenAI Codex Windows computer use and mobile remote access** expands Codex toward cross-device desktop automation rather than only code-generation or sandboxed coding tasks.
- **Codex shared MCP configuration across CLI and IDE** is an interoperability signal because one MCP setup can carry across local Codex surfaces.

### 2026-05-30
- **Hermes Agent packaging follow-up release (v2026.5.29.2)** improved packaged plugin availability by bundling `plugin.yaml` manifests in wheel and sdist releases.
- **Claude Code usage-limit increase** is a practical workflow signal because it directly affects how much real coding-agent work users can run in a session window.
- **GitHub Copilot app technical preview** is notable because it pushes GitHub-native agentic workflow, isolated sessions, terminal/browser validation, and PR handoff in one surface.

## Maintenance note
This page should stay selective. If a daily update is interesting but not clearly high-signal, keep it in `daily/` only.
