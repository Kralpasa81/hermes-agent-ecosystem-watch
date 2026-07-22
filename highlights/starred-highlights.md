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

### 2026-07-22
- **Hermes gateway's stranded-platform recovery generalized to every adapter** — yesterday's Discord-only relay fix and today's `fix(gateway)` #69112 close the same class of bug (a platform going permanently dark inside a live gateway process, invisible to `launchd`/`systemd` restart) across Discord, Telegram, qqbot, and photon in two consecutive days. The gateway now hard-exits if a platform ends up neither reconnected nor queued after a fatal error, so process managers actually restart it. Genuine availability improvement for anyone running managed Hermes gateways. (https://github.com/NousResearch/hermes-agent/commit/2ab153218ba401525ec02380305f8c3c4c8b1dc0)
- **Claude Code 2.1.217 adds subagent concurrency/budget guardrails** — closes a real gap where `--max-budget-usd` didn't stop background subagents once the cap was hit, and adds a default 20-subagent concurrency cap plus disabling nested subagent spawning by default. Direct cost-control signal for anyone running Claude Code with subagents in production. (https://github.com/anthropics/claude-code/releases/tag/v2.1.217)

### 2026-07-21
- **Hermes Agent v0.19.0 "Quicksilver" release (tagged Jul 20)** — the primary Hermes release for the window tracked by this repo. Cold-start time-to-first-token cut **~80%** (4.3s → 0.9s) across every surface, reasoning streams live by default, **smart approvals** on by default, **Bitwarden/1Password secret sources**, live subagent transcripts, durable background-delegation delivery, gateway delivery-obligation ledger (previously tracked), profile-based gateway routing, `/subscription` terminal billing, GPT-5.6/grok-4.5/kimi-k3/claude-fable-5/claude-sonnet-5 support, and a 20-PR desktop speed overhaul. Biggest Hermes release in this repo's tracked window. Simultaneously on Jul 21, `fix(relay)` #68320 closes a total-loss-of-service bug for managed Discord agents (guild replies were silently declined because `user_id` was never carried alongside `scope_id` on the outbound relay frame). (https://github.com/NousResearch/hermes-agent/releases/tag/v2026.7.20, https://github.com/NousResearch/hermes-agent/commit/f4df260f26c93f15694698869f3ea8e965eea301)

### 2026-07-19
- **Hermes gateway durable delivery-obligation ledger** — closes a genuine reliability gap where a generated-but-undelivered final response could be silently lost on a gateway crash or planned restart, forcing a full-cost turn re-run on resume. Recovered replies are now explicitly labeled ("♻️ Recovered reply — may be a duplicate") rather than silently retried, and dedup uses stable IDs from session_key + inbound message id + content. Direct capability/reliability upgrade for anyone running Hermes gateways in production. (https://github.com/NousResearch/hermes-agent/commit/5854aad8b5)

### 2026-07-18
- **Hermes `delegate_task` async-delivery fix for `hermes -z` and cron** — closes a real correctness gap where unattended one-shot and cron runs using `delegate_task` could silently lose subagent results, or (in the cron case) misroute a subagent's output into an unrelated session via an ambient session-key fallback. Direct reliability fix for anyone running Hermes unattended via `hermes -z` or cron. (https://github.com/NousResearch/hermes-agent/commit/3d9be2789552a495c7adf30148e867e7614a4bdc)
- **Claude Code `2.1.214` closes multiple real permission-check bypasses** — a nested-directory allow-rule bypass (`Edit(src/**)` wrongly matching any `dir/` in the tree), a Windows PowerShell 5.1 bypass, and several Bash-permission-analyzer blind spots (10k+ character commands, FD redirect forms, zsh `[[ ]]` subscripts, unsafe `help`/`man` options) could each let commands run without the approval prompt the user's rules required. High-signal for anyone relying on Claude Code's permission system for safety in autonomous runs. (https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md)

### 2026-07-17
- **Claude Code `2.1.212` adds hard anti-runaway-loop limits and MCP call auto-backgrounding** — a session-wide WebSearch cap (200 calls) and subagent-spawn cap (200) stop uncontrolled search/delegation loops, and MCP tool calls running over 2 minutes now move to the background automatically instead of blocking the session. Direct reliability/cost-control signal for anyone running Claude Code at scale, via SDK, or in unattended/headless automation. (https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md)

### 2026-07-16
- **Codex/ChatGPT Work 8M-user surge forces context-window rollback and repeated usage resets** — GPT-5.6's July 9 launch roughly doubled OpenAI's prior peak traffic within 48 hours; OpenAI had to cut GPT-5.6 Sol's context window back from 372k to 272k tokens, revert experimental reasoning-effort changes, and temporarily lift the 5-hour usage cap for Plus/Business/Pro. Usage-limit reset delivery is still inconsistent for some users as of today. High-signal for capacity/reliability planning: track Codex usage-limit stability, not just feature velocity, before standardizing workflows on it. (https://thenewstack.io/gpt-5-6-codex-user-surge/)

### 2026-07-15
- **Hermes bounded-capture regression fix** — closed a bug where a shared `execute()`/`_wait_for_process` drain path had started applying a `tool_output.max_bytes` truncation limit to *every* consumer, not just the terminal tool. This silently truncated `cat`/paginated `read_file`/log reads over 50KB and could corrupt read-modify-write file operations feeding the patch engine on files over 50KB. Bounded capture is now explicit opt-in, scoped only to the foreground terminal tool. Direct reliability/correctness fix for Hermes' file and terminal tools. (https://github.com/NousResearch/hermes-agent/commit/cab457d722a28d60cd90d3cd6c7e5b55a12b659a)
- **Claude Code `2.1.210` subagent security hardening** — closes a worktree-isolation bypass letting `isolation: 'worktree'` subagents run git-mutating commands against the main repo checkout, and hardens the Agent tool against indirect prompt injection via content a subagent read. High-signal for anyone running Claude Code subagents against untrusted repos or web/PR content. (https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md)

### 2026-07-14
- **Nous Research reportedly raising at a $1.5B valuation** — TechCrunch reports a new round of at least $75M led by Robot Ventures with significant participation from USV, up from Nous' prior $70M total raised. Unconfirmed by Nous Research directly, but the first major funding signal for Hermes' maker; relevant for anyone tracking Hermes' resourcing, roadmap pace, and product/business-model expansion. (https://techcrunch.com/2026/07/13/hermes-agent-maker-nous-research-in-talks-for-new-funding-at-1-5b-valuation/)
- **Claude Code `2.1.208` reliability/performance overhaul** — up to 7x faster tool rounds in tool-heavy print/SDK sessions, multiple long-session memory-leak fixes (MCP stdio stderr, LSP document handles, headless/SDK tool-result growth), and up to 79x smaller transcripts in edit-heavy sessions. High-signal for any workflow running Claude Code at scale or over long-running sessions. (https://raw.githubusercontent.com/anthropics/claude-code/refs/heads/main/CHANGELOG.md)

## Maintenance note
This page should stay selective. If a daily update is interesting but not clearly high-signal, keep it in `daily/` only. Entries older than ~2 weeks are periodically trimmed to keep this page focused on recent, still-relevant signal.
