# Meta Cost Caps & Bid Caps Strategy

## Overview
- **Cost Cap:** Maximum price per result (purchase, lead, etc.)
- **Bid Cap:** Maximum price per click (used with manual CPC only)
- **When to use:** Cost Cap is primary tool; Bid Cap is manual bidding backup
- **Purpose:** Control spending, prevent runaway costs, protect against algorithm overspend

---

## COST CAP vs BID CAP

### Cost Cap (Primary - Recommended)

**What it does:**
- Sets maximum amount Facebook will spend per conversion/result
- Example: Cost cap $25 = Facebook won't pay more than $25 per purchase
- Facebook will reduce bids internally to hit your cap
- If no sales can be found at cap price, spend may be $0 for the day

**How it works:**
```
Cost Cap: $25
Expected sales per day: 10
Maximum daily spend: 10 × $25 = $250

Actual patterns:
- Day 1: 8 sales × $25 = $200 (under budget)
- Day 2: 12 sales × $25 = $300 (over daily budget cap if daily limit exists)
- Day 3: 5 sales × $25 = $125 (under)
```

**Best for:**
- CBO (Campaign Budget Optimization) campaigns
- Protecting against overspend on tight margins
- Predictable cost structure
- Any pixel trained on conversion events

**Drawback:**
- May limit scale (Facebook stops spending if can't hit cap at volume)
- If cap too tight, you get zero sales but under budget

### Bid Cap (Secondary - Manual Bidding)

**What it does:**
- Sets maximum amount Facebook will spend per click
- Only used with manual CPC (cost-per-click) bidding
- Example: Bid cap $1.00 = max $1 per click
- Facebook optimizes for clicks within this bid constraint

**How it works:**
```
Bid Cap: $1.00
Expected CTR: 2% (for $1,000 ad spend)
Clicks: $1,000 ÷ $1.00 = 1,000 clicks
Conversion rate: 5%
Sales: 1,000 × 5% = 50 sales
CPA: $1,000 ÷ 50 = $20
```

**Best for:**
- Manual bidding strategies (rare; MOB Strategy uses this)
- Direct control preference (less algorithmic freedom)
- Accounts that understand their CTR/conversion rate relationship

**Drawback:**
- CPA isn't directly controlled (depends on conversion rate)
- Less effective than cost cap for direct conversion optimization
- Requires deeper understanding of CTR behavior

---

## COST CAP STRATEGY (3-TIER TESTING)

### Tier 1: Aggressive Cost Cap (20% Below Target)

**Setup:**
```
Target CPA: $25
Aggressive Cap: $20 (20% below target)

Meaning: Spend $20 max per purchase, not a penny more
```

**Expected behavior:**
- Very tight control; won't overspend
- Limited volume (Facebook can't find $20 sales at scale)
- Budget not fully utilized
- Cost efficiency: High
- Scale potential: Low
- ROAS: Likely 2.5+ (cheap traffic only)

**When to use:**
- Testing phase (want to validate before scaling)
- Tight margin products (can't afford high CPA)
- Micro-budget testing ($50-100/day)
- Finding absolute lowest-cost traffic

**Risk:**
- May get zero sales if cap too restrictive
- Underutilizes budget

**Example Daily Pattern:**
```
Day 1: 4 sales × $20 = $80 (of $200 daily budget)
Day 2: 3 sales × $20 = $60
Day 3: 6 sales × $20 = $120
Average: 4-5 sales/day; cost controlled but volume low
```

### Tier 2: Balanced Cost Cap (At or Slightly Above Target)

**Setup:**
```
Target CPA: $25
Balanced Cap: $26-27 (at or 5-10% above target)

Meaning: Spend up to $26-27 per purchase
```

**Expected behavior:**
- Good balance of scale and efficiency
- Budget mostly utilized
- Cost fairly predictable
- Scale potential: Medium-good
- ROAS: Likely 2.0-2.3

**When to use:**
- Primary strategy for most campaigns
- Standard budgets ($200+/day)
- Mature accounts with stable metrics
- Production campaigns (not testing)

**Advantage:**
- Allows some flexibility (slightly above target) to find scale
- Still protects against overspend
- Best balance for most situations

**Risk:**
- If target CPA calculated wrong, inefficient
- May give algorithm too much freedom (can hit cap daily)

**Example Daily Pattern:**
```
Day 1: 8 sales × $26.50 = $212
Day 2: 9 sales × $26.50 = $238.50
Day 3: 7 sales × $26.50 = $185.50
Average: 8 sales/day; predictable budget spend
```

### Tier 3: Loose Cost Cap (20-30% Above Target)

**Setup:**
```
Target CPA: $25
Loose Cap: $30-32 (20-30% above target)

Meaning: Spend up to $30-32 per purchase; more freedom
```

**Expected behavior:**
- Maximum volume/reach
- Cost higher but achieves scale
- Budget fully utilized
- Scale potential: High
- ROAS: Likely 1.8-2.2 (paying for volume)

**When to use:**
- Scaling phase (proven ROAS, want volume)
- MOB Strategy (uses loose caps for volatility)
- High-ticket products ($1,000+ AOV; can afford higher CPA)
- Seasonal campaigns (demand high; can pay premium)

**Advantage:**
- Achieves maximum volume
- Algorithm has flexibility to scale
- Finds edge-case audiences

**Risk:**
- Spending can exceed expectations
- CPA creep upward
- If used wrong, wasteful spending

**Example Daily Pattern:**
```
Day 1: 12 sales × $30 = $360
Day 2: 15 sales × $30 = $450
Day 3: 11 sales × $30 = $330
Average: 12-13 sales/day; higher volume, higher spend
```

---

## 3-TIER TESTING METHODOLOGY

### Running All Three Tiers Simultaneously

**Setup:**
```
Campaign A: [Aggressive] Tier 1 - $20 cap
Campaign B: [Balanced] Tier 2 - $26 cap
Campaign C: [Loose] Tier 3 - $30 cap

Same creative, same audience, different cost caps
Daily budget: $200 each ($600 total)
Runtime: 14 days
```

**What to measure:**

| Metric | Tier 1 | Tier 2 | Tier 3 |
|--------|--------|--------|--------|
| **Total Spend** | $1,500-2,000 | $2,500-3,000 | $3,500-4,000 |
| **Total Sales** | 75-100 | 95-130 | 130-170 |
| **Average CPA** | $18-22 | $22-28 | $24-30 |
| **ROAS** | 2.5-3.5 | 1.8-2.5 | 1.5-2.2 |
| **Scale Stability** | Volatile (few sales) | Stable | Very stable |

### Decision Matrix After 14 Days

**Scenario A: All tiers performing 2.0+ ROAS**
- **Winner:** Tier 3 (loose cap)
- **Reason:** Highest volume = most revenue, even if lower ROAS
- **Action:** Adopt Tier 3 as primary; pause Tier 1
- **Result:** 40% more volume than Tier 2

**Scenario B: Tier 2 beats both**
- **Winner:** Tier 2 (balanced)
- **Reason:** Sweet spot between volume and efficiency
- **Action:** Adopt Tier 2 as primary; pause Tier 1 & 3
- **Result:** Best efficiency-to-volume ratio

**Scenario C: Tier 1 dramatically outperforms (3.5+ ROAS vs 2.0)**
- **Winner:** Tier 1 (aggressive cap)
- **Reason:** Massive efficiency; maybe audience loves this cap price
- **Action:** Adopt Tier 1 but test increasing budget (maybe low volume issue)
- **Result:** Very profitable but may need more budget to scale

**Scenario D: Wide variation (1.5 to 3.0 ROAS across tiers)**
- **Diagnosis:** Cost cap itself isn't the lever; likely creative or audience issue
- **Action:** Fix creative/audience first; then re-test tiers
- **Result:** Different creative may change tier preference

---

## WHEN TO ADJUST COST CAPS

### Increase Cost Cap If:
- ✓ Budget not being fully spent (under-utilization)
- ✓ Want higher volume/scale
- ✓ ROAS is still 2.0+ (have room to pay more)
- ✓ CPA trending upward (means algorithm wants higher bids)

**How to increase:**
```
Current: Cost cap $25, spending $150/day of $200 budget
Action: Increase to $27 (10% bump)
Result after 3 days: Check if spending increases to $180+

If yes: Good, algorithm found more inventory
If no: Maybe $27 still too tight; try $30
```

### Decrease Cost Cap If:
- ✓ CPA consistently hitting cap ceiling
- ✓ ROAS declining below target
- ✓ Want more cost efficiency
- ✓ Budget constraints (need lower spend)

**How to decrease:**
```
Current: Cost cap $30, CPA averaging $29
Action: Decrease to $26 (13% reduction)
Result after 3 days: Check if CPA improves, volume drops

Expected trade-off: Lower CPA, fewer sales
```

### DO NOT adjust if:
- ✗ Campaign just launched (need 7+ days of data)
- ✗ Had one bad day (variance; don't react)
- ✗ Creative just changed (need 3+ days new data)
- ✗ Seasonal variation (don't change during peak/trough)

---

## COST CAP SELECTION BY CAMPAIGN TYPE

| Campaign Type | Recommended Cap | Rationale |
|---|---|---|
| **Simple Method** | Target CPA + 10% | Needs some flexibility to scale open targeting |
| **Crazy Method** | Target CPA | Multiple assets; need tight control |
| **MOB Strategy** | Target CPA + 20% | Designed for loose caps; used with manual bidding |
| **Blender Method** | Target CPA | New pixels need cost control |
| **Lookalike Scaling** | Target CPA + 5% | Established audience; slight flexibility OK |

---

## COST CAP + DAILY BUDGET INTERACTION

**Important:** Cost cap and daily budget work together.

**Example:**
```
Daily Budget: $200
Cost Cap: $25
Expected Sales: 8 (if algorithm finds $25 sales)

Day 1: 8 sales × $25 = $200 (hits both cap and budget)
Day 2: 10 sales attempted; only 8 fit in budget
  - Algorithm picks 8 best sales at $25 = $200 spent
  - Misses 2 potential sales (budget constraint)
```

**If you want higher volume:**
- Increase daily budget first (not cost cap)
- Cost cap controls per-result price
- Daily budget controls total spend
- Both must increase for true scaling

---

## COMMON MISTAKES WITH COST CAPS

### Mistake 1: Cost Cap Too Tight (Below Profit)
```
Product profit: $30 per sale
Cost cap set to: $10

Problem: Impossible. You'd need 3x volume to maintain profit.
Result: Algorithm can't find $10 sales; zero spend.
Fix: Set cost cap at 50-70% of your profit margin, not 25%
```

### Mistake 2: Adjusting Cap Too Frequently
```
Day 1: ROAS 1.8; increase cap from $25 to $28
Day 2: ROAS 1.5; decrease cap back to $25
Day 3: ROAS 1.9; increase again to $28

Problem: Constant changes prevent algorithm from optimizing.
Result: Algorithm never settles; worse overall performance.
Fix: Change cost cap once per week minimum; give 7 days between adjustments.
```

### Mistake 3: Misunderstanding Cap as Bid
```
Set Cost Cap $25 thinking: "Facebook will bid $25 per click"
Reality: Facebook bids whatever is needed to buy conversions at $25 cost goal.
Confusion: Why is CPC $3 if cap is $25? Because it takes 8 clicks to get 1 sale.
Fix: Remember: Cost Cap = per-conversion, not per-click.
```

### Mistake 4: Not Accounting for Test Budget
```
Daily Budget: $200
Cost Cap: $25
Expect: 8 sales at exactly $200

Reality: Algorithm uses ~20% of budget for testing other audiences/creatives.
Actual available: ~$160 for target
Result: Only 6-7 sales despite budget allowance.

Fix: Factor in algorithmic testing reserve; if want 8 sales, increase budget to $250.
```

---

## WHEN TO USE BID CAPS (MOB STRATEGY ONLY)

**Bid cap is used with manual CPC bidding, which is primarily for MOB Strategy:**

**Setup:**
```
Bidding: Manual CPC
Bid Cap: $1.50 (max per click)
Daily Budget: $300
Expected CTR: 2%
Expected clicks: 300 ÷ $1.50 = 200 clicks
Expected CPA: Depends on conversion rate (unknown in advance)
```

**Why this is risky:**
- You control bid but not cost per result
- CPA depends on conversion rate you might not know
- If conversion rate is low, CPA explodes
- Better to use cost cap (direct result control)

**When BID CAP is necessary:**
- Manual bidding preference (rare)
- Testing to understand CTR/conversion relationship
- Complex attribution scenarios
- Very specific bid strategy requirements

**MOB Strategy exception:**
- MOB uses both: Cost cap + manual bidding + bid cap
- Gives maximum control for volatile spending strategy
- Requires expert account management

---

## TESTING FRAMEWORK

### Week 1: Find Baseline Cost Cap
- Run campaign with balanced tier cost cap (at target CPA)
- Measure CPA, ROAS, volume for 7 full days
- This is your baseline

### Week 2: Test Tier 1 & Tier 3
- Campaign 1: Tier 1 (20% below baseline cap)
- Campaign 2: Original baseline (control)
- Campaign 3: Tier 3 (20% above baseline cap)
- Run 7 days; measure all three

### Week 3: Decision & Scaling
- Identify winner tier
- Adopt winner
- Pause losers
- Scale winner at 10% daily

---

## KEY TAKEAWAYS

1. **Cost cap = per-conversion maximum spend** (most important control)
2. **Bid cap = per-click maximum** (only for manual CPC; rarely used)
3. **3-tier testing = find optimal cap** for your account
4. **Aggressive cap = low volume, high efficiency**
5. **Loose cap = high volume, lower efficiency**
6. **Balanced cap = best for most situations**
7. **Increase cap for scale; decrease cap for efficiency**
8. **Never adjust cap based on one day** (wait 7 days minimum)
9. **Cost cap + daily budget control total spend** (both matter)
10. **Test tiers simultaneously** to find winner faster
