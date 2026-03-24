---
name: Meta Campaign Optimization & Diagnostics
description: |
  MANDATORY TRIGGERS: User asks about Meta/Facebook campaign performance, diagnosing Meta ads, Meta CPM/CTR/CPC analysis, creative fatigue on Meta, Meta ROAS analysis, Meta attribution, delayed reporting, engagement management, hiding comments, working with averages, downscaling, or third-party tracking for Meta.
  FOR: Day-to-day Meta campaign management, diagnostic frameworks (CPM/CTR/CVR/ROAS), creative fatigue detection, engagement management, working with rolling averages, delayed reporting interpretation, checkout-to-purchase ratio, third-party tracking evaluation, reporting correlation method, and attribution analysis.
  Do NOT use for: Google campaign optimization (use optimize-google). Campaign structure changes or method selection (use strategy-meta-ads). Creative testing methodology (use test-creative). Meta Pixel or CAPI setup (use setup-meta-tracking).
---

# Meta Campaign Optimization & Diagnostics

## When to Read Reference Files

Load `ref-meta-diagnostics.md` when:
- User shares campaign metrics and needs diagnosis
- User asks about CPM/CTR/CPC relationships
- User needs benchmark targets for Meta
- User asks about creative fatigue or frequency thresholds

Load `ref-meta-daily-management.md` when:
- User asks about daily optimization routines
- User asks about the 24-48 hour boost
- User asks when to add new creatives to working campaigns
- User needs downscaling protocol or engagement management guidance

Load `ref-meta-attribution.md` when:
- User asks about post-iOS attribution
- User evaluates third-party tools (Triple Whale, Hyros, Northbeam)
- User asks about view-through vs. click-through attribution
- User needs reporting correlation method

---

## Diagnostic Quick Reference

When a user reports a performance problem, diagnose using this framework:

### Step 1: Identify the Bottleneck

| Symptom Combination | Diagnosis | Fix |
|---|---|---|
| High CPM + Low CTR | Creative problem (ad not engaging) | New creatives, new hooks, test different formats |
| High CPM + High CTR | Competitive auction (not your fault) | Test different placements, times, or countries |
| Low CPM + Low CTR | Targeting/creative mismatch | Creative is reaching people but not resonating |
| High CPC + High CPM | Competitive market | Not a creative problem; market forces |
| High CPC + Low CPM | Creative/targeting issue | Creative gets impressions but not clicks |
| Low CTR + High CVR | Creative filters well (attracts few but qualified clicks) | This may be GOOD -- check overall CPA |
| High CTR + Low CVR | Landing page problem, NOT ad problem | Fix website, not creative |
| CTR same + AOV drops | Upsell/website problem, NOT ad problem | Fix backend, not ads |

### Step 2: Check Key Metrics (Priority Order)

1. **Cost per unique click** -- creative quality indicator
2. **Conversion rate** -- website/offer quality indicator
3. **CPM** -- pixel training / targeting quality indicator
4. **Cost per purchase** -- overall efficiency
5. **AOV** -- business model / upsell indicator

Numbers tell you WHERE the problem is: bad creatives vs. bad conversion rate vs. untrained pixel vs. bad AOV.

---

## Benchmark Targets (US Market)

| Metric | Good | Acceptable | Bad |
|---|---|---|---|
| **CTR (all)** | 5%+ | 3-5% | Below 3% |
| **CTR (link)** | 1.5%+ | 1-1.5% | Below 1% |
| **Hook Rate (video)** | 35%+ | 20-35% | Below 15% |
| **Hold Rate (video)** | 11%+ finishing full video | 8-11% | Below 8% |
| **Avg Video Watch Time** | 10+ seconds | 5-10 seconds | Below 5 seconds |
| **Conversion Rate** | 3%+ | 2-3% | Below 2% |
| **CPM (trained pixel, broad)** | $10-20 | $20-30 | $30+ |
| **Frequency (prospecting)** | Below 2 | 2-3 | Above 3 |
| **Frequency (retargeting MOF)** | Up to 5x | 5-8x | Above 8x |
| **Frequency (retargeting BOF)** | Up to 10x | 10-15x | Above 15x |

---

## The Golden Rule of Optimization

**If something is working, do NOT touch it.** 99.9% of the time, changes make it worse.

This applies to:
- Adding new ads to a winning campaign (disrupts the dominant ad's balance)
- Changing audience settings on a profitable ad set
- Adjusting budgets on a campaign that is hitting targets
- Tweaking ad copy on a converting creative

**Instead:** Put new creatives/tests in their OWN new campaign. Let working campaigns run undisturbed.

### Two Exceptions Where You Can Touch Working Campaigns:
1. Campaign is dying anyway -- worst case you close it; try new creatives of the SAME angle
2. Seasonal transition (swap Black Friday ads for Christmas ads in same campaign) -- same hot pocket, different offer

---

## Working with Averages

- Do NOT optimize based on single days -- use rolling 7-day or 14-day averages
- Good days and bad days are normal
- Some days a campaign delivers 5 ROAS, some days 0.5 -- if the average is above break-even, it is working
- Do NOT panic-close campaigns on bad days or over-celebrate on good days
- Meta may spend $55 one day, $40 the next, $60 another -- weekly total respects 7x daily budget

---

## Creative Fatigue Detection

### How to Detect
- Check frequency: if above 1.5-2.0 on prospecting AND performance declining = fatigue
- If frequency is normal but metrics dropping = creative is just underperforming (not fatigued)

### How to Fix
- Diversify with new landing pages (changes synergy without changing the ad)
- Iterate the winning creative (new hook, new headline, new color)
- Launch replacement creatives in a NEW campaign (do not add to the fatiguing campaign)
- Cross-reference: load `test-creative` skill for iteration methodology

---

## Engagement Management

### Why It Matters
- Facebook CANNOT distinguish good engagement from bad engagement for budget allocation
- High spend + high engagement but NO sales = check comments
- People fighting in comments = bad engagement driving spend without conversions

### Protocol
1. **Hide negative comments immediately** -- one negative comment invites more (crowd psychology)
2. Turn objections into positives by responding publicly
3. Use recurring questions/objections from comments as hooks in future ads
4. Monitor comments daily on high-spend campaigns

---

## Downscaling Protocol

When you need to reduce spend:
1. When killing an ad set in CBO: reduce CBO budget by the amount that ad set was spending
2. Scale down testing percentage when performance drops
3. **When account underperforms: test LESS, not more.** Focus on consolidating what works.
4. Common mistake: media buyers panic and launch MORE tests during downturns (wrong response)

---

## Cross-References

| Condition | Skill to Load |
|---|---|
| Optimization reveals structural problems (wrong campaign type, poor method selection) | `strategy-meta-ads` |
| Creative fatigue detected, need new creatives | `test-creative` |
| Need to scale a winning campaign | `scale-campaigns` |
| Attribution or tracking issues identified | `setup-meta-tracking` |
| Google campaigns also running, need cross-channel view | `optimize-google` |
