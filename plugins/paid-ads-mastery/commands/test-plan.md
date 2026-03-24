---
name: Test Plan
description: Creative testing planner that asks platform, what to test, budget, CPA target. Outputs methodology, variants to create, kill criteria, and timeline.
---

# Creative Testing Plan Generator

## Step 1: What Are You Testing?

**Select your primary test variable:**

A) **Hook Testing** (Video only)
   - What: First 2-5 seconds of video
   - Why: Hook rate above 35% = must-have
   - Examples: Transition effects, shocking visuals, pattern interrupts
   - Go to Step 2a

B) **Copy Testing** (Meta + Google)
   - What: Headline and body text combinations
   - Why: Copy = ~30% of performance
   - Examples: Benefit-driven vs. urgency vs. testimonial
   - Go to Step 2b

C) **Audience Testing** (Meta only)
   - What: Different audience layers/interests
   - Why: Audience fit = major performance driver
   - Examples: Interest clusters, lookalike % variations, demo targeting
   - Go to Step 2c

D) **Format Testing** (Meta)
   - What: Video vs. Static vs. Carousel
   - Why: Different formats engage differently
   - Examples: 9x16 vs. 1x1 vs. 4x5 carousel
   - Go to Step 2d

E) **USP Testing** (Video)
   - What: Unique selling point focus
   - Why: Different messaging angles convert differently
   - Examples: Speed vs. quality vs. affordability vs. social proof
   - Go to Step 2e

---

## Step 2a: Hook Testing Plan

**Platform:** Meta (Video)
**Duration:** 3-5 days per batch
**Budget Formula:** 20% of main campaign budget

### Your Test Setup:

