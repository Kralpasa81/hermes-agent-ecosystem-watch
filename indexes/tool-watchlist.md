# Tool Watchlist

A rolling list of tools, platforms, and programs that matter for the Hermes-adjacent and AI agent ecosystem.

## Core tracked tools

### Hermes Agent
- Area: open-source agent framework
- Why it matters: primary watch target for releases, docs, gateway, tools, cron, skills, MCP, and workflow changes
- Current watch note: June 17 main-branch work focused on provider/MCP and deployment reliability: Anthropic OAuth calls now normalize real MCP-server tool names from `mcp_` to `mcp__` on the wire to avoid extra-usage billing misclassification, interactive CLI completion no longer blocks typing on every keystroke or treats URLs as file paths, Kubernetes/containerd/CRI container detection is broader, and gateway message timestamps are opt-in by default.
- Source: https://github.com/NousResearch/hermes-agent

### Claude Code
- Area: coding agent / agentic development workflow
- Why it matters: strong benchmark and ecosystem signal for coding-agent UX, limits, and workflow features
- Current watch note: `v2.1.179` is a reliability-focused release: partial responses are preserved on mid-stream connection drops, the `running tool` spinner no longer gets stuck, remote background tasks no longer appear stuck between turns, remote plugin loading is faster, WSL2 mouse-wheel scrolling is fixed, and large sandbox `denyRead`/`allowRead` globs no longer make Linux sessions unusable.
- Source: https://github.com/anthropics/claude-code/releases/tag/v2.1.179

### Anthropic Claude Fable 5 / Mythos 5
- Area: frontier model tier for coding agents and long-horizon knowledge work
- Why it matters: affects Claude Code, GitHub Copilot model choice, provider routing, governance, cost, data-retention review, and high-complexity autonomous coding workflows
- Current watch note: Announced June 9, then materially changed on June 12. Anthropic says a US government export-control directive requires suspending access to Fable 5 and Mythos 5 for all customers, while access to other Anthropic models is not affected. This changes the availability picture for Claude Code, Copilot model choice, provider routing, and teams evaluating Mythos-class coding workflows.
- Sources: https://www.anthropic.com/news/claude-fable-5-mythos-5, https://www.anthropic.com/news/fable-mythos-access

### OpenAI Codex / OpenAI developer stack
- Area: coding agents / developer tooling
- Why it matters: major ecosystem direction-setter for agent workflows, desktop automation, CLI/IDE flows, MCP configuration, and API/platform patterns
- Current watch note: Codex CLI `0.140.0` remains the latest stable CLI release with substantive notes, while the Codex changelog now lists expanded EEA/UK/Switzerland availability for Computer Use on macOS/Windows, the Codex Chrome extension, Memories, and Chronicle. `0.141.0-alpha.4` is visible as a prerelease but has no detailed release notes yet.
- Sources: https://developers.openai.com/codex/changelog, https://github.com/openai/codex/releases/tag/rust-v0.140.0, https://github.com/openai/codex/releases/tag/rust-v0.141.0-alpha.4

### GitHub Copilot
- Area: IDE assistant / GitHub-native coding workflows
- Why it matters: relevant for practical agent workflows, MCP, code review, memory controls, model governance, and developer automation
- Current watch note: June 15 Copilot usage metrics now supplement client-side telemetry with server-side telemetry, improving enterprise active-user/DAU coverage and alignment with billing/activity data, while detailed feature/model/IDE breakdowns may remain unattributed for server-side-only detections. June 12 code-review governance controls and June 11 Agentic Workflows remain stronger workflow signals.
- Sources: https://github.blog/changelog/2026-06-15-copilot-usage-metrics-now-include-more-of-your-active-users, https://github.blog/changelog/2026-06-12-copilot-code-review-new-configurations-and-controls

### GitHub Copilot SDK
- Area: embeddable agent runtime / developer SDK
- Why it matters: stable programmatic access to Copilot planning, tool invocation, file edits, streaming, multi-turn sessions, custom tools, MCP servers, hooks, tracing, BYOK, and cloud/remote sessions
- Current watch note: General availability was announced on June 2, with SDK support across six language stacks and new Rust/Java availability called out at GA.
- Source: https://github.blog/changelog/2026-06-02-copilot-sdk-is-now-generally-available

### GitHub Agentic Workflows
- Area: GitHub Actions-native agentic engineering automation
- Why it matters: brings reasoning-based agents into governed CI/CD infrastructure for triage, CI failure analysis, documentation updates, security remediation, dependency maintenance, routine change review, reporting, and compliance
- Current watch note: Public preview was announced June 11. Workflows are written in natural-language Markdown, compiled into standard GitHub Actions YAML, run with read-only defaults and sandboxing, and can use `GITHUB_TOKEN` instead of long-lived PATs with organization billing via `copilot-requests: write`. Also watch the June 16 GitHub Actions Node 24 default-runtime migration because agentic workflows and their third-party JavaScript actions inherit the underlying Actions runtime behavior.
- Sources: https://github.blog/changelog/2026-06-11-github-agentic-workflows-is-now-in-public-preview, https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners

### OpenAI Codex Sites
- Area: Codex-hosted app/site canvas
- Why it matters: extends Codex from coding tasks into hosted interactive sites, dashboards, internal tools, lightweight apps, and games that can be shared within a workspace
- Current watch note: Announced as a June 2 preview inside the Codex app alongside role-specific plugins and annotations.
- Source: https://openai.com/index/codex-for-every-role-tool-workflow/

### MCP ecosystem
- Area: protocol / tool interoperability layer
- Why it matters: increasingly central to connecting agents with external tools and services
- Current watch note: June 6 review promoted the MCP 2026-07-28 release candidate as a high-signal interoperability update with breaking changes: stateless HTTP-friendly core, MCP Apps for server-rendered UI, Tasks for long-running work, OAuth/OIDC-aligned authorization, JSON Schema 2020-12 support, and a formal deprecation policy. June 5 also noted an active individual IETF Internet-Draft on MCP security considerations; it has no formal IETF standing but remains a useful risk signal.
- Source: https://modelcontextprotocol.io/

## Watchlist policy
- Add a tool only if it is materially relevant.
- Update entries when a platform shifts meaningfully.
- Do not bloat this file with trivial launches or low-signal copycat tools.
