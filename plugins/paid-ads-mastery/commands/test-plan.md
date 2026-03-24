---
name: Test Plan
description: Design a creative or campaign testing plan with hypotheses, setup instructions, kill criteria, measurement framework, and timeline. Activates test-creative and research-creative skills.
---

# Creative Test Plan Builder

## Step 1: Gather Test Context

Ask the user:

1. **Platform:** Meta, Google, TikTok, or multi-platform?
2. **What are you testing?** (Select one or more)
   - A) New creative concepts (big swings)
   - B) Iterations of an existing winner
   - C) Ad copy variations
   - D) Audience/targeting changes
   - E) Landing page or offer changes
3. **Current monthly ad spend:** (determines creative volume targets)
4. **Target CPA or ROAS:** (needed for kill criteria)
5. **Existing winners:** Do you have any proven creatives to iterate on?
6. **Timeline:** When do you need results? (minimum 2 weeks recommended)

---

## Step 2: Select Testing Methodology

**Load skill:** `test-creative` > ref-testing-methods.md

### Methodology Selection Matrix

| Situation | Recommended Method | Setup |
|---|---|---|
| First-time testing, moderate budget | **Standard ABO** | 4 creatives/ad set, same audience, same copy |
| Budget-constrained, need cost control | **Manual Bid Testing** | Cost cap at target CPA; no spend = creative fails |
| High budget, need rapid discovery | **High-Budget Shotgun** | 50 creatives, $500-1K/day, kill at 1x CPA |
| Scaling a proven winner | **Nuke** | 1 winner, duplicate ad set 9-25x |
| Hands-off preference | **CBO Algorithm** | Drop creatives in CBO, let algorithm choose |
| Google RSA testing | **RSA Iteration Loop** | Templatize > Aggregate > Diagnose > Iterate |

---

## Step 3: Build Test Hypotheses

For each creative being tested, define:

### Hypothesis Template
```
HYPOTHESIS: [What you believe will happen and why]
VARIABLE: [The ONE thing being changed]
CONTROL: [What stays the same]
SUCCESS METRIC: [Primary KPI -- ROAS, CPA, hook rate, CTR]
KILL CRITERIA: [When to stop the test]
MINIMUM DATA: [How many conversions needed for confidence]
```

### Examples

**Concept Test:**
```
HYPOTHESIS: A pain-point UGC video will outperform our current product demo
because our audience is problem-aware, not product-aware.
VARIABLE: Creative concept (UGC pain-point vs. product demo)
CONTROL: Same audience, same ad copy, same landing page
SUCCESS METRIC: CPA below $45
KILL CRITERIA: 1x CPA ($45) spent with zero conversions = kill
MINIMUM DATA: 5-10 conversions per creative (5-10% of weekly volume)
```

**Iteration Test:**
```
HYPOTHESIS: Changing the hook on our winning video will lower CPA
because hook rate has declined from 38% to 22% (fatigue signal).
VARIABLE: Hook only (3 new hooks on same body)
CONTROL: Same body, same CTA, same audience, same copy
SUCCESS METRIC: Hook rate above 35% AND CPA below $40
KILL CRITERIA: Hook rate below 15% after 1,000 impressions = kill
MINIMUM DATA: 3-5 day trend minimum
```

---

## Step 4: Design the Test Setup

### Meta Test Setup Checklist
- [ ] Testing campaign created (separate from scaling campaigns)
- [ ] One variable being tested per creative set
- [ ] Same audience across all variants
- [ ] Same ad copy across all variants (unless copy IS the variable)
- [ ] Same landing page across all variants
- [ ] Seed ads created, Post IDs ready
- [ ] Naming convention applied
- [ ] Budget: minimum 1x CPA per ad set per day
- [ ] Launch scheduled for midnight or 6 AM
- [ ] Kill criteria documented before launch

### Google Test Setup Checklist
- [ ] Test assets created (new RSA headlines, new titles, new images)
- [ ] Control group identified (current best-performing assets)
- [ ] Testing window defined (minimum 7-14 days for Shopping, 14-21 days for Search)
- [ ] Success metrics defined (CPI or RPI, NOT Google's Low/Good/Best labels)
- [ ] Negative keywords reviewed before test launch

---

## Step 5: Creative Volume Plan

**Load skill:** `test-creative` > ref-testing-volume-pipeline.md

Based on monthly ad spend, determine how many creatives to produce:

| Monthly Spend | New Concepts | Iterations | Total per Month |
|---|---|---|---|
| $0-$1K | 4-6 | 4-6 | 8-12 |
| $1K-$5K | 8-12 | 8-12 | 16-24 |
| $5K-$25K | 15-25 | 15-25 | 30-50 |
| $25K-$100K | 25-40 | 30-50 | 55-90 |
| $100K+ | 40-80+ | 50-120+ | 90-200+ |

### Budget Split
| Performance State | Concepts (%) | Iterations (%) |
|---|---|---|
| Performance UP | 50% | 50% |
| Performance STABLE | 40% | 60% |
| Performance DOWN | 20% | 80% |

---

## Step 6: Generate the Test Plan Document

```
CREATIVE TEST PLAN
==================

Platform: [Meta / Google / TikTok]
Testing Period: [Start date] to [End date]
Monthly Ad Spend: [$X]
Testing Budget: [20% of total = $Y]

METHODOLOGY: [Standard ABO / Manual Bid / etc.]

HYPOTHESES:
1. [Hypothesis 1 -- full template]
2. [Hypothesis 2 -- full template]
3. [Hypothesis 3 -- full template]

CREATIVE PRODUCTION NEEDED:
- [# of new concepts] new concepts by [date]
- [# of iterations] iterations of [winner name] by [date]
- Formats: [video / static / carousel]
- Creators needed: [UGC / in-house / AI]

KILL CRITERIA:
- Individual creative: Kill at 1x CPA spend ($X) with zero conversions
- Test batch: Kill entire batch if zero winners after 5 days
- Statistical significance: Need [X] conversions per creative (5-10% of weekly volume)

TIMELINE:
- Week 1: Launch test batch, monitor daily, do NOT optimize
- Week 2: Kill losers, identify emerging winners, begin iterations
- Week 3: Scale winners, launch iteration batch
- Week 4: Full analysis, document learnings, plan next cycle

REPORTING:
- Monday: Winner report (ROAS, spend, hook rate, CTR by creative)
- Mid-week: Slack update on emerging winners/urgent kills
- End of test: Full test results document with learnings

NAMING CONVENTION:
[YYYY-MM-DD]_[CONCEPT]_[FORMAT]_[VARIATION]_[CREATOR]

NEXT STEPS AFTER TEST:
- Winners --> Move to scaling campaign (load scale-campaigns skill)
- Winning concepts --> Produce 4-8 iterations (load test-creative skill)
- Learnings --> Feed into next test cycle hypothesis development
```

---

## Follow-Up

| Situation | Next Action |
|---|---|
| Need to write the actual creatives | `create-ad-copy` or `create-video-ads` or `create-ai-ads` |
| Need creative research before building hypotheses | `/research-brief` |
| Test complete, ready to scale winners | `/scale-plan` |
| Test revealed structural problems | `/audit-campaign` |
