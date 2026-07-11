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

### 2026-07-11
- **GPT-5.6 Sol / Terra / Luna in GitHub Copilot** (July 9) — OpenAI's latest model family lands across all major Copilot surfaces with a three-tier structure: Sol (highest reasoning ceiling, complex long-horizon agentic work), Terra (balanced default for everyday coding), Luna (lightweight, cost-efficient). Available in VS Code, JetBrains, Xcode, Eclipse, Copilot CLI, Copilot app, GitHub.com, and mobile. Billed at provider list pricing; Enterprise/Business admins must enable the policy. (https://github.blog/changelog/2026-07-09-openais-gpt-5-6-sol-terra-and-luna-are-now-available-in-github-copilot/)
- **VS Code June 2026 Copilot bundle** (posted July 8, covers v1.123–v1.127) — agentic browser tools GA (agents can navigate/screenshot/validate within VS Code); parallel agent sessions with multi-chat; full session + subagent cost visibility; model provider discovery from Marketplace; Autopilot improvements (smarter task completion); session sync across machines; 1M context for Anthropic/OpenAI models; MCP OAuth credential storage; enterprise MDM-managed settings. Collectively a large step forward for in-IDE agentic workflows. (https://github.blog/changelog/2026-07-08-github-copilot-in-visual-studio-code-june-2026-releases/)

### 2026-07-10
- **MCP 2026-07-28 Release Candidate** — largest MCP spec revision since launch. Stateless HTTP core (sessions and `initialize` handshake removed), MCP Apps (server-rendered UIs), Tasks extension, OAuth/OIDC-aligned authorization, JSON Schema 2020-12 for tools, and formal deprecation policy. Direct impact for Hermes: MCP-connected skills/tools will need to target the stateless model. Final spec ships July 28. (https://blog.modelcontextprotocol.io/posts/2026-07-28-release-candidate/)

### 2026-07-08
- **Hermes Agent v0.18.2 (v2026.7.7.2)** — same-day patch fixing the WhatsApp Baileys dependency (installer / tagged-release Docker reliability). Important for deployments that use Hermes' WhatsApp bridge. (https://github.com/NousResearch/hermes-agent/releases/tag/v2026.7.7.2)
- **OpenAI Assistants API sunset (Aug 26, 2026)** — Assistants beta is scheduled to be deprecated; migrate to the Responses API. High-signal for integrators still using Assistants-era workflows. Migration guide: https://platform.openai.com/docs/assistants/migration

### 2026-07-06
- **Hermes multiplex-profile cross-bot response leak fix** matters because secondary Hermes profiles were replying through the default profile's bot token across every messaging platform (Telegram, Discord, etc.) — a real correctness/security bug for multi-bot deployments — and the fix pairs with fail-closed adapter resolution instead of silent fallback.
- **Claude Code default permission mode changed to "Manual"** matters because it changes the default safety posture of a mainstream coding agent simultaneously across CLI, VS Code, and JetBrains.

### 2026-07-02
- **Hermes Agent `v0.18.0` / “The Judgment Release”** matters because it resets the public Hermes baseline around first-class MoA, completion verification, `/goal`, `/learn`, `/journey`, gateway scalability, Desktop projects, memory graph work, and background subagents.
- **Hermes P0/P1 clean sweep** matters because the release reports zero open P0/P1 items at cut time, making it a strong reliability and maintenance-health signal for production users.

### 2026-07-01
- **Claude Sonnet 5 as the Claude Code default** matters because it changes default coding-agent capability, context-window size, and promotional cost assumptions for mainstream developer workflows.
- **Hermes CDP-URL redaction consolidation** matters because browser automation and supervisor logs must not leak session/control tokens in unattended deployments.
- **Hermes cron BSM secret re-resolution per run** matters because recurring scheduled jobs need fresh secret resolution and robust delivery/listing behavior.
- **Hermes post-compression context sentinel clamping** matters because long-running sessions need accurate context reporting after compression events.

### 2026-06-30
- **Hermes compression/session reliability fixes** matter because long-running autonomous sessions depend on context compression that fails open, releases locks, and resumes without stale cooldown or lease state.
- **Hermes cron pre-run timeout increase** matters because recurring automations often need real setup/bootstrap time before the actual task starts.
- **Hermes gateway routing self-healing** matters because always-on messaging deployments need stale session-route metadata to recover at message time rather than silently misrouting or failing.
- **Claude Code `2.1.196` background-agent, MCP auth, and stream-watchdog fixes** matter because they improve long-running coding-agent reliability, enterprise IdP compatibility, and stuck-stream recovery.
- **Skills Over MCP working-session focus** is a forward-looking interoperability signal for making agent skills discoverable through MCP rather than locked to individual host formats.

### 2026-06-29
- **Hermes Desktop/Dashboard decoupling around `hermes serve`** matters because cleaner headless runtime boundaries can improve remote control, thin-client Desktop use, and future operator-surface reliability.
- **Hermes external cron provider status correction** is high-signal because scheduled automations must report accurately when jobs are delegated to non-built-in schedulers such as Chronos.
- **Hermes strict skill path containment** matters because skills are a core extension surface, and path-boundary correctness is a safety requirement for unattended agents.

### 2026-06-28
- **Hermes fallback-chain and content-filter recovery fixes** matter because provider stalls, refusal/content-filter handling, and transport failures directly affect whether long-running autonomous sessions finish cleanly.
- **Hermes gateway and messaging hardening across Telegram, WhatsApp, Matrix, systemd, and cache-media delivery** is high-signal because always-on messaging gateways are core Hermes deployment surfaces.
- **Hermes redaction / credential / proxy correctness fixes** matter because output integrity and credential safety are practical trust boundaries for unattended agents.

### 2026-06-27
- **Hermes Photon/iMessage stabilization** matters because `v0.17.0` made Photon a major gateway surface, and sidecar upgrades plus tapback-context correlation directly affect practical messaging reliability.
- **Hermes self-hosted OIDC redirect handling** is high-signal because dashboard auth behind real identity-provider and reverse-proxy deployments is a core operational trust boundary.
- **Claude Code `2.1.195` plugin consent, exact hook matching, and background-agent recovery fixes** matter because extension loading, MCP/tool policy precision, and long-running agent reliability are common enterprise failure points.
- **Copilot Business / Enterprise MAI-Code-1-Flash GA** matters because mainstream coding-agent model choice is expanding toward lower-latency, usage-billed, admin-governed model routing.

### 2026-06-26
- **Hermes relay identity and gateway security work** matter because multi-platform relay identity, stricter authorization, email spoofing protection, and browser secret-output redaction directly affect always-on gateway trust boundaries.
- **Hermes cron and gateway-history reliability fixes** are high-signal because scheduled jobs, retained outputs, recoverable history, and stable watcher reconnects are core unattended-agent requirements.
- **Claude Code `2.1.193` telemetry and auto-mode changes** matter because shell safety classification and assistant-response logging defaults can materially affect enterprise safety, privacy, and observability settings.
- **Codex Remote GA** is workflow-shaping because mobile approval/control of connected desktop hosts plus QR pairing changes how coding-agent work can be supervised away from the main machine.
- **Copilot code review efficiency and plugin governance** matter because file-exploration-backed reviews and marketplace restrictions affect cost control and enterprise-safe agent extension.

## Maintenance note
This page should stay selective. If a daily update is interesting but not clearly high-signal, keep it in `daily/` only.
