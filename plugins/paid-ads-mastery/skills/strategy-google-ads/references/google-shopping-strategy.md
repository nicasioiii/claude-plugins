# Google Shopping Campaign Strategy

## Overview
- **Best For:** E-commerce with product catalogs
- **Data Timeline:** 4-6 weeks to profitability (faster than Search)
- **Minimum Products:** 20-25 active products needed to start
- **Budget:** $200-500/day recommended starting point
- **Expected ROAS:** 3.0-4.0+ (higher than Search due to high intent)

---

## PRE-LAUNCH CHECKLIST

Before creating first Shopping campaign:

- [ ] **Merchant Center Account:** Set up and linked to Google Ads account
- [ ] **Product Feed:** Uploaded with at least 20-25 products
- [ ] **Products Approved:** All in "Approved" status (check Product Status tab)
- [ ] **Product Data Quality:**
  - [ ] Title: 50+ characters, keyword-rich
  - [ ] Image: High-quality, lifestyle preferred over white background
  - [ ] Price: Competitive, not 50% off everything
  - [ ] Description: 50-200 words, original (not copy-pasted from suppliers)
- [ ] **Google Ads Account:** Conversion tracking set up (GA4 or Google Ads conversion pixel)
- [ ] **Landing Pages:** Product pages load in <2 seconds, mobile responsive

---

## CAMPAIGN STRUCTURE: HIGH BID vs LOW BID

### Recommended Setup for Testing Phase

**Campaign 1: [GTC High Bid] - Testing Phase**
- Budget: $200-300/day
- Bidding: Maximize Clicks initially, then Manual CPC
- Bid Amount: $0.40-0.60 per product (higher, conservative testing)
- Products: 15-20 of your best-performing products from history
- Duration: 2-3 weeks (to accumulate 30 conversions)
- Goal: Identify products that convert well at higher bids

