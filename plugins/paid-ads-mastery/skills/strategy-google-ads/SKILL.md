---
name: Google Ads Campaign Strategy
description: Google Ads campaign structures for Shopping, Search, Performance Max, and YouTube including the 30-30 smart bidding rule, keyword tier system, Quality Score optimization, bidding progressions, campaign segmentation by budget, and full-funnel strategy. Use when planning Google campaign architecture, choosing bidding strategies, or deciding between campaign types.
---

# Google Ads Campaign Strategy

## Quick Navigation
- **Choosing a Campaign Type** → Decision Tree below
- **Bidding Strategy Decision** → Smart Bidding section
- **Shopping Campaign Setup** → Reference file
- **Full-Funnel Strategy** → Reference file

---

## CAMPAIGN TYPE DECISION TREE

**Start here: What's your goal?**

### IF E-commerce + Want to show products directly in ads
→ Use **Google Shopping** ([read full guide](./references/google-shopping-strategy.md))
- Campaigns feed products from Merchant Center
- High intent (users searching for products)
- Fast ROI (usually 4-6 weeks to profitability)
- Minimum products: 20-25 active
- Budget: $200-500/day to start

### IF E-commerce + Have good landing pages + Want to reach buyers in consideration phase
→ Use **Performance Max (PMax)** ([read full guide](./references/google-pmax-strategy.md))
- Reaches all Google channels in one campaign
- Requires 50+ conversions historical data (to optimize)
- Asset groups (headlines, descriptions, images, videos)
- Minimum budget: $100/day to learn (but $150+ recommended)
- New accounts: Start with Shopping first; layer PMax after

