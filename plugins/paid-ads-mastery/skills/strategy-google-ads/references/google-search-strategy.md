# Google Search Campaign Strategy

## Overview
- **Best For:** Service businesses, B2B, high-intent keywords
- **Data Timeline:** 3-6 months to profitability (slower than Shopping)
- **Minimum budget:** $500-1,000/day to accumulate data
- **Quality Score importance:** Critical (5-point difference = 2-4x cost change)
- **Expected ROI:** 4-6 months due to longer consideration cycle

---

## KEYWORD TIER STRUCTURE

### Tier 1: Branded Keywords (10% of budget)
**Keywords:** Your company name, product name, branded variations
**Match type:** Exact match
**Bid level:** High (safe ROI; protect against competitors)
**Expected:** 50-70% conversion rate (warm traffic)
**Timeline:** Profitable in Week 1

**Examples:**
- "Your Company Name"
- "Your Product Name"
- "Your Brand + Review"

### Tier 2: High-Intent Keywords (40% of budget)
**Keywords:** Problem + solution aware; ready to buy
**Match type:** Exact match, phrase match
**Bid level:** Medium-high
**Expected:** 10-25% conversion rate
**Timeline:** Profitable in Week 3-4

**Examples (for CRM software):**
- "Best CRM software"
- "CRM for small business"
- "Affordable CRM platform"
- "CRM software comparison"

### Tier 3: Mid-Intent Keywords (35% of budget)
**Keywords:** Problem aware; considering solutions
**Match type:** Phrase match, broad match (modified)
**Bid level:** Medium
**Expected:** 3-10% conversion rate
**Timeline:** Profitable in Month 2-3

**Examples:**
- "How to organize customer data"
- "Sales management software"
- "Customer database tools"

### Tier 4: Awareness Keywords (15% of budget)
**Keywords:** Early funnel; problem definition
**Match type:** Broad match
**Bid level:** Low
**Expected:** 0.5-3% conversion rate
**Timeline:** Month 3+ to profitability

**Examples:**
- "Customer management"
- "Business sales tools"
- "Team collaboration software"

---

## AD GROUP STRUCTURE (CRITICAL)

**Rule: 3-5 tight keywords per ad group; one topic per group**

### Correct Structure
```
Campaign: Google Search - CRM
├─ Ad Group 1: "Best CRM"
│  ├─ Keyword 1: "best CRM software" (phrase)
│  ├─ Keyword 2: "best CRM for small business" (phrase)
│  ├─ Keyword 3: "top CRM platforms" (exact)
│  └─ Ad Copy 1: "Best CRM Solutions | XYZ Platform"
│
├─ Ad Group 2: "CRM Affordable"
│  ├─ Keyword 1: "affordable CRM" (exact)
│  ├─ Keyword 2: "cheap CRM software" (exact)
│  ├─ Keyword 3: "free CRM trial" (exact)
│  └─ Ad Copy 2: "Affordable CRM | $29/month | No Hidden Fees"
│
└─ Ad Group 3: "Sales Management"
   ├─ Keyword 1: "sales management software" (exact)
   ├─ Keyword 2: "sales tracking tools" (phrase)
   └─ Ad Copy 3: "Sales Management Made Easy | Real-Time Tracking"
```

**Why this works:**
- Google pairs keywords to ad copy (tight relevance = high Quality Score)
- Ad copy mentions keyword theme (users see relevant ads)
- Quality Score improves (relevance + CTR + landing page match)

### Incorrect Structure (Don't Do This)
```
Ad Group: "Random Keywords"
├─ "best CRM"
├─ "sales software"
├─ "business productivity"
├─ "team communication"
└─ Ad Copy: "Business Software Solutions"

Problem: Keywords unrelated to each other; ad copy generic; Quality Score tank
```

---

## MATCH TYPE STRATEGY

| Match Type | Reach | Control | When to Use |
|---|---|---|---|
| **Exact** | Lowest (exact phrase only) | Highest | Tier 1 & 2 (branded, high-intent) |
| **Phrase** | Medium (phrase + word order flexible) | Medium | Tier 2 & 3 (mid-intent) |
| **Broad (Modified)** | High (similar meaning) | Low | Tier 3 & 4 (early funnel) |
| **Broad** | Highest (algorithm decides) | Lowest | Avoid until 1000+ conversions |

**Progression Example:**
```
Month 1: Exact match only (control data quality)
Month 2: Add phrase match to Tier 2 (expand slightly)
Month 3: Add broad-modified to Tier 3 (test lower funnel)
Month 6+: Consider broad match if data proves it works
```

---

## QUALITY SCORE OPTIMIZATION

### 3-Point Improvement Plan

**Points needed:** Improve from 6 → 9 (typical improvement = 30-40% CPC reduction)

**Step 1: Landing Page Relevance (40% of QS)**
- [ ] Landing page headline matches ad headline
- [ ] Landing page copy addresses keyword theme
- [ ] Load time <2 seconds (test on PageSpeed Insights)
- [ ] Mobile responsive (test on mobile device)
- [ ] Example: Keyword "best CRM" → Landing page is CRM comparison page (NOT generic homepage)

**Step 2: Ad Relevance (35% of QS)**
- [ ] Ad copy includes primary keyword
- [ ] Ad matches keyword theme (not generic)
- [ ] Headlines specific, not vague
- [ ] Example: Keyword "affordable CRM" → Ad: "Affordable CRM | $29/mo" (NOT "Software Solutions")