**Campaign 2: [GTC Low Bid] - Alternative Testing**
- Budget: $100-150/day
- Bidding: Maximize Clicks initially, then Manual CPC
- Bid Amount: $0.20-0.30 per product (lower, aggressive testing)
- Products: Different 15-20 products (or subset you're unsure about)
- Duration: 2-3 weeks
- Goal: Find products that convert at lower costs

**Why split:** Different products may have different bid-to-conversion ratios. Testing both speeds up learning.

### Campaign Naming Convention
```
[GTC High Bid] - [Category] - [Start Date]
Example: [GTC High Bid] - Apparel - 03-06-2026

[GTC Low Bid] - [Category] - [Start Date]
Example: [GTC Low Bid] - Apparel - 03-06-2026
```

---

## BIDDING STRATEGY PROGRESSION

### Phase 1: Learning (Week 1-2)

**Setup:**
- Bidding Type: Maximize Clicks
- Max CPC Bid: $0.40-0.60 (High Bid campaign)
- Max CPC Bid: $0.20-0.30 (Low Bid campaign)

**What happens:**
- Google finds cheapest clicks possible within your bid limit
- Accumulates 10-30 clicks per day (adjust budget if lower)
- You're not optimizing for conversions yet; just building data

**Monitoring:**
- [ ] Check daily spend (should be close to budget)
- [ ] Check click volume (should see 20+ clicks per day at $200/day budget)
- [ ] Monitor which products get impressions
- [ ] Watch for products with $0 spend (may not be compatible with Ads)

**Decision point (end of Week 2):**
- If seeing conversions: Continue to Phase 2
- If zero conversions: Check product feed quality or landing page
- If clicks too low: Increase bid amount ($0.60 → $0.80)

### Phase 2: Initial Optimization (Week 3-4)

**When to switch:** After 15-30 clicks, see which products get clicks and look at early conversion signals

**Setup:**
- Bidding Type: Manual CPC (or ECPC if you have 5+ conversions)
- Bid strategy: Adjust bids by product performance

**Manual CPC Approach:**
```
Product Status | Bid Adjustment | Why
---|---|---
High CTR, conversions | +15-20% ($0.46 → $0.55) | Increase investment in winners
Medium CTR, 0 conversions | Hold bid | Wait for conversion data
Low CTR, 0 conversions | -20% ($0.40 → $0.32) | Reduce waste on clickers that don't convert
Zero impressions | +25-30% ($0.40 → $0.52) | Bid higher to get impressions
```

**Timeline:**
- Run 7 days with new bids
- Accumulate another 15-20 conversions (total 30+ across both campaigns)
- Identify products with clear positive ROAS

**Decision point (end of Week 4):**
- Have 30+ conversions total?
  - Yes: Go to Phase 3
  - No: Increase budget 25% or adjust bids upward

### Phase 3: Smart Bidding (Week 5+)

**When to switch:** After 30-50 conversions and 3+ weeks of data

**Bidding Type Options:**

**Option A: Enhanced CPC (ECPC) - Safer**
- You set base bid (e.g., $0.50)
- Google automatically increases/decreases bids based on likelihood to convert
- Keeps you somewhat in control
- Good transition from manual to smart bidding
- Expected result: CPC stays similar, conversion rate improves

**Option B: Target ROAS - Aggressive**
- Set target ROAS (e.g., 3.0)
- Google optimizes bids to hit your profitability goal
- Requires clear ROAS data (thus 50+ conversions needed)
- Less control; algorithm fully takes over
- Expected result: More stable ROAS; volume varies based on algorithm

**Option C: Maximize Conversions - Volume Play**
- Google spends full budget on maximum conversions possible
- Only use if profit margin is good (low worry about CPA)
- Best for high-AOV products with healthy margins
- Expected result: Highest volume; lowest cost-per-conversion

**Recommendation for beginners:** Use ECPC (middle ground). Switch to Target ROAS only after you've proven 60+ conversions with consistent ROAS.

---

## MANUAL CPC OPTIMIZATION PROCESS

### Weekly Optimization Routine (Every 7-14 days)

**Step 1: Filter Data**
- Set date range: Last 7-14 days
- Filter: Impressions ≥ 500 (eliminates noise from low-impression products)
- Product Status = "Ready to serve" (exclude disapproved products)

**Step 2: Rank by Cost**
- Sort by "Spend" (highest to lowest)
- Identify top 10 products by spend
- These get most of your budget; focus optimization here

**Step 3: Evaluate Each Product**

| Metric | Decision |
|--------|----------|
| **CPA > Profit Margin × 3** | Exclude this product; it's too expensive |
| **CPA between 1.5-3x profit margin** | Keep; may become profitable at scale; don't bid higher |
| **CPA < 1.5x profit margin** | Winner; increase bid +10-20% |
| **Zero conversions but clicks** | Either: (1) Increase bid to improve placement, or (2) Exclude if product just bad fit |

**Example:**
```
Product: Hiking Boots, Profit Margin: $35

Metrics this week:
- Clicks: 45
- Conversions: 3
- Spend: $45
- CPA: $45 ÷ 3 = $15

Decision:
- CPA $15 < Profit margin $35? Yes ✓
- CPA as % of margin: $15 ÷ $35 = 43% (excellent)
- Action: Increase bid from $0.35 → $0.40 (15% increase)
```

**Step 4: Execute Changes**
- Apply bid adjustments
- Exclude underperforming products (optional; can just reduce bid to $0.05)
- Save changes

**Step 5: Monitor**
- Wait 3-7 days for algorithm to stabilize with new bids
- Don't optimize again until 7-14 days pass (prevents constant re-training)

### Exclusion Strategy

**When to exclude a product:**
```
CPA > 3x Profit Margin AND
No other redeeming factor (brand awareness, etc.)
THEN Exclude
```

**How to exclude:**
- Product-level: In Merchant Center, mark as "inactive"
- Campaign-level: In Google Ads, go to Shopping campaigns, click product → exclude

**Effect:** Google stops showing ads for that product; budget redistributes to remaining products.

---

## PRODUCT OPTIMIZATION FOR GOOGLE SHOPPING

### Product Title Optimization

**Formula:** [Primary Keyword] + [Variant] + [Brand] = 50-80 characters max

**Example (Colorblind Glasses):**
```
❌ Bad: "Colorblind Test Glasses for Men Women Cheap"
Why: Keyword stuffing; reads poorly; "cheap" reduces perceived value

✓ Good: "Colorblind Corrective Glasses | Premium Color Vision Test Eyewear"
Why: Primary keyword left-justified; includes variant; quality signal
```

**Rules:**
- Most important keyword first (left-justified)
- Secondary keyword in middle (e.g., variant: "men", "women", "professional")
- Brand/quality signal at end
- Don't repeat keywords
- Don't use ALL CAPS (reduces CTR; bad formatting)
- Include top 2-3 keywords naturally

### Product Images

**Critical rule: Lifestyle images beat white background 99% of the time**

**Image hierarchy (order of importance):**
1. Lifestyle image (person using product; 50% impact) ← MOST IMPORTANT
2. Multiple angles (product detail shots; 30% impact)
3. Product in context (e.g., fitted on body; 15% impact)
4. White background (last resort; 5% impact)

**Examples that work:**
- Hiking boots: Person on trail in boots + close-up sole detail
- Phone case: Phone in case on desk + corner detail shot
- Yoga mat: Person doing yoga on mat + material close-up

**Examples that fail:**
- Hiking boots: Just boots on white background
- Phone case: Just case on white background
- Yoga mat: Just mat on white background (no context)

**Image specs:**
- Minimum 3-5 images per product (lifestyle is one; angles are others)
- High resolution (1000x1000 minimum; 3000x3000 ideal)
- No watermarks or logos overlaid
- Lightning: Natural or professional (avoid shadows on product)

### Product Pricing Strategy

**Rule: Don't set 50% off for every product**

Consumers become suspicious when:
- Everything is "on sale"
- Prices seem artificially high then discounted
- Competitors selling at lower baseline

**Right approach:**
1. Price products fairly vs. your sourcing cost + healthy margin
2. Use discount sparingly (peak seasons, slow-moving inventory)
3. Don't use "compare-at" prices initially (Google flags as suspicious)

**Price validation:**
- Check: Are 20+ competitors selling at this price point?
  - Yes: Your price is good ✓
  - No: Either you're overpriced or in a niche market (OK either way)

### Product Descriptions

**Length:** 100-200 words (Google reads descriptions; don't over-stuff)

**Structure:**
```
Sentence 1: Problem/benefit statement
Sentence 2-3: Key features (2-3 main features)
Sentence 4-5: Differentiation (why yours is better)
Sentence 6: Call-to-action or guarantee

Example (Hiking Boots):
"Lightweight hiking boots built for comfort on long trails. Features waterproof membrane,
cushioned sole, and ankle support. Made from durable leather with reinforced toe box.
30-day money-back guarantee. Ships within 24 hours."
```

**Do:**
- ✓ Use natural language (people-readable)
- ✓ Include top keyword once or twice naturally
- ✓ Mention unique selling points
- ✓ Use bullets for features (easier to scan)

**Don't:**
- ✗ Copy from AliExpress/eBay/manufacturer (Google detects duplication)
- ✗ Keyword stuff ("Hiking boots hiking boots hiking boots hiking...")
- ✗ Use manufacturer generic copy (shows zero effort)

---

## CAMPAIGN MONITORING & METRICS

### Daily Checklist
- [ ] Campaign spend (on track for daily budget?)
- [ ] Conversion count (should see 5-15/day if $300/day spend)
- [ ] Overall ROAS (target 3.0+; if below 2.0, something wrong)

### Weekly Analysis
- [ ] Rank products by spend (which get most budget?)
- [ ] Rank products by ROAS (which are most efficient?)
- [ ] Identify top 10 "winners" (20% of products generating 80% of sales)
- [ ] Check for "zombies" (products with $0 spend for 7+ days)
- [ ] Plan bid adjustments (increase winners, exclude losers)

### ROAS Target
- **Minimum viable:** 3.0 ROAS (3x return on ad spend)
- **Good:** 4.0-6.0 ROAS
- **Excellent:** 7.0+ ROAS
- **Below 2.0:** Likely not profitable; audit product feed or landing pages

---

## TROUBLESHOOTING

### Problem: Zero impressions for products
**Diagnosis:** Products either not in feed or have low quality scores
**Solution:**
1. Check Merchant Center product status (should be "Approved")
2. Verify products are in campaign's product selection (if using filters)
3. Increase bid for affected products ($0.20 → $0.40)
4. Check: Is product title relevant to any keywords?

### Problem: High clicks, zero conversions
**Diagnosis:** Landing page issue (product page doesn't match ad intent)
**Solution:**
1. Check landing page loads fast (<2 seconds)
2. Verify product page content matches product description
3. Check: Are forms/checkout pages mobile responsive?
4. Test: Can you buy the product yourself on mobile?

### Problem: Campaign spending full budget but low ROAS
**Diagnosis:** Budget's spread too thin across low-quality products
**Solution:**
1. Exclude bottom 20% products (lowest ROAS)
2. Concentrate budget on top performers (highest ROAS)
3. Reduce bids on mid-tier products
4. Quality Score may be low; improve product images/titles

### Problem: ROAS was 4.0, now 2.5
**Diagnosis:** Either audience saturation OR product feed quality issue
**Solution:**
1. Check: Did you add new low-quality products? If yes, exclude them.
2. Check: Has stock quality decreased (cheaper sourcing)? If yes, update product images/descriptions.
3. Check: Is this a seasonal dip? (Some products have seasons)
4. If still stuck: Pause campaign for 2 days; algorithm reset often helps

---

## SCALING STRATEGY

**Once campaign reaches ROAS 3.0+:**

### Scaling Method 1: Budget Increase (Conservative)
```
Week 1: $300/day ROAS 3.2
Week 2: $350/day (17% increase) ROAS target: 3.0+
Week 3: $400/day (14% increase) ROAS target: 2.8+
Week 4: $450/day (12% increase) ROAS target: 2.6+
```

Stop increasing when ROAS drops below 2.5 (saturation reached).

### Scaling Method 2: Campaign Duplication (Recommended)
```
Campaign A (Original): $300/day, ROAS 3.2
Campaign B (Duplicate): $300/day (same products, fresh learning phase)
Campaign C (New products): $200/day (test different product set)
Total: $800/day

Each campaign optimizes independently; if one saturates, others continue growing.
```

**Why duplication works:**
- Each campaign finds independent optimization path
- Less cannibalization than single large campaign
- Risk diversification

---

## KEY TAKEAWAYS

1. **High Bid vs Low Bid structure** helps identify optimal price points
2. **Maximize Clicks first (week 1-2)** builds conversion data
3. **Switch to Manual CPC (week 3-4)** when you have 15-30 conversions
4. **Optimize every 7-14 days**, not daily (prevents algorithm re-training)
5. **Lifestyle images > white background** 99% of the time
6. **Exclude products with CPA > 3x profit margin** after 3+ weeks
7. **Quality Score 7+ essential** to keep CPC low
8. **ROAS 3.0+ is success**; below 2.0 = audit the feed
9. **Don't over-optimize products**; let algorithm learn (7-day minimum)
10. **Scale via duplication** (multiple campaigns) rather than single large campaign
