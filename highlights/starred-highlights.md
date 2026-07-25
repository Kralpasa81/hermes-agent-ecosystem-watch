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

### 2026-07-25
- **Claude Opus 5 launches as a genuine cross-ecosystem event.** New default Opus model in Claude Code `2.1.219` (1M context, fast mode at $10/$50 per Mtok) shipped the same day across nine GitHub Copilot surfaces (VS Code, Visual Studio, Copilot CLI, cloud agent, Copilot app, JetBrains, Xcode, Eclipse, github.com). A real day-one multi-vendor model launch with an attached pricing/fast-mode change, not a staggered rollout. (https://github.com/anthropics/claude-code/releases/tag/v2.1.219, https://github.blog/changelog/2026-07-24-claude-opus-5-is-now-available-in-github-copilot)
- **Hermes closes two real cross-session leak bugs in one day.** A desktop background-queue drain could deliver a queued message into the session the user happened to be viewing instead of the session that owned it; a shared terminal bash snapshot could leak one session's `HERMES_SESSION_ID` into a concurrent session on the same backend. Both are genuine multi-session-isolation correctness fixes with regression tests, not cosmetic bugs. (https://github.com/NousResearch/hermes-agent/commit/062d261955, https://github.com/NousResearch/hermes-agent/commit/f2e32ceead)
- **Hermes ships a crash-survivable in-flight turn journal for desktop.** A full app or machine crash mid-turn previously discarded everything the crashed turn had streamed with no trace; the visible tail is now journaled locally (bounded, throttled) and reconciled with the backend's live projection on resume. Genuine reliability improvement against a real data-loss class. (https://github.com/NousResearch/hermes-agent/commit/8d8d1d61fe)

### 2026-07-24
- **Hermes cron reconciliation fix closes a real 20-hour silent-outage class.** A direct-run/scheduled-fire race for the same job occurrence could leave a recurring cron job permanently orphaned — the winning direct run advanced `next_run_at` but never notified the external provider, so its one-shot for that occurrence stayed stale forever, while `/api/status` kept reporting green the entire time. Now a claimed direct execution notifies the provider so it re-arms correctly. Genuine reliability fix for anyone running Hermes cron jobs behind an external scheduler/provider. (https://github.com/NousResearch/hermes-agent/commit/ef6ce56cad)
- **GitHub MCP Server ships stateless-core support ahead of the July 28 MCP spec cutover.** A concrete, shipped implementation — not just a roadmap note — removing Redis-backed sessions entirely, replacing deep packet inspection with guaranteed HTTP-header fields for logging/secret-scanning, and upgrading stdio elicitation to the new multi-round-trip HTTP flow with backward compatibility. Strongest evidence yet that the breaking stateless-MCP transition is shipping on schedule. (https://github.blog/changelog/2026-07-23-github-mcp-server-supports-the-next-mcp-specification/)

### 2026-07-23
- **Hermes unifies the clarify-request lifecycle across every surface** — six coordinated PRs fix wrong/hardcoded timeouts (CLI silently used 120s instead of the real `agent.clarify_timeout`), a race that rendered the clarify question above its own explanation, and late-reply handling that used to hit a raw JSON-RPC error on TUI/gateway reconnects. Genuine cross-surface workflow-reliability fix for Hermes' interactive clarify flow on CLI, TUI, desktop, and gateway. (https://github.com/NousResearch/hermes-agent/commit/507d479c8c)
- **Claude Code 2.1.218 closes an agent-hook workspace-trust bypass** — hooks defined in agent frontmatter now require their own folder (not just the invoking session) to have accepted workspace trust before running. Real security-hardening fix for anyone using Claude Code custom agents/hooks. (https://github.com/anthropics/claude-code/releases/tag/v2.1.218)

## Maintenance note
This page should stay selective. If a daily update is interesting but not clearly high-signal, keep it in `daily/` only. Entries older than ~2 weeks are periodically trimmed to keep this page focused on recent, still-relevant signal.
