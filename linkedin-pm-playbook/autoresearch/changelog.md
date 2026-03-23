# Autoresearch Changelog — pm-visibility

Baseline: 39/65 (60.0%) → Final: 63/65 (96.9%)
Total experiments: 5 | All 5 kept | 0 discarded

---

## Experiment 1 — KEEP
**Score:** 46/65 (70.8%) ↑+10.8 points
**Change:** Fixed story-first instruction ambiguity. Rewrote Post Generation Instructions as explicit 3-step sequence with STEP 1 labelled "NEVER SKIP THIS." Removed conflicting "pick from story bank AND ask" phrasing. Added explicit ask prompt: "What's the raw situation behind this? Give me the messy version."
**Reasoning:** Two places in the skill contradicted each other on cold post requests. In practice this caused the skill to default to drafting immediately from the story bank without extracting a fresh story. Biggest single failure in baseline.
**Result:** EVAL 1 (story-first) went from 0/5 to 5/5 on cold requests. EVAL 1 on raw story improved 3→5. +10.8 points overall.
**Remaining failures:** EVAL 4 (self-critique) still 0/5 for GitHub and comment outputs. EVAL 3 partial slips on cold posts.

---

## Experiment 2 — KEEP
**Score:** 58/65 (89.2%) ↑+18.4 points
**Change:** Added explicit post-output quality checklists to both GitHub project briefs and comment outputs. GitHub check: PM angle clear?, demo achievable on free tier?, README tells product story? Comment check: domain-neutral?, adds genuine value?, stands alone as mini-post?
**Reasoning:** EVAL 4 (self-critique) was scoring 0/5 on both GitHub and comment outputs because the self-critique step was only defined for LinkedIn posts. Structural gap — two of five inputs had no quality enforcement at all.
**Result:** GitHub jumped 5→10, comments jumped 3→10. EVAL 4 now fires for all output types. +18.4 points — largest single gain.
**Remaining failures:** EVAL 2 (banned structures) 1/5 slip on cold posts. EVAL 3 2/5 slip on cold posts (domain label leaking from story bank).

---

## Experiment 3 — KEEP
**Score:** 60/65 (92.3%) ↑+3.1 points
**Change:** Relabelled all story bank entries from domain-specific labels ("Healthcare marketplace", "ambulance-as-dark-store") to system-level labels ("[On-demand services marketplace]", "[0→1 consumer app]"). Added hard hook rule: first sentence of any post MUST open with a system, decision, failure, or outcome — never an industry, company name, or job title.
**Reasoning:** When the skill pulled from the story bank, the domain labels were leaking into post hooks. "Healthcare marketplace" → post opens with healthcare context. Relabelling forces system framing from the source.
**Result:** EVAL 3 on cold post request improved from 3→5. +3.1 points.
**Remaining failures:** EVAL 2 still 1/5 slip (banned structure check exists in Uniqueness section but not enforced at draft time). EVAL 1 still 2/5 slip on vivid raw stories.

---

## Experiment 4 — KEEP
**Score:** 61/65 (93.8%) ↑+1.5 points
**Change:** Moved banned-structure check into Step 3 self-critique so it fires at draft time. Added explicit list of triggers to check: numbered lessons, "Excited to share", "As a PM your most important skill is", manufactured unpopular opinions, framework explainers without examples, opening with industry/company/title.
**Reasoning:** Banned structures list existed in the "Uniqueness" section but was too far from the draft step to reliably fire. Moving it into Step 3 ensures it runs every time a post is produced.
**Result:** EVAL 2 on cold post request improved from 4→5. +1.5 points.
**Remaining failures:** EVAL 1 still 2/5 slip on Input 2 (vivid raw story occasionally triggers immediate draft).

---

## Experiment 5 — KEEP
**Score:** 63/65 (96.9%) ↑+3.1 points
**Change:** Made sharpening question mandatory even for vivid/complete-seeming raw stories. Added explicit instruction: "Even if the story is vivid and complete-seeming, always ask one question. The question should target: what was the real decision, what was sacrificed, or what surprised him."
**Reasoning:** When a raw story was very specific and emotionally clear (e.g. the founder-killed-roadmap scenario), the skill was tempted to draft immediately because the story felt complete. But the sharpening question always surfaces something the surface story misses. Making it unconditional closes the slip.
**Result:** EVAL 1 on Input 2 improved from 3→5. +3.1 points. Hit 96.9% — above 95% ceiling.
**Remaining failures:** 2/65 residual slips — both in edge cases where inputs are ambiguous. Acceptable floor.
