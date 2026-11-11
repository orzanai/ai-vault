# 02 · SKILLS: 5 free add-ons for Claude Code

From the reel: *"Your Claude Code is running at 20%."* → [@orzan.ai](https://instagram.com/orzan.ai)

Run these inside Claude Code. Commands are copied from each project's README (checked 2026-11-10).
**New to this? Start with 1 and 2.**

---

## 1. Superpowers: spec → plan → subagents, tests first
https://github.com/obra/superpowers · MIT

Claude stops jumping straight into code. It asks what you're building, shows you a short spec to approve, writes a plan, then runs subagents that build it with red/green TDD.
```
/plugin install superpowers@claude-plugins-official
```

## 2. Karpathy rules: one CLAUDE.md, four rules
https://github.com/multica-ai/andrej-karpathy-skills

Based on Andrej Karpathy's notes on LLM coding pitfalls: **Think before coding · Simplicity first · Surgical changes · Goal-driven execution.**
```
/plugin marketplace add forrestchang/andrej-karpathy-skills
/plugin install andrej-karpathy-skills@karpathy-skills
```
Or per project:
```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/forrestchang/andrej-karpathy-skills/main/CLAUDE.md
```

## 3. Agent Skills by Addy Osmani: a senior engineer's workflow as commands
https://github.com/addyosmani/agent-skills · MIT

`/spec` `/plan` `/build` `/test` `/review` `/ship` (+ `/constraints`, `/webperf`, `/code-simplify`). The right skill also activates automatically for what you're doing.
```bash
npx skills add addyosmani/agent-skills
```
In Claude Code, use `/agent-skills:review` where a built-in command has the same name.

## 4. Anthropic's official skills
https://github.com/anthropics/skills

From the team that makes Claude: `frontend-design`, `webapp-testing`, `mcp-builder`, `skill-creator`, plus the `docx` / `pdf` / `pptx` / `xlsx` skills behind Claude's file creation.
```
/plugin marketplace add anthropics/skills
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```

## 5. Chrome DevTools MCP, from Google's Chrome team
https://github.com/ChromeDevTools/chrome-devtools-mcp · Apache-2.0

Claude controls a real Chrome: reads the console (with source-mapped stack traces), inspects network requests, takes screenshots and records performance traces.
```
/plugin marketplace add ChromeDevTools/chrome-devtools-mcp
/plugin install chrome-devtools-mcp@chrome-devtools-plugins
```
⚠️ It can see everything in that browser, so don't use it in a profile that's logged into sensitive accounts. Usage statistics are on by default (opt out with `--no-usage-statistics`).

---
Next on [@orzan.ai](https://instagram.com/orzan.ai): Claude watches a YouTube video and turns it into a skill.

[← Back to the vault](README.md)
