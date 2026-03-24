---
name: 20-Point Copy Audit
description: "Run a comprehensive 20-point copy audit on any existing page. Score each element, identify top improvements. Output: scored audit report. TRIGGERS: audit, review, copy audit, page audit, diagnose, what's wrong, improve page, fix page."
---

# /audit-page -- 20-Point Copy Audit

## Purpose
Run a comprehensive copy audit on any existing landing page, sales page, or ad. Scores 20 elements across 5 categories. Produces a scored report with prioritized improvement recommendations.

## Input Required
Ask the user to provide ONE of:
- A URL to the page being audited
- The full copy text pasted in
- A screenshot or description of the page

Also ask:
- "Who is the target audience for this page?"
- "What awareness stage are they in when they arrive?" (If unsure, help them diagnose using awareness-sophistication skill)
- "What is the primary conversion goal?" (opt-in, purchase, book a call, etc.)
- "Where does traffic come from?" (ads, email, organic, referral)

---

## The 20-Point Audit

Score each element 0-5 (0 = missing, 1 = poor, 5 = excellent).

### FOUNDATION (Points 1-5)
| # | Element | Score | Notes |
|---|---------|-------|-------|
| 1 | **One Reader** -- Written for a specific segment? | /5 | |
| 2 | **Awareness Match** -- Matches visitor's awareness stage? | /5 | |
| 3 | **Message Match** -- Matches the ad/email/link that brought them? | /5 | |
| 4 | **One Big Idea** -- Single clear idea throughout? | /5 | |
| 5 | **One Offer** -- Exactly one offer, no competing CTAs? | /5 | |

### HOOK & ABOVE THE FOLD (Points 6-9)
| # | Element | Score | Notes |
|---|---------|-------|-------|
| 6 | **Headline Clarity** -- Value prop understood in 5 seconds? | /5 | |
| 7 | **7-Second Test** -- Answers: What is it? Why should I care? What do I do next? | /5 | |
| 8 | **Unique Mechanism** -- Named and positioned as different/superior? | /5 | |
| 9 | **Primary Promise** -- Big, bold, specific, measurable, envisionable? | /5 | |

### BODY COPY & ARGUMENT (Points 10-14)
| # | Element | Score | Notes |
|---|---------|-------|-------|
| 10 | **Benefit Depth** -- Three tiers: functional > dimensionalized > emotional? | /5 | |
| 11 | **Proof Strategy** -- Every major claim supported with appropriate proof? | /5 | |
| 12 | **Objection Handling** -- Top 3-5 objections addressed before the close? | /5 | |
| 13 | **Story/Narrative** -- Compelling story element? Reader as hero? | /5 | |
| 14 | **Readability** -- FK < 8? Short paragraphs? Scannable? Strong verbs? | /5 | |

### OFFER & CLOSE (Points 15-18)
| # | Element | Score | Notes |
|---|---------|-------|-------|
| 15 | **Offer Presentation** -- Clear value stacking? Everything listed? | /5 | |
| 16 | **Price Justification** -- Anchored, reframed, and trivialized? | /5 | |
| 17 | **Guarantee** -- Clear, prominent, risk-reversing? | /5 | |
| 18 | **CTA Strength** -- Value-driven, first person, contrast, reassurance? | /5 | |

### TECHNICAL & CONGRUENCY (Points 19-20)
| # | Element | Score | Notes |
|---|---------|-------|-------|
| 19 | **Congruency** -- Promise matches guarantee? Ad matches page? No contradictions? | /5 | |
| 20 | **Formatting & Friction** -- No global nav on LP? Minimal forms? Fast load? | /5 | |

---

## Output: Audit Report

### Score Summary
```
FOUNDATION:      [X]/25
HOOK:            [X]/20
BODY:            [X]/25
CLOSE:           [X]/20
TECHNICAL:       [X]/10
────────────────────────
TOTAL:           [X]/100
```

### Interpretation
- 80-100: Strong page. Test micro-optimizations.
- 60-79: Good foundation. Fix weakest 3-5 elements.
- 40-59: Major gaps. Partial rewrite needed.
- Below 40: Fundamental issues. Start over.

### Top 3 Priority Fixes
For each fix, provide:
1. **Element scored lowest:** [Name] -- scored [X]/5
   - **What's wrong:** [Specific diagnosis]
   - **How to fix it:** [Specific, actionable recommendation]
   - **Which skill to use:** [Skill name for detailed guidance]
   - **Expected impact:** [High/Medium/Low]

### Routing to Skills
Based on audit findings, route the user to the appropriate skill:

| Low Score | Route To |
|-----------|----------|
| One Reader (1) | customer-research |
| Awareness Match (2) | awareness-sophistication |
| Message Match (3) | page-architecture |
| One Big Idea (4) | big-idea-mechanism |
| One Offer (5) | offer-engineering |
| Headline Clarity (6) | headline-hook-craft |
| 7-Second Test (7) | page-architecture |
| Unique Mechanism (8) | big-idea-mechanism |
| Primary Promise (9) | big-idea-mechanism |
| Benefit Depth (10) | benefit-translation |
| Proof Strategy (11) | objection-proof-psychology |
| Objection Handling (12) | objection-proof-psychology |
| Story/Narrative (13) | story-narrative |
| Readability (14) | body-copy-craft |
| Offer Presentation (15) | offer-engineering |
| Price Justification (16) | offer-engineering |
| Guarantee (17) | offer-engineering |
| CTA Strength (18) | cta-conversion-elements |
| Congruency (19) | testing-audit-optimization |
| Formatting (20) | page-architecture |

---

## After the Audit
Offer the user:
- "Want me to help fix the top priority item right now?"
- "Want to run /plan-test to build a testing plan based on these findings?"
- "Want to run /audit-homepage if this is a homepage specifically?"
