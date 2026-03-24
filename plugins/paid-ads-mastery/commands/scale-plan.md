---
name: Scale Plan
description: Create a scaling roadmap based on current performance. Identifies scaling method, budget progression, creative needs, and risk mitigation. Activates scale-campaigns, strategy-meta-ads OR strategy-google-ads, and optimize-meta OR optimize-google.
---

# Scaling Roadmap Builder

## Step 1: Assess Scaling Readiness

Ask the user:

1. **Platform:** Meta, Google, or both?
2. **Current daily spend:** How much are you spending per day right now?
3. **Current ROAS / CPA:** What is your 14-day rolling average?
4. **Break-even ROAS / Max CPA:** What is your profitability threshold?
5. **Target daily spend:** Where do you want to be?
6. **Winning creatives:** How many proven winners do you have?
7. **Creative production capacity:** How many new creatives can you produce per week?
8. **Countries:** Are you in one country or multiple?

---

## Step 2: Validate Scaling Prerequisites

Before recommending any scaling method, confirm these prerequisites are met. **If any fail, scaling will not work -- fix the prerequisite first.**

### Prerequisites Checklist

| Prerequisite | Check | If Failing |
|---|---|---|
| **Break-even ROAS achievable** | Current ROAS > break-even for 14+ days | Fix unit economics (margins, AOV, offer) |
| **Proven creatives exist** | At least 2-3 creatives above account average for 5+ days | Build creative pipeline first (`/test-plan`) |
| **Conversion tracking is solid** | No tracking gaps, enhanced conversions enabled | Fix tracking (`setup-meta-tracking` or `setup-google-ads`) |
| **Offer is strong** | CVR above 2% (e-commerce) or lead quality validated | Improve offer before scaling |
| **Creative pipeline exists** | Can produce 8+ new creatives per week | Build production capacity first |

### The Fundamental Scaling Truth

If lowering budget = good ROAS and increasing budget = bad ROAS, the problem is NOT your ad strategy. Reasons you cannot scale:
- Weak offer
- Bad creatives (not enough variety/angles)
- Low AOV
- Poor conversion rate
- Too much competition
- Product-market limitations

"Facebook/Google is just an amplifier of reality -- if the product cannot scale in reality, ads cannot force it."

---

## Step 3: Select Scaling Method (Meta)

**Load skill:** `scale-campaigns` for detailed method execution.

### Meta Scaling Methods

