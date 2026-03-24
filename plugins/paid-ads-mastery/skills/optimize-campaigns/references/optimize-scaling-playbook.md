# Scaling Playbook

## Vertical Scaling (Budget Increases on Single Campaign)

**Definition:** Increase daily budget on a performing campaign
**Best For:** Campaigns with stable ROAS for 7+ days
**Risk Level:** Low (conservative growth)
**Expected Saturation Point:** 3-5x original budget

### The 10% Rule

**Primary Scaling Rule:** Increase budget by exactly 10% every 3-5 days when ROAS is healthy

```
Example Campaign: $200/day at ROAS 2.1

Day 1-2: $200 (baseline)
Day 3-4: $200 (confirm stable)
Day 5: Increase 10% → $220
Day 6-7: $220 (monitor)
Day 8: Check ROAS. If >2.0 → Increase 10% → $242
Day 9-10: $242 (monitor)
Day 11: Check ROAS. If >2.0 → Increase 10% → $266
Continue 10% increases every 3-5 days until:
  - ROAS drops below 1.5x breakeven (scale stop)
  - Campaign shows signs of fatigue (pause and refresh)
  - Budget reaches $1,000+ (switch to horizontal scaling)
```

### When NOT to Follow 10% Rule (Adjust Scaling Speed)

**Speed Up: 15-20% increases** when:
- ROAS consistently >2.5x for 14+ days
- CPA declining or flat (no inflation)
- Frequency <2.0
- You have backup creatives ready (hedge against fatigue)

**Slow Down: 5% increases** when:
- ROAS within 20% of breakeven
- CPA trending up 10-15%
- Frequency trending up 0.3+/day
- Competition indicators (CTR declining)

**Stop Scaling** when:
- ROAS drops below 1.5x breakeven
- Frequency >3.5x with declining conversions
- CPA >2x target
- Account showing fatigue signals (hold rate dropping on video)

---

## Horizontal Scaling (Duplicating Campaigns)

**Definition:** Create 2-3 exact copies of winning campaign with variations
**Best For:** When main campaign is capped or nearing saturation
**Risk Level:** Medium (audience overlap, cannibalization)
**Expected Return:** Duplicate 1 = 70% of original, Duplicate 2 = 50%, Duplicate 3 = 30%

### Duplication Strategy

**When Main Campaign Reaches $500-700/day:**

```
MAIN CAMPAIGN: $500/day at ROAS 2.2
  ├─ DUPLICATE 1: Launch at $250/day (estimate 70% = ROAS 1.54)
  │   └─ 3-5 days later, scale DUPLICATE 1 to $350/day
  │
  └─ DUPLICATE 2: Launch at $250/day (estimate 50% = ROAS 1.1)
      └─ Only if MAIN + DUP1 combined stable for 7 days
      └─ 5-7 days later, monitor for cannibalization

EXPECTED RESULT:
Week 1: MAIN $500 + DUP1 $250 = $750 total
Week 2: MAIN $550 + DUP1 $350 = $900 total
Week 3: MAIN $605 + DUP1 $385 + DUP2 $250 = $1,240 total
```

### Duplication Do's and Don'ts

**DO:**
- Duplicate when main campaign is proven (>14 days, stable ROAS)
- Launch duplicate at 50% of main budget
- Use DIFFERENT audience layers (lookalike 1% vs 2-3%, or different demographics)
- Wait 5-7 days between launches (prevent account saturation shock)
- Keep main budget scaling during duplication phase

**DON'T:**
- Duplicate too early (main must have >7 days stable data)
- Launch duplicates at same budget as main (causes competition for same audience)
- Create >3 duplicates (diminishing returns kick in)
- Duplicate failing campaigns (will just lose more money)

### Cannibalization Check

**How to Know if Duplicates are Cannibalizing:**

1. **Total Spend Increased but Total Conversions Flat**
   - MAIN: 50 conversions
   - MAIN + DUP1: 70 conversions (expected 75+ with 70% rule)
   - Signal: 15% cannibalization
   - Action: Adjust audience targeting or pause DUP1 for 7 days

2. **Main Campaign ROAS Drops When Duplicate Launched**
   - MAIN: ROAS 2.2 → drops to 2.0 after DUP1 launch
   - Signal: Competing for same audience
   - Action: Change DUP1 audience (age, location, interest) OR pause DUP1

