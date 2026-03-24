---
name: Scale Plan
description: Scaling roadmap that asks platform, current spend/ROAS, target spend. Outputs scaling method, budget increase schedule, guardrails, and safety checks.
---

# Scaling Roadmap Generator

## Step 1: Current Campaign Status

**Platform:** [Meta / Google / Both]
**Campaign Name:** [Campaign name]
**Current Daily Spend:** $[___]
**Current ROAS:** [___]x
**Days Running:** [___ days]
**Blended CPA vs. Target:** [___% above/below target]
**Current Frequency:** [___]x (Meta only)

---

## Step 2: Scaling Goal

**Target Daily Budget:** $[___]
**Timeline:** [Weeks / Months]
**Total Increase Needed:** [Calculate from Step 1]

**Example:**
- Current: $200/day
- Target: $1,000/day
- Increase needed: $800 (+400%)
- Over: 4 weeks
- Daily increase: ~$200/week or 10%/day

---

## Step 3: Scaling Method Selection

**What type of scaling is best for your situation?**

### Option A: Vertical Scaling Only
**Best for:** Single winning campaign, tight budget, <$500/day spend
**Method:** Increase budget on same campaign incrementally
**Risk:** Audience saturation faster
**Expected ceiling:** 3-5x original budget
→ Go to Step 4a

### Option B: Horizontal Scaling Only
**Best for:** Multiple proven creatives, larger budget, multi-product
**Method:** Launch duplicate campaigns with different audiences
**Risk:** More management, cannibalization between campaigns
**Expected ceiling:** 2-3x via duplication
→ Go to Step 4b

### Option C: Hybrid Scaling (Recommended)
**Best for:** Most accounts $2,000+ monthly budget
**Method:** Vertical + Horizontal combined
**Risk:** Requires active management
**Expected ceiling:** 5-10x original (higher potential)
→ Go to Step 4c

---

## Step 4a: Vertical Scaling Plan

**Current Daily Spend:** $[___]
**Target Daily Spend:** $[___]
**Scaling Duration:** [___ weeks/days]

### 10% Daily Increase Strategy (Recommended)

```
Day 1: $[current spend]
Day 5: $[current] × 1.10 = $[new]
Day 10: $[previous] × 1.10 = $[new]
Day 15: $[previous] × 1.10 = $[new]
...continuing until target reached

TIMELINE TO TARGET:
Current: $[___]
Target: $[___]
Days needed: [Calculate: log(target/current) / log(1.10)]
Weeks needed: [Divide by 7]
```

### Daily Scaling Checklist:

**Every 3-5 days (Increase day):**
- [ ] Check 3-day average ROAS (must be >1.5x breakeven)
- [ ] Check CPA trend (must be stable ±10%)
- [ ] Check frequency (must be <3.0x)
- [ ] Increase budget by 10%
- [ ] Monitor 3 days before next increase

**Daily (Non-increase days):**
- [ ] Monitor spend pacing (should be 1/7 of weekly)
- [ ] Alert if ROAS drops >0.2 from average
- [ ] Alert if CPA spikes >20%
- [ ] Check top 5 creatives performance
- [ ] Document in scaling log

### Safety Guardrails:

**PAUSE Scaling If:**
- ROAS drops below 1.3x breakeven for 2 consecutive days
- CPA spikes >30% above rolling average
- Frequency exceeds 3.5x with declining conversions
- Account quality score drops to "Fair"
- Campaign re-enters Learning Phase unexpectedly

**STOP Scaling If:**
- ROAS falls below 1.0x breakeven (losing money)
- CPA 2x target for 3+ days
- Can't maintain daily increases (audience capped)
- Budget reaches $[industry limit for vertical scaling, e.g., 3-5x original]

### Scale Ceiling:

**Expected saturation point:** [Calculate: 3-5x original budget]

When you hit this, switch to → **Horizontal Scaling** (launch duplicates)

---

## Step 4b: Horizontal Scaling Plan

**Current Daily Spend:** $[___]
**Target Daily Spend:** $[___]
**Main Campaign Status:** [Proven? >14 days running? ROAS stable?]

### Duplication Strategy:

