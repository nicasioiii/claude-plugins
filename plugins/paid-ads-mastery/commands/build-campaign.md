---
name: Build Campaign
description: Interactive campaign builder that asks platform, business type, objective, budget, and pixel maturity. Outputs a complete campaign blueprint with structure, targeting, creative strategy, and scaling plan based on the strategy skills.
---

# Build Campaign Wizard

## Step 1: Platform Selection

**Question:** Which platform are you building on?

**Options:**
- A) **Meta Ads** (Facebook/Instagram) → Go to Step 2a
- B) **Google Ads** (Shopping/Search/PMax) → Go to Step 2b
- C) **Unsure** → Recommendation: Start with Meta for brand new products, Google for validated products with existing traffic demand

---

## Step 2a: Meta Ads - Business Type

**Question:** What type of business are you running?

**Options:**
1. **E-commerce / Dropshipping** (Physical products)
   - Budget allocation strategy: 70% cold, 30% retargeting
   - Expected ROAS target: 2.0-2.5x
   - Go to Step 3a

2. **Niche/Fashion/Beauty** (Lifestyle products)
   - Budget allocation strategy: 60% cold, 40% retargeting
   - Expected ROAS target: 1.8-2.2x
   - Go to Step 3a

3. **Information Products / Courses** (Digital)
   - Budget allocation strategy: 80% cold, 20% retargeting
   - Expected ROAS target: 2.5-4.0x
   - Go to Step 3a

4. **SAAS / Recurring Revenue** (Subscription)
   - Budget allocation strategy: 75% cold, 25% retargeting
   - Expected ROAS target: 3.0-5.0x
   - Go to Step 3a

---

## Step 2b: Google Ads - Business Type

**Question:** Do you have validated product demand?

**Option A: High Search Volume Product** (25,000+ monthly searches)
- Recommendation: Start with Shopping Campaign
- Go to Step 3b

**Option B: New / Unvalidated Product**
- Recommendation: Start with Search Ads or Performance Max
- Go to Step 3b

**Option C: Multiple Products / Brand**
- Recommendation: Performance Max for reach + Shopping for demand capture
- Go to Step 3b

---

## Step 3a: Meta Campaign Structure Selection

**Question:** How long have you had a pixel active on your site?

**Option A: New Pixel** (<2 weeks of data)
- Recommended methodology: **Blender Method** (lookalike + interest hybrid)
- Campaign structure: 1 CBO campaign, 3-4 ad sets (3 different audience types)
- Budget: Start $300-500/day, let algorithm learn for 7 days
- Expected timeline: Learning phase 7-10 days, then scale
- Go to Step 4a

**Option B: Established Pixel** (2-8 weeks of data)
- Recommended methodology: **Simple Method** (catalog-based, open targeting)
- Campaign structure: 1-2 CBO campaigns with dynamic product ads
- Budget: Start at ($target_CPA × 50 sales) / 7 days, scale 10% daily post-learning
- Expected timeline: Exit learning phase by day 7-14, then scale aggressively
- Go to Step 4a

**Option C: Mature Pixel** (8+ weeks of data, proven conversions)
- Recommended methodology: **Crazy Method** (interest duplication) OR **Simple Method** at scale
- Campaign structure: Multiple ABO campaigns with different audience layers
- Budget: $500+ daily, allocate 20% to testing, 80% to proven audiences
- Expected timeline: Skip learning phase, immediate scale
- Go to Step 4a

---

## Step 3b: Google Campaign Structure Selection

**Question:** What's your product price point and margin?

**Option A: Low Ticket** (<$50, <40% margin)
- Recommended: **Shopping Campaign with Maximize Clicks**
- Start with 20-25 products minimum
- Budget: $300-500/day
- Scaling: Conservative (10% increases)
- Go to Step 4b

**Option B: Mid Ticket** ($50-200, 40-60% margin)
- Recommended: **Shopping Campaign OR Performance Max**
- Shopping: High Bid + Low Bid testing setup
- PMax: 1-3 asset groups, phase-based strategy
- Budget: $500-1,000/day
- Go to Step 4b

