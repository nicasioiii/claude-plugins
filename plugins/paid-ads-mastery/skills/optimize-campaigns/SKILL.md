---
name: Campaign Optimization & Diagnostics
description: Daily monitoring routines, creative testing methodologies, kill-vs-scale decision frameworks, performance benchmarks by platform, diagnostic decision trees, scaling playbook (vertical, horizontal, hybrid), retargeting strategies, creative fatigue detection, attribution diagnosis, and breakeven ROAS calculations. Use when optimizing running campaigns, diagnosing performance issues, deciding what to kill or scale, or planning testing strategies.
---

# Campaign Optimization & Diagnostics

## Quick Reference: Daily Monitoring Checklist

**Time Required:** 15 minutes
**Frequency:** Daily (morning and evening for active campaigns)

### What to Check First (Priority Order)

1. **Campaign Spend vs. Budget** — Is today's spend on track? (Should be ~1/7 of weekly budget)
2. **Daily ROAS** — Compare today's ROAS to 7-day rolling average (±0.2-0.3 variance is normal)
3. **Cost Per Action (CPA)** — Is CPA within your target range? (Signals quality traffic)
4. **Account Health Alerts** — Any pixel issues, conversion tracking errors, or learning phase messages?
5. **Creative Performance** — Which creatives are above/below account average? Which need replacement?

### Alarm Thresholds — When to Take Action

| Metric | Healthy | Yellow Flag | Red Flag |
|--------|---------|-------------|----------|
| **ROAS** | Above breakeven +0.5 | ±0.2 below target | >0.3 below target, trending down |
| **CPA** | 30-50% below target | At target | 1.5x target |
| **CTR** | Platform benchmark+ | Benchmark -20% | Benchmark -40%+ |
| **Hook Rate** (video) | 35%+ | 20-35% | <20% |
| **Cost Per Init Checkout** | Trending down | Flat | Trending up 10%+ |
| **Daily Spend Variance** | ±15% of avg | ±25% | ±40%+ |

### Meta Specific Alerts

- **Learning Phase:** If campaign re-enters, pause immediately and investigate (likely audience exhaustion)
- **Insufficient Data:** Stop all optimizations for 24 hours; let pixel collect baseline
- **High Frequency:** If avg frequency >3 and ROAS dropping, pause for 3 days then relaunch
- **Account Quality Score:** If dropped, audit payment method, account age, recent pauses

### Google Specific Alerts

- **Disapproved Ads:** Check policy violations immediately (affects whole campaign performance)
- **Low Quality Score:** If 3-4 quality score on keywords, pause those keywords
- **Budget Limiting:** Message indicates account getting impressions-capped; increase budget or reduce bids
- **Zero Impression Keywords:** Check bid vs. competition; raise CPC or move to phrase match

---

## Creative Testing Methodologies

**Goal:** Generate variants systematically to find winners, extend creative lifecycle, and minimize fatigue.

### 1. Standard ABO (Ad Set Budget Optimization)

**Best For:** Testing when you want full control over budget split
**Budget Formula:** Weekly test budget = 20% of main spend

```
Example: $1,000/day main spend
  → Weekly test = $1,400 ($200/day × 7 days)
  → Split across 4 creatives = $350/creative/week = $50/day each
```

**Setup:**
- 1 Campaign (ABO)
- 4-6 Ad Sets (1 per creative variant)
- 1 Ad per Ad Set
- Run 7-14 days simultaneously

**Kill Criteria:**
- Spent 1x CPA with zero conversions
- CTR >40% below account average
- CPC >50% above account average

**Scale Criteria:**
- ROAS >1.5x account average
- Hold rate (video) >15% above average
- CPA <30% below target

---

### 2. CBO Algorithm Testing (Advantage Shopping / PMax)

**Best For:** Letting algorithm optimize budget distribution across variants
**Budget Formula:** Weekly test = $50-200/day depending on CPA

```
Example: $15 CPA target
  → $100/day test budget ÷ $15 CPA = ~6-7 conversions/day target
```

**Setup:**
- 1 Campaign (CBO)
- Multiple Ad Sets with 2-4 creatives each
- Algorithm splits budget to top performers

