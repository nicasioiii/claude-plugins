# Meta MOB Strategy (Manual Bidding + Cost Control)

## Overview
- **Name:** MOB = "Mother of Bombs" (developed strategy using manual bidding)
- **Structure:** ABO (Ad Set Budget) + Manual Bidding + Cost Caps + 1-day attribution
- **Risk Level:** High volatility, but cost is controlled
- **Daily Spend Pattern:** Volatile ($977 one day, $7K next, $2K next)
- **Role:** Supplementary scaling (adds 25-35% extra revenue alongside other campaigns)
- **Requires:** Very trained pixel; 50+ assets minimum; checking 2-3x daily

---

## WHEN TO USE MOB STRATEGY

### DO USE if:
✓ Pixel has 500+ conversions (very trained)
✓ You want cost control (hard ceiling on maximum spend)
✓ Can check account 2-3x daily (volatility requires monitoring)
✓ Using as supplementary strategy (not main campaign)
✓ Have 50+ assets available (most will fail; need volume)
✓ AOV is $100+ (can absorb higher cost structures)
✓ Want to find edge cases where aggressive bidding works

### DON'T USE if:
✗ Pixel < 200 conversions (not trained enough)
✗ Can't monitor daily (volatility unmanaged = overspend)
✗ Need budget predictability (you won't get it)
✗ Running as only campaign (too risky; use Simple or Crazy instead)
✗ Account has fewer than 20 assets
✗ Have strict daily budget limits (MOB will fluctuate)

---

## CAMPAIGN SETUP (ABO + MANUAL BIDDING)

### Campaign Level
1. **Campaign Name:** "[MOB] [Target] - [Date]" (Example: "[MOB] Value Optimization - 03-06-2026")
2. **Campaign Objective:** Conversions
3. **Campaign Budget Optimization (CBO):** DISABLED (use ABO instead)
4. **Daily Budget:** Set at Ad Set level, NOT campaign (each ad set gets own budget)

### Ad Set Level (ABO Structure)
1. **Ad Set Name:** "Manual Bidding - [Optimization] - [Audience]"
   - Example: "Manual Bidding - Value - All Interests"
2. **Daily Budget (Ad Set Level):** $200-500 per ad set
3. **Audience:**
   - Targeting: Your proven audiences (interests, lookalikes, or broad demographics)
   - Can create multiple ad sets (one per audience) to test
4. **Placements:** All enabled
5. **Optimization Event:** Choose one:
   - **Value Optimization** (preferred if pixel trained on value)
   - **Conversions** (fallback if pixel not trained on value)
6. **Bidding:** MANUAL (critical setting)
7. **Attribution Window:** 1-day click (critical to MOB strategy)

### Manual Bidding Configuration

**Two Approaches:**

**Approach 1: Cost Per Result (Cost Cap)**
1. **Bid Type:** Cost Per Result (Manual)
2. **Cost Cap:** Set at target CPA or cost per value goal
   - Example: Target $25 CPA → Set $25-30 cost cap
   - **Safety rule:** Never set cap below target CPA (defeats purpose)
3. **Daily Budget (per ad set):** $200-500 (volatility will vary actual spend)
4. **Result:** Facebook will try to hit your cost cap; spend will fluctuate wildly

**Approach 2: Bid Per Result**
1. **Bid Type:** Bid Per Result
2. **Manual Bid:** Set at ~70% of target CPA
   - Example: Target $25 CPA → Bid $17-20 per result
3. **Daily Budget:** $200-500
4. **Result:** May not spend full budget if Facebook can't hit your bid at volume

**Recommendation:** Start with Approach 1 (Cost Cap). Easier to understand spend control.

### Cost Cap Setting (Critical Decision)

**What Cost Cap Does:**
- Facebook will not spend MORE than this per result
- But Facebook CAN spend LESS
- Daily spend will be: (Sales at cost cap) × Cost cap
- If no sales found at cost cap, spend may be $0 for the day

**Cost Cap Options:**

| Setting | Cost Cap Value | Spend Pattern | Best For |
|---------|---|---|---|
| **Aggressive** | 20% below target CPA | Very cheap, but low volume | Low-budget testing |
| **Balanced** | At target CPA | Good balance | Primary MOB campaign |
| **Loose** | 20-30% above target CPA | Higher spend, lower restrictions | Maximum scale |

**Examples:**

```
Target CPA: $25

Aggressive Setup:
- Cost Cap: $20
- Expected: 5-15 sales/day, spend $100-300/day
- Risk: Very inconsistent

Balanced Setup:
- Cost Cap: $25-27
- Expected: 10-25 sales/day, spend $250-675/day
- Best choice for most accounts

Loose Setup:
- Cost Cap: $30-32
- Expected: 20-40 sales/day, spend $600-1,280/day
- Maximum volume but less efficient
```

---

## ROAS TARGET SETTING (VALUE OPTIMIZATION)

**For Value Optimization (preferred approach):**

1. **Calculate Target ROAS:**
   - Profit Margin: (AOV - Cost) / AOV
   - Example: ($80 - $30) / $80 = 62.5%
   - Break-Even ROAS: 1 / 0.625 = 1.6
   - Target ROAS: 1.6 × 1.3 = 2.1

2. **Set Control ROAS (with variance buffer):**
   - Facebook has ±0.2-0.3 daily variance
   - Add buffer: Target 2.1 + buffer = 2.3-2.5 control ROAS
   - Set in campaign: "Target ROAS 2.3-2.5"

3. **Cost Cap as Backup:**
   - Also set cost cap (insurance policy)
   - Cost Cap: AOV ÷ Target ROAS = $80 ÷ 2.5 = $32
   - If value optimization fails, cost cap catches it

**Why the buffer matters:**
- Real ROAS fluctuates daily 0.2-0.3 points
- Without buffer, you're constantly hitting/exceeding target
- Buffer allows algorithm room to optimize

---

## ASSET REQUIREMENTS

**MOB Strategy needs VOLUME:**
- Minimum: 20 assets
- Recommended: 50+ assets
- Why: Most will fail (normal). Only 5-7 will be profitable.
- Expected outcome: $0-300 spend on losers; $11K+ on winners

**Real Case Study:**
- 50 assets across MOB campaigns
- Total spend: $440K
- Profitable assets: 7
- Loser assets: 43 (spend between $0-$300 each)
- Winner assets: $11K-50K each

**Asset Variety Strategy:**
- Mix of video and static images
- Different hooks and copy angles
- Different audiences (if running multiple ad sets)
- Goal: Find outlier assets that work with aggressive bidding

---

## DAILY MONITORING & MANAGEMENT

### Daily Check (2-3x per day recommended)

**Morning (8am):**
- [ ] Check overnight spend (how much was spent?)
- [ ] Check daily spend so far (e.g., 9am = 4 hours passed, spent $X?)
- [ ] Is it on track for budget, or wildly off?
- [ ] Any negative ROAS signs?

**Midday (12pm):**
- [ ] Check spend at 50% point of day (by 12pm, what % of budget spent?)
- [ ] If already spent 80% of daily budget by noon, alert for overspend
- [ ] Are sales coming in consistent?

**Evening (5pm):**
- [ ] Check daily total at this point
- [ ] If ROAS dropping below 1.3, consider pause for next day
- [ ] Identify top-spending assets (are they profitable?)

**Night (Review before next day):**
- [ ] What was total daily spend?
- [ ] What was ROAS?
- [ ] Which assets were profitable?
- [ ] Decide: Continue tomorrow, pause campaign, or adjust cost cap?

### Weekly Review

- [ ] Calculate 7-day ROAS
- [ ] Identify profitable assets (which got >$500 spend AND positive ROAS?)
- [ ] Identify loser assets (which got $0-100 spend? Kill those.)
- [ ] Check cost cap effectiveness (are we hitting cap limit? Adjust if needed.)
- [ ] Decide if campaign should continue or be paused

---

## VOLATILITY PATTERNS

**Why MOB Has Volatile Spending:**

1-day attribution window means:
- Facebook only guarantees reporting within 24 hours
- If day has no sales, little/no spend
- If day has many sales, can spend entire budget in hours
- Next day: Completely different pattern

**Real Daily Spend Example:**
```
Day 1: $6,400 (12 sales × $533 average cost)
Day 2: $977 (2 sales × $488 average cost)
Day 3: $7,000 (14 sales × $500 average cost)
Day 4: $2,150 (4 sales × $537 average cost)
Day 5: $5,800 (11 sales × $527 average cost)
```

**Pattern Analysis:**
- Some days hit many sales; others few
- Cost per result fairly stable (~$500-530)
- Total spend varies wildly ($977 to $7K)
- **This is NORMAL.** Not a problem.

**Expected Variance:**
- ±50% daily variance is normal
- ±20% weekly variance is normal
- If exceeding ±100% daily, cost cap may be too loose

---

## KILL CRITERIA (When to Pause MOB Campaign)

**Kill if:**
✗ ROAS drops below 1.2 for 2+ consecutive days
✗ Cost cap being hit daily (customers finding too expensive) → lower cost cap
✗ Spending $0 for 3+ days (audience exhausted)
✗ CPA trending upward consistently week-over-week

**Pause (don't kill) if:**
- One bad day (volatility; give it 2 days to recover)
- Just started (need 10-14 days data)
- Asset changes being tested (changes cause dips; wait 3 days)

---

## SUPPLEMENTARY POSITIONING (Why MOB is Add-On, Not Main)

**Real Case Study: $440K Account**
- Simple Method Campaign: $300K spend, $950K revenue, ROAS 3.17
- Crazy Method Campaigns: $120K spend, $312K revenue, ROAS 2.6
- MOB Strategy: $40K spend, $153K revenue, ROAS 3.8
- **Total:** $440K spend, $1,415K revenue

**Insight:**
- MOB added 25-35% extra revenue without main campaigns suffering
- MOB ROAS was highest (3.8) but volume was lowest
- MOB worked as supplementary edge case, not replacement

**Why MOB is Supplementary:**
- High volatility requires daily monitoring (not passive)
- Limited reach (same audiences as main campaigns)
- Better used for finding edge cases than primary volume
- Adding 5-10 MOB campaigns alongside 2-3 Simple/Crazy campaigns = total optimization

---

## MOB vs SIMPLE METHOD vs CRAZY METHOD

| Aspect | MOB | Simple Method | Crazy Method |
|--------|-----|--------------|--------------|
| **Automation** | Manual bidding | Automatic | Automatic |
| **Stability** | Volatile spend | Predictable | Somewhat predictable |
| **Monitoring** | 2-3x daily | 1x daily | 1x daily |
| **Role** | Supplementary | Primary | Primary/Scaling |
| **Risk** | High (volatility) | Medium | Medium |
| **ROAS Potential** | 3.5-4.5 | 2.0-3.0 | 1.8-2.5 |
| **Setup time** | 30 min | 30 min | 1 hour |
| **Best for** | Edge case finding | Catalog scale | Proven asset scale |

---

## TROUBLESHOOTING

### Problem: Spending $0 some days
**Diagnosis:** Cost cap too tight; Facebook can't find sales at your cost cap
**Solution:**
1. Increase cost cap by 10-15% (e.g., $25 → $28)
2. Give it 2-3 days; if still $0, increase more
3. If still fails, audience exhausted; pause campaign

### Problem: ROAS 1.5 Week 1, now 0.8 Week 2
**Diagnosis:** Audience saturation or cost cap too loose (spending on bad traffic)
**Solution:**
1. Check: Is cost cap being hit (Facebook saying "at cap limit")? If yes, lower cap.
2. Check: Are winning assets still winning? Or did they flip to losers?
3. If assets flipped: Creative fatigue; replace creative and try again
4. Pause 2 days; algorithm may need reset

### Problem: Cost cap not being applied (spending more than cap)
**Diagnosis:** Facebook may have set it as suggestion, not hard limit
**Solution:**
1. Verify cost cap is set as "Cost Per Result - Manual" (not automatic)
2. Check campaign settings; confirm cap is saved correctly
3. May need to pause and recreate campaign with manual settings
4. Test with lower cost cap to force compliance

### Problem: Only 5 assets getting all the spend
**Diagnosis:** Normal. Rest are losers. Keep them in campaign (they reduce bid pressure)
**Solution:** This is working as designed. Don't kill the 45 losers. Let them sit at $0 spend. Only 5-7 assets should win with MOB.

---

## KEY TAKEAWAYS

1. **MOB = Manual Bidding + ABO + Cost Caps + 1-day attribution**
2. **Spend is wildly volatile** ($977 to $7K daily is normal)
3. **Cost caps prevent overspend** but may limit scale
4. **Supplementary strategy** = adds 25-35% on top of main campaigns
5. **Requires daily monitoring** 2-3x per day (not passive)
6. **Expected asset performance:** 5-7 winners, 45 losers = success
7. **ROAS potential is highest** (3.5-4.5) but volume is lower
8. **Buffer in ROAS targets** to account for ±0.2-0.3 daily variance
9. **Only 1-2 MOB campaigns** alongside main campaign; more = cannibalization
10. **Kill fast** if ROAS < 1.2 for 2+ days; don't let it bleed budget
