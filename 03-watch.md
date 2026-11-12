# 03 · WATCH: turn any YouTube video into a Claude skill

From the reel: *"Claude can watch any YouTube video and turn it into a skill it uses forever."* → [@orzan.ai](https://instagram.com/orzan.ai)

Works in **Claude Code** (a desktop app Code session, VS Code, or the terminal). It does **not** work in regular Claude chat or Cowork. Commands are copied from the plugin's README (checked 2026-11-12).

---

## 1. Install /watch (free, MIT, 20K+ ⭐)
https://github.com/bradautomates/claude-video

Inside a Claude Code session:
```
/plugin marketplace add bradautomates/claude-video
/plugin install watch@claude-video
```
Start a new session if `/watch` doesn't show up yet. In autocomplete it may appear as `/watch:watch`.

In the desktop app: **Customize → Plugins → Add → Add marketplace → Add from a repository**, paste the GitHub URL above, **Sync**, then install **Watch**.

## 2. The prompt
```
/watch <YouTube link>

Watch this, learn what it teaches, and turn it into a reusable skill.
Save it as ~/.claude/skills/<short-name>/SKILL.md with:
- a `name`
- a `description` that says exactly WHEN I'd want to use it (put the trigger first)
- the method as clear numbered steps, plus the checklists, examples and mistakes-to-avoid from the video
Keep it under 300 lines. Show me the file before saving.
```
Want it polished? Install Anthropic's skill-creator (`/plugin install example-skills@anthropic-agent-skills`) and add "use skill-creator to refine and test it".

## 3. Use it
- Claude uses the skill **automatically** when your task matches its description,
- or you call it yourself: `/<short-name>`.
- Feed it several videos on the same topic and ask Claude to merge them into one skill.

## Ideas to start with
- A great **code review** talk → `/code-reviewer`
- A **system design** lecture → `/architect`
- A **debugging** or **testing** tutorial → `/debugger`
- Your favorite **landing page copywriting** video → `/landing-copy`

## Good to know
- Videos with captions are fastest. Ones without can be transcribed (local WhisperX, or Groq/OpenAI with your own key). See the repo README.
- Long videos use more tokens. Start with talks under about 1 hour.
- Read the skill before you trust it: it's only as good as the video.

---
Next on [@orzan.ai](https://instagram.com/orzan.ai): a team of AI agents that works while you sleep.

[← Back to the vault](README.md)