```
PHASE 1 (Week 1): Establish Main Campaign
  Main Campaign: $[current] → $[increase 10%]

PHASE 2 (Week 2): Identify Winning Creatives
  Main Campaign: $[previous] (monitoring top creatives)
  Top Creative: __ (ROAS ___)

PHASE 3 (Week 3): Launch Duplicate 1
  Main Campaign: $[X] (continue scaling 10%)
  Duplicate 1: $[Y] = 50-70% of Main
  (Monitor both for audience overlap)

PHASE 4 (Week 4): Launch Duplicate 2 (Optional)
  Main Campaign: $[X] (continue 10% scaling)
  Duplicate 1: $[Y] (continue 10% scaling)
  Duplicate 2: $[Z] = 50% of Duplicate 1
  (Watch for cannibalization)

EXPECTED RESULT:
Week 1: $[current]
Week 2: $[current × 1.1]
Week 3: Main $[X] + Dup1 $[Y] = $[Total]
Week 4: Main $[X×1.1] + Dup1 $[Y×1.1] + Dup2 $[Z] = $[Total]
```

### Duplication Audience Strategy:

**Duplicate 1 Targeting:**
- If main: 1-2% lookalike → Try 2-3% lookalike
- If main: Interest-based → Try lookalike 1%
- If main: Open targeting → Try interest-targeted

**Duplicate 2 Targeting:**
- If main: Lookalike → Try broad interest (15M+)
- If main: Interest → Try different interest
- If main: Open → Try demographic-specific

### Cannibalization Monitoring:

```
If Main ROAS drops >10% after launching Duplicate:
  → Likely competing for same audience
  → ACTION: Change Duplicate targeting
  → OR: Pause Duplicate for 7 days

If total conversions from both < expected from Main alone:
  → Audience split, not additive
  → ACTION: Modify Duplicate audience
  → OR: Create separate creative for Duplicate

If both maintain ROAS >1.5x breakeven:
  → Healthy scaling, continue
  → Expect Duplicate @ 60-70% of Main performance
```

### Scale Ceiling:

**Expected max duplicates:** 3 campaigns total
- Main: 100% of original ROAS
- Duplicate 1: 70% of original ROAS
- Duplicate 2: 50% of original ROAS
- Beyond 2: Diminishing returns + management overhead

---

## Step 4c: Hybrid Scaling Plan (Vertical + Horizontal)

**This combines both strategies for maximum growth with managed risk.**

### Month-by-Month Timeline:

```
MONTH 1 (Weeks 1-4): Vertical Only
Week 1: Main $[X]
Week 2: Main $[X × 1.1]
Week 3: Main $[X × 1.21]
Week 4: Main $[X × 1.33]
Month 1 Total: $[X × 1.21] (21% growth)
Status: Main campaign proven, creative validated

MONTH 2 (Weeks 5-8): Vertical + Horizontal Launch
Week 5: Main $[X × 1.46] + Dup1 $[X × 0.73] = $[Total]
Week 6: Main $[X × 1.61] + Dup1 $[X × 0.80] = $[Total]
Week 7: Main $[X × 1.77] + Dup1 $[X × 0.88] = $[Total]
Week 8: Main $[X × 1.95] + Dup1 $[X × 0.97] = $[Total]
Month 2 Total: ~$[X × 2.92] (192% month 1 → month 2 growth)
Status: Duplicate performing at 60-70% Main = healthy

MONTH 3 (Weeks 9-12): Aggressive Hybrid
Week 9: Main $[X × 2.14] + Dup1 $[X × 1.06] + Dup2 $[X × 0.53] = $[Total]
Week 10: Main $[X × 2.36] + Dup1 $[X × 1.17] + Dup2 $[X × 0.59] = $[Total]
Week 11: Main $[X × 2.59] + Dup1 $[X × 1.29] + Dup2 $[X × 0.65] = $[Total]
Week 12: Main $[X × 2.85] + Dup1 $[X × 1.42] + Dup2 $[X × 0.71] = $[Total]
Month 3 Total: ~$[X × 5.98] (Doubled from month 2)
Status: 3 campaigns running optimally
```