**Step 3: Click-Through Rate (25% of QS)**
- [ ] Bid high enough to get top position (higher position = higher CTR)
- [ ] Ad copy compelling (use benefit language)
- [ ] Add ad extensions (site links, callouts, structured snippets)
- [ ] Test headlines (goal: 5%+ CTR for high-intent keywords)

### Expected Quality Score Timeline
```
Week 1: QS 5-6 (new campaign)
Week 2: QS 6-7 (ad impressions, some optimization)
Week 3: QS 7-8 (CTR data, landing page proof)
Week 4+: QS 8-10 (sustained performance, high CTR)
```

---

## BIDDING STRATEGY PROGRESSION

### Week 1-2: Maximize Clicks
- Bid: $2-5 per click (rough estimate)
- Goal: 20-50 clicks on Tier 1 keywords
- Data collected: Which keywords get clicks
- Action: None yet; just build data

### Week 3-4: Manual CPC
- Adjust bids based on keyword performance
- High-performing keywords (5%+ CTR): +15-20% bid
- Low-performing keywords (<2% CTR): -20% bid
- Tier 1 brands: Bid high (protect position)
- Goal: Accumulate 30+ conversions

### Week 5-6: Enhanced CPC (ECPC)
- Set base bid (manual estimate)
- Google auto-adjusts upward/downward based on conversion likelihood
- Less control than manual, better than full smart bidding
- Goal: Reach 60+ conversions

### Week 7+: Target CPA or Maximize Conversions
- If data shows consistent CPA: Switch to Target CPA (set ceiling on cost)
- If want volume: Switch to Maximize Conversions
- Requires 100+ conversions minimum

---

## PRODUCT/SERVICE LANDING PAGE STRATEGY

**Rule: One landing page per ad group theme**

### Landing Page Hierarchy
```
Homepage (generic; avoid)
  ↓
Category Page (better; product category overview)
  ↓
Product Page (best; specific product matching keyword)
  ↓
Free Trial/Demo Page (best; incentive-driven for awareness keywords)
```

**Landing page matching example:**
```
Ad Group: "CRM for Nonprofits"
├─ Keyword: "nonprofit CRM software"
├─ Ad Copy: "CRM Built for Nonprofits | Free Trial"
└─ Landing Page: /nonprofit-crm/ (NOT /crm-overview/ or homepage)
```

---

## COMMON STRUCTURE MISTAKES

| Mistake | Effect | Fix |
|---|---|---|
| **One ad group, 50 keywords** | QS 4-5 (keywords unrelated) | Split into 5-10 ad groups by theme |
| **Keyword "insurance" + Ad "Car Insurance"** | QS 6 (relevant but not tight) | Ad: "Cheap Car Insurance Quote" (more specific) |
| **Landing page = homepage** | QS 5-6 (generic) | Use product/category page matching keyword |
| **Broad match keywords only** | QS 5-6; wasted budget on random clicks | Use exact/phrase in Tier 1-2; broad only in Tier 4 |
| **Ad group name = "Misc"** | Not a QS issue but hard to manage | Rename to keyword theme |

---

## MONTHLY OPTIMIZATION

### Step 1: Identify Losers
- Filter: Keywords with 20+ clicks, <1% conversion rate
- Action: Pause or lower bid 50% (give low performers chance but not full budget)
- Timeline: Monthly review

### Step 2: Scale Winners
- Filter: Keywords with 10+ conversions, >2% conversion rate
- Action: Increase bid +20-30% (invest in proven winners)
- Timeline: Monthly review

### Step 3: Tier Progression
- Tier 1: 100% budget allocation (safe; branded)
- Tier 2: 70-80% budget (high-intent proves out)
- Tier 3: 40-60% budget (mid-intent slower to convert)
- Tier 4: 10-20% budget (awareness; long-tail testing)

---

## EXPECTED TIMELINE TO PROFITABILITY

```
Month 1: Learning phase
- Spend: $10K-15K
- Conversions: 30-50
- ROAS: 0.5-1.0 (not yet profitable)
- Action: Optimize ad copy, landing pages, bid structure

Month 2: Early optimization
- Spend: $10K-15K
- Conversions: 60-100
- ROAS: 0.8-1.2 (approaching breakeven)
- Action: Scale winners; pause losers

Month 3: Profitability
- Spend: $10K-15K
- Conversions: 80-150
- ROAS: 1.2-1.8 (profitable)
- Action: Scale 15-20% weekly if ROAS stable

Month 4-6: Scaling
- Spend: $15K-30K+/month
- Conversions: 150-300+
- ROAS: 1.5-2.5+ (healthy growth)
- Action: Layer PMax, retargeting, expanded keywords
```

---

## KEY TAKEAWAYS

1. **Tier your keywords by intent** (branded, high, mid, awareness)
2. **3-5 tight keywords per ad group** (one topic = high QS)
3. **Exact/phrase match in Tier 1-2; broad in Tier 3-4**
4. **Quality Score 7+ essential** (saves 40% CPC vs QS 4)
5. **Ad copy must include keyword** (improves QS + CTR)
6. **Landing page matches keyword theme** (not homepage)
7. **Maximize Clicks first; Manual CPC after 30 conversions; Smart bidding after 100**
8. **Monthly optimization:** Scale winners, pause losers
9. **Timeline to profit: 3-4 months** (longer than Shopping)
10. **Budget minimum $500/day** to accumulate sufficient data