3. **Total ROAS (Blended) Declines Below Target**
   - MAIN ($500): ROAS 2.2 = $1,100 revenue
   - DUP1 ($250): ROAS 1.5 = $375 revenue
   - Total: $750 spend, $1,475 revenue = ROAS 1.97 (below 2.0+ target)
   - Action: Pause DUP1, focus on vertical scaling MAIN only

---

## Hybrid Scaling (Vertical + Horizontal Combined)

**Definition:** Scale both main campaign AND launch duplicates simultaneously
**Best For:** Accounts with $2,000+ monthly budget and 2-3 proven creatives
**Risk Level:** Medium (requires close monitoring)

### Hybrid Scaling Timeline

```
WEEK 1: Vertical Only (Build momentum on main)
  Main: $200/day
  Budget: $1,400 weekly

WEEK 2: Vertical + Horizontal Launch
  Main: $220/day (10% increase)
  Duplicate 1: $150/day (new launch at 68% of current main)
  Budget: $2,590 weekly (+85%)

WEEK 3: Scale Both
  Main: $242/day (10% increase)
  Duplicate 1: $200/day (33% increase)
  Budget: $3,094 weekly (+20% from Week 2)

WEEK 4: Add Testing Campaign
  Main: $266/day
  Duplicate 1: $250/day
  Test Campaign: $100/day (new creatives or audiences)
  Budget: $4,556 weekly (+47% from Week 3)

MONTH GOAL ACHIEVED: $700+/day from original $200
```

### Safety Gates for Hybrid Scaling

Before launching Duplicate while still scaling Main:

- [ ] Main campaign has 14+ days of stable ROAS >1.5x breakeven
- [ ] Creative has been running 21+ days (fatigue detection clear)
- [ ] Account quality score is "Good" or "Excellent"
- [ ] CPA has been stable ±10% for 7+ days
- [ ] Have backup creative ready (if main needs refresh)
- [ ] Test budget allocation: 20% of total spend going to new creatives

---

## Scaling by Campaign Type

### Catalog/DPA Scaling (Meta)

**Best Method:** Vertical + Horizontal hybrid
**Scaling Speed:** Conservative (audience fatigue faster)
**Budget Increase Frequency:** Every 5 days instead of 3

```
Optimal Timeline:
Week 1: $100/day main
Week 2: $110/day main
Week 3: $121/day main + $80/day duplicate = $201 total
Week 4: $133/day main + $110/day dup = $243 total
Month End: $200+/day combined (2x start)
```

### Interest/Lookalike Scaling (Meta)

