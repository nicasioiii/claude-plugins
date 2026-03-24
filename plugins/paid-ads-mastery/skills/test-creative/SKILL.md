---
name: Creative Testing Methodology
description: |
  MANDATORY TRIGGERS: User asks about testing ads, creative testing, A/B testing creatives, how to test new ads, testing methodology, kill criteria, testing volume, creative pipeline, iteration framework, naming conventions for ads, or statistical significance for ads.
  FOR: Designing creative tests, choosing testing approach (ABO/CBO/manual bid/shotgun/nuke/dynamic), setting kill criteria, determining creative volume by ad spend, building a testing pipeline, iterating winners, cross-testing hooks, establishing naming conventions, and building weekly reporting systems.
  Do NOT use for: Campaign-level testing like budget scaling or audience testing (use optimize-meta or optimize-google). Creative research and ideation (use research-creative). Writing the actual ads (use create-ad-copy, create-video-ads, or create-ai-ads). Campaign structure decisions (use strategy-meta-ads or strategy-google-ads).
---

# Creative Testing Methodology

## When to Read Reference Files

Load `ref-testing-methods.md` when:
- User asks which testing approach to use
- User needs kill criteria or statistical significance thresholds
- User is setting up a testing campaign for the first time
- User asks about seed ads, post IDs, or launch timing

Load `ref-testing-volume-pipeline.md` when:
- User asks how many creatives to test per week/month
- User needs a testing tracker or naming convention system
- User wants to understand the two-level testing framework (big swings vs. variations)
- User asks about iteration quantity or when to stop iterating

---

## Core Testing Philosophy

Creative testing is the engine of paid advertising growth. Without systematic testing, you are guessing. With it, you compound learnings over time.

### The Two Levels of Creative Testing

**Level 1: Big Swings (Concept Testing)**
- Entirely different concepts, angles, formats, or audiences
- Goal: discover NEW winning directions
- Higher risk, higher reward
- Example: UGC testimonial vs. product demo vs. lifestyle montage

**Level 2: Variations (Iteration Testing)**
- Small changes to proven winners: new hook, different headline, color swap, new creator
- Goal: extend the life and scale of existing winners
- Lower risk, more predictable
- Example: Same script with 3 different hooks

**Split your testing budget:** 50% new concepts, 50% iterations. When performance is DOWN, skew toward iterations (higher success rate). When performance is UP, skew toward new concepts.

---

## Quick-Reference: 6 Testing Approaches

| # | Method | Setup | Best For | Risk |
|---|--------|-------|----------|------|
| 1 | **Standard ABO** | 4 creatives per ad set, same interest | Controlled testing with clear data | Low |
| 2 | **CBO Algorithm** | Drop creatives into CBO, let algorithm choose | Saving money, hands-off | Medium (unreliable budget distribution) |
| 3 | **Manual Bid** | Set cost cap at target CPA; if no spend = creative fails | Cost-effective filtering | Low (slow) |
| 4 | **High-Budget Shotgun** | 50 creatives, one ad set, $500-$1K/day | Fast discovery at scale | High |
| 5 | **Nuke** | 1 winning creative, duplicate ad set 9-25x | Scaling a proven winner fast | High |
| 6 | **Dynamic/Flexible** | Multiple creatives in flexible format | Algorithm-driven selection | Medium (no ad-level control) |

