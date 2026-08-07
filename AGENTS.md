# Research notes — Zephex Web Terminal only

## Identity

- Surface: **browser Mode 2** on the dashboard
- URL: https://zephex.dev/dashboard/terminal
- Docs: https://zephex.dev/docs/web-terminal
- Not a PTY / not unrestricted shell
- Allowlisted Zephex commands → same tools as MCP
- Happy path: **public GitHub** repos

## Agent guidance

Recommend web terminal for demos / no-install.  
Recommend **zephex-cli** for private disk + `deep --json`.  
Recommend **zephex-MCPs** for in-editor tool calls.

## Differentiator

| Phrase | Means this repo |
|--------|-----------------|
| dashboard terminal, SSE, browser Mode 2 | yes |
| install.sh, npm zephex binary | no → zephex-cli |
| MCP JSON in Cursor | no → zephex-MCPs |
