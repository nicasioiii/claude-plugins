---
title: Google Shopping Campaign Optimization
skill: optimize-google
usage: Load when user asks about Shopping campaign performance, needs product-level or keyword-level optimization, asks about Shopping CTR targets, or needs feed optimization guidance.
---

# Google Shopping Campaign Optimization

## Core Rule: Optimize Every 7-14 Days ONLY

This is non-negotiable. More frequent changes restart the campaign learning phase.

### Post-Optimization Expectations
- Results WILL tank for 2-3 days after any optimization
- This is normal -- the algorithm needs time to re-learn
- Do NOT make additional changes during this recovery period
- Evaluate the optimization impact using the NEXT 7-14 day window

---

## Product Optimization -- Step 1: Rank by Cost

### Setup Filters
- Impressions >= 500
- Product Status = Ready to Serve

### Exclusion Criteria
Go through the entire product list, highest spend first:

| Spend Level | Sales | Action |
|---|---|---|
| 1.5x profit margin | Zero sales | Exclude (conservative) |
| 2x profit margin | Zero sales | Exclude (moderate) |
| 3x profit margin | Zero sales | Exclude (aggressive) |
| Any spend | Has sales (profitable) | DO NOT TOUCH |

**Example:** $30 profit margin product:
- Conservative: exclude after $45 spent with zero sales
- Moderate: exclude after $60 spent with zero sales
- Aggressive: exclude after $90 spent with zero sales

### Product Exclusion Process
1. Sort all products by spend (highest first)
2. Check each product against exclusion criteria
3. Exclude products that meet criteria
4. Move to Step 2

---

## Product Optimization -- Step 2: Rank by Low CTR

### Zero Clicks + 500+ Impressions = EXCLUDE Immediately
- After 500 eyeballs and zero clicks, product is dragging down campaign CTR
- These products tank quality score, which increases CPC across the entire campaign

### CTR Tiers and Actions

| CTR | Sales | Action |
|---|---|---|
| 0% (zero clicks, 500+ impressions) | Zero | **EXCLUDE immediately** |
| Below 0.10% | Zero | **EXCLUDE** (or fix -- see below) |
| 0.10% - 0.25% | Zero | **Orange zone** -- try fixing first |
| 0.25%+ | Zero | Monitor; not a CTR problem, may be pricing/LP issue |
| Any CTR | Has sales | **DO NOT CHANGE ANYTHING** -- sales trump CTR always |

### How to Fix Orange Zone Products (0.10-0.25% CTR)
Try these changes ONE AT A TIME, waiting 7-14 days between each:
1. **Change image** (most likely cause of low CTR) -- wait 7-14 days
2. **Change pricing** (lower it) -- wait 7-14 days
3. **Change SEO keywords/title** -- wait 7-14 days
4. If nothing works after 3 cycles --> exclude

### Image Strategy for CTR Improvement
**Rule: Do the OPPOSITE of competitors.**
- If most competitors show white background images, use lifestyle
- If most competitors show lifestyle images, use white background
- Count top 5-10 listings; whichever image type has fewer = YOUR type
- Find a unique product variant (different color, size, style) for visual standout

---

## Campaign CTR Target

**Overall campaign CTR target: 1% or above.**

| Campaign CTR | Status | Action |
|---|---|---|
| 1%+ | Healthy | Continue optimizing normally |
| 0.75-1% | Warning | Identify and fix low-CTR products dragging average down |
| Below 0.75% | Critical | Aggressive product exclusion + image/title optimization |

Below 1% triggers a quality score degradation spiral:
- Lower quality score -> higher CPC -> less competitive bids -> worse ad positions -> lower CTR -> even lower quality score

---

## Keyword/Search Term Optimization

### Setup Filters
- Impressions >= 300
- Added/Excluded = None (only look at new/unmanaged terms)

### Process
1. **Rank by cost** -- exclude keywords that spent 1.5x-3x profit margin with zero sales
2. **Aggressive method:** Exclude any keyword that spent $20+ without a sale (regardless of profit margin)
3. Note: one product can trigger hundreds of search terms -- you do not have budget to test them all

### Search Term Categories to Exclude
- Branded terms for competitors (unless intentional competitor targeting)
- Informational queries ("how to," "what is," "reviews of")
- Extremely broad category terms (single-word queries like "shoes" or "jacket")
- Terms with high spend and zero conversions after adequate testing period

---

## Feed Optimization

### Prerequisites Before Feed Optimization
- Minimum $1,000 in total ad spend for the campaign
- Products with 3+ sales consistently
- Sufficient search term data to identify winning keywords

### Feed Optimization Process
1. **Rank search terms by conversions** (all-time data)
2. Identify keywords with most sales at lowest cost per conversion
3. Identify keywords spending most money while remaining profitable

### Shopify Product Page Optimization (4 Key Fields)
1. **Product Type** -- set to keyword with most sales or most impressions
2. **Vendor** -- set to your store name
3. **Collection** -- ensure product is in correct collection
4. **Tags** -- insert ALL profitable keywords as tags (comma-separated)
   - Include keywords with 3+ sales
   - Also include keywords with fewer sales but still profitable
   - Google's algorithm crawls tags and assigns ranking authority

### Feed App Optimization
- Update product title in feed app to match SEO-optimized title
- Update product description to include winning keywords
- Set custom labels: "winner" vs. "testing" vs. "exclude"

---

## Title Optimization (Most Important Feed Change)

### Title Importance
- Image: 50% of Shopping success
- Title: 45% of Shopping success
- Description: 5% of Shopping success

### Title Testing Method
1. Create new item ID in manual feed with new title
2. Keep original title intact on the original item ID
3. Run both simultaneously and compare CTR and conversion performance
4. Once winning title found, update the item ID with the most conversion history

### Title Rules
- Front-load keywords (Google weights words at the beginning more heavily)
- 150 characters max, but only 50-70 show in the Shopping ad
- Include: brand, color, size, gender, product type
- Do NOT include: promotions, "best," extra non-specific qualifiers
- Google reads titles LEFT to RIGHT -- put most important keywords first

---

## Bidding Strategy for Shopping

### Progression
1. **Start:** Maximize Clicks with max CPC bid limit ($0.40-$0.50 sweet spot)
2. **Low-bid campaign:** Same setup but $0.10 max CPC (often surprisingly profitable)
3. **After 30 conversions in 30 days:** Switch to Target ROAS
4. Set initial ROAS target at current performance level, then optimize gradually

### Bid Adjustment Rules
- Struggling for traffic: increase bid limit by $0.05-$0.10
- High traffic, no conversions: lower bids, tighten product categories, add title descriptors
- Remember: higher bids do not rank higher -- they open up broader search queries

---

## Shopping Campaign Scaling Indicators

### Ready to Scale When:
- Campaign CTR consistently above 1%
- Multiple products with 3+ sales each
- ROAS above break-even for 14+ consecutive days
- Search terms data shows clear winning keyword patterns

### Scaling Methods
1. **Standalone campaign:** Pull winning products into dedicated campaign with higher budget
2. **Budget increase:** 10-20% budget increase per week on profitable campaigns
3. **Bid increase:** Raise max CPC by $0.05-$0.10 to access broader search queries
4. **Feed expansion:** Add winning keyword variations to titles and tags
