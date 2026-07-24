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

### 2026-07-24
- **Hermes cron reconciliation fix closes a real 20-hour silent-outage class.** A direct-run/scheduled-fire race for the same job occurrence could leave a recurring cron job permanently orphaned — the winning direct run advanced `next_run_at` but never notified the external provider, so its one-shot for that occurrence stayed stale forever, while `/api/status` kept reporting green the entire time. Now a claimed direct execution notifies the provider so it re-arms correctly. Genuine reliability fix for anyone running Hermes cron jobs behind an external scheduler/provider. (https://github.com/NousResearch/hermes-agent/commit/ef6ce56cad)
- **GitHub MCP Server ships stateless-core support ahead of the July 28 MCP spec cutover.** A concrete, shipped implementation — not just a roadmap note — removing Redis-backed sessions entirely, replacing deep packet inspection with guaranteed HTTP-header fields for logging/secret-scanning, and upgrading stdio elicitation to the new multi-round-trip HTTP flow with backward compatibility. Strongest evidence yet that the breaking stateless-MCP transition is shipping on schedule. (https://github.blog/changelog/2026-07-23-github-mcp-server-supports-the-next-mcp-specification/)

### 2026-07-23
- **Hermes unifies the clarify-request lifecycle across every surface** — six coordinated PRs fix wrong/hardcoded timeouts (CLI silently used 120s instead of the real `agent.clarify_timeout`), a race that rendered the clarify question above its own explanation, and late-reply handling that used to hit a raw JSON-RPC error on TUI/gateway reconnects. Genuine cross-surface workflow-reliability fix for Hermes' interactive clarify flow on CLI, TUI, desktop, and gateway. (https://github.com/NousResearch/hermes-agent/commit/507d479c8c)
- **Claude Code 2.1.218 closes an agent-hook workspace-trust bypass** — hooks defined in agent frontmatter now require their own folder (not just the invoking session) to have accepted workspace trust before running. Real security-hardening fix for anyone using Claude Code custom agents/hooks. (https://github.com/anthropics/claude-code/releases/tag/v2.1.218)
- **OpenAI launches Presence** — its first managed, governed enterprise product for deploying AI voice/chat agents at scale (policies, escalation rules, monitoring, guardrails bundled), in limited availability. Interoperability/maturity signal for the packaged-agent-infrastructure category. (https://openai.com/index/introducing-openai-presence)

### 2026-07-22
- **Hermes gateway's stranded-platform recovery generalized to every adapter** — yesterday's Discord-only relay fix and today's `fix(gateway)` #69112 close the same class of bug (a platform going permanently dark inside a live gateway process, invisible to `launchd`/`systemd` restart) across Discord, Telegram, qqbot, and photon in two consecutive days. The gateway now hard-exits if a platform ends up neither reconnected nor queued after a fatal error, so process managers actually restart it. Genuine availability improvement for anyone running managed Hermes gateways. (https://github.com/NousResearch/hermes-agent/commit/2ab153218ba401525ec02380305f8c3c4c8b1dc0)
- **Claude Code 2.1.217 adds subagent concurrency/budget guardrails** — closes a real gap where `--max-budget-usd` didn't stop background subagents once the cap was hit, and adds a default 20-subagent concurrency cap plus disabling nested subagent spawning by default. Direct cost-control signal for anyone running Claude Code with subagents in production. (https://github.com/anthropics/claude-code/releases/tag/v2.1.217)

## Maintenance note
This page should stay selective. If a daily update is interesting but not clearly high-signal, keep it in `daily/` only. Entries older than ~2 weeks are periodically trimmed to keep this page focused on recent, still-relevant signal.