**Option C: High Ticket** (>$200, >60% margin)
- Recommended: **Performance Max with Search Ads supplement**
- PMax: Multiple asset groups (3-5), focus on social proof
- Search: Branded + competitor keywords with high bids
- Budget: $1,000-2,000/day
- Go to Step 4b

---

## Step 4a: Meta Creative Strategy

**Question:** What's your creative production capacity?

**Option A: Traditional Production** (in-house or agencies)
- Use: **Hook frameworks + VSL/UGC templates** from create-meta-ads-traditional skill
- Production timeline: 1 week per creative set
- Testing methodology: Standard ABO (4-6 creatives simultaneously)
- Scaling: Test 20% of budget, scale 80% on winners
- Budget allocation: Start $50-100/creative
- Go to Step 5a

**Option B: AI-Powered Production** (Midjourney, Runway, ElevenLabs)
- Use: **AI creative workflow** from create-meta-ads-ai skill
- Production timeline: 1-2 days per creative set
- Testing methodology: Shotgun method (10-20 variations quickly)
- Scaling: Test 30-50% of budget, scale 50-70% on winners
- Budget allocation: Start $30-50/creative (AI cost lower)
- Go to Step 5a

**Option C: User-Generated Content (UGC)** (Upwork, creator marketplaces)
- Use: **UGC frameworks** from create-meta-ads-traditional skill
- Production timeline: 2-4 weeks (outsourced)
- Testing methodology: Standard ABO, batch testing
- Scaling: Test 25% of budget, scale 75% on winners
- Budget allocation: Allocate creator fees outside ad budget
- Go to Step 5a

---

## Step 4b: Google Product/Keyword Strategy

**Question:** How many products do you have ready to advertise?

**Option A: <25 Products** (Limited inventory)
- Strategy: **Shopping campaign with HIGH BID testing first**
- Focus: Maximize Clicks bidding strategy
- Daily budget: $25-50/day
- Optimization frequency: Every 14 days
- Scaling trigger: ROAS >3.0 for 7+ days
- Go to Step 5b

**Option B: 25-100 Products** (Standard catalog)
- Strategy: **Dual Shopping campaigns (High Bid + Low Bid test setup)**
- Add Performance Max as secondary
- Daily budget: $50-200/day per campaign type
- Optimization frequency: Every 7-10 days
- Scaling trigger: Identify top 10 products, scale bids
- Go to Step 5b

**Option C: 100+ Products** (Full catalog)
- Strategy: **Performance Max primary + Shopping secondary**
- Shopping: Separate campaigns per collection
- PMax: Multiple asset groups for different product categories
- Daily budget: $200-500/day across all
- Optimization frequency: Every 5-7 days (more data flow)
- Scaling trigger: ROAS 3.0+ across portfolio
- Go to Step 5b

---

## Step 5a: Meta Campaign Naming & Launch

**Your Campaign Blueprint:**

```
Campaign Name: [BRAND]_[FUNNEL]_[TYPE]_[VARIABLE]_[OPTIMIZATION]_[DATE]

Example:
  MYSTORE_COLD_VID_HOOK_ABO_03_2026

Structure:
  - Campaign Type: [Catalog / Conversions / Advantage Shopping]
  - Budget: [Daily budget from steps above]
  - Objective: Sales
  - Attribution: [1-day click or 7-day if available]

Ad Sets (Name Format):
  - MYSTORE_COLD_VID_HOOK_ABO_03_2026_Audience1_18-35
  - MYSTORE_COLD_VID_HOOK_ABO_03_2026_Audience2_35-55
  - MYSTORE_COLD_VID_HOOK_ABO_03_2026_Audience3_AllAges

Ads (Name Format):
  - MYSTORE_COLD_VID_HOOK_ABO_03_2026_Audience1_Creative001_Hook1_9x16
  - MYSTORE_COLD_VID_HOOK_ABO_03_2026_Audience1_Creative002_Hook2_1x1
```

