---
title: Performance Max Optimization
skill: optimize-google
usage: Load when user asks about PMax campaign performance, needs optimization levers, asks about asset performance analysis, brand exclusion, PMax scaling, or the Fire & Ice structure for lead gen.
---

# Performance Max (PMax) Optimization

## The Reality of PMax Optimization

PMax is easy to set up and incredibly hard to optimize. It is a black box that runs across ALL Google properties (Search, Shopping, Video, Display, Discovery, Gmail, Maps). The key to PMax optimization is mastering the levers you CAN control.

---

## The 10 Optimization Levers

### 1. Negative Keyword Optimization
- Now available directly in PMax (previously required Google rep)
- Review search terms (accessible via Insights tab) and exclude irrelevant queries
- Especially important to exclude branded terms if running separate brand campaigns

### 2. Offer Optimization
- PMax amplifies your offer -- if the offer is weak, PMax cannot fix it
- Test different offers (bundles, discounts, free shipping thresholds) and measure impact
- Creative assets are only as strong as the underlying offer

### 3. Bid/Budget Adjustments
- Lower ROAS target or raise CPA target = more traffic (growth mode)
- Raise ROAS target or lower CPA target = more efficiency (profitability mode)
- Follow the 20% rule: max 10% adjustments, 1-2x per week
- Allow 2-6 weeks for learning after any change (smaller budgets = longer learning)

### 4. Final URL Expansion
- ON: Google sends traffic to any page it deems relevant (including blog posts, about pages)
- OFF: Traffic only goes to URLs you specify
- Recommendation: Turn OFF if you want to control landing pages precisely
- Use page feeds to whitelist specific landing pages when Final URL Expansion is ON

### 5. Asset Optimization (Performance Quadrants)

| | High Impression Share | Low Impression Share |
|---|---|---|
| **High Conversion Rate** | **Winners** -- scale these, keep them running | **Hidden Gems** -- increase exposure, they deserve more impressions |
| **Low Conversion Rate** | **Silent Killers** -- REMOVE FIRST! Actively hurting performance | **Underperformers** -- replace with new tests |

**Priority: Remove Silent Killers before adding new assets.** These are assets Google shows frequently that do not convert -- they waste budget and train the algorithm on bad signals.

### 6. Product Feed Optimization
- Same principles as Shopping optimization (see ref-google-shopping-optimization.md)
- Product titles are the #1 optimization lever for PMax Shopping placements
- Test titles by creating new item IDs with new titles (keep original intact)

### 7. Audience Signal / Search Theme Optimization
- Audience signals guide PMax's initial targeting but are NOT hard targeting
- Best signals: past purchasers email list + all converters/purchasers from GA4 and Google Ads
- Adding bottom-of-funnel audiences helps smart bidding build better converter avatars
- Search themes: add the keywords you want PMax to prioritize for Search placements

### 8. Value Rules Optimization
- Apply multipliers to conversions from specific audiences, devices, or locations
- Example: Conversions from California are worth 1.5x more than other states
- Helps smart bidding prioritize higher-value conversions

### 9. New Customer Acquisition Goals
- Default: bid equally for new and returning customers
- New Customer Only Mode: bids only on new customers (best for growth campaigns)
- Caution: if new customer goal cannot be met, PMax WILL bid on returning customers anyway
- New Customer Value Mode: bids higher on new, still bids on returning (rarely recommended)

### 10. Hidden Insights via Scripts
- No native asset group reporting in Google Ads
- **Mike Rhodes Asset Group Reporting Script:** creates Google Sheet with channels per asset group, impressions, and detailed performance data
- Must-have for any serious PMax operation
- Also available: channel distribution scripts that show where PMax is actually spending

---

## Brand Exclusion in PMax

### Why It Is Critical
- Brand traffic inflates PMax ROAS, masking actual non-brand performance
- A PMax campaign showing 800% ROAS might be 200% non-brand and 2000% brand
- Without brand exclusion, you cannot evaluate true prospecting performance

