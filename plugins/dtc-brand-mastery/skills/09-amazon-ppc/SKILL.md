---
name: Amazon PPC & Advertising
description: >
  MANDATORY TRIGGERS: Amazon PPC, Sponsored Products, Sponsored Brands, Sponsored Display,
  Amazon DSP, Amazon advertising, PPC campaign, bid optimization, ACOS, TACOS, PPC budget,
  keyword targeting, product targeting, auto campaign, manual campaign, placement report,
  search term report, PPC ranking, honeymoon period, PPC triangulation, broad match modifier,
  bulksheet, campaign structure, ad spend, Amazon ads, DSP retargeting, display ads,
  PPC billing, credit card stacking, campaign naming convention.
  FOR: Setting up, managing, and optimizing Amazon Sponsored Products, Brands, Display,
  and DSP -- campaign foundation (5 types), campaign naming conventions, keyword research
  methods, bid optimization framework, placement-based optimization, PPC data triangulation,
  broad match modifiers, budget benchmarks, ACOS/TACOS tracking, ChatGPT PPC tools,
  PPC billing hacks, DSP deep dive and funnel strategy, Sponsored Brands/Display
  strategy, and bulksheet operations. Synthesizes Incrementum Digital (full PPC course),
  Brandon Young (triangulation, placement bids), Kevin King (billing hacks, broad match),
  Ritu Java (ChatGPT tools), and Melisa Vong (budget benchmarks).
  Do NOT use for: Amazon listing copy and SEO optimization (use amazon-listing-optimization),
  product research and validation (use product-ideation), launch strategy and reviews
  (use launch-reviews), Facebook/Google/TikTok ads (use paid-ads-mastery plugin or
  tiktok-shop-setup for GMV Max).
---

# Amazon PPC & Advertising

## Quick Navigation
- **Campaign types and structure** -> Foundation section below
- **Bid optimization** -> Optimization section below
- **PPC triangulation** -> Data triangulation section below
- **Campaign templates and naming** -> ref-ppc-campaign-structures.md
- **DSP deep dive** -> DSP section below
- **Credit card stacking and billing** -> ref-ppc-campaign-structures.md

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| Campaign naming convention? Campaign templates? | ref-ppc-campaign-structures.md |
| How do I read placement reports? Decision matrix? | ref-ppc-campaign-structures.md |
| DSP audience types and budget allocation? | ref-ppc-campaign-structures.md |
| Credit card stacking strategy for ad spend? | ref-ppc-campaign-structures.md |
| What reporting tools should I use? SUPA v3.0? | ref-ppc-campaign-structures.md |
| How do I use bulksheets for scale? | ref-ppc-campaign-structures.md |

---

## Cross-References

| Topic | Primary Skill | Go To |
|---|---|---|
| Listing optimization (fix before PPC) | amazon-listing-optimization | `skills/amazon-listing-optimization/SKILL.md` |
| Launch strategy and honeymoon period | launch-reviews | `skills/launch-reviews/SKILL.md` |
| Pricing strategy for Amazon | pricing-finance | `skills/pricing-finance/SKILL.md` |
| TikTok Shop ads (GMV Max) | tiktok-shop-setup | `skills/tiktok-shop-setup/SKILL.md` |
| Facebook/Google ads | paid-ads-mastery plugin | Separate plugin |

---

## Campaign Foundation -- 5 Types (Incrementum Digital)

| # | Campaign Type | Targeting | Purpose |
|---|---|---|---|
| 1 | **Auto Campaigns** | Amazon's algorithmic targeting | Discovery; find converting search terms |
| 2 | **Branded Keyword** | Your own brand terms | Defend brand; capture branded searches |
| 3 | **Branded Product Targeting** | Your own ASINs | Cross-sell within your catalog |
| 4 | **Manual Keyword** | Broad/phrase/exact match | Target specific search queries |
| 5 | **Competitor Targeting** | Competitor ASINs/keywords | Steal market share |

### Campaign Naming Convention
Critical for management at scale. Must be standardized across all campaigns. Format should encode: product, match type, targeting type, and date. Details in ref-ppc-campaign-structures.md.

---

## Keyword Research Methods (Incrementum Digital)

1. **Amazon Suggested Keywords** (autocomplete) -- free, quick baseline
2. **Brand Analytics** -- advanced; requires Brand Registry
3. **Helium 10 Cerebro** -- reverse ASIN lookup on competitors
4. **Helium 10 Black Box** -- competitor product research
5. **Seasonal keyword research** -- anticipate demand shifts
6. **Complementary product research** -- target adjacent categories

