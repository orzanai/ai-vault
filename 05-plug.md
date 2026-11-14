# 05 · PLUG: the 5 MCPs to plug in first

From the reel: *"Explain it like I'm five: what's an MCP?"* → [@orzan.ai](https://instagram.com/orzan.ai)

An MCP is a snap-on piece that lets Claude use an app. These are the 5 that grown-ups plug in first. Commands are for **Claude Code** and are taken from each project's official docs (checked 2026-11-14). Run them in your terminal, then type `/mcp` inside Claude Code to finish any sign-in.

---

## 1. GitHub (official): issues, PRs, code search
https://github.com/github/github-mcp-server · MIT · 34K+ ⭐
Create a GitHub personal access token, then:
```bash
claude mcp add-json github '{"type":"http","url":"https://api.githubcopilot.com/mcp","headers":{"Authorization":"Bearer YOUR_GITHUB_PAT"}}'
```
*(That's the format for Claude Code 2.1.1 and newer. On Windows, if `add-json` fails, use the `claude mcp add --transport http` form from the repo's install guide.)*

## 2. Notion (official remote): search, read and edit your pages
https://developers.notion.com/guides/mcp/get-started-with-mcp
```bash
claude mcp add --transport http notion https://mcp.notion.com/mcp
```
Then `/mcp` to sign in with your Notion account. It respects your existing permissions.

## 3. Context7: up-to-date library docs, so Claude stops guessing old APIs
https://github.com/upstash/context7 · MIT · 64K+ ⭐
```bash
npx ctx7 setup --claude
```
(Needs Node.js 22.13+. A free API key gives higher rate limits.)

## 4. Playwright (Microsoft): Claude drives a real browser
https://github.com/microsoft/playwright-mcp · Apache-2.0 · 39K+ ⭐
```bash
claude mcp add playwright npx @playwright/mcp@latest
```

## 5. Figma (official remote): turn designs into code
https://help.figma.com/hc/en-us/articles/32132100833559-Guide-to-the-Figma-MCP-server
Remote server: `https://mcp.figma.com/mcp`
```bash
claude mcp add --transport http figma https://mcp.figma.com/mcp
```
Then `/mcp` to sign in. Available on all Figma plans; writing to the canvas outside your drafts needs a Full seat.

---

## Good to know
- **One plug at a time.** Every MCP adds tools to Claude's menu, and too many can confuse it.
- Plugs can read your data (and some can write it). Only connect accounts you're comfortable with, and review what Claude does with write tools.
- See what's connected: `claude mcp list`. Remove one: `claude mcp remove <name>`.

---
Next on [@orzan.ai](https://instagram.com/orzan.ai): RAG explained like you're five.

[← Back to the vault](README.md)
