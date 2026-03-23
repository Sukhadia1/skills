# pm-visibility Skill

**The LinkedIn + GitHub + Commenting system for Senior PMs in India's startup ecosystem.**

This skill is Claude-compatible. Load `SKILL.md` as a system prompt or drop it into your Claude Cowork skills folder. It will guide Claude to act as your personal brand coach — opinionated, direct, and built around your specific background.

---

## What This Skill Does

Takes your raw experiences, stories, and observations and turns them into:
- LinkedIn posts that pass the specificity test (not generic PM content)
- GitHub project briefs with real PM + AI builder signal
- Strategic comment templates that grow your network without being hollow

---

## The 3 Pillars

### Pillar 1 — LinkedIn Posts

The skill enforces a strict quality bar before generating any post:

**Story-first rule:** It will always ask for a raw story before drafting. If you give it a metric — "we improved SLA from 62% to 91%" — it will ask what the 38% failure actually looked like before it drafts anything.

**Three tests every post must pass:**
1. **Specificity test** — Could 500 other PMs write this? If yes, rewrite.
2. **Recruiter test** — Would a Series B hiring manager want to talk to this person?
3. **Scroll-stop test** — Does line 1 make you stop cold?

**Content mix (weekly rotation):**
- 2x Ship stories — specific decision + unexpected outcome
- 1x Systems thinking — how you see a problem differently because of what you've built
- 1x Teardown or contrarian take

**What the skill bans:**
- "5 lessons I learned as a PM" listicles
- "Excited to share..." announcements
- Opening with your industry, company name, or job title
- Any post that could have been written by someone who's never shipped

---

### Pillar 2 — GitHub Projects

The skill produces full project briefs — not just "build a chatbot." Each brief includes:
- Problem statement
- PM angle (why a PM built this, not just an engineer)
- Tech stack (free-tier deployable)
- README structure
- LinkedIn launch post hook
- Estimated build time

**Tier 1 projects (build first):**
1. **PM Copilot** — Takes a PRD → returns gaps, missing metrics, risk flags
2. **JD ↔ Resume Gap Analyzer** — Paste JD + resume → keyword gaps + positioning fixes
3. **Dispatch / Ops Simulator** — Domain-agnostic multi-agent system design demo

---

### Pillar 3 — Strategic Commenting

5–10 quality comments/day on posts from Indian PM leaders, AI builders, and target company recruiters.

The skill enforces: every comment must be able to stand alone as a mini-post. No "great insight!" filler.

Four comment templates included:
- Add a real example from your work
- Respectful pushback
- Build on their idea with a product angle
- For recruiter / hiring posts

---

## Weekly Tracking

The skill includes a weekly scorecard template:

```
WEEK OF: [date]
LinkedIn impressions: ___  |  Target: 2,000+ (ramp to 10K+ by week 8)
GitHub commits: ___
Comments posted: ___  |  Target: 35–50
Profile views: ___
InMails/DMs received: ___
Weekly rating: ___/10
```

And a diagnosis table — if impressions are flat, comments are under 20/week, or GitHub activity drops, the skill tells you exactly what to change.

---

## How to Use

### With Claude Cowork
Drop `SKILL.md` into your Claude skills folder. The skill will auto-trigger when you say things like:
- "Write me a LinkedIn post"
- "What should I build on GitHub"
- "Draft a comment for this post"
- "Weekly check-in"

### With Claude.ai (chat)
1. Start a new conversation
2. Paste the full contents of `SKILL.md` as your first message
3. Say: "This is my PM visibility skill. Activate it."
4. Use it from there

### Manual / DIY
Read the skill as a framework. Use the post skeleton, project briefs, and comment templates directly — no AI required.

---

## Files in This Folder

| File | What it is |
|------|------------|
| `SKILL.md` | Full Claude-compatible skill instructions |
| `README.md` | This file — human-readable guide |
| `autoresearch/` | Eval logs and iteration history from testing the skill |
| `autoresearch/SKILL.md.baseline` | Original version before optimization |
| `autoresearch/changelog.md` | What changed and why across versions |
| `autoresearch/evals.md` | The 5 binary evals used to score skill outputs |
| `autoresearch/results.tsv` | Scoring results across test runs |

---

## Positioning Note

This skill keeps all content **domain-neutral by default.**

It never opens with "In healthcare..." or "At an ambulance company..." — it leads with the system, decision, or failure. This makes every post transferable across industries and signals a PM who thinks in systems, not verticals.

---

## Coming Next

- `jd-analyzer` — gap analysis between any JD and your current resume
- `interview-prep` — structured answer frameworks for product sense, execution, and analytics rounds
- `outreach-templates` — cold DMs, referral asks, and recruiter follow-ups tuned for Indian hiring dynamics
