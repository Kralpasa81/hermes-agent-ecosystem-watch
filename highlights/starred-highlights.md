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

### 2026-08-02
- **A high-severity, silent data-loss bug in `hermes skills install` is fixed.** An unconditional `rmtree` on the target install path could wipe an entire pre-existing category directory — including one holding many unrelated skills — on a plain name collision, with no warning even under `--yes`. The report that triggered the fix cites 16 unrelated skills destroyed in one incident. A genuine data-integrity fix, not cosmetic. (https://github.com/NousResearch/hermes-agent/issues/75983)
- **A Node 26 runtime requirement briefly broke Hermes installs/updates across platforms, then was fully stabilized within the same day.** The breaking bump (`feat(runtime)!:`) hit npm engine checks, a stale lockfile-engines mirror, and cached `hermes_constants`, turning CI red on every PR for roughly a day before a same-window fix wave (managed npm/Node provisioning, relaxed engine ranges, resynced mirrors) restored working installs. Flagged here as a real access/reliability event for anyone installing or updating Hermes on Aug 1–2, not because the Node 26 requirement itself is newsworthy. (https://github.com/NousResearch/hermes-agent/commit/713a983e)

### 2026-07-31
- **A real org-shared-skills sync bug is closed in Hermes: org skills were silently unusable past the first propose.** Root cause was org reads hitting personal `/v1/sync/refs` / `/v1/sync/objects` endpoints (hard-scoped server-side to the caller's own owner), so a request for org state silently returned the caller's personal refs instead of an error, or 404'd — masking two further defects downstream. A concrete access/reliability fix for team and org usage, not a cosmetic patch. (https://github.com/NousResearch/hermes-agent/pull/75237)
- **GitHub Copilot's VS Code Agents window now runs Copilot, Claude, and Codex sessions in isolated Git worktrees from the same UI.** Shipped as part of the July 2026 (v1.127–v1.131) release wave, currently in public preview. A genuine cross-vendor interoperability move inside a single IDE surface, not a Copilot-only feature. (https://github.blog/changelog/2026-07-30-github-copilot-in-visual-studio-code-july-2026-releases)

### 2026-07-30
- **Hermes ships iMessage-style message reactions as a genuine full-stack capability.** Storage (existing `messages.display_metadata` column, no new table), a `message.react` RPC, a desktop-gated `react_to_message` agent tool, and clean model-context handling (reactions ride `run_message` only, so the persisted prompt and cached prefix never change) all shipped together, with a matching desktop UI (tapback pill, emoji picker, `:shortcode:` completions) bringing desktop to parity with five platform adapters that already supported reactions. A complete capability addition, not a partial or cosmetic one. (https://github.com/NousResearch/hermes-agent/commit/7d92056c49)
- **GitHub Copilot's code review support for agent skills and MCP servers reaches general availability.** After public preview, `.github/skills/*/SKILL.md` files and any MCP servers already configured for Copilot cloud agent now feed directly into every code review (MCP tool calls limited to read-only there), with attribution shown on generated comments. A concrete, large-surface-area productization of MCP and agent skills outside pure dev-tooling contexts — real interoperability reach, not a spec-level update. (https://github.blog/changelog/2026-07-29-copilot-code-review-agent-skills-and-mcp-now-generally-available)

### 2026-07-29
- **The MCP 2026-07-28 specification has gone live.** `modelcontextprotocol.io/specification/latest` now 307-redirects to `/specification/2026-07-28`, confirming the largest protocol revision since launch has shipped: a stateless HTTP core (no more session stickiness — works behind a plain round-robin load balancer), MCP Apps (server-rendered UIs), the Tasks extension, OAuth/OIDC-aligned authorization, and a formal 12-month deprecation policy. Confirmed breaking change for existing MCP client/server implementations. (https://modelcontextprotocol.io/specification/2026-07-28)

## Maintenance note
This page should stay selective. If a daily update is interesting but not clearly high-signal, keep it in `daily/` only. Entries older than ~2 weeks are periodically trimmed to keep this page focused on recent, still-relevant signal.
