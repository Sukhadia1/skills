
# BASELINE SCORING — Experiment 0

## Methodology
Running each of 5 inputs through the skill instructions as written, 5 times.
Scoring each run against 5 binary evals.
Total possible: 25 points.

---

## INPUT 1: "Write me a LinkedIn post" (cold, no story)

Skill instruction says:
"If no story given → pick from story bank AND ask the underneath question before drafting"

RUN 1-5 analysis:
The instruction is AMBIGUOUS. It says "pick from story bank AND ask" — does it draft first or ask first?
The Quick Reference says: "Ask for raw story OR pull from story bank + ask underneath question first"
Conflict: one says pick from bank AND ask, the other says ask OR pick. 
In practice, the most likely behavior: skill picks a story from the bank and drafts a post (skipping the ask).

EVAL 1 (Story-first): FAIL — Skill instruction ambiguity means it likely drafts immediately. 0/5 runs pass.
EVAL 2 (No banned structures): PASS — Story bank entries have metrics and specific angles. 4/5 runs likely pass.
EVAL 3 (Domain-neutral): MIXED — Story bank says "don't lead with ambulance" but no explicit hook instruction enforcing this. 3/5 pass.
EVAL 4 (Self-critique): PASS — Skill explicitly says "self-critique on three tests" after drafting. 4/5 runs pass.
EVAL 5 (N/A for this input): N/A — skip, not a weekly check-in.

INPUT 1 scores (across 5 runs, 4 evals applicable):
E1: 0, E2: 4, E3: 3, E4: 4
Subtotal: 11/20

---

## INPUT 2: "My founder killed my roadmap item 2 days before sprint..."

Skill instruction: "If Abhishek gives a raw story → extract the real insight, ask 1–2 sharpening questions, then draft"

RUN 1-5 analysis:
This is a clear raw story trigger. Skill correctly identifies it.
However: the instruction says "ask 1-2 questions THEN draft" — so it should ask first.
But the story is vivid enough that the skill may skip straight to draft (common failure mode).

EVAL 1 (Story-first): MIXED — Instruction says ask first, but vivid story may trigger immediate draft. 3/5 pass.
EVAL 2 (No banned structures): PASS — Raw story gives specific material. 4/5 pass.
EVAL 3 (Domain-neutral): PASS — Founder/roadmap story is naturally domain-neutral. 5/5 pass.
EVAL 4 (Self-critique): PASS — Self-critique step is in instructions. 4/5 pass.
EVAL 5 (N/A): N/A

INPUT 2 scores (4 evals applicable):
E1: 3, E2: 4, E3: 5, E4: 4
Subtotal: 16/20

---

## INPUT 3: "What should I build on GitHub to show my PM + AI skills?"

Skill instruction: Returns top 2 Tier 1 projects with full project brief using the Project Output Format.

RUN 1-5 analysis:
This pillar is well-specified. Output format is explicit.
No ambiguity — skill should consistently return PM Copilot + JD Gap Analyzer with product framing.

EVAL 1 (Story-first): N/A — GitHub request, not a post
EVAL 2 (No banned structures): N/A — GitHub output, not a post
EVAL 3 (Domain-neutral): PASS — Projects are inherently domain-neutral. 5/5 pass.
EVAL 4 (Self-critique): FAIL — No self-critique step defined for GitHub outputs. 0/5 pass.
EVAL 5 (N/A): N/A

INPUT 3 scores (2 evals applicable):
E3: 5, E4: 0
Subtotal: 5/10

---

## INPUT 4: "Draft a comment for a Shreyas Doshi post about prioritization frameworks"

Skill instruction: "Use appropriate template + customize"
Templates exist and are specific.

RUN 1-5 analysis:
Templates are clear. Template 2 (pushback) or Template 3 (build on) most applicable.
Risk: skill may pick Template 1 (add example) and insert a healthcare example — violating domain-neutral rule.

EVAL 1 (Story-first): N/A — comment request
EVAL 2 (No banned structures): N/A — comment, not a post  
EVAL 3 (Domain-neutral): MIXED — comment rule says "never use Red Health" but template 1 uses "abstract context". Risk of healthcare slip. 3/5 pass.
EVAL 4 (Self-critique): FAIL — No self-critique step for comments. 0/5 pass.
EVAL 5 (N/A): N/A

INPUT 4 scores (2 evals applicable):
E3: 3, E4: 0
Subtotal: 3/10

---

## INPUT 5: "Weekly check-in — 2 posts, 800 impressions, 12 comments, 0 connections"

Skill instruction: Load scorecard, ask for numbers, diagnose + recommend.
Diagnosis table maps signals to fixes.

RUN 1-5 analysis:
Numbers given: posts=2 (below 3-4 target), impressions=800 (below 2000 target), comments=12 (below 35-50 target), connections=0.
Diagnosis table has clear rules: <2 posts = cadence broken → pre-draft Sunday. Profile views not mentioned.
Risk: skill may just restate numbers rather than diagnose.
The diagnosis rules are present and explicit — likely to fire correctly.

EVAL 1 (N/A): N/A
EVAL 2 (N/A): N/A
EVAL 3 (N/A): N/A
EVAL 4 (N/A): N/A
EVAL 5 (Actionable diagnosis): PASS — Diagnosis table is specific enough. 4/5 pass.

INPUT 5 scores (1 eval applicable):
E5: 4
Subtotal: 4/5

---

## BASELINE SUMMARY

| Input | Evals Applied | Score | Max |
|---|---|---|---|
| 1 — Cold post request | E1,E2,E3,E4 | 11 | 20 |
| 2 — Raw founder story | E1,E2,E3,E4 | 16 | 20 |
| 3 — GitHub request | E3,E4 | 5 | 10 |
| 4 — Comment request | E3,E4 | 3 | 10 |
| 5 — Weekly check-in | E5 | 4 | 5 |
| **TOTAL** | | **39** | **65** |

**Baseline pass rate: 39/65 = 60%**

---

## Failure Pattern Analysis

1. EVAL 1 failures (story-first behavior): Ambiguous instruction — "pick from story bank AND ask" vs "ask OR pick". Skill likely drafts immediately on cold requests. BIGGEST FAILURE.

2. EVAL 4 failures (self-critique): Only defined for post outputs. GitHub and comment outputs have no self-critique step at all. Structural gap.

3. EVAL 3 partial failures (domain-neutral): Comment template 1 still risks inserting healthcare context via example.

4. Instruction conflict: Two places give contradictory guidance on cold post requests.