**Kill Criteria:**
- Campaign ROAS <breakeven for 7+ consecutive days
- Conversions trending down 20%+ vs. prior week

**Scale Criteria:**
- Consistent ROAS 1.2x+ breakeven for 7+ days
- CPC trending down or stable

---

### 3. Manual Bidding (MOB Strategy)

**Best For:** Maximum cost control, volatile spend OK
**Budget Formula:** Cost cap = CPA × expected daily conversions

```
Example: $20 CPA, want 3 sales/day
  → Cost cap = $20 × 3 = $60/day
```

**Setup:**
- Campaign with cost cap bid strategy
- 1-day attribution (optimized for volatility management)
- 3-5 ad sets each with different audiences

**Kill Criteria:**
- Cost cap hit daily without conversions
- Spend >3x cost cap with <50% of target conversions

**Scale Criteria:**
- Consistent conversions at or below cost cap
- ROAS >2.0

---

### 4. Shotgun Method (Rapid Fire Testing)

**Best For:** Speed testing when you need winners fast
**Budget Formula:** $20-50 per creative test

```
Example: Test 10 creatives
  → $30 each × 10 = $300 total
  → Run 2-3 days each
```

**Setup:**
- Launch many creatives simultaneously at low budget
- Identify top 3 performers
- Pause bottom 70%
- Scale winners 20%/day

**Kill Criteria:**
- No conversions after $50 spend
- Hold rate <5% (video)

**Scale Criteria:**
- 2+ conversions at target CPA
- ROAS >1.0

---

### 5. Crazy Method (Interest Duplication)

**Best For:** Accounts with strong audience data
**Budget Formula:** $150-300/day per creative test

```
Example: Test 5 duplicated interests
  → $200/day × 5 = $1,000/day
  → Run 3-5 days
```

**Setup:**
- Same creative, 5 different interest audiences (slight overlaps OK)
- ABO campaign with equal budget split
- Monitor which audience performs best

**Kill Criteria:**
- Average ROAS <1.2x breakeven across all audiences
- One audience performing >3x better indicates winner

**Scale Criteria:**
- 1 audience delivering ROAS >2.0
- Scale that audience, kill others

---

### 6. Rapid Fire Iteration

**Best For:** Extending a winning creative's lifecycle
**Budget Formula:** 5-10 iterations of winning creative per week

```
Example: Winning creative ROAS = 1.8
  → Allocate 30% of winning budget to iterate
  → If winning = $300/day, iterate budget = $90/day
  → Split across 5 hook variations
```

**Setup:**
- Keep 70% on proven winner
- Test 5 variations of one variable (hook, USP, CTA)
- Run 3-7 days each

**Kill Criteria:**
- New iteration underperforms winner by >20%
- Hold rate drops >10% from winner

**Scale Criteria:**
- Iteration matches winner ROAS
- New iteration beats winner by 10%+

---

## Kill vs. Scale Decision Matrix

### Meta Ads Kill/Scale Framework

| ROAS | Trend | Action | Reasoning |
|------|-------|--------|-----------|
| >2.0x target | Stable/↑ | **SCALE 20%** | Healthy, room to grow |
| 1.2-2.0x target | Stable | **SCALE 10%** | Conservative growth |
| At breakeven | ↑ last 2 days | **HOLD** | Watch for momentum |
| At breakeven | ↓ last 2 days | **PAUSE 48h** | Investigate before scaling |
| <breakeven | Flat | **PAUSE 7 days** | Relaunch with fresh creative |
| <breakeven | ↓ | **KILL** | Not recovering, reallocate budget |

### Google Ads Kill/Scale Framework

| ROAS | Conversions/Week | Action | Reasoning |
|------|------------------|--------|-----------|
| >3.0 | 5+ | **INCREASE BID 10%** | Proven scale capacity |
| 3.0-2.0 | 5+ | **INCREASE BID 5%** | Cautious scaling |
| 2.0-1.5 | 5+ | **HOLD BIDS** | Profitable but saturating |
| 1.5-breakeven | 3+ | **PAUSE KEYWORDS** | Marginal return |
| <breakeven | Any | **KILL KEYWORDS** | Losing money |
| - | <3/week | **PAUSE 14 DAYS** | Insufficient data to optimize |

