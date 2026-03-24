---
name: 7-Point Homepage Audit
description: "Run Ryan Deiss's 7-point homepage audit with 4-level scoring. Output: homepage audit report with improvement priorities. TRIGGERS: homepage, home page, homepage audit, homepage review, homepage fix."
---

# /audit-homepage -- 7-Point Homepage Audit

## Purpose
Run Ryan Deiss's 7-point homepage-specific audit. Homepages have unique challenges (multiple audience segments, awareness stages, and goals) that require a different audit from generic landing pages.

## Input Required
Ask the user to provide:
- Their homepage URL or full copy/screenshot
- Their primary target audience
- What awareness stage most homepage visitors are in
- Their primary business goal for the homepage (leads, trials, purchases, brand awareness)

---

## The 7-Point Audit

Score each element 1-4.

### Element 1: Clarity
Can a first-time visitor immediately understand what you do?

| Score | Assessment |
|-------|-----------|
| 1 | Confusing or missing value proposition. Jargon. Visitor has no idea. |
| 2 | Value prop exists but vague. Could apply to many companies. |
| 3 | Clear value prop with some specificity. |
| 4 | Crystal clear, specific, compelling. Immediately understandable. |

### Element 2: Relevance
Does the homepage speak to a specific audience?

| Score | Assessment |
|-------|-----------|
| 1 | Generic. Could be any company in any industry. |
| 2 | Somewhat targeted but broad. |
| 3 | Speaks to a clear audience. Language resonates. |
| 4 | Deeply resonant with specific avatar. Uses their exact language. |

### Element 3: Trust
Are there credibility and social proof elements?

| Score | Assessment |
|-------|-----------|
| 1 | No trust elements at all. |
| 2 | Basic: one logo bar or a generic testimonial. |
| 3 | Multiple trust signals: named testimonials, media logos, data. |
| 4 | Comprehensive trust stack: logos + testimonials + media + user numbers + case studies. |

### Element 4: Navigation
Can visitors easily find what they need?

| Score | Assessment |
|-------|-----------|
| 1 | Confusing. Too many options. No clear primary path. |
| 2 | Cluttered. Primary action competes with secondary links. |
| 3 | Clean main paths. Primary CTA visible. 4-5 nav items. |
| 4 | Intuitive. Logo left, minimal links, CTA far right. Clear primary + secondary paths. |

### Element 5: Call to Action
Is there a clear, compelling CTA?

| Score | Assessment |
|-------|-----------|
| 1 | Missing or says "Learn more" or "Submit." |
| 2 | Present but generic, poor contrast, unclear next step. |
| 3 | Clear with decent copy and contrast. Communicates value. |
| 4 | Compelling, value-driven, high contrast, reassuring text, clear next step. |

### Element 6: Above the Fold
Does the above-the-fold area pass the 7-Second Test?

Three questions that must be answered:
1. **What is it?** (What do you do?)
2. **Why should I care?** (What's the benefit?)
3. **What now?** (What should I do next?)

| Score | Assessment |
|-------|-----------|
| 1 | Fails all three. Auto-playing carousel. No clear message. |
| 2 | Answers 1-2 of three questions. |
| 3 | Answers all three clearly. |
| 4 | Answers all three AND creates desire to continue. |

### Element 7: Mobile Experience
Does the homepage work well on mobile?

| Score | Assessment |
|-------|-----------|
| 1 | Broken layout, tiny text, untappable buttons. |
| 2 | Functional but awkward. Not optimized. |
| 3 | Good mobile experience. Content reflows. CTAs tappable. |
| 4 | Mobile-first. Fast. Touch-optimized. CTA prominent. |

---

## Output: Homepage Audit Report

### Score Summary
```
1. Clarity:        [X]/4
2. Relevance:      [X]/4
3. Trust:          [X]/4
4. Navigation:     [X]/4
5. CTA:            [X]/4
6. Above the Fold: [X]/4
7. Mobile:         [X]/4
────────────────────────
TOTAL:             [X]/28
```

### Interpretation
- 25-28: Excellent homepage. Fine-tune and test.
- 18-24: Good with room for improvement. Fix 2-3 weakest elements.
- 11-17: Significant issues. Multiple elements need work.
- 7-10: Fundamental redesign needed.

### Priority Fixes (Ordered)
1. **Clarity** -- If people don't understand what you do, nothing else matters
2. **Above the Fold** -- 84% of attention lives here
3. **CTA** -- Without a clear action, interested visitors won't convert
4. **Relevance** -- Speak to a specific audience
5. **Trust** -- Add proof elements
6. **Navigation** -- Simplify
7. **Mobile** -- Ensure nothing is broken

### Specific Recommendations
For each element scoring 1-2, provide:
- **What's wrong:** [Specific diagnosis]
- **How to fix it:** [Actionable recommendation with example]
- **Reference:** [Which skill/reference file has detailed guidance]

### Homepage Template Check
Evaluate against Ryan Deiss's 11-section homepage template:
1. Top Menu (logo + minimal nav + primary CTA)
2. Headline + Subheadline
3. Hero Shot
4. Primary CTA
5. Secondary CTA (optional ghost button)
6. Trust Bar
7. How It Works (3-step process)
8. Who It's For (sub-market segmentation)
9. Trust Builders (testimonials, stories)
10. Bottom CTA
11. Footer

**Mark which sections are present, missing, or weak.**

### Awareness Stage Check
Evaluate whether the homepage messaging matches the dominant awareness stage of visitors:
- **Problem-aware visitors** need: empathy, hope, problem recognition
- **Solution-aware visitors** need: clarity, differentiation, proof
- **Product-aware visitors** need: assurance, social proof, comparison
- **Most-aware visitors** need: novelty, deals, new features

**Contrarian check:** Is the homepage accidentally modeling most-aware brands (Apple, Nike) when the audience is problem-aware?

---

## After the Audit
Offer:
- "Want me to help rewrite the headline and above-the-fold section?"
- "Want to run the full /audit-page (20-point) for deeper analysis?"
- "Want to see the homepage template in page-architecture for a rebuild?"
