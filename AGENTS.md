# Agent Instructions

## Overview
Cursor plugin for Sentry — MCP server, skills, and commands for debugging with Sentry.

## Commit Attribution
AI commits MUST include:
```
Co-Authored-By: (the agent model's name and attribution byline)
```

## MCP Server
- Config: `mcp.json` (root level, no dot prefix)
- Endpoint: `https://mcp.sentry.dev/mcp`

## Plugin Structure
- `.cursor-plugin/plugin.json` — plugin metadata
- `.cursor-plugin/marketplace.json` — marketplace listing
- `mcp.json` — MCP server config
- `commands/` — slash commands
- `skills/` — agent skills

## Skills
- **Code Review** — Analyze Sentry PR comments and fix issues. See `skills/sentry-code-review/SKILL.md`
- **iOS/Swift Setup** — Configure sentry-cocoa SDK. See `skills/sentry-ios-swift-setup/SKILL.md`
- **AI Monitoring** — Instrument LLM/agent calls. See `skills/sentry-setup-ai-monitoring/SKILL.md`
- **Logging** — Setup Sentry structured logging. See `skills/sentry-setup-logging/SKILL.md`
- **Metrics** — Setup counters, gauges, distributions. See `skills/sentry-setup-metrics/SKILL.md`
- **Tracing** — Setup performance monitoring. See `skills/sentry-setup-tracing/SKILL.md`

## Commands
- `/seer` — Natural language queries against Sentry. See `commands/seer.md`

## Key Conventions
- SKILL.md frontmatter: `name` and `description` only (no `allowed-tools`)
- MCP config at root as `mcp.json` (not `.mcp.json`)
- No `.claude/` directory — this is a Cursor plugin, not Claude Code