---

## Performance Benchmarks by Platform

### Meta Ads Benchmarks (by campaign type)

#### E-commerce (Catalog + DPA)
- **ROAS Target:** 1.8-2.5x
- **CPA:** 30-50% of product AOV
- **CTR:** 1.2-2.0%
- **CPM:** $2-5
- **Hook Rate:** 35%+
- **Hold Rate:** 10-15%
- **Frequency Cap:** 2-3x per 7 days

#### Info Products / Courses
- **ROAS Target:** 2.0-3.0x
- **CPA:** $15-50
- **CTR:** 0.8-1.5%
- **CPM:** $0.50-2.00
- **Hook Rate:** 40%+
- **Hold Rate:** 15-20%

#### SAAS / Trials
- **ROAS Target:** 3.0-5.0x
- **CPA:** $5-25
- **CTR:** 1.0-2.0%
- **CPM:** $1-3
- **Hook Rate:** 35%+

---

### Google Ads Benchmarks (by campaign type)

#### Shopping Campaigns
- **ROAS Target:** 3.0-4.0x (minimum viable 3.0)
- **CPC:** $0.20-0.50
- **Conversion Rate:** 2-5%
- **Quality Score:** 6-10 (8+ optimal)
- **Search Impression Share:** 70%+

#### Search Campaigns
- **ROAS Target:** 2.5-3.5x
- **CPC:** $0.50-2.00 (varies by keyword)
- **Quality Score:** 7-10
- **CTR:** 3-8%
- **Conversion Rate:** 2-5%

#### Performance Max
- **ROAS Target:** 2.5-3.5x (learning phase: 1.5-2.0)
- **CPC:** Google-optimized
- **Conversion Rate:** 1-4%

---

## Diagnostic Decision Trees

### Meta Diagnostic (7 Steps)

**Step 1: Is pixel firing correctly?**
- Go to Events Manager → View Test Events
- Add product to cart, purchase
- Verify Purchase event fires within 1 second
- **If NO:** Implement conversion API or fix pixel code
- **If YES:** Continue to Step 2

**Step 2: Is audience quality issue or creative issue?**
- Compare same creative across 3 different audiences
- If 2/3 audiences underperform → Creative issue
- If all audiences underperform → Audience saturation
- **Action:** If creative issue, test new hook. If saturation, pause 7 days.

**Step 3: Is CPA creeping up?**
- Compare 7-day CPA vs. 30-day average
- If 7-day CPA >20% above rolling 30-day → Cost inflation signal
- **Action:** Reduce frequency for 3 days or pause high-frequency campaigns

**Step 4: Is ROAS variance normal or systematic decline?**
- Track 7-day ROAS for last 4 weeks
- Plot on chart: Should oscillate around average (±0.3 range normal)
- If trend line declining >0.2 per week → Creative fatigue
- **Action:** Pause winning creative for 3 days then relaunch, OR test new variations

**Step 5: Is account health score affecting delivery?**
- Check Facebook Ads Manager → Account Settings → Account Quality
- Quality issues flag: Payment issues, account age <3 months, repeated pauses
- **Action:** If <good rating, resolve payment/account history before scaling

**Step 6: Is learning phase blocking scale?**
- Check campaign status → Learning Phase indicator
- If in learning phase: Pause all optimizations for 24 hours
- Re-entry signal: Campaign entered learning phase after being live 30+ days
- **Action:** If re-entry, investigate audience exhaustion; if new campaign, let algorithm learn

**Step 7: What's the long-term trend?**
- Plot ROAS + CPA over 60 days
- Healthy: ROAS stable ±0.2, CPA stable ±10%
- Declining: ROAS declining >0.05/week, CPA inflating >5%/week
- **Action:** If declining, creative fatigue = increase testing % or rotate new creatives

---

### Google Diagnostic (9 Steps)

**Step 1: Is conversion tracking live?**
- Go to Conversions → Check status of main conversion
- Verify 5+ conversions in last 7 days
- If <5: Check tag implementation, wait 24-48 hours, verify again
- **If NO data:** Implement conversion tag in GTM or Google Tag Manager