**Best Method:** Horizontal (Crazy Method / Interest Duplication)
**Scaling Speed:** Aggressive (different audiences don't cannibalize)
**Budget Increase Frequency:** Every 3 days

```
Optimal Timeline:
Day 1: Interest A - $100/day (run 3-5 days)
Day 5: Interest B - $100/day (best performing audience from A)
Day 9: Interest C - $100/day (similar to B)
Week 2: Pause bottom 2, scale winner to $300/day
Result: $300/day on best audience in 14 days
```

### Shopping Campaign Scaling (Google)

**Best Method:** Vertical (bid increases) + Horizontal (product additions)
**Scaling Speed:** Conservative (data collection slower on Google)
**Timeline:** 7-14 day cycles

```
Week 1: 20 products, $300/day, Manual CPC $0.30-0.50
Week 2: Add 10 new products (30 total), increase bids $0.05 avg
Week 3: Remove underperforming 5 products (25 total), scale winners
Month End: 25 products optimized, $600/day spend
```

### Performance Max Scaling (Google)

**Best Method:** Vertical first, then horizontal with new asset groups
**Scaling Speed:** Moderate (need 14+ days learning phase)
**Timeline:**

```
Week 1-2: Campaign in Learning Phase (expect ROAS 1.5-2.0)
  → No scaling during learning
  → Only test asset changes

Week 3-4: Post-learning phase, ROAS stabilizes
  → If ROAS >2.0 → Increase budget 20%
  → If ROAS 1.5-2.0 → Hold, test new asset group in parallel

Week 5: If parallel asset group ready
  → Launch second PMax campaign (same targeting, different assets)
  → Scale both if profitable
```

---

## Seasonal Scaling Attack Periods

### Q4 (September - December): Aggressive Growth Season

**Budget Increase:** 40-50% of total annual ad spend
**Scaling Speed:** Fastest (20% daily increases acceptable)
**ROAS Target:** 2.0x+ (can drop to 1.5x during peak Black Friday)
**Strategy:** Vertical scaling heavily, launch new campaigns weekly

```
September: Normal spend ($1,000/day)
October: +25% ($1,250/day, start holiday creatives)
November (Black Friday prep): +50% ($1,500/day, multiple campaigns)
Late November (Black Friday): +100% ($2,000/day, all systems go)
December (Holiday): +100% ($2,000/day, through Dec 23)
Dec 24-31: Scale back to normal ($1,000/day)
```

### Q1 (January - March): Resolution Surge + Crash

**Budget Increase:** January +20%, February Normal, March -30%
**Scaling Speed:** Moderate in Jan (opportunities there), cautious in Mar
**ROAS Target:** 2.2x+ in Jan-Feb, 1.8x+ in Mar

```
January (New Year): Scale aggressively (fitness, productivity, courses)
  → Budget +25% from Q4 baseline
  → Expect ROAS 2.5x+ (high intent audience)

February: Hold spend steady
  → Resolution momentum starts fading
  → ROAS stabilizing to 2.0-2.2x

March: Begin scaling back
  → Budget -20% from Feb
  → ROAS dropping to 1.8-2.0x
  → Audience fatigue evident
```

### Q2-Q3 (April - August): Summer Slump

**Budget Decrease:** -25% from Q1
**Scaling Speed:** Conservative (test new audiences instead)
**ROAS Target:** 1.8-2.0x

**Strategy:** Don't scale aggressively; use for testing:
- New creative formats
- New audience tiers
- New product launches
- New platform testing (TikTok Ads, Pinterest)

```
April: $750/day (seasonal content shift)
May: $700/day (if underperforming)
June: $750/day (Father's Day spike)
July: $700/day (summer decline)
August: $800/day (back-to-school prep)
```

---

## Cost-Benefit of Scaling Strategies

### Vertical Scaling ROI

| Method | Speed | Risk | Audience Fatigue | Best For |
|--------|-------|------|------------------|----------|
| 5% increments | Very Slow | Very Low | Minimal | Conservative brands |
| 10% increments | Moderate | Low | Low | Most campaigns |
| 15% increments | Fast | Medium | Medium | High ROAS campaigns |
| 20%+ increments | Very Fast | High | High | Limited time (seasonal) |

### Horizontal Scaling ROI

| Approach | Cannibalization | Setup Time | Scaling Ceiling | Best For |
|----------|-----------------|-----------|-----------------|----------|
| Duplicate same audience | 20-30% | 2 days | Medium | Quick scaling |
| Duplicate new audience | 5-10% | 3-5 days | High | Long-term growth |
| New creative, same audience | 40%+ | 1 day | Medium | Creative refresh |
| New campaign type entirely | 0% | 5-7 days | High | Portfolio diversification |

---

## Scaling Troubleshooting

### Problem: Budget Increases But Revenue Flat

**Diagnosis:**
- Vertical scaling hitting audience saturation
- Same audience seeing same ad too many times
- Algorithm needs refresh signal

**Solution:**
- Pause vertical scaling for 7 days
- Launch horizontal duplicate with NEW audience layer
- Test new creative hook simultaneously
- If no improvement in 7 days: Account-level fatigue, reduce spend 20% and refresh all creatives

### Problem: Duplicate Campaign Underperforms (30% vs expected 70%)

**Diagnosis:**
- Different audience than main (intentional) but poor fit
- Cannibalizing main campaign (audience overlap)
- Main campaign attracting majority-quality traffic

**Solution:**
- Option 1: Pause duplicate, iterate main until plateau
- Option 2: Change duplicate targeting (age +5 years, different interest)
- Option 3: Use duplicate for testing new creatives (accept 30% performance)

### Problem: Scaling Paused Because of High Frequency

**Diagnosis:**
- Audience too small for current budget
- Same people seeing ad 4-5+ times daily
- Creative fatigue inevitable

**Solution:**
- Increase frequency cap to force algorithm to find new people (counterintuitive)
- OR expand targeting (add adjacent interests, wider age)
- OR launch duplicate with different audience entirely
- OR pause 3 days then relaunch at lower frequency

