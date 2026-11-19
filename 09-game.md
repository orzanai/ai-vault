# 09 · GAME: one sentence → a game you can play

From the reel: *"Stop making games alone. Give your Claude 49 free agents."* → [@orzan.ai](https://instagram.com/orzan.ai)

**The repo:** [Claude Code Game Studios](https://github.com/Donchitos/Claude-Code-Game-Studios) by Donchitos. Free and MIT-licensed, about 40K GitHub stars. Facts are from its README, checked 2026-11-16.

---

## 1. Set it up (5 minutes)
You need Git, Claude Code, Python 3 and Bash. Chrome, Edge or Chromium lets it play-test the game.
```bash
git clone https://github.com/Donchitos/Claude-Code-Game-Studios.git my-game
cd my-game
claude
```
Start `claude` from the project root. The README warns that starting in a subfolder skips its hooks and permissions.

## 2. The exact first prompt
```
/prototype a fishing game where the rare fish only bite at dusk
```
Swap in your own idea. Claude asks a few questions, writes a one-page brief, builds a browser game, runs it and checks it. Not sure what to make? Run `/start` for a guided intro.

## 3. Start light, then hire the team
- The default `minimal` mode is the light path: one brief, a game you play, then one feature per session.
- **Studio mode** adds 49 specialised agents (directors, leads, specialists down to a QA tester), plus design docs, sprints and gates. `/next-step` suggests it once your game grows to about nine stories or features.
- **The twist from the authors' own test:** they built the same brief at different rigor levels.
  - `minimal`: 1 document and 0 minutes before code.
  - `standard`: 30 documents and 58 minutes.
  - Two blind reviewers and a human playtest ranked the heavier build **last**.
  - It was one brief and the results are self-reported, but it's why light mode is the default.
- To raise the rigor later: `/project-settings modes.rigor=standard`

## 4. Good first ideas
- "a typing game where the words fall faster every 30 seconds"
- "a tiny farming game with one crop and a day/night cycle"
- "a one-button platformer where you can only jump at night"
