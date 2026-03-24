# Retargeting Strategy & Audience Tiers

## Core Retargeting Principle

**Rule:** Retargeting budget should be 15-30% of total ad spend, not supplementary.
- Reason: Retargeting converts 3-5x higher than cold prospecting
- Safety: Never let retargeting audience run dry (refresh pixel data continuously)

---

## Audience Tier Hierarchy & Budget Allocation

### Tier 1: Hottest Audience (20-25% of budget)

**Audience Definition:** People who initiated checkout in last 3-7 days

**Meta Pixel Events to Target:**
- InitiateCheckout (highest priority)
- AddPaymentInfo (alternative)

**Google Audiences:**
- All users who visited checkout page in last 7 days

**Budget Allocation:** 20-25% of total spend
**ROAS Target:** 3.0-4.0x (hottest, most likely to buy)
**Frequency Cap:** 1x per day (don't overwhelm)
**Creative Strategy:** Urgency + CTA-focused
- "Complete your purchase"
- "Your cart is waiting"
- Guarantee/money-back messaging
- Scarcity angle ("Only 2 left in stock")

**CPA Target:** 50-60% of cold traffic CPA
**Timeline:** Keep active 7-14 days post-checkout initiation

---

### Tier 2: Warm Audience (25-30% of budget)

**Audience Definition:** All website visitors in last 30 days

**Meta Pixel Events to Target:**
- Website Visitors (last 30 days)
- Exclude: Recent Purchasers (last 30 days)

**Google Audiences:**
- All users who visited site in last 30 days

**Budget Allocation:** 25-30% of total spend
**ROAS Target:** 2.0-2.5x
**Frequency Cap:** 2x per week (avoid frequency fatigue)
**Creative Strategy:** Educational + Testimonial-focused
- Product education videos
- Customer testimonials
- Benefit highlights (answering "why buy from us")
- FAQ-addressing content
- Multi-part educational series

**CPA Target:** 70-80% of cold traffic CPA
**Timeline:** Keep active 30 days (continuous refresh as new visitors added)

---

### Tier 3: Cold Lookalike Audience (15-20% of budget)

**Audience Definition:** Lookalike audience built from purchasers

**Meta Setup:**
- Create Lookalike from: All Purchasers (last 180 days)
- Lookalike percentage: 1-2% (tighter = more similar to buyers)

**Google Setup:**
- Create Audience: Similar to purchasers
- Audience size: 2% similar

**Budget Allocation:** 15-20% of total spend
**ROAS Target:** 1.5-2.0x
**Frequency Cap:** 3x per week
**Creative Strategy:** Proof-based
- Customer success stories
- Before/after transformations
- Social proof (review highlights)
- "People like you bought this"
- Demographic-specific messaging

**CPA Target:** 100-120% of cold prospecting CPA
**Timeline:** Continuous (lookalike audience refreshes monthly)

---

### Tier 4: Prospecting (Cold Traffic) (15-20% of budget)

**Audience Definition:** Broad targeting without retargeting filters

**Meta Targeting:**
- Open targeting (no specific interests) OR
- Interests 15-25M size (proven relevance)
- Exclude: Website Visitors + Recent Purchasers

**Google Targeting:**
- Broad match keywords
- Competitor keywords
- In-market audiences

**Budget Allocation:** 15-20% of total spend
**ROAS Target:** 1.2-1.5x (lowest converting, largest potential)
**Frequency Cap:** Unlimited (new audience)
**Creative Strategy:** Hook-first, viral
- Strong pattern interrupt
- Entertainment-first approach
- "Stop scrolling" hooks
- Viral format testing
- Niche-specific angles

**CPA Target:** 100% (baseline)
**Timeline:** Continuous

---

### Tier 5: Testing & Experimental (10-15% of budget)

**Audience Definition:** New/untested audiences and creatives

**Meta Testing Ideas:**
- Lookalike from email list (highest intent)
- Lookalike from website viewers (warm prospect)
- Interest combinations (Crazy Method)
- Demographic-specific (age/gender/location tests)

**Google Testing Ideas:**
- Affinity audiences (interest-based)
- Intent audiences (search-based)
- Lookalike from converters
- In-market audiences

**Budget Allocation:** 10-15% of total spend
**ROAS Target:** 1.0-1.2x (testing tolerance)
**Frequency Cap:** 5x per week (test faster)
**Creative Strategy:** Experimental
- New hooks/angles
- Emerging content formats
- Niche messaging tests
- Platform-specific variations

**Kill Decision:** Kill after $50 spend with <1 conversion
**Scale Decision:** Move to main tier if ROAS >1.5x after $200 spend

---

## Exclusion Strategy

### Must-Exclude Audiences

**Exclude 1: Recent Purchasers (Last 30-60 Days)**
- Reason: Avoid upsetting recent buyers with re-targeting ads
- Meta: Create Custom Audience from Purchase events (30-day window)
- Google: Audience exclusion for converters (30 days)
- Exception: Only include if running upsell/cross-sell campaigns

**Exclude 2: High-Frequency Viewers (3+ Ad Views in 7 Days)**
- Reason: Frequency fatigue, diminishing returns
- Meta: Setup in campaign → Frequency Cap settings (3x per 7 days)
- Google: Frequency cap (capped impressions) set to 3-5
- Impact: Protects creative lifecycle

**Exclude 3: Engaged But Non-Converting (3+ Initiates, 0 Purchases)**
- Reason: These are likely tire-kickers (window shoppers)
- Meta: Create exclusion audience from InitiateCheckout (30 days)
- Google: Exclude users who visited checkout but didn't convert
- Exception: Show only "overcoming objections" creative (try new angle once)

**Exclude 4: Organic/Email Buyers (If Tracked)**
- Reason: Avoid paying for sales you got free through organic/email
- Meta: Create exclusion from UTM parameters (track non-paid sources)
- Google: Exclude if you can tag organic conversions separately
- Note: Only if you have UTM/attribution working properly

### Optional Exclusions (Case-by-Case)

**Exclude: Video View Audience (If Testing Display Ads)**
- If campaign is image/display only, exclude people who only watch videos
- Reason: Different audience intent (entertainment vs. purchase)

**Exclude: Landing Page Bounces Only**
- Exclude people who visited landing page <3 seconds
- Reason: Not genuine visitors, just accident clicks

---

## Retargeting Creative Strategy by Tier

### Tier 1: Cart Abandoners
- Message: "Your items are still available"
- Visual: Product image + price
- CTA: "Complete Your Order Now"
- Offer: Optional small discount or free shipping sweetener
- Format: Static image with bold headline
- Frequency: Daily for 3 days, then pause for 4 days, restart

### Tier 2: Site Visitors (No Purchase)
- Message: "See Why Customers Love [Product]"
- Visual: Testimonials, results, lifestyle use
- CTA: "Learn More" or "See Details"
- Offer: Information/education, not discount
- Format: Video (demo or testimonial) or carousel
- Frequency: 2x per week

### Tier 3: Lookalike Purchasers
- Message: "Join 10,000+ Satisfied Customers"
- Visual: Social proof, before/after, transformation
- CTA: "Shop Now"
- Offer: Standard offer (same as prospecting)
- Format: Video with customer testimonials
- Frequency: 3x per week

### Tier 4: Cold Prospecting
- Message: "Discover [Product]"
- Visual: Strong hook, pattern interrupt
- CTA: "Shop Now"
- Offer: Lead magnet or special (optional)
- Format: Video (hook-first) or carousel
- Frequency: Unlimited

### Tier 5: Testing
- Message: Variable (testing)
- Visual: Variable (testing)
- CTA: Variable (testing)
- Offer: Variable (testing)
- Format: Variable (video vs. static, carousel vs. single, etc.)
- Frequency: 5x per week during test window

---

## Budget Allocation Formula

### For Account <$2,000/month Total Spend

```
Total Budget: $2,000
├─ Tier 1 (Hottest, 25%): $500
├─ Tier 2 (Warm, 30%): $600
├─ Tier 3 (Lookalike, 15%): $300
├─ Tier 4 (Cold Prospecting, 20%): $400
└─ Tier 5 (Testing, 10%): $200

Retargeting Total (Tiers 1-3): $1,400 (70%)
Prospecting Total (Tiers 4-5): $600 (30%)
```

### For Account $2,000-5,000/month

```
Total Budget: $3,500
├─ Tier 1 (25%): $875
├─ Tier 2 (28%): $980
├─ Tier 3 (17%): $595
├─ Tier 4 (20%): $700
└─ Tier 5 (10%): $350

Retargeting Total: $2,450 (70%)
Prospecting Total: $1,050 (30%)
```

### For Account $5,000+/month

```
Total Budget: $7,500
├─ Tier 1 (20%): $1,500
├─ Tier 2 (30%): $2,250
├─ Tier 3 (15%): $1,125
├─ Tier 4 (20%): $1,500
└─ Tier 5 (15%): $1,125

Retargeting Total: $4,875 (65%)
Prospecting Total: $2,625 (35%)

Additional: Tier 5 testing increases to 15% (enables faster iteration)
```

---

## Retargeting Audience Sizing

### Minimum Audience Sizes (To Avoid Underspend)

**Tier 1: Initiators**
- Minimum: 5,000 people
- If <5,000: Expand window from 3 days to 7 days
- If still <5,000: Budget is too high for this tier; reduce allocation

**Tier 2: Site Visitors (30 days)**
- Minimum: 50,000 people
- If <50,000: Reduce retargeting % allocation; more cold prospecting needed
- Expansion: Increase window from 30 to 60 days

**Tier 3: Lookalike**
- Minimum: 1% lookalike = typically 100,000+ people
- If unavailable: Increase lookalike % to 2-3% (expands audience)
- Note: 3% lookalike still performs better than cold prospecting

---

## Retargeting Window Strategy

### When to Extend / Shrink Windows

**Extend Window (Larger Audience):**
- If ROAS is strong and audience <minimum size
- If prospecting audience is weak (retargeting should increase)
- Example: Expand Tier 2 from 30 to 45 days if getting strong ROAS

**Shrink Window (Tighter Targeting):**
- If frequency fatigue detected (CPA increasing, frequency >3)
- If ROAS dropped but audience still healthy
- Example: Reduce Tier 1 from 7 days to 3 days to eliminate stale initiators

**Formula: Optimal Window = (Conversion lag in days) × 2**
- Example: If average conversion takes 5 days, use 10-day window
- Accounts for people who see ad, don't convert immediately, convert later

---

## Retargeting Performance Monitoring

### Weekly Retargeting Audit

1. **Compare Tier Performance:**
   - Which tier has best ROAS? (Should be Tier 1)
   - Which tier has worst ROAS? (Usually Tier 4, expected)
   - If Tier 4 outperforming Tier 1: Investigate audience quality

2. **Check Audience Sizes:**
   - Are all tiers above minimum?
   - If shrinking: Increase window or refresh pixel tracking

3. **Frequency Analysis:**
   - Is any tier showing frequency >recommended cap?
   - If yes: Reduce frequency or pause for 3 days

4. **Budget Allocation Efficiency:**
   - Calculate: ROAS × Budget allocation = profit contribution
   - Reallocate from worst-performing to best-performing tier

### Monthly Retargeting Strategy Reset

- Review which audiences have "cold" (stale) users
- Refresh exclusions (people who recently purchased)
- Test new creative angles in Tier 5 for potential Tier 1/2 use
- Adjust windows based on conversion data
- Plan for seasonal adjustments (Tier 4 budget increase in Q4)

