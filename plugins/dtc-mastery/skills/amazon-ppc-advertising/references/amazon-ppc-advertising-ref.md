---
name: Amazon PPC Advertising Reference
description: >
  Campaign types overview with targeting and use cases, Amazon SERP anatomy,
  bid optimization framework detail, ACOS/TACOS calculations, DSP funnel deep
  dive with audience building, ChatGPT + Google Sheets PPC tools (10 tools),
  Amazon Advertising Academy module structure, and traffic-stealing tactics.
  When to Read: User needs campaign setup specifics, bid math, DSP audience
  details, or wants to build PPC automation tools.
  Cross-references: For ranking formula and placement strategy frameworks, see
  SKILL.md above. For listing optimization that improves PPC conversion, see
  amazon-listing-optimization.
---

# Amazon PPC Advertising -- Complete Reference

## Campaign Types Overview (Incrementum Digital)

| Type | Targeting | Best For |
|---|---|---|
| Sponsored Products - Auto | Amazon selects keywords | Discovery, new products, keyword harvesting |
| Sponsored Products - Manual Keyword | You choose keywords | Scaling proven keywords from auto campaigns |
| Sponsored Products - Manual Product | Target specific ASINs | Conquesting competitors, stealing traffic |
| Sponsored Brands | Headline + brand store link | Brand awareness, top of search real estate |
| Sponsored Display | Audience/product targeting | Retargeting, competitor conquesting |
| DSP | Amazon audiences on/off Amazon | Full funnel, advanced retargeting, OTT video |

---

## Amazon SERP Anatomy (Incrementum Digital)

**From top to bottom:**
1. Sponsored Brands -- headline ads at very top
2. Top of Search -- first row of Sponsored Product ads (premium position)
3. Amazon Choice / Deals / Highly Rated -- organic badges
4. Rest of Search -- mid-page Sponsored Product rows
5. Sponsored Display / DSP -- left sidebar and in-feed placements
6. Brands Related to Search -- bottom of page Sponsored Brand ads

---

## Bid Optimization Framework (Incrementum Digital)

**Bid vs CPC:** Your bid is the maximum. Actual CPC is often lower (second-price auction model).

**Key metrics:**
- **ACOS (Advertising Cost of Sales)** = Ad Spend / Ad Revenue
- **TACOS (Total ACOS)** = Ad Spend / Total Revenue (includes organic sales)

**Optimization rules:**
| Scenario | Action |
|---|---|
| Good-performing targets (low ACOS, converting) | Increase bids to gain more impressions |
| High-ACOS targets | Reduce bids incrementally (do not slash) |
| Non-converting targets after sufficient impressions | Add as negative match |
| Profitable keywords in auto campaigns | Graduate to manual exact match |

**Placement multipliers:** Adjust top-of-search and product page bids separately from base bid. Use placement report data to set modifiers.

**When to start optimizing:** After sufficient data accumulation. Do not make bid changes on 2-3 days of data.

---

## Campaign Launch Sequence (Synthesized)

**Phase 1: Discovery (Week 1-2)**
1. Launch Sponsored Products Auto campaign for keyword harvesting
2. Set conservative daily budget ($20-50/day depending on category)
3. Let auto campaign accumulate data for 7-14 days

**Phase 2: Manual Expansion (Week 2-4)**
4. Pull search term report from auto campaign
5. Graduate converting search terms to Manual Keyword campaigns (exact match)
6. Create broad match campaigns with modifiers (+keyword) for new keyword discovery
7. Add non-converting terms as negative keywords in auto campaign

**Phase 3: Competitive Targeting (Week 3-6)**
8. Launch Manual Product targeting campaigns against competitors
9. Use Kevin King tactic: target products launched in last 10-90 days (low reviews, heavy spend)
10. Launch Sponsored Brands for top-of-search headline real estate

**Phase 4: Scale and Optimize (Ongoing)**
11. Pull placement report weekly -- adjust TOS/ROS/PDP modifiers
12. Pull SQPR monthly -- lean into positive-advantage keywords, fix or abandon negative-advantage ones
13. Consider DSP when search spend exceeds $25K-$50K/month

---

## DSP Deep Dive (Liran Hirschkorn + Vanessa Hung + Tim Jordan)