**Launch Checklist:**
- [ ] Pixel is active and firing test purchases
- [ ] Creatives reviewed for brand compliance
- [ ] All ad sets have proper audience setup (no overlap >30%)
- [ ] Budget pacing set to standard (not accelerated)
- [ ] Set frequency cap: 3x per 7 days for cold traffic
- [ ] Set 24-hour reporting attribution window
- [ ] Schedule launch for midnight (fresh auction environment)
- [ ] Set calendar reminder: Monitor learning phase exit (day 7)

**Recommended Daily Monitoring:**
- Check spend vs. budget: Should be ~1/7 of weekly budget
- Check ROAS: Volatile in learning phase, don't overreact
- Check pixel: Ensure events firing
- Kill if: ROAS <breakeven after $100+ spend with <1 conversion

---

## Step 5b: Google Campaign Naming & Launch

**Your Campaign Blueprint:**

```
Shopping Campaign: [PRODUCT]_[BIDSTRATEGY]_[GEO]_[PHASE]_[DATE]

Example:
  MyProduct_MaximizeClicks_US_Testing_03_2026

Setup:
  - Campaign Type: Standard Shopping
  - Bidding: Maximize Clicks (for new accounts)
  - Daily Budget: [From Step 4b]
  - Merchant Center: Select account with products
  - Geographic: United States
  - Networks: Search Network ONLY (uncheck Display)

Product-Level Optimization:
  - Minimum bid: $0.30-0.50
  - Max bid: Auto-increased as data flows
  - Attribution window: 1-day click (standard)
```

**For Performance Max (if applicable):**

```
Campaign: [BRAND]_[TARGETING]_[PHASE]_AssetGroup1_[DATE]

Example:
  MYSTORE_Prospecting_Testing_AssetGroup1_03_2026

Asset Group Setup:
  - Headlines: 3-5 variations
  - Descriptions: 3-5 variations
  - Images: 4-6 high-quality
  - Videos: 1-2 optional
  - Logo: 1 required
```

**Launch Checklist:**
- [ ] All products have original descriptions (50-200 words)
- [ ] All products have 3-5 high-quality lifestyle images
- [ ] Titles optimized with primary keywords left-to-right
- [ ] Product feed verified in Merchant Center (0 errors)
- [ ] Landing page matches product offers
- [ ] Conversion tracking live (5+ daily conversions expected)
- [ ] Campaign launched with Maximize Clicks bidding (not Target ROAS)
- [ ] Daily budget is $25+ minimum (anything lower = underfunded)

**Recommended Daily Monitoring:**
- Check conversion tracking: Should have 3-5+ daily conversions
- Check budget: Should hit 90-110% of daily budget target
- Check impression share: Target 70%+
- Check quality score: Monitor keywords, target 7+

---

## Next Steps After Launch

**After 7 Days (Meta):**
→ Check if campaign exited Learning Phase
→ Evaluate performance: ROAS vs. target?
→ If ROAS >target: SCALE 10%
→ If ROAS <target: TEST new creative variant

**After 7 Days (Google):**
→ Check conversion data: 50+ conversions?
→ Check quality scores: <5 keywords?
→ Review top 5 products by spend
→ Pause 0-conversion products
→ Increase bids on 3+ sale products

**After 14 Days (Meta + Google):**
→ Review: activate /optimize skill for ongoing monitoring
→ Plan: creative refresh (20% new + 80% optimization of winners)

---

## Quick Reference: What To Do Next

**Choose a skill to dive deeper:**
- 👉 **Creative production?** → `/create-meta-traditional` or `/create-meta-ai` or `/create-google`
- 👉 **Need winning audience research first?** → `/research-creative`
- 👉 **Campaign is live, need to monitor?** → `/optimize-campaigns`
- 👉 **Deciding scale vs. kill?** → `/scale-plan` or use `/optimize` for decision trees