**Step 2: Is quality score issue?**
- Go to Keywords → Quality Score column
- Calculate: % of keywords with QS 6-10 (should be 70%+)
- QS <5: Auction competition issue OR low relevance
- **Action:** Improve ad copy relevance or increase max CPC bids

**Step 3: Is budget limiting?**
- Check Diagnostics → Budget/Insufficient Budget messages
- If appearing: Your bids too low OR budget cap too low relative to demand
- **Action:** Increase daily budget 10% OR increase max CPC bids

**Step 4: Is bid strategy appropriate?**
- Current bidding: Maximize Clicks / Target ROAS / Manual CPC?
- Maximize Clicks: Best for <$500 account spend (learning phase)
- Target ROAS: Only if $500+ conversion history; risky on new accounts
- Manual CPC: Most control but requires constant monitoring
- **Action:** If new campaign <$500 spend, use Maximize Clicks

**Step 5: What's the impression share problem?**
- Go to Dimensions → Top vs. Other column
- Impression Share <70%: Bidding too low OR budget capped
- Impression Share Lost to Budget: Increase daily budget 20%
- Impression Share Lost to Rank: Increase max CPC bid 15%
- **Action:** Increase limiting factor budget or bids

**Step 6: Is audience fatigue happening?**
- Compare CPC + Conversion Rate vs. 4 weeks ago
- CPC trending up 20%+: Auction competition or audience saturation
- Conversion Rate trending down 30%+: Audience fatigue
- **Action:** Expand keywords (add broad match variants) or create new audiences

**Step 7: Is product feed quality issue?**
- Go to Merchant Center → Diagnostics
- High "Processing errors" (>5% of feed): Fix product data
- Missing images: Add required 4-6 images per product
- Low-quality images: Replace with lifestyle images
- **Action:** Fix feed issues, then monitor campaign 48 hours for recovery

**Step 8: Is seasonal trend or algorithm change?**
- Check Google Trends for product category (search volume)
- Compare to campaign volume: Is drop proportional to search volume?
- Check Google Blog for algorithm updates (Shopping feature changes)
- **Action:** If seasonal, adjust budget for expected dip. If algorithm change, monitor 7 days

**Step 9: What's the profitability status?**
- Calculate: ROAS × (1 - Platform Fee) × Margin
- Example: ROAS 3.0 × 0.98 × 0.4 = 1.176 profit/dollar (viable)
- If <1.1: Campaign not sustainable
- **Action:** Scale only if profitable or use as loss leader for customer acquisition

---

## Scaling Playbook

### Vertical Scaling (Budget Increases on Same Campaign)

**Rule:** Increase by 10% when ROAS is healthy, not aggressive
**Timing:** Every 3-5 days when performing well

```
Example: Campaign doing $150/day at ROAS 2.1
  Day 1: $150
  Day 2: $150 (collect baseline)
  Day 3: $150 (collect baseline)
  Day 4: $165 (10% increase) ← ROAS check
  Day 5: $165 (monitor)
  Day 6: $165 (monitor)
  Day 7: $182 (10% increase if ROAS >2.0) ← ROAS check

Safe scaling limit: Stop at 3-5x original budget. Beyond that = audience saturation.
```

**Safety Guardrails:**
- Don't increase if ROAS <1.5x breakeven
- Don't increase >20% in one day (risks algorithm reset)
- Watch CPA closely; if inflating >15%, pause scaling

---

### Horizontal Scaling (Duplicating Winning Campaigns)

**Best For:** When main campaign is capped
**Setup:** Create 2-3 exact duplicates of winning campaign with different audience layers

```
Example: Campaign A doing $500/day ROAS 2.0 (capped out)
  → Duplicate Campaign A → Campaign B (run simultaneously)
  → Duplicate Campaign A → Campaign C (run 3 days later)

Expected impact: Campaign B gets 60-70% of Campaign A's ROAS (some audience overlap)
                 Campaign C gets 40-50% (more overlap)

Total: $500 + $350 + $250 = $1,100/day (net +$100 vs. single capped campaign)
```

**Cannibalization Formula:**
- Duplicate 1: Expect 70% of original performance
- Duplicate 2: Expect 50% of original performance
- Duplicate 3: Expect 30% of original performance
- Beyond 3: Stop duplicating (audience exhaustion)

