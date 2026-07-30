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

### 2026-07-30
- **Hermes ships iMessage-style message reactions as a genuine full-stack capability.** Storage (existing `messages.display_metadata` column, no new table), a `message.react` RPC, a desktop-gated `react_to_message` agent tool, and clean model-context handling (reactions ride `run_message` only, so the persisted prompt and cached prefix never change) all shipped together, with a matching desktop UI (tapback pill, emoji picker, `:shortcode:` completions) bringing desktop to parity with five platform adapters that already supported reactions. A complete capability addition, not a partial or cosmetic one. (https://github.com/NousResearch/hermes-agent/commit/7d92056c49)
- **GitHub Copilot's code review support for agent skills and MCP servers reaches general availability.** After public preview, `.github/skills/*/SKILL.md` files and any MCP servers already configured for Copilot cloud agent now feed directly into every code review (MCP tool calls limited to read-only there), with attribution shown on generated comments. A concrete, large-surface-area productization of MCP and agent skills outside pure dev-tooling contexts — real interoperability reach, not a spec-level update. (https://github.blog/changelog/2026-07-29-copilot-code-review-agent-skills-and-mcp-now-generally-available)

### 2026-07-29
- **The MCP 2026-07-28 specification has gone live.** `modelcontextprotocol.io/specification/latest` now 307-redirects to `/specification/2026-07-28`, confirming the largest protocol revision since launch has shipped: a stateless HTTP core (no more session stickiness — works behind a plain round-robin load balancer), MCP Apps (server-rendered UIs), the Tasks extension, OAuth/OIDC-aligned authorization, and a formal 12-month deprecation policy. Confirmed breaking change for existing MCP client/server implementations. (https://modelcontextprotocol.io/specification/2026-07-28)
- **Hermes ships a real streaming-TTS latency win with a genuine cross-provider adapter contract.** A new opt-in seam on `BasePlatformAdapter` lets voice-capable gateway platforms (LiveKit, Discord voice) consume LLM output as streaming PCM audio before the full response completes, cutting perceived voice latency from ~2–3.5s to ~500–800ms. Gemini and xAI streaming providers were added alongside ElevenLabs/OpenAI, with a `tts.streaming.provider` knob to pin or auto-select. A concrete capability and reliability improvement, not a cosmetic feature. (https://github.com/NousResearch/hermes-agent/commit/3a4aa2f8e6, https://github.com/NousResearch/hermes-agent/commit/bc4dcb1b02)

### 2026-07-28
- **A real MCP interoperability gap with Figma is closed in Hermes.** Figma's `mcp.figma.com` OAuth registration endpoint is a `client_name` allowlist — Claude Code and Codex succeeded, Hermes 403'd. Fixed by auto-setting `client_name` + `client_secret_post` for Figma hosts and forcing interactive OAuth from non-TTY desktop shells; verified end-to-end with `hermes mcp login figma` surfacing 26 tools. A concrete, shipped interoperability fix against a real third-party MCP server, not a roadmap item. (https://github.com/NousResearch/hermes-agent/commit/1eb5ee1e)

### 2026-07-27
- **A real security-relevant dependency bug was closed: `hermes update` was silently downgrading already-CVE-patched environments back onto a vulnerable `cryptography` pin.** The salvaged CVE-pin refresh in #60685 had landed on pin versions below the actual fix for GHSA-537c-gmf6-5ccf, so any user who had already upgraded past that pin got silently downgraded straight back to it on the next `hermes update`. Fixed by moving pins to the versions that are both fixed and mergeable (`cryptography` 46.0.7 → 48.0.1, capped below 49.x by `msal`/`alibabacloud-tea-openapi`), with the anti-downgrade floor guard kept and corrected. (https://github.com/NousResearch/hermes-agent/commit/623762f2)
- **Hermes desktop ships "Artifacts": versioned cards, sandboxed live preview, right-rail viewer.** Substantial generated content (full HTML documents, large SVGs, 48+ line/3k+ char code fences) now promotes out of the transcript into openable, versioned artifacts with a `PREVIEW`/`SOURCE` toggle, copy, kind-aware download, and open-in-browser for HTML — offered on click rather than auto-hijacking the transcript. A genuine new capability, not a bug fix. (https://github.com/NousResearch/hermes-agent/commit/236b1b56)

### 2026-07-26
- **A real SQLite corruption bug in `hermes sessions optimize` was root-caused and closed.** Raw byte-probes on live databases were cancelling a running `VACUUM`'s exclusive POSIX lock — a documented SQLite hazard — letting concurrent writers corrupt `state.db`. Measured A/B reproduction: 2/2 corrupt with the raw read in place, 0/229 vacuum errors with it removed. Fixed by reading page metadata over the existing connection instead of a raw open/close, with three review-driven follow-ups closing a check/use race, an invisible read-only-connection path, and a fail-open error handler that had silently disabled the guard. Genuine data-integrity fix backed by reproducible measurement, not a cosmetic patch. (https://github.com/NousResearch/hermes-agent/commit/fbd5e5772b, https://github.com/NousResearch/hermes-agent/commit/fe431651c5)

## Maintenance note
This page should stay selective. If a daily update is interesting but not clearly high-signal, keep it in `daily/` only. Entries older than ~2 weeks are periodically trimmed to keep this page focused on recent, still-relevant signal.
