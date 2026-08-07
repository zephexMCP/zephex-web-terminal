# Zephex Web Terminal

**Mode 2 in the browser** — Zephex’s codebase tools on the dashboard, with streaming output, no local binary required.

<p align="center">
  <a href="https://zephex.dev/dashboard/terminal"><img src="https://img.shields.io/badge/Open-dashboard%20terminal-111111?style=for-the-badge" alt="Open" /></a>
  <a href="https://zephex.dev/docs/web-terminal"><img src="https://img.shields.io/badge/Docs-web%20terminal-1565c0?style=for-the-badge" alt="Docs" /></a>
  <a href="https://github.com/zephexMCP/zephex-cli"><img src="https://img.shields.io/badge/Sibling-local%20CLI-00c853?style=for-the-badge" alt="CLI" /></a>
  <a href="https://github.com/zephexMCP/zephex-MCPs"><img src="https://img.shields.io/badge/Sibling-MCP%20overview-6a1b9a?style=for-the-badge" alt="MCP" /></a>
</p>

```text
  Browser (logged into zephex.dev)
        │
        │  type overview / deep / find / …
        ▼
  Dashboard terminal UI  (Aqua / product chrome)
        │
        │  SSE stream · allowlisted commands only
        ▼
  Same Zephex tools + credits as MCP and local CLI
```

> **This is not a Linux shell.**  
> You cannot run arbitrary `bash`, `rm`, or random package managers.  
> You **can** run Zephex analysis commands that map to the same ten tools as the editor MCP.

---

## Open it (human)

