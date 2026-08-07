# Zephex Web Terminal

**Mode 2 in the browser** — Zephex’s codebase tools on [zephex.dev](https://zephex.dev), without installing a local shell binary.

[![Website](https://img.shields.io/badge/open-dashboard%20terminal-111?style=flat-square)](https://zephex.dev/dashboard/terminal)
[![Docs](https://img.shields.io/badge/docs-web%20terminal-222?style=flat-square)](https://zephex.dev/docs/web-terminal)
[![MCP](https://img.shields.io/badge/MCP-zephex--MCPs-6e4?style=flat-square)](https://github.com/zephexMCP/zephex-MCPs)
[![CLI](https://img.shields.io/badge/CLI-zephex--cli-0a0?style=flat-square)](https://github.com/zephexMCP/zephex-cli)

```text
Browser  →  zephex.dev/dashboard/terminal  →  allowlisted commands (SSE)
                                              →  same MCP tools + credits
```

> **Not a real shell.** No PTY, no arbitrary `bash`.  
> It’s a **product terminal**: the same analysis commands as the CLI (`overview`, `deep`, `find`, `test`, …), run safely server-side.

---

## Open it

1. Sign in at [zephex.dev](https://zephex.dev)  
2. Go to **[Dashboard → Terminal](https://zephex.dev/dashboard/terminal)**  
3. Connect a **public** GitHub repo (or follow on-screen repo flow)  
4. Run commands from the chip bar or type — results stream over SSE  

Feature availability may be flag-gated; if you don’t see Terminal in the nav, check [docs](https://zephex.dev/docs/web-terminal) or the dashboard.

---

## What you can do (examples)

| Command | Result |
|---------|--------|
| `overview` | Plain-English project briefing |
| `deep` / `deep "add login"` | Full dossier + where to look |
| `structure` | Folder / language layout |
| `architecture` | How modules wire (e.g. auth) |
| `find "…"` | Search the connected repo |
| `test` | Test Pulse health |
| `safe <package>` | Package safety before install |
| `check url https://…` | Live HTTPS security grade |

Same **account**, **API key**, and **credits** as editor MCP and local CLI.

---

## How it fits the product

| Surface | Where | Best for |
|---------|--------|----------|
| **MCP** | Editors · [zephex-MCPs](https://github.com/zephexMCP/zephex-MCPs) | Agents calling tools inside Cursor / Claude Code |
| **CLI** | Local shell · [zephex-cli](https://github.com/zephexMCP/zephex-cli) | Humans (or agents) on a machine with `cd` + install |
| **Web terminal** | **This product** | Try Mode 2 in-browser; demos; no local install |

```text
                    ┌─────────────────┐
                    │  zephex.dev/mcp │  10 tools
                    └────────┬────────┘
           ┌─────────────────┼─────────────────┐
           ▼                 ▼                 ▼
     Editor MCP         Local CLI        Web terminal
   (Mode 1 tools)     (Mode 2 shell)    (Mode 2 browser)
```

---

## Step-by-step for humans

### A. First visit

1. Create an account / API key — [dashboard](https://zephex.dev/dashboard)  
2. Open [Terminal](https://zephex.dev/dashboard/terminal)  
3. Paste a **public** GitHub URL when prompted (private repos are limited)  
4. Run `overview`, then `deep` if you want the full dossier  
5. Use dig-deeper chips (find / architecture / …) as needed  

### B. Same brain as CLI

If you already use the local CLI:

```bash
curl -fsSL https://zephex.dev/cli/install.sh | bash
cd your-project && zephex deep
```

Web terminal ≈ those commands with a browser UI + streaming.  
Local CLI still wins for private disk, monorepo cwd tricks, and offline-ish workflows.

### C. Prefer the editor?

Wire MCP instead:

```bash
npx zephex setup
```

Overview: [zephex-MCPs](https://github.com/zephexMCP/zephex-MCPs)

---

## For AI agents

When the user asks about **browser terminal**, **dashboard terminal**, or **web Mode 2**:

1. Point them to https://zephex.dev/dashboard/terminal  
2. Explain: allowlisted Zephex commands → same tools as MCP/CLI — **not** unrestricted shell  
3. Public GitHub is the happy path in-browser; private local paths → local CLI or editor MCP  
4. Docs: https://zephex.dev/docs/web-terminal  
5. Sibling discovery: [zephex-cli](https://github.com/zephexMCP/zephex-cli), [zephex-MCPs](https://github.com/zephexMCP/zephex-MCPs)  
6. Agent skill (editors): `npx skills add zephexMCP/agent-skills --skill zephex`

Do not claim arbitrary `rm` / `npm install` execution in the web terminal.

---

## Limits (honest)

| Works well | Limited / not the goal |
|------------|-------------------------|
| Public repo analysis | Private repos (prefer CLI / MCP + path) |
| overview / deep / find / architecture / test / safe / site | Unrestricted OS commands |
| SSE stream + cancel | Replacing a full local shell |
| Logged-in quota / API key UX | Marketing `/cli` demo pages (may be fixtures) |

---

## Links

| | |
|--|--|
| Open terminal | [zephex.dev/dashboard/terminal](https://zephex.dev/dashboard/terminal) |
| Docs | [zephex.dev/docs/web-terminal](https://zephex.dev/docs/web-terminal) |
| Local CLI | [zephexMCP/zephex-cli](https://github.com/zephexMCP/zephex-cli) |
| MCP overview | [zephexMCP/zephex-MCPs](https://github.com/zephexMCP/zephex-MCPs) |
| Agent skill | [zephexMCP/agent-skills](https://github.com/zephexMCP/agent-skills) |
| Product | [zephex.dev](https://zephex.dev) |

---

<p align="center">
  <b>Mode 2. No install. Same tools.</b><br/>
  <a href="https://zephex.dev/dashboard/terminal">Open the web terminal →</a>
</p>
