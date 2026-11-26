# SAVED: let Claude go through your saved reels and hand you the 5 worth doing

From the reel: *"Stop saving reels. I have 4,161 saved. I never go back."*

Saving feels like learning. It isn't. This sets Claude Code loose on your saved folder. It **opens each reel**, reads the caption and the text on screen, sorts everything into topics, and gives you a short list to actually do this week.

---

## Step 1: get your saved list (one file)
In the Instagram app: **Settings → Accounts Center** (it may say *Meta Account*) **→ Your information and permissions → Export your information → Create export.** Pick your Instagram account, choose only **Saved**, and set the format to **JSON**.

Instagram tells you when it's ready (it can take a while). Download and unzip it. Your saved list is in the `your_instagram_activity` folder, in a file named like `saved_posts.json`.

## Step 2: what you need
- **Claude Code** (any paid Claude plan)
- **Claude in Chrome** (the browser extension), with Instagram open and you signed in, so Claude can open each reel

## Step 3: paste this into Claude Code
Run it in the folder where you unzipped the export.

```
Go through my saved Instagram reels and tell me which ones are worth doing.

1. Find my saved-posts file in this folder (look in your_instagram_activity for a file
   with "saved" in its name). List the post links, newest first.
   Take only the newest 50 for now.
2. For each link, use Claude in Chrome to open it in a new tab. Read the caption and
   take a screenshot to read any text on screen. Wait 20 seconds between reels so
   Instagram doesn't block you. Never like, comment, follow, unsave or message anything.
   Only read.
3. For each reel, write one line: the topic, and the one concrete thing it tells you to do.
   Skip memes and anything with no action in it.
4. Sort them into 4–6 topics (for example: recipes, workouts, tools, trips, money, skills).
5. Save the result to saved-reels.md:
   - "This week": the 5 most useful, doable things, each with its link
   - then each topic with its reels
   - then "Safe to forget": the ones with nothing to do
6. Tell me when it's done. Keep it short.
```

Want more? Run it again and say "the next 50".

---

## Honest notes
- Claude reads the **caption and what's on screen**. It doesn't listen to the audio, so a reel that only explains things out loud gets a weaker summary.
- Instagram limits how fast any account can open posts. That's why it waits between reels and starts with 50. Doing all of them at once won't work.
- Your saved list stays on your computer. Claude only opens what's in the file.

Follow [@orzan.ai](https://instagram.com/orzan.ai). The next free one drops tomorrow.
