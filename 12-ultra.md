# ULTRA: get 6 months of Claude Ultra free through open source

From the reel: *"Stop paying $200 for Claude. Your GitHub can get it free."*

Anthropic's **Claude for Open Source** program gives **6 months of Claude Ultra for free** to people who build open source. Ultra is Claude's biggest plan, normally **$200/month**, so that's **$1,200** of Claude.

What Ultra includes (claude.com/pricing):
- Everything in Max
- No 5-hour limit
- 10× Pro usage every week
- $200/month in API credits
- Claude Code

Apply here: **https://claude.com/contact-sales/claude-for-oss**

---

## The 10-second check (most people miss this one)

The "active contributor" track counts **100+ pull requests merged into repos you don't own in the last 12 months**. Count yours with the GitHub CLI:

```bash
ME=$(gh api user --jq .login)
SINCE=$(date -v-12m +%F 2>/dev/null || date -d '12 months ago' +%F)
gh search prs --author=@me --merged --merged-at=">=$SINCE" --limit 1000 \
  --json repository --jq "[.[] | select(.repository.nameWithOwner | startswith(\"$ME/\") | not)] | length"
```

- No `gh`? Install it (`brew install gh`), then run `gh auth login` once.
- No terminal? Search this on github.com: `is:pr is:merged author:YOUR_NAME -user:YOUR_NAME merged:>=2025-11-21` (put in your own name and the date 12 months ago).
- The number excludes repos under your own account. PRs to an org you run still count in the result, so subtract those yourself if you want to be strict.

---

## The five ways in (from the official page)

1. **Maintainers**: your project has 500+ dependent repos, 100+ dependent packages, or 200K+ monthly downloads.
2. **Core contributors**: you're a listed committer on a foundation or language project (for example CPython, Rust, the Node TSC, Apache, CNCF, Kubernetes, Linux, Django, Rails).
3. **Active contributors**: 100+ PRs merged into repos you don't own in the last 12 months (the check above).
4. **Community builders**: one of your repos had 20+ unique outside contributors in the last 12 months.
5. **Critical infrastructure**: your project's OpenSSF criticality score is 0.4 or higher.

**None of these fit?** The form has a catch-all: if you maintain something the ecosystem quietly depends on, **apply anyway**.

---

## What to write in the "apply anyway" box

Keep it short and concrete. Reviewers want proof that people rely on your work:

- **What it is** in one line, with the repo link.
- **Who uses it**: dependents, downloads, notable projects or companies that use it (link them).
- **How active you are**: releases, issues you close, how long you've maintained it.
- **What you'd do with Ultra**: a specific backlog (tests, docs, a refactor, a migration).

Example:
> I maintain `tiny-lib` (github.com/you/tiny-lib), a date parser used by 180 repos including X and Y, about 40K downloads a month. I've shipped 23 releases in 2 years and close most issues within a week. With Ultra I'd finish the v3 rewrite and add full test coverage.

---

## Good to know

- It's **6 months**. Before it ends Anthropic emails you, then you go back to your previous plan or Free.
- The page doesn't state a deadline or a number of spots. Older articles mention "10,000 spots" or "5,000+ stars": that was an earlier version of the program.
- It's reviewed by Anthropic, so qualifying on one of the tracks makes approval likely, not guaranteed.

Source: claude.com/contact-sales/claude-for-oss and claude.com/pricing (checked 2026-11-21).
