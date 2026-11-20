# 10 · LIMITS: real ways to cut your Claude Code token use

From the reel: *"Stop wasting your Claude limit. Free Graphify cuts it 70x. Well… or not."* → [@orzan.ai](https://instagram.com/orzan.ai)

Every tip here comes from Anthropic's own Claude Code docs ([Manage costs](https://code.claude.com/docs/en/costs), [Best practices](https://code.claude.com/docs/en/best-practices), [Memory](https://code.claude.com/docs/en/memory)), checked 2026-11-20.

---

## 0. First, measure
- `/usage` shows what this session used (look under **Session**). It also flags any habit behind 10% or more of your recent usage.
- `/context` shows what's filling your context window right now: CLAUDE.md, MCP tools, files, chat.

You can't cut what you can't see. Check both before and after trying the tips below.

## 1. Context: the biggest lever
- **`/clear` between unrelated tasks.** Every message re-sends the whole conversation. Per the docs, "`/clear` costs nothing".
- **`/compact` with a focus** when you want to keep going: `/compact Focus on the API changes and failing tests`. On a very long session, compacting is itself a big request, so clear when you can.
- **Be specific.** "Improve this codebase" makes Claude scan broadly. "Add input validation to `signup()` in `auth.ts`" doesn't.
- **Plan first** (Shift+Tab to plan mode) on big changes, so Claude doesn't build the wrong thing and redo it.
- **Stop early:** press `Esc` the moment it heads the wrong way, and use `/rewind` to go back to a checkpoint.

## 2. CLAUDE.md: loaded every single session
- Keep each CLAUDE.md **under 200 lines**. Only write down what Claude can't figure out from the code.
- Splitting it with imports **doesn't** save anything: imported files still load.
- Instead, put folder-specific notes in **that folder's own CLAUDE.md**, which only loads when Claude works there, or in **path rules** (`.claude/rules/` with `paths:`).
- Move long procedures into **skills**, which load only when a task needs them.
- `/doctor` suggests cuts for anything Claude can already work out from the code.

## 3. Tools and MCP servers
- Run `/mcp` and **disable servers you're not using**. Connected servers add their tool names and instructions to your context even when idle.
- Prefer a CLI (`gh`, `aws`…) when one exists. It costs less context than an MCP server.

## 4. The right model and effort
- `/model`: Sonnet handles most coding work and costs less than Opus. Save Opus for the hard parts.
- `/effort low` for quick back-and-forth; raise it only for tricky problems.
- For subagents doing simple searches, set `model: haiku` in their config.

## 5. Keep noise out of the main chat
- Hand big searches, test runs and log digging to a **subagent**. The noisy output stays in its context, and only a short summary comes back. Ask for that summary to be short.
- A **hook** can trim tool output before Claude sees it, e.g. only the lines containing `ERROR`, or the last 100 lines of a test run.

## 6. So is Graphify worth it?
- **"Claude rereads your whole codebase every session": false.** Claude Code searches first, then opens the files it needs ([How Claude Code works](https://code.claude.com/docs/en/how-claude-code-works)).
- **The famous 70x** is one question on one big repo, not a work session ([RoboRhythms](https://www.roborhythms.com/graphify-review/)).
- **KubeNine's real-work test** (3 rounds of feature work, blind-graded): "None of these results is a 50–60% (or 71.5×) session-level saving." ([KubeBlogs, Aug 2026](https://www.kubeblogs.com/graphify-claims-71-5x-fewer-tokens-we-tested-it-on-real-production-work/))
- **Where it does help:** exploring a huge repo you've never seen, or linking up a pile of research notes. [Graphify on GitHub](https://github.com/graphify-labs/graphify).
- Want to know for your own repo? Run the same task with and without it, then compare `/usage`.
