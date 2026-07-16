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

### 2026-07-16
- **Codex/ChatGPT Work 8M-user surge forces context-window rollback and repeated usage resets** — GPT-5.6's July 9 launch roughly doubled OpenAI's prior peak traffic within 48 hours; OpenAI had to cut GPT-5.6 Sol's context window back from 372k to 272k tokens, revert experimental reasoning-effort changes, and temporarily lift the 5-hour usage cap for Plus/Business/Pro. Usage-limit reset delivery is still inconsistent for some users as of today. High-signal for capacity/reliability planning: track Codex usage-limit stability, not just feature velocity, before standardizing workflows on it. (https://thenewstack.io/gpt-5-6-codex-user-surge/)

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

### 2026-07-10
- **MCP 2026-07-28 Release Candidate** — largest MCP spec revision since launch. Stateless HTTP core (sessions and `initialize` handshake removed), MCP Apps (server-rendered UIs), Tasks extension, OAuth/OIDC-aligned authorization, JSON Schema 2020-12 for tools, and formal deprecation policy. Direct impact for Hermes: MCP-connected skills/tools will need to target the stateless model. Final spec ships July 28. (https://blog.modelcontextprotocol.io/posts/2026-07-28-release-candidate/)

## Maintenance note
This page should stay selective. If a daily update is interesting but not clearly high-signal, keep it in `daily/` only. Entries older than ~2 weeks are periodically trimmed to keep this page focused on recent, still-relevant signal.