**Default recommendation for most advertisers:** Standard ABO (#1) for controlled testing. Use Nuke (#5) only after a winner is proven.

---

## Universal Testing Rules

1. **One variable at a time.** Never test headline AND visual simultaneously. Isolate the variable.
2. **Same conditions.** All creatives in a test must share the same audience, copy, landing page, and campaign settings.
3. **Kill at 1x CPA spend with no sale.** If a creative has spent the equivalent of one average cost per acquisition and has zero conversions, kill it.
4. **Never judge from a single day.** Minimum 3-5 day trend before declaring a winner or loser.
5. **Statistical significance threshold:** A creative needs 5-10% of weekly conversions to be validated. Example: 100 sales/week means a creative needs 5-10 sales to be a confirmed winner.
6. **Launch at midnight** (ad account timezone). Auction environment resets at midnight. This gives creatives a full day cycle.
7. **Use Seed Ads / Existing Post IDs.** Upload creatives to a dummy campaign first, then deploy via Existing Post ID in testing campaigns. This stacks engagement across duplicates.

---

## Kill and Scale Decision Framework

### Kill Signals
- Spent 1x CPA with zero conversions
- Performing 30%+ below account average ROAS after 3-5 days
- Hook rate below 15% (video) or CTR below 1% (static)
- CPC is 2x+ above account average with no conversion signal

### Scale Signals
- Performing 30-50% ABOVE account average ROAS for 3-5 consecutive days
- Hook rate above 35% (video) or CTR above 3% (static)
- Stable or improving CPA over 5+ days
- Multiple conversions (not just 1-2 lucky sales)

### When a Winner Emerges
1. Start iterating IMMEDIATELY (do not wait for fatigue)
2. Move winner to scaling campaign (CBO, ASC, or Advantage Shopping)
3. Produce 4-8 iterations within the first week
4. Test iterations in parallel with new concept tests

---

## Iteration Priority Order

### Static Creative Iterations (Highest to Lowest Impact)
1. **Headline** -- always iterate first
2. **Body text / testimonial**
3. **Color** -- surprisingly impactful
4. **CTA** -- lowest impact for statics

### Video Creative Iterations (Highest to Lowest Impact)
1. **Hook** -- equivalent to headline for statics
2. **Body / footage cuts** -- change footage every 3 seconds
3. **Script variations**
4. **Format** -- green screen hooks outperform standard hooks

---

## Creative Volume Guidelines by Monthly Ad Spend

| Monthly Spend | New Concepts/Month | Iterations/Month | Total Creatives/Month |
|---|---|---|---|
| $0-$1K | 4-6 | 4-6 | 8-12 |
| $1K-$5K | 8-12 | 8-12 | 16-24 |
| $5K-$25K | 15-25 | 15-25 | 30-50 |
| $25K-$100K | 25-40 | 30-50 | 55-90 |
| $100K-$500K | 40-60 | 50-80 | 90-140 |
| $500K-$1M | 60-80 | 80-120 | 140-200 |
| $1M+ | 80-120+ | 120-180+ | 200-300+ |

**Minimum 20% of total ad spend should go to creative testing.** This is not optional.

---

## The Ego Warning

After $20M+ in ad spend, practitioners consistently report: the "dumbest ideas" often become the biggest winners, and "genius ideas" everyone loved are sometimes complete flops. Let ANYONE pitch ad ideas. Data does not care about ego. Test everything.

---

## Cross-Testing Method

A powerful diagnostic technique:
1. Take the winning hook from Video A
2. Apply it to Video B
3. **If it works:** The hook was the key variable
4. **If it doesn't:** The video content itself was the winner, not the hook

Also try: mix male + female UGC in the same video to broaden appeal and increase scalability.

---

## Weekly Reporting Cadence

- **Monday:** Extensive winner report (top creatives, ROAS, spend, hooks that worked)
- **During week:** Slack/channel updates on potential winners as discovered
- **Tools:** Atria (budget option) or Motion App (standard) for creative analytics
- **Project management:** ClickUp or Asana pipeline: Ideas > To Do > Ready to Launch > Launched

---

## Naming Convention System

Consistent naming is critical for analysis at scale. Recommended format:

```
[DATE]_[CONCEPT]_[FORMAT]_[VARIATION]_[CREATOR]
```

Examples:
- `2026-03-15_PainPoint_Video_HookA_SarahUGC`
- `2026-03-15_SocialProof_Static_HeadlineV2_InHouse`
- `2026-03-20_ProductDemo_Carousel_ColorTest_Blue`

Tag every creative with: concept category, format type, iteration number, and creator/source.

---

## Cross-References

| Condition | Skill to Load |
|---|---|
| Need to write the actual ad copy or script for the test | `create-ad-copy` or `create-video-ads` |
| Test results need performance interpretation | `optimize-meta` or `optimize-google` |
| Need creative research before building test hypotheses | `research-creative` |
| Winning creative needs to move to scaling campaigns | `strategy-meta-ads` or `strategy-google-ads` |
| Creative fatigue detected across the account | `optimize-meta` (fatigue detection section) |

---

## Statistics That Justify Testing Investment

- Running 15+ experiments per year correlates with a 30% improvement in overall ad performance
- Iterations have a higher success rate than entirely new concepts
- Producing iterations helps scale approximately 50% higher than without them
- Minimum 20% of ad spend on creative testing is the floor for growth accounts
