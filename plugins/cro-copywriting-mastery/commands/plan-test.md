---
name: Build Test Priority Matrix
description: "Build a prioritized test plan. Identify what to test first and expected impact. Output: prioritized test plan. TRIGGERS: test plan, what to test, A/B test, split test, optimize, test priority, testing roadmap."
---

# /plan-test -- Build a Test Priority Matrix

## Purpose
Help the user build a prioritized testing roadmap based on their current page performance and audit findings. Produces a ranked test queue with hypotheses and expected impact.

## Input Required

### Required
Ask the user:
1. "What page are you optimizing?" (URL or description)
2. "What is the primary conversion goal?" (opt-in, purchase, trial, demo request)
3. "What is the current conversion rate?" (If unknown, ask for any performance data they have)
4. "How much traffic does this page get monthly?"

### Helpful (ask if available)
5. "Have you run /audit-page or /audit-homepage? If so, share the scores."
6. "What have you already tested? What were the results?"
7. "Where are people dropping off?" (bounce rate, scroll depth, cart abandonment)
8. "What tools do you have access to?" (A/B testing, heatmaps, user testing)

---

## Step 1: Identify the Bottleneck

Based on the data provided, diagnose the primary bottleneck:

| Symptom | Likely Bottleneck | Test Priority Area |
|---------|------------------|--------------------|
| High bounce rate (>70%) | Hook/headline or message mismatch | Headline, awareness match |
| Low scroll depth (<30%) | Body copy or wrong page type | Page type, body copy |
| Good scroll, low CTA clicks | CTA weakness or unhandled objections | CTA copy, proof/objections |
| Clicks to checkout, low purchase | Offer, price, or checkout friction | Offer, pricing, form |
| Good conversion, low revenue | AOV too low | Pricing, upsells, order bumps |
| No data available | Unknown | Start with 7-second test and 5-second test |

---

## Step 2: Generate Test Candidates

Based on the bottleneck and any audit scores, generate 5-8 test candidates from the priority hierarchy:

| Priority | Element | Expected Lift | Effort |
|----------|---------|--------------|--------|
| P1 | Offer changes | 50-500%+ | High |
| P1 | Pricing/packaging | 20-200% | Medium |
| P2 | Headline/hook angle | 20-100%+ | Low |
| P2 | Page type/template | 20-50% | High |
| P3 | Awareness stage targeting | 15-50% | Medium |
| P3 | Proof/testimonial strategy | 10-40% | Medium |
| P4 | CTA copy and design | 5-25% | Low |
| P4 | Social proof placement | 5-20% | Low |
| P5 | Body copy rewrite | 5-15% | High |
| P5 | Guarantee presentation | 5-15% | Low |
| P6 | Visual design/layout | 3-10% | Medium |
| P6 | Form field reduction | 3-10% | Low |
| P7 | Button color/size | 1-5% | Low |
| P7 | Micro-copy tweaks | 1-3% | Low |

---

## Step 3: Write Hypotheses

For each test candidate, write a hypothesis:

**Template:**
"If we [specific change], then [specific metric] will [increase/decrease] by [estimated range] because [reason based on data or audit finding]."

**Example hypotheses:**
- "If we change the headline from 'Project Management Made Simple' to 'Stop Losing 8 Hours a Week to Task Chaos,' then conversion rate will increase 15-30% because our audience is problem-aware and needs to see their pain reflected, not our solution described."
- "If we add three specific testimonials next to our main claims, then scroll-to-CTA rate will increase 10-20% because our audit showed proof strategy scored 1/5."
- "If we remove the coupon code field from checkout, then cart abandonment will decrease 5-15% because 40% of visitors are leaving to search for coupons."

---

## Step 4: Determine Test Method

Based on monthly traffic, recommend the appropriate method:

| Monthly Traffic | Recommended Method |
|----------------|-------------------|
| 10,000+ visitors | A/B test (standard) |
| 3,000-10,000 visitors | A/B test (larger changes only, longer duration) |
| 1,000-3,000 visitors | Before/after measurement + qualitative tests |
| Under 1,000 visitors | Qualitative only (5-second test, 7-second test, user testing) |

---

## Step 5: Build the Test Queue

### Output: Prioritized Test Plan

```
TEST PRIORITY MATRIX
Page: [Page name/URL]
Current Conversion Rate: [X%]
Monthly Traffic: [X visitors]
Goal: [Increase conversion rate / Increase AOV / Reduce bounce / etc.]

════════════════════════════════════════════
TEST 1 (RUNNING NEXT)
────────────────────────────────────────────
Name: [Descriptive name]
Priority: P[#]
Element: [What's being changed]
Hypothesis: [If/then/because]
Primary Metric: [What you'll measure]
Method: [A/B test / Before-after / Qualitative]
Duration: [X weeks]
Traffic needed: [X visitors per variant]
Expected lift: [X-X%]
Status: READY TO LAUNCH

════════════════════════════════════════════
TEST 2 (ON DECK)
────────────────────────────────────────────
Name: [Descriptive name]
Priority: P[#]
Element: [What's being changed]
Hypothesis: [If/then/because]
Primary Metric: [What you'll measure]
Method: [A/B test / Before-after / Qualitative]
Duration: [X weeks]
Expected lift: [X-X%]
Status: DESIGNING VARIANT

════════════════════════════════════════════
TEST 3 (IN PLANNING)
────────────────────────────────────────────
Name: [Descriptive name]
Priority: P[#]
Element: [What's being changed]
Hypothesis: [If/then/because]
Expected lift: [X-X%]
Status: HYPOTHESIS ONLY

════════════════════════════════════════════
BACKLOG
────────────────────────────────────────────
4. [Test name] -- P[#] -- [Brief description]
5. [Test name] -- P[#] -- [Brief description]
6. [Test name] -- P[#] -- [Brief description]
```

---

## Tool Recommendations

Based on the user's situation, recommend specific tools:

| Need | Tool | Cost |
|------|------|------|
| A/B testing | Convert.com, VWO, Optimizely | $50-500/mo |
| Heatmaps | Microsoft Clarity (free), Hotjar, Crazy Egg | Free-$50/mo |
| 5-second tests | Lyssna (formerly UsabilityHub) | Free-$75/mo |
| User testing | UserTesting.com | $49+/test |
| On-site polls | Hotjar, Qualaroo | $30-100/mo |
| Readability | Hemingway Editor | Free |
| Headlines | CoSchedule Headline Analyzer | Free |

---

## After the Plan
Offer:
- "Ready to build the variant for Test 1? I can help write the copy."
- "Want me to create the control/variant comparison document?"
- "After the test runs, bring back the results and I'll help analyze them."

## Cross-References
- `testing-audit-optimization` skill: Full testing methodology and benchmarks
- `/audit-page`: Run this first if no audit has been done
- `/audit-homepage`: Use for homepage-specific optimization