**Current Hook:** [Describe what's running now]

**Competing Hook Ideas:**

1. **Hook Variation 1:** [Hook type + description]
   - Pattern: [Visual pattern interrupt]
   - Expected advantage: [Why you think it'll win]

2. **Hook Variation 2:** [Hook type + description]
   - Pattern: [Different pattern]
   - Expected advantage: [Why you think it'll win]

3. **Hook Variation 3:** [Hook type + description]
   - Pattern: [Different pattern]
   - Expected advantage: [Why you think it'll win]

4. **Hook Variation 4:** [Hook type + description]
   - Pattern: [Different pattern]
   - Expected advantage: [Why you think it'll win]

5. **Hook Variation 5:** [Hook type + description]
   - Pattern: [Different pattern]
   - Expected advantage: [Why you think it'll win]

### Test Structure:

```
Campaign: [Campaign Name]_HOOK_TEST_[Date]
Ad Sets: 5 equal ad sets, one per hook
Budget: [$X/day ÷ 5 = $X per hook]
Duration: 5 days
Optimization: Video Views (to isolate hook impact)

SUCCESS METRIC: Hook Rate >35%
SECONDARY: Hold Rate >10% (if video >10 sec)

Timeline:
Day 1-2: Collect baseline hook rate data
Day 3-5: Identify 1-2 winners (highest hook rate)
Day 6: Scale winning hook to 50% of main budget
Day 7: Retire losing hooks
```

### Kill Criteria:

- Hook Rate <15% by Day 3 → Kill immediately
- Hold Rate drops >20% from baseline → Kill and replace
- Spend $[CPA threshold] with zero conversions → Kill
- CTR <0.5% → Likely bad hook, prepare replacement

### Scale Criteria:

- Hook Rate >40% for 2+ consecutive days → Scale to 50% of main
- Hold Rate stable/increasing → Indicates good hook + content
- CPM stable or declining while hook rate up → Good signal

---

## Step 2b: Copy Testing Plan

**Platform:** Meta + Google
**Duration:** 7-14 days per batch
**Budget Formula:** 15% of main campaign budget

### Your Test Setup:

**Current Copy:** [Paste current winning copy]

**Competing Copy Ideas:**

| Copy Type | Angle | Example | Why Test |
|-----------|-------|---------|----------|
| Variation 1 | [Angle] | [Sample headline] | [Reason] |
| Variation 2 | [Angle] | [Sample headline] | [Reason] |
| Variation 3 | [Angle] | [Sample headline] | [Reason] |
| Variation 4 | [Angle] | [Sample headline] | [Reason] |

### Test Structure:

```
Campaign: [Campaign Name]_COPY_TEST_[Date]
Ad Sets: 4 equal ad sets, one per copy variant
Budget: [$X/day ÷ 4 = $X per copy]
Duration: 7 days (more data than hooks)
Optimization: Conversions (not CTR)

SUCCESS METRIC: Conversion Rate (not CTR)
SECONDARY: CPA within ±15% of target

Timeline:
Day 1-3: Collect baseline conversion data
Day 4-7: Identify 1-2 winners (highest ROAS)
Day 8: Scale winning copy to 75% of main budget
Day 9-14: Test variations of winning copy
Day 15: Archive losing copies
```

### Kill Criteria:

- CPA >2x target after $[spend threshold] → Kill
- Conversion Rate <50% of account average → Kill
- Spend $[amount] with zero conversions → Kill immediately
- CTR >40% below benchmark → Kill (traffic quality issue)

### Scale Criteria:

- ROAS >1.5x account average for 3+ days → Scale to 75%
- CPA <target consistently → Scale and test variations
- Conversion rate above benchmark → Spend full week testing
- Weekly performance stable ±5% → Graduate to main budget

---

## Step 2c: Audience Testing Plan (Meta)

**Platform:** Meta
**Duration:** 7-14 days per batch
**Budget Formula:** 25% of main campaign budget

### Your Test Setup:

**Current Audience:** [Describe main audience]

**Competing Audience Ideas:**

1. **Audience A:** [Interest/lookalike details]
   - Size: __ million
   - Expected fit: [Why this audience?]

2. **Audience B:** [Interest/lookalike details]
   - Size: __ million
   - Expected fit: [Why this audience?]

3. **Audience C:** [Interest/lookalike details]
   - Size: __ million
   - Expected fit: [Why this audience?]

4. **Audience D:** [Interest/lookalike details]
   - Size: __ million
   - Expected fit: [Why this audience?]

### Test Structure:

```
Campaign: [Campaign Name]_AUDIENCE_TEST_[Date]
Ad Sets: 4, one per audience (same creative for fair test)
Budget: [$X/day ÷ 4 = $X per audience]
Duration: 7-10 days (longer than hook tests)
Optimization: Value or Conversions
Creative: SAME across all audiences (fair comparison)

SUCCESS METRIC: ROAS (which audience converts best)
SECONDARY: CPA (cost to reach this audience)

Timeline:
Day 1-3: Baseline data collection
Day 4-7: Identify 1-2 best audiences (highest ROAS)
Day 8-14: Scale top audience, test variations
Day 15: Archive poor-performing audiences
```

### Kill Criteria:

- ROAS <1.0x breakeven by Day 5 → Kill
- Frequency >3.5x with declining conversions → Kill
- CPA >1.5x target after 20+ conversions → Kill
- No sales after $[spend] → Kill

### Scale Criteria:

- ROAS >1.5x breakeven consistently → Scale to 50-75%
- CPA <target by 20%+ → Scale and test duplicates
- Frequency <2.5x with high ROAS → Safe to scale
- Stable performance >7 days → Graduate to main budget

---

## Step 2d: Format Testing Plan (Meta)

**Platform:** Meta
**Duration:** 7-14 days
**Budget Formula:** 20% of main campaign budget

### Your Test Setup:

**Currently Running:** [Format and performance]

**Format Competitors:**

| Format | Dimensions | Best Placement | Sample | Expected Advantage |
|--------|-----------|-----------------|--------|-------------------|
| 9x16 Video | Vertical | Reels | [Link or description] | Full screen attention |
| 1x1 Square | Square | Feed/Stories | [Link or description] | Less intimidating |
| 4x5 Portrait | Portrait | Feed focus | [Link or description] | Fashion-friendly |
| Carousel | Multiple | Feed/Reels | [Link or description] | Multi-product display |

### Test Structure:

```
Campaign: [Campaign Name]_FORMAT_TEST_[Date]
Ad Sets: 4, one per format (same creative adapted to format)
Budget: [$X/day ÷ 4 = $X per format]
Duration: 10 days (longer data window)
Optimization: Value or Conversions
Creative: ADAPTED (same message, different format)

SUCCESS METRIC: ROAS (which format converts best)
SECONDARY: CTR + Cost Per Result

Timeline:
Day 1-4: Baseline data
Day 5-10: Identify winner(s)
Day 11-20: Scale winning format, test variations
Day 21: Archive low performers
```

### Kill Criteria:

- Hold Rate <8% for video formats → Kill
- CPM >30% above average → Poor audience match
- Conversion Rate <baseline by 25%+ → Kill
- ROAS <1.2x breakeven after $[spend] → Kill

### Scale Criteria:

- ROAS 1.5x+ benchmark for 5+ days → Scale to 70%
- CTR within ±10% of benchmark → Safe to scale
- Hold rate (video) >12% → Excellent engagement
- Cost per result stable/declining → Graduate to main

---

## Step 2e: USP Testing Plan (Video)

**Platform:** Meta
**Duration:** 5-7 days per batch
**Budget Formula:** 15% of main campaign budget

### Your Test Setup:

**Product USPs to Test:**

1. **Speed** — "[Product] gets results fast"
   - Message: How quickly does it work?
   - Social proof: Timeline testimonials

2. **Quality** — "[Product] is premium/superior"
   - Message: Craftsmanship, materials, durability
   - Social proof: Expert endorsements

3. **Affordability** — "[Product] is value for money"
   - Message: Price comparison, ROI calculation
   - Social proof: Budget-conscious testimonials

4. **Social Proof** — "Everyone's using [product]"
   - Message: Popularity, community, trends
   - Social proof: User count, influencer endorsements

5. **Transformation** — "[Product] changes your life"
   - Message: Before/after, lifestyle improvement
   - Social proof: Success stories, results

### Test Structure:

```
Campaign: [Campaign Name]_USP_TEST_[Date]
Ad Sets: 5, one per USP (same format, different message)
Budget: [$X/day ÷ 5 = $X per USP]
Duration: 5-7 days
Optimization: Conversions
Creative: SAME VIDEO, different copy/voiceover for each USP

SUCCESS METRIC: Conversion Rate + ROAS
SECONDARY: Which USP resonates with audience?

Timeline:
Day 1-3: Baseline data
Day 4-5: Identify winner(s) (which USP converts best)
Day 6-7: Scale winning USP
Day 8+: Double down on winning angle
```

### Kill Criteria:

- Conversion rate <50% of average → Kill this USP
- CPA >target by 30%+ → USP not resonating
- Spend $[amount] with <2 conversions → Kill
- ROAS <1.0x breakeven → Not working for audience

### Scale Criteria:

- ROAS >1.5x breakeven consistently → This USP wins
- Conversion rate above benchmark → Audience loves this angle
- CPM stable/declining while ROAS up → Perfect signal
- CPA 10-20% below target → Outstanding performance

---

## Step 3: Budget Allocation & Timeline

**Total Testing Budget Available:** $[X/week]
**Main Campaign Budget:** $[X/day]
**Testing % of Total:** [__% recommended: 20-30%]

### Test Sequence:

```
WEEK 1: Hook Testing (5 variations)
  Budget: [X]
  Duration: 5 days
  Winner by: Day 6

WEEK 2: Copy Testing (4 variations of winning hook)
  Budget: [X]
  Duration: 7 days
  Winner by: Day 13

WEEK 3: Audience Testing (4 variations)
  Budget: [X]
  Duration: 7 days (parallel with main campaigns)
  Winner by: Day 20

WEEK 4: Iteration Testing (variants of top 3 winners)
  Budget: [X]
  Duration: 7 days
  Finalize by: Day 28

MONTH RESULTS:
  - Top 2-3 creatives ready for main budget
  - 3-4 backup creatives tested and viable
  - Audience + copy combo optimized
  - Projected ROAS improvement: [15-25%]
```

---

## Step 4: Kill & Scale Thresholds

### Auto-Kill Rules:

```
IF spend > $[CPA threshold] AND conversions < 1
  → Kill this variant immediately

IF ROAS < [breakeven] for 3+ consecutive days
  → Kill this variant, reallocate budget

IF hold rate < 8% for 2 days (video)
  → Hook is failing, replace immediately

IF frequency > 4.0 with ROAS declining
  → Audience fatigue, pause and refresh
```

### Auto-Scale Rules:

```
IF ROAS > [1.5x target] for 3+ days
  → Scale to 50% of main budget

IF conversion rate > [benchmark] + 20%
  → Scale to 75% of main budget

IF CPA < [target] - 20% and stable
  → Validate for 7 days, graduate to main

IF winning 3 variants emerge
  → Create 5-10 variations of each, expand testing
```

---

## Step 5: Reporting Template

### Weekly Test Report:

**Metric** | **Variant A** | **Variant B** | **Variant C** | **Variant D** | **Winner**
---|---|---|---|---|---
**Spend** | $300 | $300 | $300 | $300 | -
**Conversions** | 18 | 22 | 12 | 25 | D ✅
**ROAS** | 1.8x | 2.2x | 1.2x | 2.5x | D ✅
**CPA** | $16.67 | $13.64 | $25 | $12 | D ✅
**CTR** | 1.8% | 2.1% | 0.9% | 2.3% | D ✅
**Status** | Monitor | Scale | Kill | Scale+ | Scaling to main

---

## Next Steps

- **Design variants needed?** → `/write-ad` command
- **Have creative ready, need final numbers?** → `/scale-plan` for scaling thresholds
- **Campaign live, need monitoring?** → `/optimize-campaigns` skill for daily management
- **Want to strategize full testing roadmap?** → Activate `/optimize-campaigns` skill reference section
