# JOBS: let Claude check 30 company career pages for you

From the reel: *"Delete LinkedIn. Claude checks 30 career pages for you in 7 minutes."*

Most companies post their openings on their own career page or job board (Greenhouse, Lever, Ashby, Personio, Workday…). Checking 30 of them by hand takes an evening. This prompt has Claude Code do it for you and hand back a clean table with direct links to apply.

**What happened when I ran it (Nov 27, 2026):**
- **Marketing roles, entry to mid level, one city:** Claude checked **30 companies** in about **7 minutes** and found **7 open roles**, each with a direct link.
- **A harder role (junior data analyst, same city):** it checked 30 companies and found **0 exact matches**. It said so plainly and listed the closest roles instead of making jobs up.

---

## What you need
- **Claude Code** (any paid Claude plan), with web search allowed.
- Nothing else: no extra tools and no accounts.

## The prompt (paste into Claude Code)
Change the three lines at the top. Everything else stays.

```
ROLE: [e.g. marketing manager, junior data analyst, UX designer]
CITY: [e.g. Berlin, or "remote, Europe"]
LEVEL: [entry / junior / mid]

Find open jobs for the role above. Rules:
1. Use ONLY company career pages and their job boards (Greenhouse, Lever, Ashby,
   Personio, Workday, SmartRecruiters, or the company's own careers site).
   Use their public job APIs where you can.
   Never use LinkedIn, Indeed, Glassdoor, Stepstone or any other aggregator as a source.
2. Check at least 30 different companies that hire for this role in this city.
3. Only list a job if you actually saw its page or API entry and it looks open now.
   Skip senior, lead, head and director roles unless I asked for them.
4. Never invent a job. If there is no exact match, say so, and list the closest open roles.
5. Save the result to jobs.md:
   - first line: "Companies checked: N | Open roles found: M"
   - then a table: company | job title | level | link
   - then a short list of the companies that had nothing for me
6. Tell me when it's done. Keep it short.
```

Want more? Run it again and say "30 more companies".

---

## Honest notes
- This **doesn't replace applying.** It saves you the searching. You still open each link and apply on the company's own site.
- Some big career sites only load with JavaScript, block bots or are very long, so Claude may only read part of them. It tells you which ones.
- Job boards change daily. Check each link before you apply.
- Results depend a lot on the role and the city. A niche junior role might return zero, and that's real information too.

Follow [@orzan.ai](https://instagram.com/orzan.ai). The next free one drops tomorrow.
