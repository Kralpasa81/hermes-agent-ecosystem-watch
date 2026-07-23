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

### 2026-07-23
- **Hermes unifies the clarify-request lifecycle across every surface** — six coordinated PRs fix wrong/hardcoded timeouts (CLI silently used 120s instead of the real `agent.clarify_timeout`), a race that rendered the clarify question above its own explanation, and late-reply handling that used to hit a raw JSON-RPC error on TUI/gateway reconnects. Genuine cross-surface workflow-reliability fix for Hermes' interactive clarify flow on CLI, TUI, desktop, and gateway. (https://github.com/NousResearch/hermes-agent/commit/507d479c8c)
- **Claude Code 2.1.218 closes an agent-hook workspace-trust bypass** — hooks defined in agent frontmatter now require their own folder (not just the invoking session) to have accepted workspace trust before running. Real security-hardening fix for anyone using Claude Code custom agents/hooks. (https://github.com/anthropics/claude-code/releases/tag/v2.1.218)
- **OpenAI launches Presence** — its first managed, governed enterprise product for deploying AI voice/chat agents at scale (policies, escalation rules, monitoring, guardrails bundled), in limited availability. Interoperability/maturity signal for the packaged-agent-infrastructure category. (https://openai.com/index/introducing-openai-presence)

### 2026-07-22
- **Hermes gateway's stranded-platform recovery generalized to every adapter** — yesterday's Discord-only relay fix and today's `fix(gateway)` #69112 close the same class of bug (a platform going permanently dark inside a live gateway process, invisible to `launchd`/`systemd` restart) across Discord, Telegram, qqbot, and photon in two consecutive days. The gateway now hard-exits if a platform ends up neither reconnected nor queued after a fatal error, so process managers actually restart it. Genuine availability improvement for anyone running managed Hermes gateways. (https://github.com/NousResearch/hermes-agent/commit/2ab153218ba401525ec02380305f8c3c4c8b1dc0)
- **Claude Code 2.1.217 adds subagent concurrency/budget guardrails** — closes a real gap where `--max-budget-usd` didn't stop background subagents once the cap was hit, and adds a default 20-subagent concurrency cap plus disabling nested subagent spawning by default. Direct cost-control signal for anyone running Claude Code with subagents in production. (https://github.com/anthropics/claude-code/releases/tag/v2.1.217)

### 2026-07-21
- **Hermes Agent v0.19.0 "Quicksilver" release (tagged Jul 20)** — the primary Hermes release for the window tracked by this repo. Cold-start time-to-first-token cut **~80%** (4.3s → 0.9s) across every surface, reasoning streams live by default, **smart approvals** on by default, **Bitwarden/1Password secret sources**, live subagent transcripts, durable background-delegation delivery, gateway delivery-obligation ledger (previously tracked), profile-based gateway routing, `/subscription` terminal billing, GPT-5.6/grok-4.5/kimi-k3/claude-fable-5/claude-sonnet-5 support, and a 20-PR desktop speed overhaul. Biggest Hermes release in this repo's tracked window. Simultaneously on Jul 21, `fix(relay)` #68320 closes a total-loss-of-service bug for managed Discord agents (guild replies were silently declined because `user_id` was never carried alongside `scope_id` on the outbound relay frame). (https://github.com/NousResearch/hermes-agent/releases/tag/v2026.7.20, https://github.com/NousResearch/hermes-agent/commit/f4df260f26c93f15694698869f3ea8e965eea301)

## Maintenance note
This page should stay selective. If a daily update is interesting but not clearly high-signal, keep it in `daily/` only. Entries older than ~2 weeks are periodically trimmed to keep this page focused on recent, still-relevant signal.