### IF E-commerce + Already have Search campaigns working
→ Layer **YouTube Ads** ([read full guide](./references/google-youtube-strategy.md))
- 7 must-have ad elements (hook, USP, proof, objection, CTA, end screen, frequency cap)
- Sweet spot duration: 1:30-3:00 (skip ads at 5 seconds)
- Only layer if search/shopping working (don't start with video)

### IF Service business OR Local + Want high-intent customers
→ Use **Google Search** ([read full guide](./references/google-search-strategy.md))
- Keyword-based; users searching for what you offer
- Quality Score critical (keyword relevance, ad quality, landing page)
- Ad groups (tight keyword grouping; 3-5 keywords per group)
- Budget: $500-1,500/day minimum for viable testing
- ROI: 3-6 months to profitability (longer than Shopping)

### IF Unknown where to start + Have no existing data
→ Start with **Shopping IF e-commerce**, else **Search** ([read guides](./references/))
- Shopping faster to results
- Search requires better landing page structure
- Both scale from same product/offer

---

## THE 30-30 SMART BIDDING RULE (CRITICAL)

**Rule: Use Smart Bidding if you have 30+ conversions in 30 days**

```
Conversions in last 30 days?
├─ 30+: Use Smart Bidding (Maximize Conversions, Target ROAS, etc.)
├─ 15-29: Use Maximize Clicks (quasi-smart, safer while learning)
└─ <15: Use Manual CPC (full control; algorithm learning minimal)
```

### Why 30-30 Matters

Smart bidding algorithms require data to work. Without minimum data:
- **0-14 conversions:** Algorithm has nothing to learn from; manual is safer
- **15-29 conversions:** Algorithms can learn but still volatile; Maximize Clicks safer
- **30+ conversions:** Algorithm has sufficient pattern data; smart bidding works well

**Real consequence of ignoring this:**
```
Scenario: New account, 3 conversions, set Target ROAS 2.5
Expected: System targets ROAS 2.5
Reality: System bids randomly (no data); ROAS 0.8-4.0 wildly volatile
Result: Wasted budget; impossible to interpret performance

Correct approach: Use Maximize Clicks until 30 conversions, then switch to Target ROAS
```

---

## CAMPAIGN STRUCTURE BY BUDGET

### IF Budget < $200/day
→ **Single General Testing Campaign (GTC)**
- One Shopping OR Search campaign
- All products/keywords in one campaign
- Use Maximize Clicks bidding
- Goal: Accumulate 30+ conversions to test smarter bidding
- Timeline: 2-4 weeks depending on conversion rate

### IF Budget $200-500/day
→ **High Bid + Low Bid Split (Shopping)**
- Campaign 1: [High Bid] - Conservative bidding, test products
- Campaign 2: [Low Bid] - Aggressive bidding, winner scaling
- Each gets $200-250/day
- Use Maximize Clicks on both initially
- After 30+ conversions in High Bid: Switch to Target ROAS
- Expected: 4-6 weeks to clear 60 conversions (30 per campaign)

**OR Single Performance Max (if enough historical data)**
- One PMax campaign $200-500/day
- Only if account has 50+ conversions already from other source
- Good for scaling proven products to all channels

### IF Budget $500-1,500/day
→ **Segmented by Product Category (Shopping) OR Keywords (Search)**
- Campaign 1: High-Volume Products (apparel, electronics, etc.)
  - Budget: $200-300/day
  - Single products from high-demand categories

- Campaign 2: Mid-Volume Products
  - Budget: $150-250/day
  - Secondary products; test new inventory

- Campaign 3: Low-Volume/Testing
  - Budget: $100-200/day
  - New products, experimental categories

- Campaign 4: High-Bid Premium
  - Budget: $100-200/day
  - Winners from other campaigns at higher bids

**Bidding progression:**
- New campaigns: Maximize Clicks
- After 30 conversions: Manual CPC or ECPC
- After 60 conversions + proving ROAS: Target ROAS
- Mature campaigns (3+ months, 200+ conversions): Maximize Conversions

### IF Budget $1,500+/day
→ **Full Funnel Strategy** ([read guide](./references/google-full-funnel.md))
- Demand Gen campaigns (brand awareness, reach)
- Demand Capture campaigns (search, shopping)
- Retargeting campaigns (YouTube, RLSA)
- Allocate: 20% awareness, 50% capture, 30% retargeting
- Each pillar: Own campaign set with tailored bidding

---

## BIDDING STRATEGY PROGRESSION

### Bidding Progression for New Accounts

**Month 1 (Days 1-30):**
```
Campaign Status: <30 conversions
Recommended Bidding: Maximize Clicks
Why: Algorithm learning phase; doesn't need conversion optimization yet
What happens: Google optimizes for clicks, not conversions; CPC lower
Expected data: 10-30 clicks per day (assuming $5-10/day spend)
```

**Month 2 (Days 31-60):**
```
Campaign Status: 30-80 conversions
Recommended Bidding: Manual CPC or Enhanced CPC (ECPC)
Why: Enough conversion data to start optimizing, but too new for smart bidding
Manual CPC approach: Gradually increase bids on high-conversion keywords
ECPC approach: Let algorithm adjust your manual bids based on conversion probability
Expected data: 15-50 conversions per day
```

**Month 3+ (60+ conversions):**
```
Campaign Status: 60+ conversions, 3+ weeks data
Recommended Bidding: Target ROAS or Maximize Conversions
Why: Enough data for smart algorithm to learn patterns
Target ROAS: Set target profitability (e.g., 3.0 ROAS); algorithm bids to hit it
Maximize Conversions: Just maximize volume at your budget
Expected result: More predictable performance; lower CPA than earlier phase
```

### Bidding Strategy Decision Matrix

| Account Age | Conversions | Recommended | Why |
|---|---|---|---|
| **New** | <15 | Manual CPC | No data for algorithms |
| **New** | 15-29 | Maximize Clicks | Safe quasi-smart option |
| **New** | 30-59 | Manual CPC or ECPC | Enough for optimization, not smart yet |
| **Established** | 60+ | Target ROAS | Smart bidding safe |
| **Mature** | 300+ | Maximize Conversions | Highest volume play |
| **Any** | Any | Maximize Clicks | Safest universal default |

---

## QUALITY SCORE OPTIMIZATION

**Quality Score factors (in order of importance):**

| Factor | Importance | How to Improve |
|--------|------------|---|
| **Landing Page Quality** | 40% | Fast load (<2s), mobile-responsive, relevant to ad |
| **Keyword Relevance** | 35% | Exact match keywords in ad groups (3-5 per group), match ads to keywords |
| **Click-Through Rate (CTR)** | 25% | Compelling ad copy, clear CTA, match user intent |

**Quality Score impact:**
```
Quality Score 10: Cost per click baseline ($1.00 example)
Quality Score 9: +11% cost ($1.11)
Quality Score 8: +25% cost ($1.25)
Quality Score 7: +50% cost ($1.50)
Quality Score 6: +100% cost ($2.00)
Quality Score 5-1: 2-4x cost baseline
```

**A 1-point Quality Score difference = 10-25% CPC change**

### Quality Score Improvement Plan

**Immediate (Week 1):**
- [ ] Check landing page load speed (should be <2 seconds)
- [ ] Verify landing page is mobile responsive
- [ ] Check that landing page content matches ad copy

**Short-term (Week 2-3):**
- [ ] Reorganize ad groups (one topic per group; 3-5 keywords max)
- [ ] Rewrite ad copy to include primary keyword
- [ ] Increase bid incrementally; let Quality Score improve reduce effective CPC

**Medium-term (Week 4-8):**
- [ ] A/B test ad copy (goal: improve CTR 10-25%)
- [ ] Optimize landing page based on heatmap/user behavior
- [ ] Add ad extensions (site link, callout, structured snippet)

**Expected result:** Quality Score improvement of 1-3 points = 15-40% CPC reduction over 4 weeks

---

## SHOPPING CAMPAIGN BIDDING PROGRESSION

**Shopping campaigns have specific bidding progression:**

```
Week 1-2: Maximize Clicks
├─ Set max CPC around $0.30-0.50
├─ Let algorithm find products that get clicks cheaply
└─ Accumulate data on which products are clickable

Week 3-4: Manual CPC Optimization
├─ Identify products with positive ROAS (even if not scalable yet)
├─ Increase bids on positive ROAS products by 10-20%
├─ Decrease bids on losing products
└─ Aim to accumulate 30+ conversions

Week 5-6: Enhanced CPC (ECPC) or Continue Manual
├─ Switch to ECPC if saw 30+ conversions
├─ ECPC auto-adjusts your manual bids based on conversion probability
├─ Manual: Continue hand-tuning if you prefer control
└─ Begin identifying "winners" (ROAS 3.0+)

Week 7+: Target ROAS
├─ If campaign has 50+ conversions AND clear winner products
├─ Switch to Target ROAS (example: 3.0 ROAS target)
├─ Let algorithm handle all bids; you set profitability goal
└─ Monitor; should see more stable results
```

---

## KEYWORD TIERS & MATCH TYPES (SEARCH ONLY)

**Keyword Tier Structure (Organize by search intent strength):**

| Tier | Keyword Type | Match | Budget % | Bid Strategy | ROI Timeline |
|---|---|---|---|---|---|
| **Tier 1** | Branded (Your name) | Exact | 10% | Maximize Conversions | 2-4 weeks |
| **Tier 2** | High-Intent (Problem + solution aware) | Broad exact, phrase | 40% | Target ROAS (if data exists) | 3-8 weeks |
| **Tier 3** | Mid-Intent (Problem aware) | Phrase, broad | 35% | Maximize Clicks → ECPC | 6-12 weeks |
| **Tier 4** | Low-Intent (Awareness) | Broad | 15% | Maximize Clicks | 8-16 weeks |

**Example keyword tiers for a SaaS product:**

```
Tier 1 (Branded - 10%):
├─ "Your Company Name"
├─ "Your Product Name"
└─ Budget: 10% of total; bid high (ROI certain)

Tier 2 (Problem + Solution - 40%):
├─ "Best CRM software"
├─ "CRM for small business"
├─ "CRM platform comparison"
└─ Budget: 40% (high intent; searches show buying consideration)

Tier 3 (Problem Aware - 35%):
├─ "How to choose CRM"
├─ "CRM software features"
├─ "What is a CRM"
└─ Budget: 35% (mid intent; helping them understand need)

Tier 4 (Awareness - 15%):
├─ "Customer relationship management"
├─ "Sales tools"
├─ "Business automation"
└─ Budget: 15% (broad; early funnel; lowest conversion rate)
```

**Bidding strategy:** Tier 1 bids highest (safe ROI); Tier 4 bids lowest (testing phase)

---

## PERFORMANCE MAX vs SMART SHOPPING (COMPARISON)

| Aspect | Performance Max (PMax) | Smart Shopping (Deprecated) |
|---|---|---|
| **Channels** | All Google channels (Search, Display, YouTube, Gmail, Maps) | Shopping feed only |
| **Control** | Lowest (Google optimizes everything) | Higher (You manage products) |
| **Data requirement** | 50+ conversions to optimize | 20+ conversions to start |
| **Scale potential** | High (reaches all channels) | Medium (Shopping only) |
| **Setup time** | 30 minutes (feeds in assets) | 30 minutes (set up feed) |
| **ROAS learning** | Slower (multi-channel learning) | Faster (single channel) |
| **Best for** | Established accounts scaling across channels | Pure Shopping feed optimization |
| **Status** | Active; recommended | Deprecated (Google pushing to PMax) |

**Modern recommendation:** Use Shopping first (faster data), add PMax once you have 100+ conversions.

---

## FULL-FUNNEL STRATEGY (ADVANCED)

For budgets $1,500+/day, implement 4-pillar framework:

1. **Top-of-Funnel (20% of budget):** Brand awareness, reach
   - Display campaigns, YouTube reach
   - Lower intent but wide audience

2. **Middle-of-Funnel (30% of budget):** Demand generation
   - YouTube consideration ads
   - Search broad-match keywords
   - Lookalike audiences

3. **Bottom-of-Funnel (35% of budget):** Demand capture
   - Shopping campaigns
   - Search high-intent keywords
   - Branded search campaigns

4. **Retention (15% of budget):** Post-purchase
   - Remarketing, YouTube retargeting
   - RLSA (Remarketing Lists for Search Ads)
   - Cross-sell campaigns

**Total = coordinated system; no single channel is "the answer"**

[See full-funnel reference guide](./references/google-full-funnel.md) for detailed budget allocation, channel mix, and monthly reporting.

---

## SCALING STRATEGY (GTC - General Testing Campaign)

**GTC Scaling Method:**

**Phase 1 (Week 1-2): Testing**
- Single campaign, all products/keywords
- Daily budget: $50-100
- Bidding: Maximize Clicks
- Goal: Identify winning products/keywords (positive ROAS)
- Data collected: 15-30 conversions expected

**Phase 2 (Week 3-4): Separation**
- Split into two campaigns:
  - Campaign A: Winners only (winners identified from Phase 1)
  - Campaign B: Remaining products/keywords
- Campaign A budget: 60% ($60-150/day)
- Campaign B budget: 40% ($40-100/day)
- Bidding A: Manual CPC (bid higher on winners); Bidding B: Maximize Clicks
- Goal: Scale winners while continuing testing rest

**Phase 3 (Week 5-6): Stratification**
- Create three campaigns:
  - High Performers (Top 20% products): 50% of budget, higher bids
  - Medium Performers (Next 30% products): 30% of budget, medium bids
  - Testing (Remaining 50% products): 20% of budget, lower bids
- Use stratified bidding (highest on High Performers)
- Goal: Accumulate 60-100 conversions to enable smart bidding

**Phase 4 (Week 7+): Smart Bidding**
- If campaign has 60+ conversions: Switch to Target ROAS or Maximize Conversions
- Continue stratification (separate campaigns by performance)
- Scale winners: Increase budget 20% per week (if ROAS maintained)
- Test lookalikes/audiences: Add remarketing layers

---

## NEXT STEPS: DETAILED REFERENCES

Each campaign type has complete setup guides:

1. **[google-shopping-strategy.md](./references/google-shopping-strategy.md)** — Complete Shopping campaign SOP, bidding progression, product optimization

2. **[google-search-strategy.md](./references/google-search-strategy.md)** — Keyword tiers, ad group architecture, Quality Score, match types

3. **[google-pmax-strategy.md](./references/google-pmax-strategy.md)** — Performance Max asset groups, efficiency vs growth campaigns, audience signals, scaling

4. **[google-youtube-strategy.md](./references/google-youtube-strategy.md)** — YouTube 7 must-have ad elements, 8 templates, duration optimization, targeting

5. **[google-full-funnel.md](./references/google-full-funnel.md)** — 4-pillar framework, budget allocation, demand gen vs capture, reporting

6. **[google-scaling-strategy.md](./references/google-scaling-strategy.md)** — GTC scaling phases, standalone campaigns, 20% weekly growth rule, bid management

---

## CRITICAL RULES (Non-Negotiable)

| Rule | Why | Breaking It Causes |
|---|---|---|
| **30-30 Rule** | Need 30 conversions to use smart bidding safely | Volatile bids, wasted budget |
| **Quality Score 7+** | Lower cost per click significantly | 2-4x cost if ignored |
| **Product images lifestyle-focused** | Outperforms white background 99% | Lower CTR, fewer clicks |
| **Title keywords left-justified** | Google reads left-to-right | Lower ranking, fewer impressions |
| **Single product per campaign initially** | Easier to optimize and scale | Confusing performance data |
| **7-day minimum before optimization** | Prevents constant algorithm re-training | Re-entry into learning; wasted budget |
| **Landing page matches ad intent** | Quality Score factor; user experience | High bounce rate, low conversion |

---

## ANTI-PATTERNS (DON'T DO)

| Anti-Pattern | Result | Right Approach |
|---|---|---|
| Start with Target ROAS on new account | Unstable bids; wasted budget | Start Maximize Clicks; migrate to Target ROAS at 30+ conversions |
| Optimize every 2-3 days | Constant re-training; algorithm never learns | Optimize every 7-14 days; give algorithm time |
| Mix unrelated keywords in one ad group | Quality Score drops; higher CPC | 3-5 related keywords per ad group |
| Ignore Quality Score | 2-4x cost per click | Optimize landing page, keywords, ad copy |
| Start Performance Max without historical data | Algorithm has nothing to learn from | Start with Shopping; add PMax after 50+ conversions |
| Use broad match with low budget | Wasted spend on irrelevant clicks | Exact/phrase match initially; broaden after 30+ conversions |
| Don't segment by campaign | Can't identify winners or scalable products | Separate winning products into own campaigns |

---

## For Help With:
- **"Which campaign should I use?"** → See Decision Tree above
- **"Should I use Target ROAS yet?"** → Check 30-30 Rule + Bidding Strategy Progression
- **"Product feed not approving"** → See [google-shopping-strategy.md](./references/google-shopping-strategy.md)
- **"Quality Score is low"** → See Quality Score section above
- **"Should I scale?"** → See [google-scaling-strategy.md](./references/google-scaling-strategy.md)
- **"Multi-channel strategy"** → See [google-full-funnel.md](./references/google-full-funnel.md)
- **"YouTube not working"** → Check [google-youtube-strategy.md](./references/google-youtube-strategy.md) (duration, elements, targeting)
