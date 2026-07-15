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

### 2026-07-15
- **Hermes bounded-capture regression fix** — closed a bug where a shared `execute()`/`_wait_for_process` drain path had started applying a `tool_output.max_bytes` truncation limit to *every* consumer, not just the terminal tool. This silently truncated `cat`/paginated `read_file`/log reads over 50KB and could corrupt read-modify-write file operations feeding the patch engine on files over 50KB. Bounded capture is now explicit opt-in, scoped only to the foreground terminal tool. Direct reliability/correctness fix for Hermes' file and terminal tools. (https://github.com/NousResearch/hermes-agent/commit/cab457d722a28d60cd90d3cd6c7e5b55a12b659a)
- **Claude Code `2.1.210` subagent security hardening** — closes a worktree-isolation bypass letting `isolation: 'worktree'` subagents run git-mutating commands against the main repo checkout, and hardens the Agent tool against indirect prompt injection via content a subagent read. High-signal for anyone running Claude Code subagents against untrusted repos or web/PR content. (https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md)

### 2026-07-14
- **Nous Research reportedly raising at a $1.5B valuation** — TechCrunch reports a new round of at least $75M led by Robot Ventures with significant participation from USV, up from Nous' prior $70M total raised. Unconfirmed by Nous Research directly, but the first major funding signal for Hermes' maker; relevant for anyone tracking Hermes' resourcing, roadmap pace, and product/business-model expansion. (https://techcrunch.com/2026/07/13/hermes-agent-maker-nous-research-in-talks-for-new-funding-at-1-5b-valuation/)
- **Claude Code `2.1.208` reliability/performance overhaul** — up to 7x faster tool rounds in tool-heavy print/SDK sessions, multiple long-session memory-leak fixes (MCP stdio stderr, LSP document handles, headless/SDK tool-result growth), and up to 79x smaller transcripts in edit-heavy sessions. High-signal for any workflow running Claude Code at scale or over long-running sessions. (https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md)

### 2026-07-13
- **Claude Fable 5 access extended again, through July 19** — second extension in six days (July 7 → July 12 → July 19), announced after the prior deadline had already passed. Claude Code's 50% higher weekly rate limits extend alongside it. High-signal for access/limits planning: any workflow standardizing on Fable 5 or running Claude Code at scale needs to track this on a roughly weekly cadence rather than assume a fixed cutoff. (https://www.anthropic.com/news/redeploying-fable-5)

### 2026-07-12
- **Claude Code auto mode GA on Bedrock / Vertex AI / Foundry** (v2.1.207) — removes the `CLAUDE_CODE_ENABLE_AUTO_MODE` opt-in flag for the three major cloud runtimes; Bedrock, Vertex, and Claude Platform on AWS now default to Claude Opus 4.8. Meaningful for enterprise teams running Claude Code at scale on managed endpoints. (https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md)
- **Claude Code built-in Desktop browser** (Week 28, July 6–10) — sandboxed, configurable browser surface in the Desktop app with safety classifiers on external sites. Removes the need for an external browser bridge to let Claude validate web work against live sites. (https://code.claude.com/docs/en/whats-new/2026-w28)

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

## Maintenance note
This page should stay selective. If a daily update is interesting but not clearly high-signal, keep it in `daily/` only. Entries older than ~2 weeks are periodically trimmed to keep this page focused on recent, still-relevant signal.