| Method | How It Works | Best For | Risk |
|---|---|---|---|
| **Vertical (Safe)** | Increase budget 20% every 48 hours | Conservative growth on proven campaigns | Low |
| **Vertical (Aggressive)** | Increase budget 70% every 24 hours | Fast scaling with seasoned pixel | Medium |
| **Horizontal / Nuke** | Duplicate winner into 9-25 ad sets at $25-50 each | Fast discovery of new audience pockets | High |
| **Crazy Method** | Duplicate identical ad sets in CBO (budget/CPP = # ad sets) | Finding multiple hot pockets | Medium |
| **Manual Bid** | Cost cap or bid cap on winning creatives | Cost-controlled scaling | Medium |
| **Sniper** | Very low manual bid; captures cheapest audience pockets only | Efficiency-focused scaling | Low |
| **Surge** | One ad set, very high budget | Opposite of nuke -- broad shotgun | High |
| **ASC / Advantage Shopping** | Add winning creatives to ASC campaign | Evergreen scaling | Low |
| **Multi-Country** | Expand to new countries with winning creatives | Market expansion | Medium |

### Meta Scaling Decision Tree

```
Current daily spend < $100?
  --> Vertical scaling (aggressive OK at small budgets; 20% rule irrelevant here)

$100-$500/day?
  --> Vertical (20% every 48hr) + Horizontal (nuke winners)
  --> Start Crazy Method if you have multiple proven creatives

$500-$2K/day?
  --> Crazy Method as primary amplifier
  --> Vertical scaling 20% rule matters here
  --> Test cost caps / bid caps

$2K+/day and hitting ceiling (daily loop)?
  --> New creative angles (new hot pockets)
  --> New countries
  --> Promotions to inflate data
  --> Fix AOV or CVR
```

### The Daily Loop Warning
If adding more campaigns/budget does not increase total sales (just redistributes same sales across more campaigns), you have hit a daily loop. Simply duplicating the same creatives in more campaigns = spending more for the same results.

**How to break the daily loop:**
1. New creatives with DIFFERENT angles (target different hot pockets)
2. Different products or offers
3. New countries
4. Promotions to inflate overall account data
5. Improve AOV, conversion rate, or offer strength

---

## Step 4: Select Scaling Method (Google)

### Google Scaling Methods

| Method | How It Works | Best For |
|---|---|---|
| **Budget Increase** | 10-20% per week on profitable campaigns | Standard gradual scaling |
| **Bid Target Relaxation** | Lower Target ROAS by 10% or raise Target CPA by 10% | More volume at slightly lower efficiency |
| **Standalone Campaign** | Pull winning products into dedicated campaign with higher budget | Shopping scaling |
| **PMax Expansion** | Add new PMax campaigns by category | Large catalog scaling |
| **Search Expansion** | Add non-brand keywords, expand match types | Capture more search demand |
| **YouTube TOF** | Launch top-of-funnel YouTube campaigns | Demand generation for growth |

### Google Scaling Decision Framework

**14-Day ROAS Check:**
| 14-Day ROAS vs. Target | Action |
|---|---|
| Above target by 20%+ | Scale: increase budget 10-20% per week |
| At target (within 10%) | Hold: maintain current settings |
| Below target by 10-20% | Optimize first: check feed, search terms, assets |
| Below target by 20%+ | Do NOT scale. Fix fundamentals first. |

---

## Step 5: Generate Scaling Roadmap

```
SCALING ROADMAP
===============

Platform: [Meta / Google / Both]
Current State: $[X]/day at [Y] ROAS
Target State: $[Z]/day at [target] ROAS
Timeline: [4-8 weeks typical]

PREREQUISITES STATUS:
- [ ] Unit economics validated (break-even ROAS: [X])
- [ ] Proven creatives: [number] winners
- [ ] Creative pipeline: [X] new creatives/week capacity
- [ ] Tracking: [status]
- [ ] Offer: [CVR status]

PHASE 1: FOUNDATION (Week 1-2)
- Scaling method: [method]
- Budget progression: $[current] --> $[target week 2]
- Creative needs: [X iterations of current winners]
- Risk mitigation: [kill criteria if scaling fails]

PHASE 2: ACCELERATION (Week 3-4)
- Scaling method: [method -- may add second method]
- Budget progression: $[week 2] --> $[target week 4]
- Creative needs: [X new concepts + X iterations]
- New campaigns to launch: [specifics]

PHASE 3: STABILIZATION (Week 5-6)
- Goal: maintain new spend level at target ROAS
- Expected stabilization: 7-14 days after reaching target spend
- Creative needs: [ongoing pipeline -- X/week]
- Monitoring cadence: [daily metrics, weekly reviews]

PHASE 4: EXPANSION (Week 7-8, if targets met)
- Options: new countries, new campaign types, new platforms
- Creative needs: [adapted creatives for new markets]
- Budget: [progressive increase plan]

GUARDRAILS:
- If ROAS drops below [X] for 3+ days: pause scaling, diagnose
- If CPA exceeds [X] for 5+ days: reduce budget to last profitable level
- Weekly creative refresh minimum: [X new creatives]
- Monthly creative audit: review all active creatives for fatigue

CREATIVE PIPELINE REQUIREMENTS:
- New concepts per week: [X]
- Iterations per week: [X]
- Formats: [video / static / carousel mix]
- Load test-creative skill for volume guidelines
```

---

## Step 6: Budget Progression Schedule

### Conservative Scaling (Low Risk)

| Week | Daily Budget | Change | Cumulative Growth |
|---|---|---|---|
| 1 | $[current] | Baseline | 0% |
| 2 | +10% | +10% | +10% |
| 3 | +10% | +10% | +21% |
| 4 | +10% | +10% | +33% |
| 6 | +10% | +10% | +61% |
| 8 | +10% | +10% | +95% (~2x) |

### Aggressive Scaling (Higher Risk)

| Week | Daily Budget | Change | Cumulative Growth |
|---|---|---|---|
| 1 | $[current] | Baseline | 0% |
| 2 | +20% | +20% | +20% |
| 3 | +20% | +20% | +44% |
| 4 | +20% | +20% | +73% |
| 5 | +20% | +20% | +107% (~2x) |

**Rule:** If ROAS drops more than 15% below target at any step, HOLD for one week before continuing.

---

## Follow-Up

| Situation | Next Action |
|---|---|
| Need more winning creatives to fuel scaling | `/test-plan` |
| Scaling hit a ceiling (daily loop) | `/audit-campaign` to diagnose |
| Need to build campaigns for new country | `/build-campaign` |
| Need to restructure for scaling | `strategy-meta-ads` or `strategy-google-ads` |
