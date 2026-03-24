---
name: Build Campaign
description: Design a complete campaign from scratch. Asks about platform, product, budget, goals, and pixel maturity. Outputs campaign architecture, targeting plan, budget allocation, and creative brief. Activates strategy-meta-ads OR strategy-google-ads, research-creative, and strategy-cross-channel.
---

# Build Campaign Wizard

## Step 1: Gather Essential Information

Ask the user these questions before proceeding. Do not skip any.

### Required Inputs
1. **Platform:** Meta (Facebook/Instagram), Google Ads, TikTok, or multi-platform?
2. **Business type:** E-commerce, lead generation, SaaS, info products, local business?
3. **Product/service:** What are you selling? Price point? Margins?
4. **Monthly budget:** How much are you prepared to spend on ads?
5. **Goal:** Sales/revenue target, lead volume, ROAS target, or CPA target?
6. **Pixel/tracking maturity:** New account, established (some data), or seasoned (months of conversion data)?
7. **Creative assets available:** What do you have ready? (video, static images, UGC, nothing yet)
8. **Geographic target:** Which countries/regions?

---

## Step 2: Calculate Unit Economics

Before designing any campaign, validate the business can support paid advertising.

**For e-commerce:**
- Profit Margin = (AOV - All Costs) / AOV
- Break-Even ROAS = 1 / Profit Margin
- If break-even ROAS > 4x, warn user that scaling will be extremely difficult

**For lead gen:**
- Break-Even CPL = Profit per Deal x Lead-to-Sale Rate
- If break-even CPL < $20, warn user that most ad platforms cannot deliver profitably

**For SaaS:**
- LTV:CAC ratio must be 3:1 minimum
- Max CAC = LTV / 3

Reference: `optimize-google` skill > ref-google-unit-economics.md for detailed formulas.

---

## Step 3: Platform-Specific Campaign Architecture

### Meta Ads Campaign Blueprint

**Load skill:** `strategy-meta-ads` for method selection.

| Pixel Maturity | Recommended Method | Campaign Type | Starting Budget |
|---|---|---|---|
| New pixel (<100 purchases) | Stacked LLA or Blender Method | CBO, 3-5 ad sets | Budget/CPP = # of ad sets |
| Established (100-500 purchases) | Interest testing progressing to broader | CBO or ASC | Budget/CPP = # of ad sets |
| Seasoned (500+ purchases) | Broad + Crazy Method + ASC | Multiple CBO + ASC | Scale aggressively |

**Campaign structure rules:**
- Daily budget / Average CPP = number of ad sets
- Max 3-5 ads per ad set
- Never mix creative types in same campaign (video separate from static separate from catalog)
- Always use Advantage+ placements
- Launch at midnight or 6 AM target market time
- Optimize for Purchase event (never add-to-cart)

**Budget allocation:**
- Cold traffic: 70-80%
- Retargeting: 10-20%
- Testing: 10-20% (minimum 20% of total)

### Google Ads Campaign Blueprint

**Load skill:** `strategy-google-ads` for structure selection.

**The Four Pillars (build at least 3):**
1. **Search** -- brand + non-brand campaigns
2. **Shopping / PMax** -- workhorse for e-commerce (60%+ of spend)
3. **Remarketing** -- YouTube + Display for the 95-99% who visit but do not purchase
4. **Top of Funnel** -- YouTube for demand generation (when ready to scale)

| Product Type | Primary Campaign | Secondary | Starting Budget |
|---|---|---|---|
| High search volume (25K+ monthly) | Standard Shopping (High Bid + Low Bid) | Brand Search | $50-100/day minimum |
| Low search volume | PMax or Search Ads | Display remarketing | $100+/day for PMax |
| Large catalog (100+ SKUs) | PMax primary + Shopping secondary | Brand Search | $200+/day total |
| Lead generation | Search (brand + non-brand) | PMax (Fire & Ice) | CPA x 50 / 30 = daily budget |

**Bidding progression:**
1. Start: Enhanced CPC or Maximize Conversions
2. After 30 conversions in 30 days: switch to Target CPA or Target ROAS
3. Set initial target at current performance, then adjust 10% per week

### TikTok Ads Campaign Blueprint

**Load skill:** `strategy-tiktok-ads` for platform-specific guidance.

- Minimum 5-7 unique creatives per campaign
- Sweet spot ad length: 20-35 seconds
- Budget: minimum $50 per ad set per day
- Creative refresh: when CPA rises 20% above week-one average

---

## Step 4: Creative Brief

Based on platform and business type, generate a creative brief:

**Load skill:** `research-creative` for audience and messaging foundations.

### Creative Brief Template

```
CAMPAIGN CREATIVE BRIEF

Product: [from user input]
Target Audience: [from research-creative persona work]
Primary Benefit: [single core transformation]
Awareness Level: [unaware / problem-aware / solution-aware / product-aware / most-aware]
Recommended Formats: [video / static / carousel / UGC -- based on platform]
Recommended Angles: [3-5 angles from the 10 types: promotion, education, social proof, etc.]

Hook Direction: [based on awareness level]
- Unaware: Pattern interrupt, curiosity, stories
- Problem Aware: Validate experience, educate on problem
- Solution Aware: Differentiate approach, unique mechanism
- Product Aware: Address objections, social proof, demos
- Most Aware: Urgency, scarcity, promotions

Creative Volume Needed: [from test-creative volume guidelines]
Testing Method: [Standard ABO recommended for most]
```

---

## Step 5: Launch Checklist

### Meta Launch Checklist
- [ ] Pixel active and firing purchase events
- [ ] Seed ads created, Post IDs ready
- [ ] Naming convention applied to all creatives
- [ ] Budget calculated: budget/CPP = ad sets
- [ ] Advantage+ placements enabled
- [ ] Purchase optimization event selected
- [ ] Launch scheduled for midnight or 6 AM
- [ ] Kill criteria defined (1x CPA spend, no sale = kill)
- [ ] Testing tracker set up

### Google Launch Checklist
- [ ] Google Ads conversion code installed (NOT GA4 only)
- [ ] Enhanced conversions enabled
- [ ] Product feed approved in Merchant Center (0 errors)
- [ ] Titles SEO-optimized (keywords left-to-right)
- [ ] Negative keyword seed list prepared
- [ ] Bidding strategy set (Enhanced CPC or Max Conversions for start)
- [ ] Campaign-level daily budget set ($25+ minimum for Shopping)
- [ ] Conversion window set (30-day click recommended)

---

## Step 6: Post-Launch Monitoring Plan

**Week 1:** Do NOT touch campaigns. Monitor only. Let the algorithm learn.
- Meta: expect 24-48 hour boost, then possible dip. This is normal.
- Google: may not see impressions for first few days with PMax. Normal.

**Week 2:** First optimization cycle.
- Meta: evaluate 7-day rolling averages. Kill underperformers at 1x CPA spend.
- Google Shopping: first 7-14 day optimization (product-level, keyword-level).

**Week 3-4:** Scale or iterate.
- Scale winners by 10-20% budget increase per week.
- Load `test-creative` skill for iteration planning.
- Load `optimize-meta` or `optimize-google` for ongoing diagnostics.

---

## Next Steps

| Need | Command / Skill |
|---|---|
| Write actual ad copy or scripts | `/write-ad` command or `create-ad-copy` / `create-video-ads` |
| Deep creative research first | `/research-brief` command or `research-creative` skill |
| Diagnose a launched campaign | `/audit-campaign` command |
| Plan creative tests | `/test-plan` command |
| Scale a working campaign | `/scale-plan` command |
