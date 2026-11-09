# 01 · AUDIT: 7 security holes in vibe-coded apps

From the reel: *"Your vibe-coded app has 7 security holes."* → [@orzan.ai](https://instagram.com/orzan.ai)

**How to use:** open your project in Claude Code (or Cursor / Codex) from the repo root, paste the prompt below, and let it audit. It changes nothing until you approve each fix.

```text
You are a senior application security engineer. Audit this codebase for the
7 most common holes in AI-built apps. Be concrete: cite file paths and line
numbers. Do not change anything yet.

1. SECRETS IN THE CLIENT
   Search all frontend code and build output for API keys, tokens or secrets
   (e.g. "sk-", "pk_live", "AIza", "Bearer", any *_KEY / *_SECRET). Any secret
   that reaches the browser is public. Server-only keys must live in server code
   or server-side env vars only.

2. DATABASE ACCESS RULES
   If Supabase: list every table and whether Row Level Security is enabled,
   and whether the policies actually restrict rows to the owner. If Firebase:
   review the Firestore/Storage rules for "allow read, write: if true" or
   similar. Show what the public/anon key can read or write today.

3. RATE LIMITING
   Find every endpoint that is public, does auth (login, signup, password
   reset, OTP), or calls a paid API (LLMs, email, SMS). Report which have no
   rate limit, no per-user quota, and no max request/response size.

4. AUTHORIZATION ON THE SERVER
   Find admin pages, admin API routes and any "isAdmin"/role checks. Flag any
   check that only runs in the browser. Every protected route and API handler
   must verify the session and role on the server. Also check for IDOR: can
   user A fetch user B's data by changing an id?

5. SECRETS IN GIT
   Check whether .env or other secret files are tracked, or were ever committed
   in git history. Check that .gitignore covers them. If anything leaked, list
   which keys must be rotated (rotation is required; deleting the file is not
   enough).

6. CORS AND HEADERS
   Find the CORS config. Flag "Access-Control-Allow-Origin: *", especially
   together with credentials or on authenticated routes. Recommend an explicit
   allowlist. Also check for missing basic security headers.

7. PROMPT INJECTION
   Find every place where user-controlled text (messages, uploads, scraped web
   pages, emails) goes into an LLM prompt, especially where the model can call
   tools, read private data, or take actions. Flag missing separation between
   instructions and user content, missing tool permission limits, and any path
   where the model's output is executed or trusted without checks.

OUTPUT
- A table: # | Hole | Status (OK / AT RISK / CRITICAL) | Where (file:line) | Fix
- Then the fixes in priority order, CRITICAL first.
- Then STOP and ask me which fixes to apply. Apply them one at a time, and
  after each one, explain how I can verify it worked.
```

## What it checks

| # | Hole | What goes wrong |
|---|------|-----------------|
| 1 | Secrets in the client | API key in the frontend → anyone burns your credits |
| 2 | Database access rules | Supabase RLS off → your whole user table is public |
| 3 | Rate limiting | One script, 10k requests → surprise bill |
| 4 | Server-side authorization | Hidden admin page ≠ protected admin page |
| 5 | Secrets in git | Pushed `.env` → bots find it in minutes |
| 6 | CORS and headers | `*` origin → any site can call your API |
| 7 | Prompt injection | "Ignore your instructions" → your agent works for them |

## Tips

- Run it more than once. A second pass often finds what the first missed.
- Run it again before every launch and after any big AI-generated change.
- If a key was ever exposed: **rotate it first**, then fix the code. Deleting the file is not enough.

---

[← Back to the vault](README.md)
