# JARVIS: get Stanford's free OpenJarvis talking you through your morning

From the reel: *"Tony Stark's JARVIS is free now. Stanford built it for your laptop."*

**OpenJarvis** is a free, open-source personal AI from Stanford: Hazy Research and the Scaling Intelligence Lab at Stanford SAIL. It runs on your own computer.
- License: Apache 2.0
- Repo: https://github.com/open-jarvis/OpenJarvis (about 18K ⭐)
- Docs: https://open-jarvis.github.io/OpenJarvis/

---

## The exact commands (macOS or Linux)

**1. Install.** About 3 minutes on broadband. It sets up uv, Python, Ollama and a starter model.
```bash
curl -fsSL https://open-jarvis.github.io/OpenJarvis/install.sh | bash
```
On Windows, use PowerShell instead: `irm https://open-jarvis.github.io/OpenJarvis/install.ps1 | iex`

**2. Switch to the morning briefing preset.**
```bash
jarvis init --preset morning-digest-mac --force
```
On Linux, use `morning-digest-linux`.

**3. Connect Gmail, Calendar and Tasks.** One Google sign-in covers all three.
```bash
jarvis connect gdrive
```

**4. Hear your first briefing.**
```bash
jarvis digest --fresh
```

If `jarvis` isn't found, run `source .venv/bin/activate` first, or put `uv run` in front of each command.

---

## Rather not touch the terminal? Let Claude Code do it

Open Claude Code in an empty folder and paste:
> Install OpenJarvis from https://github.com/open-jarvis/OpenJarvis using its official install script. Then set up the morning-digest preset for my OS, and tell me when I need to sign in to Google.

Read what it runs before you approve it. That's good practice with any install script.

---

## Other things it can do (built-in presets)
- `deep-research`: multi-step research with citations
- `code-assistant`: runs code, edits files, uses the shell
- `scheduled-monitor`: an agent that checks something on a schedule and remembers
- `chat-simple`: plain chat, no tools

Try one with `jarvis init --preset <name> --force`.

---

## Plugging in Claude for the hard stuff

By default OpenJarvis uses a local model through Ollama, so your data stays on your machine. It also supports cloud engines (Anthropic, OpenAI, Gemini) for harder tasks. The setup steps are on the docs site under "cloud engines". Using a cloud model means that request leaves your laptop.

---

## Honest limits
- **The local model is slower and simpler than Claude or ChatGPT.** The briefing is fine; hard reasoning is not.
- **It needs a decent laptop.** More RAM lets you run bigger, smarter local models.
- **It's research software.** Expect rough edges and check the repo for updates.

Source: the OpenJarvis README and Stanford's blog (scalingintelligence.stanford.edu/blogs/openjarvis), checked 2026-11-22.
