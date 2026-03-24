---
title: Meta Campaign Diagnostic Framework
skill: optimize-meta
usage: Load when user shares Meta campaign metrics and needs diagnosis, asks about CPM/CTR/CPC relationships, needs benchmark targets, or reports creative fatigue symptoms.
---

# Meta Campaign Diagnostic Framework

## The Diagnostic Decision Tree

When a user reports performance issues, walk through these steps in order:

### Step 1: Calculate Break-Even ROAS
- **Formula:** 1 / Profit Margin (as decimal)
- Example: AOV $80, costs $30 = 62.5% margin. Break-even = 1 / 0.625 = 1.6 ROAS
- If current ROAS is below break-even, every dollar spent is losing money
- If profit margin is 10%, need 10 ROAS to break even -- nearly impossible for most products

### Step 2: Identify Key Metrics (Priority Order)
1. **Cost per unique click** -- is the creative attracting quality traffic?
2. **Conversion rate** -- is the website/offer converting?
3. **CPM** -- is the pixel trained? Is targeting efficient?
4. **Cost per purchase** -- overall campaign efficiency
5. **AOV** -- is the business model sustainable?

### Step 3: Run the Diagnostic Matrix

| High CPM | Low CPM |
|---|---|
| + Low CTR = **Creative problem.** Ad is not engaging. Replace creative. | + Low CTR = **Targeting mismatch.** Reaching people but message does not resonate. Adjust angle. |
| + High CTR = **Competitive auction.** Market is expensive. Not creative fault. Test placements/times. | + High CTR = **Ideal scenario.** Creative is working and market is accessible. Scale. |

| High CPC | Low CPC |
|---|---|
| + High CPM = **Competitive market.** Industry-level issue, not creative. | + High CPM = **Unusual.** May indicate very niche targeting with high competition. |
| + Low CPM = **Creative/targeting issue.** Impressions are cheap but clicks are expensive. Creative not compelling enough. | + Low CPM = **Strong creative.** Efficient clicks in accessible market. Scale. |

### Step 4: Website vs. Ad Diagnosis

| Metric Pattern | Problem Location |
|---|---|
| High CTR + Low CVR | Website/landing page problem. Creative is doing its job. |
| Low CTR + High CVR | Creative filters well. Fewer clicks but high quality. May be acceptable. |
| CTR same + AOV drops | Upsell/backend problem. Not ad problem. |
| CVR drops + AOV increases | Higher quality but lower volume traffic. May need broader targeting. |
| CTR decreases + CPM decreases | Overall traffic quality declined. Algorithm shifted to cheaper, lower-quality inventory. |

---

## CPC-CPM Relationship Analysis

**Always compare CPC and CPM together. Never evaluate CPC in isolation.**

The relationship between CPC and CPM reveals the true story:

| CPC | CPM | Interpretation |
|---|---|---|
| High | High | Competitive market. Your creative is fine; the auction is expensive. |
| High | Low | Targeting/creative issue. Cheap impressions but people are not clicking. |
| Low | High | Strong creative. Despite expensive auction, people are clicking. |
| Low | Low | Ideal. Efficient market + compelling creative. |

### CPC Formula Context
- CPC = CPM / (CTR x 1000)
- A CPM of $20 with 2% CTR = $1.00 CPC
- A CPM of $20 with 5% CTR = $0.40 CPC
- Improving CTR through creative is the fastest way to lower CPC

---

## Creative Performance Metrics

### Hook Rate (Video Ads)
- **Definition:** Percentage of viewers who watch past 3 seconds
- **Good:** 35%+ (US market)
- **Bad:** Below 15%
- **Action if bad:** Replace hook. Keep body if body metrics are fine.

### Hold Rate (Video Ads)
- **Definition:** Percentage of viewers who finish the full video
- **Acceptable:** ~11% finishing full video
- **Context:** Only ~10% of people finish ANY video. 11% is above average.
- **Average video watch time:** 3-5 seconds is typical; 10 seconds is very good

### Thumbstop Rate
- **Definition:** Ratio of 3-second video views to impressions
- **Purpose:** Measures scroll-stopping power independent of watch time
- **Benchmark:** 20-30% is average; 40%+ is excellent

### Waterfall Rate
- **Definition:** Drop-off rate at each interval of the video (25%, 50%, 75%, 100%)
- **Purpose:** Identifies exactly WHERE viewers lose interest
- **Action:** If massive drop at 10-second mark, the content after the hook is failing

### The Two Metrics Creative Strategists Own
1. **Thumbstop / Hook Rate** -- can the creative stop the scroll?
2. **Hold Rate / Average Watch Time** -- can the creative maintain attention?

Everything after (CTR, CVR, CPA) involves the landing page, offer, and business fundamentals.

---

## Creative Fatigue Detection Protocol

### Frequency-Based Detection
| Frequency | Performance Trend | Diagnosis |
|---|---|---|
| Above 1.5-2.0 | Declining | **Creative fatigue.** Audience has seen ad too many times. |
| Above 1.5-2.0 | Stable/improving | NOT fatigued. Frequency alone is not the problem. |
| Below 1.5 | Declining | **Not fatigue.** Creative is underperforming for other reasons. |
| Above 3.0 (prospecting) | Any decline | **Urgent fatigue.** Implement exclusions or replace creative immediately. |

### Non-Frequency Fatigue Indicators
- CTR declining over 7+ days while impressions remain stable
- CPA increasing steadily over 5+ days
- Hook rate declining on video ads
- Comment sentiment turning negative ("I keep seeing this ad")

### Fatigue Response Protocol
1. Do NOT add new creatives to the fatiguing campaign
2. Launch replacement creatives in a NEW campaign
3. Iterate the fatiguing creative (new hook, new headline, new color) in a separate test
4. Diversify with new landing pages (changes synergy without changing ad)
5. Consider pausing the fatigued creative for 2-4 weeks, then relaunching

---

## Ad Performance Diagnostic Cheatsheet

### Common Root Causes for Poor Performance
1. **Auction overlap** -- multiple campaigns targeting same audience, bidding against yourself
2. **100% spend outside learning phase** -- insufficient conversion volume
3. **Lack of exclusions** -- prospecting campaigns hitting existing customers
4. **Small audiences exhausted** -- targeting too narrow, frequency too high
5. **Insufficient scaling method variety** -- relying on one approach only
6. **Bad engagement driving budget** -- negative comments consuming spend
7. **Creative type mismatch in campaign** -- mixing video + static in same campaign

### Quick Fixes (Try These First)
1. Check comments -- hide negatives immediately
2. Check frequency -- if above 2.0 on prospecting, creative is fatiguing
3. Check conversion rate -- if CVR dropped, problem is website not ads
4. Check checkout-to-purchase ratio -- if checkouts exist but purchases lag, wait 48-72 hours for delayed reporting
5. Check if budget was changed -- any budget change can disrupt optimization for 24-48 hours

---

## Metric Formulas Quick Reference

| Metric | Formula |
|---|---|
| ROAS | Revenue / Ad Spend |
| CPA | Ad Spend / Conversions |
| CTR (all) | (All Clicks / Impressions) x 100 |
| CTR (link) | (Link Clicks / Impressions) x 100 |
| CPC | Ad Spend / Clicks |
| CPM | (Ad Spend / Impressions) x 1000 |
| Hook Rate | (3-Second Views / Impressions) x 100 |
| Hold Rate | (Complete Views / 3-Second Views) x 100 |
| Frequency | Impressions / Reach |
| Break-Even ROAS | 1 / Profit Margin |
| Profit Margin | (AOV - Cost) / AOV |
