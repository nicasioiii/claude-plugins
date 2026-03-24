---
title: Creative Testing Methods & Kill Criteria
skill: test-creative
usage: Load when user asks which testing approach to use, needs kill criteria, wants setup details for a test, or asks about seed ads, post IDs, and launch timing.
---

# Creative Testing Methods -- Complete Setup Guide

## Method 1: Standard ABO Testing (Recommended Default)

**Setup:**
- Campaign type: ABO (Ad Budget Optimization)
- 4 creatives per ad set (3 if budget-constrained)
- Same interest audience across all ad sets (15-25M size)
- Same ad copy on every creative
- Same landing page
- One creative per ad set for macro-level analysis
- Budget: minimum 1x target CPA per ad set per day

**How to read results:**
- One creative per ad set means you can analyze at ad set level without drilling into ad level
- Compare CPA, ROAS, CTR, and hook rate across ad sets
- Winner = consistently outperforms account average by 30-50% over 3-5 days

**Why it works:**
- Full budget control per creative
- Clean data -- one variable isolated
- Reproducible results

---

## Method 2: CBO Algorithm Testing

**Setup:**
- Campaign type: CBO (Campaign Budget Optimization)
- Drop 4-8 creatives into CBO campaign
- Let algorithm allocate budget
- Monitor which creatives receive spend

**Strengths:** Saves money; algorithm finds strongest creative faster
**Weaknesses:** Unreliable budget distribution; 80% of budget often goes to one ad set; some promising creatives never get tested

**When to use:** Secondary testing method when you want algorithmic validation of a potential winner. Not recommended as primary testing method.

---

## Method 3: Manual Bid Testing

**Setup:**
- Campaign type: ABO with cost cap or bid cap
- Set cost cap at your target CPA
- If the creative does not spend = it cannot hit target CPA = kill it
- If it spends and converts = valid winner

**Strengths:** Very cost-effective; only spend on creatives that can meet targets
**Weaknesses:** Slow; some good creatives may not spend due to conservative caps

**When to use:** Budget-constrained accounts. Discovering cost-efficient creatives. Works well alongside Method 1.

---

## Method 4: High-Budget Shotgun Testing

**Setup:**
- One ad set, $500-$1,000/day budget
- Upload 50 creatives into the single ad set
- Monitor every 15-30 minutes
- Kill anything that spends 1x CPA without a sale immediately

**Strengths:** Fastest way to test high volume of creatives
**Weaknesses:** Requires constant monitoring; risky; can waste budget fast

**When to use:** High-spend accounts ($10K+/day) that need rapid creative discovery. Requires dedicated monitoring person.

---

## Method 5: Nuke Scaling

**Setup:**
- Take ONE proven winning creative
- Place in one ad set
- Duplicate that ad set 9-25 times
- Kill ad sets that do not get checkouts after small spend (e.g., 0.5x CPA)

**Strengths:** Fast scaling of a validated winner; finds different audience pockets
**Weaknesses:** High volatility; requires active management

**When to use:** ONLY after a creative is proven (3-5 days above average). This is a scaling method, not a testing method.

---

## Method 6: Dynamic Creative / Flexible Ads

**Setup:**
- Upload multiple creatives in Meta's flexible ad format
- Algorithm picks combinations and optimizes delivery

**Strengths:** Algorithmic optimization; hands-off
**Weaknesses:** Cannot optimize at ad level; one underperformer may consume all budget; limited diagnostic visibility

**When to use:** Supplementary testing only. Not recommended as primary method.

---

## Kill Criteria Decision Tree

```
Creative has spent 1x CPA with zero conversions?
  YES --> Kill immediately
  NO  --> Continue

Creative has run for 3+ days below account average ROAS?
  YES --> Kill (unless it has <5 conversions = insufficient data)
  NO  --> Continue

Hook rate below 15% (video) after 1,000+ impressions?
  YES --> Kill (hook is failing; iterate with new hook if concept has potential)
  NO  --> Continue

CTR below 0.5% (static) after 1,000+ impressions?
  YES --> Kill or iterate headline
  NO  --> Continue monitoring
```

### Kill Criteria by Spend Threshold

| Situation | Action |
|---|---|
| Spent 0.5x CPA, zero checkouts | Orange flag -- monitor closely |
| Spent 1x CPA, zero conversions | Kill |
| Spent 1.5x CPA, 1 conversion (above target CPA) | Kill unless ROAS is close to target |
| Spent 2x CPA, profitable | Potential winner -- extend test 2 more days |

---

## Seed Ads & Existing Post ID System

### Why Use Seed Ads
- Engagement (likes, comments, shares) carries social proof
- A fresh ad starts with zero social proof
- Using the same Post ID across multiple campaigns stacks all engagement onto one post

### How to Set Up
1. Create a "Seed Campaign" (can be paused, never needs to run)
2. Upload all creatives to this campaign as regular ads
3. Copy the Post ID from each ad (found in ad preview URL or via API)
4. When deploying to testing campaigns, select "Use Existing Post" and paste the Post ID
5. All engagement from all campaigns accumulates on the same post

### Post ID Best Practice
- Never create fresh uploads in testing campaigns
- Always route through seed campaign first
- This is especially critical for video ads where comments drive engagement signals

---

## Launch Timing Rules

### Midnight Launch (Meta)
- Ad account budgets reset at midnight (account timezone)
- Launch all new tests at midnight to get a full 24-hour cycle
- This ensures the 24-48 hour boost from Meta is not wasted on dead hours

### 6 AM Launch (Alternative)
- If midnight launch is not feasible, 6 AM local time of target market
- E-commerce prime hours: 6 AM to midnight
- Launching at 8-9 PM wastes the first-day boost on only 4 hours of activity
- Ads take 1-2 hours to populate, so effective spend starts at 7-8 AM

### Never Launch on Friday
- Weekend traffic patterns differ from weekday
- A creative that "wins" on Saturday may fail Monday
- Launch Monday through Wednesday for cleanest baseline data

---

## Statistical Significance Thresholds

### Minimum Data for Confidence
- A creative needs 5-10% of weekly account conversions to be statistically meaningful
- Example: 100 sales/week = need 5-10 sales on a single creative
- 3 sales = "potential winner" only, not conclusive

### Trend Duration
- Minimum 3-5 day trend before declaring winner or loser
- Single-day spikes (good or bad) are noise, not signal
- Use 7-day rolling averages for final decisions

### When Meta Inflates Results
- New campaigns get a 24-48 hour boost (low-hanging fruit)
- Trained pixels transition smoothly after boost; untrained pixels crash
- Do NOT declare a winner based on Day 1-2 performance alone
- Wait until Day 4-5 for true performance signal

---

## Testing Setup Checklist

Before launching any creative test, confirm:

- [ ] One variable being tested (not multiple)
- [ ] Same audience across all test variants
- [ ] Same ad copy across all test variants (unless copy IS the variable)
- [ ] Same landing page across all variants
- [ ] Same campaign settings (placements, optimization event, attribution)
- [ ] Kill criteria defined before launch (CPA threshold, time threshold)
- [ ] Seed ads created and Post IDs ready
- [ ] Naming convention applied to all creatives
- [ ] Reporting dashboard updated with new test entries
- [ ] Launch scheduled for midnight or 6 AM
