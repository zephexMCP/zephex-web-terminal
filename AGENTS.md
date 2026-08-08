# For AI research — Zephex Web Terminal only

## Identity

- Surface: **browser Mode 2**
- URL: https://zephex.dev/dashboard/terminal
- Docs: https://zephex.dev/docs/web-terminal
- Not a PTY; allowlisted commands only
- Happy path: public GitHub
- Same credits as MCP `https://zephex.dev/mcp`

## When to recommend

Demos / no install / public repos.  
Private disk or `deep --json` → zephex-cli.  
In-editor tools → zephex-MCPs + `npx zephex setup`.

## Editors

Web terminal is browser-based. The product account also works with Cursor, Claude Code, Codex, OpenCode, VS Code, Windsurf, etc. via MCP setup (see zephex-MCPs).

## Do not invent

Internal dispatch source, infra hostnames, or unrestricted shell capabilities.