### Decision Gates (Mandatory Checks):

**Before Increasing Main Budget:** ✅
- [ ] ROAS >1.5x breakeven for 3+ consecutive days
- [ ] CPA stable ±10% (not inflating)
- [ ] Frequency <3.0x
- [ ] Account quality score = Good/Excellent
- [ ] No red flags in daily monitoring

**Before Launching Duplicate:** ✅
- [ ] Main campaign running 14+ days
- [ ] Main ROAS stable >1.5x for 7+ days
- [ ] Creative not showing fatigue (hold rate stable)
- [ ] Duplicate audience is clearly different from Main
- [ ] Have backup creative ready if Duplicate underperforms

**Before Continuing Scaling (Weekly):** ✅
- [ ] Blended ROAS across all campaigns >1.5x breakeven
- [ ] Total CPA within target ±15%
- [ ] No campaign showing ROAS <1.3x
- [ ] Account not showing red flags

---

## Step 5: Weekly Scaling Checklist

**Every Sunday (Scaling Review):**

- [ ] **Spend Pacing:** Are you on track for week's budget target?
- [ ] **ROAS Health:** Is blended ROAS stable? Any drops?
- [ ] **CPA Trend:** Is CPA trending up (red flag) or stable?
- [ ] **Frequency:** Any campaigns exceeding 3.5x?
- [ ] **Creative Health:** Are top 3 creatives still performing?
- [ ] **Scale Decision:** Should I increase budget tomorrow?
  - YES if: ROAS >target, CPA stable, frequency low
  - NO if: ROAS declining, CPA inflating, frequency high
  - HOLD if: Data insufficient (need 3+ more days)

**Every Thursday (Adjustment Check):**

- [ ] Check for any alerts from daily monitoring
- [ ] Any campaigns showing red flags?
- [ ] Any creatives hitting kill threshold?
- [ ] Need to pause anything before weekend?

---

## Step 6: Scaling Troubleshooting

### Problem: Budget increased but ROAS flat
**Diagnosis:** Reaching audience saturation
**Solution:**
1. Pause vertical scaling for 7 days
2. Expand targeting (remove interest exclusions)
3. OR launch horizontal duplicate
4. Monitor: If ROAS recovers after 7 days → Audience was capped

### Problem: Duplicate campaign underperforms (20% vs expected 70%)
**Diagnosis:** Audience mismatch or cannibalizing Main
**Solution:**
1. Check: Is Duplicate audience clearly different from Main?
2. If yes → Creative issue, test new hook
3. If no → Change Duplicate targeting entirely
4. OR pause Duplicate for 14 days, relaunch with new audience

### Problem: Scaling halted (can't increase anymore)
**Diagnosis:** Audience exhaustion at this budget level
**Solution:**
1. Pause 7 days (audience reset)
2. Relaunch at 50% current budget
3. Introduce new creative hook
4. OR expand to new placements/platforms
5. OR test new audience layers

---

## Step 7: Success Metrics

### Scaling Win Condition:

```
✅ Target daily budget reached and sustained
✅ ROAS maintained >1.5x breakeven throughout scaling
✅ CPA remained stable ±15% (no inflation)
✅ Frequency never exceeded 4.0x
✅ Account quality score stayed "Good" or better
✅ No campaign had to be killed during scaling
```

### Scaling Milestone Tracking:

| Week | Budget | ROAS | CPA | Campaigns | Status |
|------|--------|------|-----|-----------|--------|
| 1 | $[___] | [__]x | $[__] | Main | On track ✅ |
| 2 | $[___] | [__]x | $[__] | Main | On track ✅ |
| 3 | $[___] | [__]x | $[__] | M+D1 | On track ✅ |
| 4 | $[___] | [__]x | $[__] | M+D1+D2 | On track ✅ |

---

## Next Steps

- **Need daily monitoring guidance?** → `/optimize-campaigns` skill
- **Campaign underperforming, need audit?** → `/audit-campaign` command
- **Need more creatives for scaling?** → `/write-ad` or `/create-meta-traditional`
- **Strategic planning for platform?** → `/strategy-meta` or `/strategy-google` skill
