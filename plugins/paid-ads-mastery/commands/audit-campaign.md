---
name: Audit Campaign
description: Diagnose an existing campaign using diagnostic frameworks. Identifies bottlenecks and prescribes fixes. Activates optimize-meta OR optimize-google, plus scale-campaigns when scaling diagnostics are needed.
---

# Campaign Audit Wizard

## Step 1: Identify Platform and Gather Data

Ask the user:

1. **Platform:** Meta/Facebook, Google Ads, or both?
2. **Campaign type:** What campaigns are running? (CBO, ASC, Shopping, PMax, Search, etc.)
3. **Time period:** How long has the campaign been running?
4. **Current performance:** Ask for these metrics:

### Meta Metrics Needed
- ROAS (7-day and 14-day rolling average)
- CPA (cost per acquisition)
- CTR (all) and CTR (link)
- CPM
- CPC
- Frequency
- Hook rate (for video ads)
- Conversion rate (website)
- Daily spend vs. budget
- AOV

### Google Metrics Needed
- ROAS or CPA
- CTR
- CPC
- Conversion rate
- Quality Score (for Search)
- Campaign CTR (for Shopping -- target 1%+)
- Impression Share and IS Lost (Budget) / IS Lost (Rank)
- Search terms report highlights
- Asset performance ratings (for PMax)

---

## Step 2: Run Platform-Specific Diagnostic

### Meta Campaign Diagnostic

**Load skill:** `optimize-meta` > ref-meta-diagnostics.md

**Diagnostic Matrix:**

| Check | What to Look At | Red Flag |
|---|---|---|
| **CPM + CTR combo** | High CPM + Low CTR = creative problem. Low CPM + Low CTR = targeting mismatch. | Any combo with low CTR |
| **CPC + CPM combo** | High CPC + Low CPM = creative not compelling. High CPC + High CPM = competitive market. | High CPC regardless of CPM |
| **Frequency** | Above 2.0 on prospecting with declining performance = fatigue | Above 3.0 = urgent |
| **Hook rate** | Below 15% = hook is failing | Below 15% |
| **CVR** | Below 2% = landing page problem | Below 2% |
| **CTR high + CVR low** | Landing page problem, NOT ad problem | Misalignment between ad and LP |
| **Checkout-to-purchase ratio** | If checkouts exist but purchases lag, delayed reporting likely | Wait 48-72 hours |
| **Comments** | Negative comments driving engagement = wasted spend | Visible negative comments |

### Google Campaign Diagnostic

**Load skill:** `optimize-google` > ref-google-unit-economics.md (for bottleneck analysis)

**Bottleneck Analysis:**

```
Impressions --> Clicks --> Conversions --> Revenue --> Profit
     |              |           |              |          |
    CTR           CVR      Close Rate    Deal Value   Margins
```

Identify which link is broken:

| Bottleneck | Symptom | Solution |
|---|---|---|
| Impressions | Low impression share | Increase budget or bids |
| CTR | Impressions but few clicks | Improve ad copy, extensions, headlines |
| CVR | Clicks but few conversions | Fix landing page or offer |
| Profitability | Conversions but losing money | Fix unit economics or bidding strategy |

**Shopping-Specific Checks:**
- Campaign CTR below 1%? Product images and titles need optimization.
- Products spending with zero sales? Exclude at 1.5-3x profit margin with no conversions.
- Zero-click products with 500+ impressions? Exclude immediately.

**Search-Specific Checks:**
- Quality Score below 5? Follow 3-phase QS playbook (Ad Relevance > Expected CTR > LP Experience).
- Irrelevant search terms consuming budget? Add negatives.
- Has campaign hit 30/30 threshold for Target CPA/ROAS switch?

**PMax-Specific Checks:**
- Brand traffic mixed in? Exclude brand queries -- they inflate ROAS.
- Any Silent Killers? (High impression share + low conversion rate = remove first)
- Campaign live less than 2 weeks? May still be in learning phase.

---

## Step 3: Identify Root Cause Category

| Category | Symptoms | Prescription |
|---|---|---|
| **A: Creative Problem** | Low CTR, low hook rate, high CPM + low engagement, fatigue | Load `test-creative`. Produce new variations. |
| **B: Landing Page / Offer** | High CTR + low CVR, high bounce, cart abandonment | Out of scope (CRO). Advise LP optimization. |
| **C: Targeting / Structure** | High frequency, auction overlap, budget on wrong audiences | Load `strategy-meta-ads` or `strategy-google-ads`. |
| **D: Tracking / Attribution** | Ads Manager vs. revenue discrepancy, missing conversions | Load `optimize-meta` > ref-meta-attribution.md or `setup-google-ads`. |
| **E: Unit Economics** | Cannot scale profitably, break-even ROAS too high | Load `optimize-google` > ref-google-unit-economics.md. Business problem. |
| **F: Scaling Ceiling** | More budget = worse ROAS. Daily loop detected. | Load `scale-campaigns`. New angles, countries, or offer needed. |

---

## Step 4: Generate Action Plan

```
CAMPAIGN AUDIT RESULTS
======================

Platform: [Meta / Google / Both]
Audit Period: [dates]
Current Performance: [ROAS / CPA summary]

ROOT CAUSE: [Category A-F with explanation]

IMMEDIATE ACTIONS (This Week):
1. [Highest priority fix with specific instructions]
2. [Second priority fix]
3. [Third priority fix]

SHORT-TERM ACTIONS (Next 2-4 Weeks):
1. [Structural or strategic change]
2. [Creative production needed]
3. [Testing plan]

METRICS TO MONITOR:
- [Primary KPI to track improvement]
- [Secondary KPI]
- [Leading indicator]

EXPECTED TIMELINE:
- [When to expect improvement]
- [When to reassess if no improvement]

SKILLS TO LOAD FOR EXECUTION:
- [Relevant skills for the prescribed actions]
```

---

## Step 5: Follow-Up Recommendations

| Situation | Next Action |
|---|---|
| Need new creatives | `/write-ad` or `create-ad-copy` / `create-video-ads` |
| Need a testing plan | `/test-plan` |
| Need to restructure campaigns | `/build-campaign` with revised parameters |
| Ready to scale after fixes | `/scale-plan` |
| Need creative research for new angles | `/research-brief` |