---

### Hybrid Scaling (Vertical + Horizontal Combined)

**Best For:** Accounts with $2,000+ daily spend potential

```
Example: Main campaign doing $200/day ROAS 2.2

Phase 1 (Weeks 1-2): Vertical scale main
  → $200 → $220 → $242 (10% increments)

Phase 2 (Week 3): Start horizontal
  → Launch duplicate at $100/day
  → Keep main at $242/day

Phase 3 (Week 4): Scale both
  → Main: $242 → $266 (10% increase)
  → Duplicate: $100 → $110 (10% increase)

Result: Week 1 = $200, Week 4 = $376 (88% growth, not aggressive)
```

---

### Budget-Dependent Scaling Strategies

**Under $500/day spend:**
- Focus on ONE high-performing campaign
- Vertical scale only (10% increments every 3-5 days)
- Test 3 new creatives weekly (20% test budget)
- Goal: Hit $500/day on 1 campaign first

**$500-$2,000/day spend:**
- Vertical scale main campaign to $1,000
- Launch 1 horizontal duplicate when main capped
- Test 5-7 new creatives weekly
- Run 2-3 testing campaigns simultaneously

**$2,000+ /day spend:**
- Vertical scale multiple campaigns
- Horizontal duplicates for each winning creative
- Rotate new audiences in dedicated testing campaigns
- Dynamic bidding on winners

---

## Retargeting Strategy

### Audience Tiers (Budget Allocation)

| Tier | Audience | Budget % | ROAS Target | Frequency Cap |
|------|----------|----------|-------------|---------------|
| **Tier 1: Hottest** | Initiators, Cart Abandoners | 20-25% | 3.0-4.0x | 1x/day |
| **Tier 2: Warm** | All Site Visitors (30 days) | 25-30% | 2.0-2.5x | 2x/week |
| **Tier 3: Cold Lookalike** | Lookalike from purchasers | 15-20% | 1.5-2.0x | 3x/week |
| **Tier 4: Prospecting** | Broad interests, age/location | 15-20% | 1.2-1.5x | Unlimited |
| **Tier 5: Testing** | New audiences, new creatives | 10-15% | 1.0-1.2x | 5x/week |

### Exclusion Windows

- **Recent Purchasers:** Exclude last 30-60 days (prevent churn)
- **High Frequency Viewers:** Exclude people who viewed ad 5+ times in 7 days
- **Non-Converting Clickers:** Exclude after 3+ adds to cart with no purchase
- **Organic Buyers:** Exclude recent purchasers from paid retargeting (if using UTM)

### Creative Strategy by Tier

- **Tier 1 (Initiators):** CTA-focused, urgency, "Complete your order"
- **Tier 2 (Site Visitors):** Educational content, testimonials, benefit-focused
- **Tier 3 (Lookalike):** Discovery ads, USP-focused, "People like you bought X"
- **Tier 4 (Cold Prospecting):** Hook-first, viral format, pattern interrupt
- **Tier 5 (Testing):** New creative tests, niche angles, experimental formats

---

## Creative Fatigue Detection

### Warning Signs (Action Needed in Next 5 Days)

1. **Frequency trending up:** Average frequency rising 0.2+ per day
2. **ROAS variance increasing:** Daily ROAS ±0.4+ (vs. normal ±0.2)
3. **CPA creeping:** 10-15% above 7-day rolling average
4. **CTR declining:** 15-20% below account average
5. **Hold rate dropping (video):** 20%+ drop from baseline

### Critical Fatigue (Action Needed Immediately)

1. **ROAS below breakeven** for 3+ consecutive days
2. **Hold rate <5%** (video) or CTR <0.5%
3. **CPA >2x target** with stable spend
4. **Frequency >4x** with declining conversions
5. **Account quality score:** Dropped to "Poor"

### Recovery Actions (In Order of Priority)

1. **Pause for 48 hours** (let algorithm reset)
2. **Reduce frequency cap** (1x per day instead of 3x)
3. **Test new creative hook** (same message, different visual)
4. **Rotate to backup creative** (if available)
5. **Expand audience** (remove interest exclusions, widen age range)
6. **Lower bid** (CPA tool instead of ROAS, slower spend)
7. **Increase testing budget** (create new variants while main recovers)

