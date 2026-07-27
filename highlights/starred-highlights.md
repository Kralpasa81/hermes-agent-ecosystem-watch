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

### 2026-07-27
- **A real security-relevant dependency bug was closed: `hermes update` was silently downgrading already-CVE-patched environments back onto a vulnerable `cryptography` pin.** The salvaged CVE-pin refresh in #60685 had landed on pin versions below the actual fix for GHSA-537c-gmf6-5ccf, so any user who had already upgraded past that pin got silently downgraded straight back to it on the next `hermes update`. Fixed by moving pins to the versions that are both fixed and mergeable (`cryptography` 46.0.7 → 48.0.1, capped below 49.x by `msal`/`alibabacloud-tea-openapi`), with the anti-downgrade floor guard kept and corrected. (https://github.com/NousResearch/hermes-agent/commit/623762f2)
- **Hermes desktop ships "Artifacts": versioned cards, sandboxed live preview, right-rail viewer.** Substantial generated content (full HTML documents, large SVGs, 48+ line/3k+ char code fences) now promotes out of the transcript into openable, versioned artifacts with a `PREVIEW`/`SOURCE` toggle, copy, kind-aware download, and open-in-browser for HTML — offered on click rather than auto-hijacking the transcript. A genuine new capability, not a bug fix. (https://github.com/NousResearch/hermes-agent/commit/236b1b56)

### 2026-07-26
- **A real SQLite corruption bug in `hermes sessions optimize` was root-caused and closed.** Raw byte-probes on live databases were cancelling a running `VACUUM`'s exclusive POSIX lock — a documented SQLite hazard — letting concurrent writers corrupt `state.db`. Measured A/B reproduction: 2/2 corrupt with the raw read in place, 0/229 vacuum errors with it removed. Fixed by reading page metadata over the existing connection instead of a raw open/close, with three review-driven follow-ups closing a check/use race, an invisible read-only-connection path, and a fail-open error handler that had silently disabled the guard. Genuine data-integrity fix backed by reproducible measurement, not a cosmetic patch. (https://github.com/NousResearch/hermes-agent/commit/fbd5e5772b, https://github.com/NousResearch/hermes-agent/commit/fe431651c5)
- **Partial session recovery stopped deleting the exact data it had just salvaged.** A real `--allow-partial` recovery run (reported in Discord) copied 20,817 of 20,824 message rows, then orphan cleanup deleted every one of them because the `sessions` table itself was too damaged to salvage — final output was 0 sessions, 0 messages. Placeholder session rows are now reconstructed before cleanup runs, so salvaged conversation text survives while the loss is still honestly reported. (https://github.com/NousResearch/hermes-agent/commit/d2e733e636)

### 2026-07-25
- **Claude Opus 5 launches as a genuine cross-ecosystem event.** New default Opus model in Claude Code `2.1.219` (1M context, fast mode at $10/$50 per Mtok) shipped the same day across nine GitHub Copilot surfaces (VS Code, Visual Studio, Copilot CLI, cloud agent, Copilot app, JetBrains, Xcode, Eclipse, github.com). A real day-one multi-vendor model launch with an attached pricing/fast-mode change, not a staggered rollout. (https://github.com/anthropics/claude-code/releases/tag/v2.1.219, https://github.blog/changelog/2026-07-24-claude-opus-5-is-now-available-in-github-copilot)
- **Hermes closes two real cross-session leak bugs in one day.** A desktop background-queue drain could deliver a queued message into the session the user happened to be viewing instead of the session that owned it; a shared terminal bash snapshot could leak one session's `HERMES_SESSION_ID` into a concurrent session on the same backend. Both are genuine multi-session-isolation correctness fixes with regression tests, not cosmetic bugs. (https://github.com/NousResearch/hermes-agent/commit/062d261955, https://github.com/NousResearch/hermes-agent/commit/f2e32ceead)
- **Hermes ships a crash-survivable in-flight turn journal for desktop.** A full app or machine crash mid-turn previously discarded everything the crashed turn had streamed with no trace; the visible tail is now journaled locally (bounded, throttled) and reconciled with the backend's live projection on resume. Genuine reliability improvement against a real data-loss class. (https://github.com/NousResearch/hermes-agent/commit/8d8d1d61fe)

### 2026-07-24
- **Hermes cron reconciliation fix closes a real 20-hour silent-outage class.** A direct-run/scheduled-fire race for the same job occurrence could leave a recurring cron job permanently orphaned — the winning direct run advanced `next_run_at` but never notified the external provider, so its one-shot for that occurrence stayed stale forever, while `/api/status` kept reporting green the entire time. Now a claimed direct execution notifies the provider so it re-arms correctly. Genuine reliability fix for anyone running Hermes cron jobs behind an external scheduler/provider. (https://github.com/NousResearch/hermes-agent/commit/ef6ce56cad)
- **GitHub MCP Server ships stateless-core support ahead of the July 28 MCP spec cutover.** A concrete, shipped implementation — not just a roadmap note — removing Redis-backed sessions entirely, replacing deep packet inspection with guaranteed HTTP-header fields for logging/secret-scanning, and upgrading stdio elicitation to the new multi-round-trip HTTP flow with backward compatibility. Strongest evidence yet that the breaking stateless-MCP transition is shipping on schedule. (https://github.blog/changelog/2026-07-23-github-mcp-server-supports-the-next-mcp-specification/)

## Maintenance note
This page should stay selective. If a daily update is interesting but not clearly high-signal, keep it in `daily/` only. Entries older than ~2 weeks are periodically trimmed to keep this page focused on recent, still-relevant signal.