### ChatGPT Seed Keyword Generator (Ritu Java)
- Ask ChatGPT for top 10 audiences for your product + what keywords each audience uses
- Plug results into Helium 10 Magnet for search volume validation
- Faster than manual brainstorming; discovers non-obvious keyword angles

---

## PPC Budget Benchmarks (Melisa Vong)

| Stage | Daily Budget | Notes |
|---|---|---|
| Starting out | $5-$15/day | Much lower than Facebook budgets |
| After 10+ reviews | Increase based on performance | Without reviews, PPC is "throwing money into a fire pit" |
| Scaling | Based on ACOS/TACOS targets | Scale profitable campaigns gradually |

---

## Bid Optimization Framework (Incrementum Digital)

### Key Concepts
- **Bid vs. CPC:** Your bid is the MAXIMUM you're willing to pay; CPC is what you actually pay
- **Sales Attribution:** Understand Amazon's attribution window before optimizing
- **Optimization Frequency:** Don't adjust too frequently -- insufficient data leads to overreaction

### Optimization Scenarios
1. **Good performance, high ACOS:** Adjust bids to improve profitability while maintaining volume
2. **Non-converting targets:** Reduce bids or pause; add as negative keywords
3. **Campaigns with placement multipliers:** Requires special optimization approach (see placement section)
4. **Optimization exceptions:** Some situations where standard rules don't apply (new product launch, brand defense)

---

## Placement-Based Bid Optimization (Brandon Young -- BDSS 2025)

### How It Works
Pull placement report showing performance by: Top of Search (TOS), Rest of Search (ROS), Product Detail Pages (PDP).

### Example Data
| Placement | Conversion Rate | CPC |
|---|---|---|
| Top of Search | 17% | $1.72 |
| Rest of Search | 11% | $1.11 |
| Product Detail Pages | 6% | $0.72 |

### Strategy
- Conversion rate is #1 factor for organic ranking
- Low-conversion placements (PDP at 6%) actively HURT organic rank
- **Set base bid low ($0.60) with 300% TOS modifier**, 0% ROS, 0% PDP
- Result: $1.80 effective bid for TOS, $0.60 for ROS/PDP
- **Warning:** Over-reducing can crash impressions. Start at 60% reduction and monitor.

---

## PPC Data Triangulation (Brandon Young -- BDSS 2025)

**Do NOT optimize on ACOS/TACOS alone.** Triangulate three data points per keyword:

1. **Impression rank** -- how many competitors have more impressions than you
2. **Conversion rate** -- on that specific keyword
3. **Organic rank** -- your organic position for that keyword

### Decision Matrix

