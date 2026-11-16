# 06 · BOOK: 3 easiest ways to give Claude your own files

From the reel: *"Stop letting your AI guess. Make it read your files first."* (Explain it like I'm five: RAG) → [@orzan.ai](https://instagram.com/orzan.ai)

**RAG in one line:** before the AI answers, it looks up the right pages in *your* files and reads them first. You don't have to build it yourself to use it. Here are three ways, from zero setup to "I'm a developer". Facts checked 2026-11-15.

**But how does it find the right page when the shelf is huge?** It doesn't read every book. Each page gets a "meaning fingerprint" (an *embedding*), and so does your question. It grabs the few pages whose fingerprints sit closest to your question's, and reads only those. That's the *retrieval* part. Reading them before answering is the *augmented generation* part.

---

## 1. Claude Projects: zero setup
claude.ai → **Projects** → **New project** → add your files under **Project knowledge**.
- Every chat in that project can use those files.
- Paste this into the project instructions:
  ```
  Answer from the project files first. Name the file and quote the line you used.
  If the answer isn't in the files, say so instead of guessing.
  ```
- Free accounts get up to 5 projects. When your files outgrow what fits in one chat, Claude switches to RAG mode by itself and can hold "up to 10x" more ([Anthropic](https://support.claude.com/en/articles/11473015-retrieval-augmented-generation-rag-for-projects)). Anthropic's help pages disagree on whether free plans get that mode, so check yours: a project shows an indicator when RAG is on.

## 2. Claude + Google Drive: your files stay where they are
In claude.ai: **Customize → Connectors → Google Drive → Connect**, and sign in with Google. Then turn it on in a chat (**+ → Connectors**) and just ask:
```
Find my notes about the onboarding project in Drive and tell me what's still open.
```
- Claude searches your Drive, reads Docs, Sheets, Slides and PDFs, and its answer cites the files it used ([Anthropic](https://support.claude.com/en/articles/10166901-use-google-workspace-connectors)).
- Available on every Claude plan. On Team and Enterprise, an owner has to switch it on first.
- It can only open files your Google account can open.

## 3. Claude Code on a folder: for builders
Open Claude Code inside a folder of notes, docs or code and just ask. It searches the files itself (grep, glob, read) and opens only what it needs.
```bash
cd ~/my-notes
claude
```
```
> Which of these notes mention our refund policy? Quote each one with its file name.
```
Fun fact: Claude Code's creator said early versions used RAG with a local vector database, and that this "agentic search" approach "generally works better" ([Boris Cherny](https://x.com/bcherny/status/2017824286489383315)).

---

## Bonus: answers *only* from your files
**Gemini Notebook** (Google's tool, called NotebookLM until July 2026): https://notebook.google.com. Add PDFs, Docs, web pages or YouTube videos. Free: 50 sources per notebook. Every answer links to the exact passage it used, so it's great for study notes, contracts and policies.

## Want to build real RAG yourself?
- **Contextual Retrieval** by Anthropic: a simple trick that makes finding the right pages much more reliable, with the full method and code: https://www.anthropic.com/news/contextual-retrieval
- **The original paper** that named RAG: Lewis et al., "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks" (2020): https://arxiv.org/abs/2005.11401

## Good to know
- RAG doesn't make the AI smarter. It hands it the right pages. Outdated or messy files mean outdated or messy answers.
- It can still misread a page, so ask it to quote the line it used.
- Only upload files you're allowed to share.

---
More Explain-it-like-I'm-five episodes on [@orzan.ai](https://instagram.com/orzan.ai). The kid is still collecting coins.

[← Back to the vault](README.md)
