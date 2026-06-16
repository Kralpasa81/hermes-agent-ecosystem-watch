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

### 2026-06-16
- **Hermes remote-gateway Desktop hardening** is high-signal because authenticated artifact downloads and correct remote-profile REST routing are foundational for thin-client Desktop control of remote Hermes runtimes.
- **Hermes asynchronous delegation fix** matters because `delegate_task(background=true)` must reliably launch background work for multi-agent and unattended workflows.
- **OpenAI Codex CLI `0.140.0` stable release** is worth tracking because it improves usage visibility, cross-tool migration from Claude Code, Bedrock/auth handling, MCP credential storage, state recovery, and MCP startup reliability.
- **Claude Code `v2.1.178` governance and subagent hardening** matters because parameter-aware permission rules, pre-launch subagent classification, fallback-model compaction, background-session fixes, and MCP `disallowedTools` handling affect safe long-running coding-agent use.

### 2026-06-15
- **Hermes profile gateway supervision hardening** is high-signal because multi-profile and always-on gateway deployments depend on predictable default/profile gateway boundaries, persisted desired state, writable logs, and clean startup behavior.
- **Hermes dashboard restart/reroute reliability** matters because browser-admin control surfaces must restart and route to the intended machine context rather than drifting across profile or home-directory state.
- **Hermes Windows virtualenv recreation fix** is worth tracking because locked native extension files can otherwise break update/install flows on Windows, which is increasingly important after the Desktop release.

### 2026-06-14
- **Hermes sensitive-file approval hardening** is high-signal because unattended agents must not mutate shell startup files, SSH material, credentials, or other sensitive local files without explicit safety gates.
- **Hermes SSL CA bundle fail-fast guard** matters because provider and gateway calls should fail clearly when trust-store configuration is broken, rather than surfacing confusing downstream model/network errors.
- **Hermes refusal/content-filter handling** is worth tracking because model refusals and provider content filters need to be surfaced accurately instead of being retried or misclassified as generic transport failures.
- **Hermes notebook/office document extraction** is a practical capability signal because broader local document ingestion directly improves real-world agent usefulness across notebooks, documents, and office files.
- **OpenAI Codex remote exec / plugin-MCP alpha work** is an infrastructure signal because remote execution correctness and MCP/plugin de-duplication affect multi-surface coding-agent workflows.

### 2026-06-13
- **Hermes Desktop/TUI provider-routing and queued-prompt recovery** are high-signal because model-routing correctness and reliable queued submissions directly affect the new Desktop/TUI workflow after the Surface release.
- **Hermes context-compression and repair hardening** matters because preserving recent turns and preventing malformed compaction behavior protects long-running agent sessions.
- **Anthropic Fable 5 / Mythos 5 access suspension** is a major limits/access signal because a newly launched high-capability coding/research model tier became unavailable for all customers under an export-control directive.
- **Claude Code `2.1.176` model-policy and background-agent fixes** matter because managed allowlists, Remote Control correctness, and background-session recovery are enterprise coding-agent safety and reliability concerns.
- **GitHub Copilot code review governance controls** are worth tracking because org-level runner policy, content exclusions, and longer instructions materially improve agentic review customization.

### 2026-06-12
- **Hermes Slack action-handler plugin API** is high-signal because interactive Slack Block Kit workflows can now be handled through plugins rather than only posted to by Hermes.
- **Hermes MCP/tool-schema compatibility fixes** matter because prompt-only/resource-only MCP servers and cleaner `$ref` schemas improve interoperability across mixed MCP/tool ecosystems.
- **Hermes gateway/messaging attachment + reaction reliability** is worth tracking because Signal, SimpleX, email, Photon, and send-message reaction behavior are core to dependable cross-channel agent operation.
- **Claude Code managed model governance and background-session isolation** are enterprise workflow signals because model allowlists, Default fallback behavior, and provider-environment isolation affect policy enforcement and safe concurrent agent sessions.
- **GitHub Agentic Workflows public preview plus `GITHUB_TOKEN` support** is a major agent-infrastructure signal because agentic engineering automation is moving into governed GitHub Actions workflows without long-lived PATs.
- **OpenAI Codex Developer mode for browser use** is a capability signal because CDP-backed browser inspection gives coding agents better visibility into runtime, network, console, and page-state debugging.

### 2026-06-11
- **Hermes Parallel-backed web search/extract** is high-signal because web tooling is a core agent capability and the keyless Search MCP / keyed REST split affects access and reliability.
- **Hermes dashboard/profile builder plus profile-scoped skills/toolsets** matters because profile, model, skills, and MCP management are moving into an operator-friendly admin surface.
- **Hermes cron/provider, backup, update, and Windows install hardening** is worth tracking because scheduled and unattended agents depend on reliable provider resolution, backups, updates, and platform installers.
- **Claude Code nested sub-agents and 1M/Fable fixes** are workflow and capability signals because deeper agent trees, large-context recovery, model normalization, and policy enforcement affect advanced coding-agent use.
- **Copilot Chat agent-session visibility plus Copilot CLI `/security-review`** is a workflow/safety signal because agent work is easier to inspect after the fact and easier to security-check before commit.

### 2026-06-10
- **Hermes memory/skills write approval gate** is high-signal because persistent memory and skill mutations need explicit approval semantics in unattended-agent workflows.
- **Hermes Desktop/remote-session hardening** matters because remote file staging, reconnect recovery, per-chat windows, terminal-pane polish, and project-directory correctness all improve the post-Surface-release workflow.
- **Claude Fable 5 / Mythos 5 plus Claude Code `2.1.170` support** is a capability and governance signal because a new high-capability coding model tier changes model choice, cost, access policy, and data-retention review.
- **GitHub security validation for third-party coding agents** is an interoperability and safety signal because Claude, Codex, and other repository agents can receive consistent CodeQL, dependency, and secret-scanning checks before PR finalization.

### 2026-06-09
- **Hermes remote-gateway file attachments** are high-signal because remote Desktop/gateway workflows need reliable file attachment semantics across local and remote boundaries.
- **Hermes recommended-model cache fallback** matters because model selection should remain usable when Portal lookups fail or network conditions are degraded.
- **OpenAI Codex CLI `0.138.0` Desktop handoff + plugin JSON improvements** are a workflow signal because Codex is becoming easier to automate across CLI, Desktop, app-server, and plugin surfaces.
- **Claude Code `2.1.169` safe mode and MCP policy fixes** matter because troubleshooting and enterprise policy enforcement are prerequisites for dependable coding-agent use in complex environments.

### 2026-06-08
- **Hermes tool/cwd hardening** is high-signal because cwd resolution, sentinel rejection, and worktree anchoring directly affect safe file edits and terminal-backed automation.
- **Hermes gateway replacement hardening** matters because systemd/supervisor restart behavior is critical for reliable always-on gateway deployments.
- **Hermes curator built-in skill protection** is worth tracking because unattended self-improvement should not archive or consolidate load-bearing built-in skills.

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