### How to Implement
1. Create a brand exclusion list in PMax campaign settings
2. Set up a separate branded search campaign as a fallback
3. Use scripts to auto-exclude branded terms from PMax Shopping if needed
4. Monitor PMax search terms regularly for brand query leakage

---

## PMax Budget and Learning Phase

### Minimum Budget
- **$100/day per PMax campaign** for it to be effective
- Campaigns need substantial conversion data for smart bidding to work
- Cannot meaningfully optimize until 30 conversions in 30 days

### Learning Phase
- 2-6 weeks after launch (DO NOT make changes during this time)
- Smaller budgets = longer learning period
- May not see impressions for first few days (this is normal)
- Any significant change (budget, bid target, asset group changes) restarts learning

---

## Two PMax Strategy Types

### 1. Efficiency-Focused (Primary)
- Lean into Google Shopping
- Bidding: Max Conversion Value --> Target ROAS
- Expect 75-100% of spend/conversions from Shopping placements
- Highest ROAS
- Best for: accounts focused on profitability

### 2. Growth-Focused
- New customer acquisition priority
- Bidding: Max Conversions --> Target CPA
- Target CPA pushes spend into YouTube, Display, Discovery (beyond Shopping)
- Include only top/introductory products to limit Shopping and push into other channels
- Use "New Customer Only" mode
- Best for: accounts focused on growth and customer acquisition

---

## Fire & Ice Structure (Lead Gen PMax)

Standard PMax for lead gen has 3 problems:
1. Pushes same assets to all networks
2. Optimizes for same conversion goal across all networks
3. Cannot control bids/budgets per network

### Solution: Two-Campaign Structure

**FIRE Campaign (Hot / Bottom of Funnel)**
- Search-heavy asset groups
- Direct CTAs: book demo, get quote, request consultation
- Optimize for macro conversions (form fills, calls, demo bookings)
- Bid aggressively for high-intent traffic

**ICE Campaign (Cold / Top of Funnel)**
- Prospecting via Display, YouTube, Discovery
- Soft CTAs: download white paper, get checklist, free infographic
- Optimize for micro conversions (content downloads, email signups)
- Lower bids, broader reach

**Key Principle:** Match offer to channel temperature. Hot CTAs on cold channels will fail.

---

## Performance-Based Segmentation (Labelizer)

### How It Works
Tools automatically label products based on performance data:

| Label | Definition | Strategy |
|---|---|---|
| **Heroes** | Top performers by revenue/ROAS | Bid aggressively, maximize exposure |
| **Sidekicks** | Decent performers, consistent | Maintain, steady budget |
| **Villains** | Poor performers, waste budget | Reduce bids or exclude |
| **Zombies** | Zero or minimal data | Test carefully with controlled budget |

### Tools for Labelizer
- Producthero
- ProfitMetrics Shopping Booster
- Channable
- Flowboost

### Application to PMax
- Use custom labels in product feed to segment by performance
- Create separate PMax campaigns for Heroes vs. Zombies
- Bid more aggressively on Hero products, cautiously on Zombies

---

## PMax Scaling Decision Framework

### 14-Day ROAS Check
| 14-Day ROAS vs. Target | Action |
|---|---|
| Above target by 20%+ | Scale: increase budget 10-20% per week |
| At target (within 10%) | Hold: maintain current settings |
| Below target by 10-20% | Optimize: check assets, search terms, feed quality |
| Below target by 20%+ | Diagnose: may need structural changes or offer improvement |

### Scaling Methods for PMax
1. **Budget increase:** 10-20% per week on profitable campaigns
2. **Lower Target ROAS:** Allows algorithm to find more conversions (less efficient but more volume)
3. **Add new campaigns:** Segment by product category with dedicated budgets
4. **Improve feed quality:** Better titles, images, descriptions = more Shopping impressions