### Access Options
- **Amazon Direct:** $35K+ minimum budget required
- **Agency access:** Cheaper minimums, agency manages campaigns

### Audience Types
- Amazon lifestyle audiences (fitness, cooking, tech)
- In-market audiences (actively browsing specific categories)
- Demographic targeting (gender, marital status, education)
- Cross-layer audiences (e.g., "parents" AND "keto lifestyle")
- Retargeting: product viewers, add-to-cart, past purchasers
- Competitor ASIN viewers/purchasers

### 60/20/20 Funnel Budget Split

**60% Bottom of Funnel (Retargeting + Retention):**
- Target viewers who did not purchase (highest ROAS)
- Add-to-cart abandonment retargeting
- Retention for consumables: 60-180 day purchasers who have not reordered

**20% Middle of Funnel (Consideration):**
- Target competitor ASIN viewers and purchasers
- Cross-selling own product catalog
- Category-level targeting

**20% Top of Funnel (Brand Awareness):**
- Amazon lifestyle/in-market audiences
- OTT (Over The Top) streaming TV ads
- Widest reach, lowest direct ROAS

### DSP Data Benefit
Reveals customer demographics (gender, marital status, education, consideration period) that can inform Facebook ad targeting and audience building.

### DSP + Influencer Flywheel (Tim Jordan)
1. Capture non-converting traffic from influencer links as segmented audience
2. Retarget that audience with DSP
3. Build lookalike audiences from converters
4. Use DSP microsegmentation to target specific audience segments with tailored content

---

## ChatGPT + Google Sheets PPC Tools (Ritu Java)

10 PPC tools built using ChatGPT + Google Sheets Apps Script:

1. **Seed keyword generator** -- ask ChatGPT for top 10 audiences + their search keywords, feed into Magnet
2. **Keyword sorting hat** -- auto-sort keywords into broad/exact/phrase buckets by search volume + word count
3. **ASIN sorting hat** -- sort competitor ASINs into low-hanging / medium / high-risk by review count + price
4. **Negative keyword frequency analyzer** -- split search terms into single words, calculate frequency, catch bleeding words (e.g., "toddler" appearing across 42 wasted clicks in multiple long-tail terms)
5. **Campaign month-over-month trend analysis** via Apps Script
6. **Keyword theme generator** for Sponsored Brand headlines

**Method:** Describe what you want to ChatGPT, paste Apps Script code into Google Sheets Extensions > Apps Script, iterate errors back into ChatGPT for debugging.

---

## Broad Match Modifier Detail (Kevin King)

**Syntax:** Add `+` before each word you want forced into the match.

| Campaign Type | Keyword | Matches | Does NOT Match |
|---|---|---|---|
| Standard Broad | basketball shoes | sneakers, running shoes, athletic footwear | (matches too broadly) |
| Modified Broad | +basketball +shoes | basketball shoes for men, kids basketball shoes | sneakers, running shoes |

**Use case:** Intermediate step between broad (too wide) and exact (too narrow). Gets new keyword ideas while preventing irrelevant spend.

---

## Traffic Stealing Tactics (Kevin King)

### Target New Launches
1. Use X-Ray creation date field to find products launched in last 10-90 days
2. These products have heavy PPC spend but low/no reviews
3. Run product-targeting campaigns against them
4. Your established review count creates conversion advantage

### Attribution Link Keyword Hack
- Standard Amazon Attribution links do not populate search bar
- Add `field-keywords=your+keyword` to end of attribution URL
- Result: keyword appears in search bar when clicked, giving extra rank signal for that specific keyword
- (Also covered in external-traffic-list-building)

---

## Key Benchmarks

| Metric | Value | Source |
|---|---|---|
| Minimum reviews before scaling PPC | 10 | Vong |
| DSP minimum (Amazon direct) | $35K+ monthly | Hirschkorn |
| DSP minimum (agency) | Varies, lower threshold | Hirschkorn |
| DSP bottom funnel allocation | 60% of budget | Hirschkorn |
| DSP view-through true ROAS | ~4-5x (reported 10x inflated) | Hirschkorn |
| Ritu Java PPC tools built | 10 tools in 10 days | Java |
| Example TOS CVR | 17% at $1.72 CPC | Young |
| Example ROS CVR | 6% at $0.72 CPC | Young |
| New launch targeting window | Products 10-90 days old | King |