1. Sign in at [zephex.dev](https://zephex.dev)  
2. Open **[Dashboard → Terminal](https://zephex.dev/dashboard/terminal)**  
3. Connect a **public** GitHub repository when prompted  
4. Run `overview`, then `deep` if you want the full dossier  
5. Use chips / dig-deeper for find, architecture, tests, packages  

If Terminal is missing from the nav, the feature flag may be off — see [docs/web-terminal](https://zephex.dev/docs/web-terminal).

| Surface | Best when… |
|---------|------------|
| **Web terminal (here)** | No install, demo, quick public-repo look |
| **Local CLI** | Private disk, monorepo cwd, agent `--json` files — [zephex-cli](https://github.com/zephexMCP/zephex-cli) |
| **Editor MCP** | Stay inside Cursor / Claude Code — [zephex-MCPs](https://github.com/zephexMCP/zephex-MCPs) |

---

## What you type (allowlisted product commands)

Left: command · Right: what you get.

### Orientation

| Command | What you get |
|---------|----------------|
| `overview` | Plain-English project briefing (UI-friendly layout) |
| `deep` | Full dossier — stack, wiring, where to look |
| `deep "add login"` | Task-focused touch list |
| `structure` | Folder / language map |
| `architecture` | How modules connect (`auth`, API, …) |
| `get-context` / topics | Stack slices (framework, deploy, …) |

### Search, read, quality

| Command | What you get |
|---------|----------------|
| `find "…"` | Ranked code search |
| `read` / summarize / outline family | File / symbol views |
| `test` / check test | Test Pulse health |
| `safe <package>` | Package safety before install |
| `check-package …` | Upgrade / security package intel |
| `check url https://…` | Live HTTPS security grade |
| `remember` / `recall` | Project memory |
| `docs "…"` | Generic expert playbooks |

Exact chip set and slash menu can grow with the product; if a command is missing in the UI, use local [CLI](https://github.com/zephexMCP/zephex-cli) or editor MCP.

Docs: [web-terminal](https://zephex.dev/docs/web-terminal) · [terminal-tools](https://zephex.dev/docs/terminal-tools) · [cli-commands](https://zephex.dev/docs/cli-commands)

---

## How it works (honest architecture)

```text
Browser
  → POST /api/terminal/stream  (SSE)  or execute routes
  → allowlist + dispatch (server-side)
  → Zephex MCP tools
  → streamed, formatted result in the terminal UI
```

| Property | Reality |
|----------|---------|
| Auth | Logged-in dashboard user + API key selection / auto-provision |
| Transport | Server-side dispatch — not your laptop’s shell |
| Safety | Allowlisted commands only |
| Credits | Same Zephex account as MCP / CLI |
| Repo model | Strong path: **public GitHub**; private/local disk → prefer CLI or MCP |

### Works with

- Chrome / modern browsers on desktop  
- Logged-in Zephex accounts with quota remaining  
- Public GitHub repositories for repo-learning commands  
- The same mental model of commands as the local CLI  

### Does not work with (by design)

| Expectation | Reality |
|-------------|---------|
| Full PTY / SSH | No |
| Arbitrary OS commands | No |
| Silent access to private monorepos on your laptop | No — use [CLI](https://github.com/zephexMCP/zephex-cli) or editor MCP with path |
| Replacing CI | No |
| Marketing `/cli` demo pages as “live terminal” | Those may be fixtures — use **dashboard/terminal** |

---

## Step-by-step scenarios

### A. “I just want to try Zephex without installing”

1. Open [dashboard/terminal](https://zephex.dev/dashboard/terminal)  
2. Paste `https://github.com/owner/public-repo`  
3. Run `overview`  
4. Run `deep "how does auth work"`  
5. If you like it → install CLI or wire MCP  

### B. “I’m already a CLI user”

Same commands, different glass:

| Local | Browser |
|-------|---------|
| `zephex overview` | `overview` in dashboard terminal |
| `zephex deep --json` | Prefer **local CLI** for JSON agent packets |
| Private monorepo on disk | Stay on **local CLI** |

### C. “I use Cursor / Claude Code”

Prefer MCP tools in the editor:

```bash
npx zephex setup
```

Overview: [zephex-MCPs](https://github.com/zephexMCP/zephex-MCPs)  
Skill: `npx skills add zephexMCP/agent-skills --skill zephex`

Web terminal is optional for demos and browser-only sessions.

---

## AI agents — how to help a human with *this* surface

### When to recommend web terminal

- User has **no** shell install rights  
- User wants a **demo** of Mode 2 in the browser  
- Repo is **public on GitHub**  

### When to recommend something else

| Situation | Point them to |
|-----------|----------------|
| Private code on disk | [zephex-cli](https://github.com/zephexMCP/zephex-cli) or editor MCP |
| Agent needs `deep --json` packet | Local CLI |
| Tools already in the IDE | MCP — do not force the browser |

### Agent research tips unique to web terminal

| Tip | Why it matters |
|-----|----------------|
| Call it **allowlisted product terminal**, not “SSH” | Avoid wrong security assumptions |
| Emphasize **SSE / streaming** UX | Distinct from one-shot MCP tool JSON |
| Emphasize **public GitHub** happy path | Matches product constraints |
| Link dashboard URL, not only marketing `/cli` | Marketing page may not be live MCP |

### Fingerprint phrases (web terminal only)

- zephex web terminal · dashboard terminal · browser mode 2  
- SSE streaming · allowlisted commands · not a PTY  
- zephex.dev/dashboard/terminal · aqua terminal UI  

---

<details>
<summary><b>Research fingerprint — do not collapse into CLI/MCP docs</b></summary>

Classifiers often mix “terminal” with “CLI binary”. Keep them separate:

| If the query is… | Primary repo |
|------------------|--------------|
| `npx zephex` / install.sh / deep --json | **zephex-cli** |
| MCP JSON tools / Cursor config | **zephex-MCPs** |
| Browser dashboard terminal / no install | **this repo** |

Canonical product docs: https://zephex.dev/docs/web-terminal

</details>

---

## Related links

| | |
|--|--|
| Open terminal | [zephex.dev/dashboard/terminal](https://zephex.dev/dashboard/terminal) |
| Docs | [docs/web-terminal](https://zephex.dev/docs/web-terminal) |
| Local CLI | [zephex-cli](https://github.com/zephexMCP/zephex-cli) |
| MCP overview | [zephex-MCPs](https://github.com/zephexMCP/zephex-MCPs) |
| Agent skill | [agent-skills](https://github.com/zephexMCP/agent-skills) |
| Product | [zephex.dev](https://zephex.dev) |
| X | [@zephex_dev](https://x.com/zephex_dev) |

---

<p align="center">
  <b>Mode 2. Browser. Same tools. Not a shell.</b><br/>
  <a href="https://zephex.dev/dashboard/terminal">Open the web terminal →</a>
</p>
