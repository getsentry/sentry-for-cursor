# Sentry Cursor Plugin

Official Sentry integration plugin for Cursor. Query your Sentry environment in natural language, analyze issues, monitor performance, and automatically resolve bugs detected in pull requests.

## Installation

### From Cursor Marketplace

Search for "sentry" in the Cursor plugin marketplace, then install.

Restart Cursor to activate the plugin, then verify:

```bash
/help           # Should show /seer command
/mcp            # Should show sentry MCP server
```

### From Local Source

```bash
git clone https://github.com/getsentry/sentry-for-cursor.git
cd sentry-for-cursor
```

Add the local directory as a plugin source in Cursor settings.

## Slash Commands

### `/seer <query>`

Ask questions about your Sentry environment in natural language.

```
/seer What are the top errors in the last 24 hours?
/seer Show me all critical issues in mobile-app
/seer Which issues are affecting the most users?
/seer What's the request latency for the api-gateway application?
```

## Skills

### sentry-code-review

Analyzes and fixes bugs detected by Sentry in GitHub Pull Request comments. Requires [GitHub CLI](https://cli.github.com/) (`gh auth login`).

```
Review PR #118 and fix the Sentry comments
```

### Setup Skills

| Skill | Description |
|-------|-------------|
| `sentry-ios-swift-setup` | Setup Sentry in iOS/Swift apps with error monitoring, tracing, session replay, logging, and profiling |
| `sentry-setup-ai-monitoring` | Setup Sentry AI Agent Monitoring for OpenAI, Anthropic, LangChain, etc. |
| `sentry-setup-logging` | Setup Sentry Logging for JavaScript, Python, and Ruby projects |
| `sentry-setup-metrics` | Setup Sentry Metrics (counters, gauges, distributions) |
| `sentry-setup-tracing` | Setup Sentry Tracing and Performance Monitoring |

## Configuration

The plugin automatically configures the Sentry MCP server on install. No additional setup required beyond restarting Cursor.

The `sentry-code-review` skill requires GitHub CLI:

```bash
brew install gh    # macOS, or https://cli.github.com/
gh auth login
```

## Plugin Structure

```
sentry-for-cursor/
├── .cursor-plugin/
│   ├── plugin.json           # Plugin metadata
│   └── marketplace.json      # Marketplace listing
├── mcp.json                  # MCP server configuration
├── AGENTS.md                 # Agent instructions
├── commands/
│   └── seer.md               # /seer command
├── skills/
│   ├── sentry-code-review/
│   ├── sentry-ios-swift-setup/
│   ├── sentry-setup-ai-monitoring/
│   ├── sentry-setup-logging/
│   ├── sentry-setup-metrics/
│   └── sentry-setup-tracing/
├── assets/
│   └── logo.svg              # Plugin logo
└── LICENSE
```

## License

MIT