| Scenario | Impression Rank | Conversion | Organic Rank | Action |
|---|---|---|---|---|
| A: Room to grow | Low (#6) | Good (25%) | Low (#17) | **SPEND MORE** -- room to push organic rank up |
| B: Cannibalizing organic | Low (#7) | Decent | High (#2) | **REDUCE SPEND** -- ads are eating organic sales |
| C: Not indexed | N/A | N/A | 101+ | Fix listing relevancy first |
| D: Amazon uncertain | N/A | N/A | 35-55 | Keywords too broad or match type wrong |

**Optimizing only for ACOS/TACOS is a "short-term win" that can hurt long-term keyword rankings.**

---

## Broad Match Modifiers (Kevin King)

- Add **+** sign before each word in broad match campaigns to force word inclusion
- Example: **+basketball +shoes** forces both words present in any matched query
- Without modifier, Amazon may show ad for "sneakers" or "running shoes"
- Eliminates wasteful spend on irrelevant synonym matches

---

## ACOS / TACOS Tracking

- **ACOS** = Ad Spend / Ad Revenue x 100 (per campaign)
- **TACOS** = Total Ad Spend / Total Revenue x 100 (account-wide)
- TACOS is the better health metric -- captures halo effect of PPC on organic sales
- Correlation: extra ranking budget increases TACOS temporarily but should decrease it long-term as organic rank improves

---

## Amazon DSP (Demand Side Platform) Deep Dive

### What DSP Is (Incrementum Digital)
- Display and video ads appearing BOTH on and off Amazon
- Two creative types: lifestyle images OR dynamic e-commerce (auto-updates price/reviews)
- Attribution includes both clicks AND views (unlike Sponsored Ads = clicks only)

### DSP vs. Sponsored Ads

| Feature | Sponsored Ads | DSP |
|---|---|---|
| Placement | On Amazon only | On AND off Amazon |
| Attribution | Click-based | Click + view-based |
| Audience targeting | Keyword/ASIN-based | Behavioral + keyword/ASIN |
| Audience layering | Not available | Cross-layer (e.g., "parents" + "keto") |
| Access | Self-service | Agency or Amazon direct |

### DSP Funnel Strategy

| Stage | Targeting | Budget % | Expected ROAS |
|---|---|---|---|
| Top (Awareness) | Amazon lifestyle/in-market audiences, OTT/streaming | 20% | Lowest |
| Middle (Consideration) | Competitor ASIN viewers/purchasers, cross-selling | 20% | Medium |
| Bottom (Purchase/Retention) | Retargeting non-purchasers, retention for past buyers | 60% | Highest |

### DSP Cannibalization Warning
Bottom-of-funnel retargeting ROAS is INFLATED. Someone who sees a retargeting ad and then buys may have purchased anyway. A reported 10x ROAS might truly be 4-5x ROAS. View-through attribution steals credit from organic sales.

The reverse also happens: someone sees DSP ad, searches brand, clicks Sponsored Product, and attribution goes to SP not DSP.

### Who Should Use DSP
- Spending $25K-$50K+/month on Amazon search ads already
- Consumable products (high LTV; retention marketing works well)
- High-price products >$100-$200 (longer research cycle = retargeting valuable)

**Who should NOT:**
- Ad spend under $25K/month (focus on Sponsored Ads first)
- Low-price impulse purchases ($10 products)
- Brands without maxed-out Sponsored Ads potential

**Note:** Amazon actively sells DSP to brands who aren't ready for it. Evaluate critically.

---

## Sponsored Brands Strategy (Incrementum Digital)

### Three Ad Formats
1. **Product Collection** -- showcase multiple products in one ad
2. **Store Spotlight** -- drive traffic to Brand Store pages
3. **Video Ads** -- video creative in search results

### Key Considerations
- Broad Match behaves differently in Sponsored Brands vs. Sponsored Products
- Headline copy optimization is critical (character-limited)
- Custom images often outperform product-only images
- Product selection strategy: feature best-sellers or newest launches

---

## Sponsored Display Strategy (Incrementum Digital)

### Two Targeting Types
1. **Contextual Targeting** -- target based on product/category
   - Branded strategy (defend your own listings)
   - Competitor targeting strategy
2. **Audience Targeting** -- target based on shopper behavior

### VCPM & Cannibalization Warning
- View-cost-per-mille (VCPM) means you pay for impressions
- Risk of paying for impressions that would have converted organically
- Monitor for cannibalization between Sponsored Display and organic sales

---

## PPC Ranking Strategy for New Products (Incrementum Digital)

1. **Ranking Matrix** -- framework for selecting which keywords to rank for
2. **Honeymoon Period** -- leverage Amazon's new product boost window
3. **PPC Budget Calculation** -- formula for determining launch ad spend
4. **Keyword Selection** -- target keywords where you can realistically compete
5. **Category Conversion Rate Estimation** -- benchmark expected performance
6. **Phased Timeline** -- aggressive during honeymoon, optimize after

---

## "Sale Before the Sale" Strategy (Travis Ziegler -- BDSS 8)

Run your biggest discount BEFORE Prime Day, not on Prime Day:
1. Two weeks before Prime Day: run 30% off sale
2. Competitors are pulling back on PPC pre-Prime Day
3. Increase YOUR PPC while competitors decrease theirs = cheaper clicks
4. Higher conversion from discount = boost keyword rankings
5. On Prime Day: switch to smaller 5-10% coupon
6. Result: higher organic rankings + massive Prime Day traffic = more profit with less discount

---

## Instructor Disagreements

### ACOS vs. Triangulation
- **Melisa Vong / most sellers:** Optimize primarily on ACOS and TACOS metrics
- **Brandon Young:** ACOS/TACOS alone is misleading; must triangulate impression rank, conversion rate, and organic rank
- **RESOLUTION:** Start with ACOS/TACOS for basic health monitoring. As you mature, adopt Brandon Young's triangulation method for strategic keyword decisions. Both approaches are valid at different stages.

### When to Start DSP
- **Amazon (sales team):** Often pushes DSP on brands spending $10K+/month
- **Incrementum Digital:** Don't start DSP until $25K-$50K+/month in search ads and only after maxing out Sponsored Ads potential
- **RESOLUTION:** Follow Incrementum's guidance. Amazon's sales team is incentivized to sell DSP. Most brands should exhaust Sponsored Ads first.

---

## Anti-Patterns
- Launching PPC before listing is optimized (fix conversion rate first)
- Launching PPC with fewer than 10 reviews ("throwing money into a fire pit")
- Optimizing only on ACOS without considering organic rank impact
- Over-reducing placement bids (crashes impressions; start at 60% reduction)
- Running multiple products in one campaign without data to justify it
- Starting DSP before maxing out Sponsored Products/Brands
- Using default $500 billing threshold instead of requesting $10K increase
- Not using broad match modifiers (wastes spend on irrelevant synonyms)