---

## Attribution Diagnosis

### When ROAS Looks Great but Sales Slow

**Investigation Path:**

1. **Check attribution window:** Is it 1-day or 7-day?
   - 1-day = under-reports cross-channel attribution
   - 7-day = over-reports paid credit vs. organic
   - **Fix:** Use 1-day window for Meta, 7-day for Google Shopping

2. **Check pixel dupe:** Are you double-counting purchases?
   - View Events Manager → Data Quality tab
   - Look for duplicate Purchase events
   - **Fix:** Implement deduplication in Conversions API

3. **Check last-click bias:** Does your ROAS only count last-click conversions?
   - Indirect traffic (organic, email) not being attributed
   - **Fix:** Use Ads Manager conversion settings to check attribution model

4. **Check mobile app conversions:** iOS 14.5+ devices under-reporting
   - App events not visible; web events captured only
   - **Fix:** Use Conversions API (more reliable on iOS)

---

## Breakeven ROAS Calculation

### Formula

```
Breakeven ROAS = (1 + Platform Fee %) / Gross Margin %

Example:
  Product cost: $20
  Selling price: $50
  Gross margin: ($50 - $20) / $50 = 60%
  Platform fee: 5% (Stripe + shipping)

  Breakeven ROAS = (1 + 0.05) / 0.60 = 1.75x
```

### Profitability Tiers

| ROAS | Status | Action |
|------|--------|--------|
| <Breakeven | Losing money | Kill immediately |
| Breakeven to +20% | Marginal | Test only, don't scale |
| +20% to +50% | Profitable | Scale cautiously |
| +50%+ | Highly profitable | Scale aggressively |

### Example Profitability Scenarios

**Scenario 1: E-commerce with 40% margin**
- Breakeven ROAS: 1.05 ÷ 0.40 = 2.625x
- Targeting: 3.0-3.5x ROAS (healthy buffer)
- Safe scaling: When ROAS >3.0

**Scenario 2: Info product with 80% margin**
- Breakeven ROAS: 1.05 ÷ 0.80 = 1.3125x
- Targeting: 1.8-2.5x ROAS (healthy buffer)
- Safe scaling: When ROAS >1.8

**Scenario 3: Low-margin commodity with 15% margin**
- Breakeven ROAS: 1.05 ÷ 0.15 = 7.0x
- **This product likely not profitable on paid ads** (target wholesale, B2B)

---

## Seasonal Attack Periods

### Q4 (Oct-Dec): Highest ROI Period

**Budget Allocation:** 40-50% of annual paid ad spend
**Creative Strategy:** Gift-focused, urgency, scarcity
**Scaling:** Aggressive 20% daily increases
**ROAS Target:** 2.5x+ (can drop to 2.0 during peak)

---

### Q1 (Jan-Mar): Resolution & Resolution Crash

**Jan-Feb:** New Year dieting, fitness, productivity surge
**Budget:** 20% normal spend (higher ROAS expected)
**ROAS Target:** 2.0-2.5x

**Mar:** Post-resolution crash, spend drops
**Budget:** 10% normal spend (fatigue visible)
**Action:** Pause lower-performing campaigns; test new angles

---

### Q2-Q3: Summer Slump

**Budget:** 15% normal spend (traffic down, competition up)
**Creative:** Seasonal angles (Father's Day June, Back-to-School Aug)
**ROAS Target:** 1.8-2.2x

---

## Reference Files

See `/references/` folder for detailed guides:
- `optimize-daily-monitoring.md` — Expanded daily checklist templates
- `optimize-testing-methods.md` — Complete testing methodology library
- `optimize-kill-scale-matrix.md` — Platform-specific kill/scale decision trees
- `optimize-benchmarks.md` — Industry benchmarks by vertical
- `optimize-scaling-playbook.md` — Scaling formulas and case studies
- `optimize-retargeting.md` — Retargeting audience library and budget models
- `optimize-diagnostics.md` — Full diagnostic flowcharts
- `optimize-breakeven.md` — Breakeven calculator and profitability analysis
- `optimize-naming-conventions.md` — Campaign naming SOP and reporting templates
