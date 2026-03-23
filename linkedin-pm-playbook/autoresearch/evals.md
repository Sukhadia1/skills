# Eval Suite — pm-visibility skill

## Test Inputs (5 scenarios covering all pillars)

INPUT 1: Cold post request
"Write me a LinkedIn post"

INPUT 2: Raw story provided
"My founder killed my roadmap item 2 days before sprint. Said the company direction changed. I had already briefed the team and lined up engineering. Help me write a post."

INPUT 3: GitHub project request
"What should I build on GitHub to show my PM + AI skills?"

INPUT 4: Comment request
"Draft a comment for a Shreyas Doshi post about prioritization frameworks"

INPUT 5: Weekly check-in with data
"Weekly check-in — posted twice this week, got 800 total impressions, commented 12 times, 0 new connections"

---

## Eval Criteria (5 binary checks)

EVAL 1: Story-first behavior
Question: For a post request, does the response ask for a raw story OR ask an "underneath question" before producing a full draft?
Pass: Response either (a) asks the user for their raw story/experience before drafting, OR (b) asks 1-2 specific sharpening questions to dig beneath the surface metric before drafting.
Fail: Response immediately produces a full LinkedIn post draft without asking anything first — defaults straight to story bank without attempting to extract fresh material.

EVAL 2: Zero banned structures
Question: Is the post output (or post within the response) free of ALL banned structures listed in the skill?
Pass: Output contains none of: numbered listicles ("5 lessons I learned"), "Excited to share", "Unpopular opinion: [popular opinion]", "As a PM your most important skill is", vague lesson summaries that any PM could write.
Fail: Output contains any one of the banned structures, even partially.

EVAL 3: Domain-neutral framing
Question: Does the post or comment output avoid leading with healthcare/ambulance industry context?
Pass: The post leads with the problem, system, decision, or insight — not "at my ambulance company" or "in healthcare" or "at Red Health".
Fail: The post opens with or prominently features healthcare/ambulance/Red Health as the primary frame in the first 2 sentences.

EVAL 4: Self-critique applied
Question: Does the response include a self-critique scoring the output against at least 2 of the 3 quality tests (specificity / recruiter / scroll-stop)?
Pass: Response explicitly scores or flags the output on specificity test, recruiter test, or scroll-stop test — even briefly.
Fail: Response delivers output with no self-critique, quality flag, or test scoring whatsoever.

EVAL 5: Actionable diagnosis on weak data
Question: For the weekly check-in input with weak numbers, does the response give a specific diagnosis AND a concrete next action (not just a generic observation)?
Pass: Response names the specific problem (e.g. "cadence below target", "hook quality issue") AND prescribes a specific fix (e.g. "pre-draft 3 posts Sunday", "switch to ship story format", "double commenting on recruiter posts").
Fail: Response only restates the numbers, gives generic encouragement, or suggests vague improvements like "post more" without specifics.

---

## Scoring

Max score per run = 5 evals × 1 point each = 5 points
Runs per experiment = 5
Max score per experiment = 25 points
