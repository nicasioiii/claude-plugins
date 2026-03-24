# Meta Blender Method - Audience Combination Strategy

## Overview
- **Purpose:** Cost-efficient hybrid targeting for new or struggling pixels
- **Core Concept:** Layer lookalikes + interests together for expanded reach
- **When to use:** New pixel + new account, OR nothing else is working
- **Risk:** Medium (less proven than Simple or Crazy)
- **Best for:** Bootstrap-phase accounts trying to find first hot pockets

---

## CORE PRINCIPLE

**The Problem:** New pixels don't have enough conversion data to make lookalikes work alone. Pure interest targeting limits reach.

**The Solution:** Blend lookalikes + interests together so each compensates for the other's weakness:
- **Lookalikes:** Quality signal but limited reach (need data)
- **Interests:** Large reach but lower quality
- **Blended:** Interests fuel initial conversions → lookalike learns → reach expands

---

## AUDIENCE STRUCTURE (US vs EUROPE)

### US Market (Large Audience)
```
Primary Layer: Lookalikes (STACKED)
├─ 1% Lookalike (Purchase, 180-day window)
└─ 1% Lookalike (Add-to-Cart, 180-day window)

Secondary Layer: Core Interests
├─ Interest 1 (3M-10M range)
├─ Interest 2 (3M-10M range)
└─ Interest 3 (3M-10M range)

Detailed Targeting: CHECKED for expansion (if pixel trained)
Expected Reach: 2.5M+ people
```

**Why 1% lookalikes:**
- 1% gives ~180K-500K people per lookalike (depending on country)
- Two 1% lookalikes = 500K total reach combined
- Large enough to get initial sales; small enough to be quality

**Why interests 3M-10M:**
- Balances with lookalike reach
- If you add 50M interest to 500K lookalike, 50M wins all budget
- Comparable size = budget distributed to both

### Europe Market (Smaller Audience)
```
Primary Layer: Lookalikes (STACKED)
├─ 5% Lookalike (Purchase, 180-day window)
└─ 5% Lookalike (Add-to-Cart, 180-day window)

Secondary Layer: Core Interests
├─ Interest 1 (2M-8M range)
├─ Interest 2 (2M-8M range)
└─ Interest 3 (2M-8M range)

Detailed Targeting: CHECKED for expansion (only if very trained pixel)
Expected Reach: 1M-1.5M people
```

**Why 5% for Europe:**
- Fewer total users; lookalikes smaller at 1%
- 5% lookalike = ~40K-100K reach (still meaningful)
- Two 5% lookalikes = ~200K combined
- Interests must be comparable size (2M-8M range)

---

## CRITICAL AUDIENCE SIZING RULE

**Rule: Don't mix different-sized interests**

**Wrong Setup:**
```
Lookalike 1%: 500K
Interest 1: 50M
Result: Budget goes 99% to Interest; Lookalike gets starved
```

**Correct Setup:**
```
Lookalike 1%: 500K
Interest 1: 5M (same size tier)
Interest 2: 8M (same size tier)
Result: Budget distributed evenly across all three
```

**Size Tiers (Keep these separate):**
- **Tier 1:** 500K-2M (small interests; use with 1% lookalikes)
- **Tier 2:** 2M-10M (medium interests; use with 1-5% lookalikes)
- **Tier 3:** 10M-30M (large interests; use with 5-10% lookalikes)
- **Tier 4:** 30M+ (massive interests; only with open targeting)

---

## CAMPAIGN SETUP

### Campaign Level
1. **Campaign Name:** "[Blender] [Audience 1 + Audience 2] - [Date]"
   - Example: "[Blender] Purchase 1% + Fitness Interest - 03-06-2026"
2. **Campaign Objective:** Conversions
3. **Campaign Budget Optimization (CBO):** Enabled
4. **Daily Budget:** $200-400/day (Blender usually takes longer; don't be too tight)
5. **Bid Strategy:** Automatic

### Ad Set Level
1. **Ad Set Name:** "Blender - Lookalikes + Interests"
2. **Targeting Stack (Add all together):**
   - **Saved Audience 1:** Purchase Lookalike 1% (180-day window)
   - **Saved Audience 2:** Add-to-Cart Lookalike 1% (180-day window)
   - **Interest 1:** [Core interest, 3M-10M range]
   - **Interest 2:** [Related interest, 3M-10M range]
3. **Detailed Targeting Expansion:**
   - **IF new pixel:** UNCHECKED (safer, smaller reach ~300K)
   - **IF trained pixel:** CHECKED (larger reach ~2.5M)
   - **IF unknown:** Start UNCHECKED; enable later if needed
4. **Locations:** Your primary country
5. **Age/Gender:** Based on buyer analysis
6. **Placements:** All enabled
7. **Optimization Event:** Conversions (safe; or Value if pixel trained)
8. **Attribution Window:** 7-day click

### Creative Requirements
- Use best-performing creatives from previous campaigns
- Can duplicate in Crazy Method style (optional)
- Single strong creative is sufficient

---

## DETAILED TARGETING EXPANSION EXPLAINED

**What it does:**
- Without expansion: Facebook shows ads to exactly matched audience (300K reach)
- With expansion: Facebook expands beyond exact match to similar people (2.5M reach)
- Expansion respects: Country + Age + Gender (won't go outside those bounds)
- Expansion ignores: Interests are just starting point; real targeting is "similar to these people"

**When to enable:**
- **New pixel:** UNCHECKED (no expansion; stay conservative)
- **100+ conversions:** Can test CHECKED; often helps
- **500+ conversions:** CHECKED is safe; pixel is trained enough

**Risk of expansion:**
- Trained pixel with expansion = great reach + quality
- Untrained pixel with expansion = reach explodes but traffic quality drops
- Example: New pixel, expansion ON = $40K spend, 2 sales, $20K CPA (bad)

---

## BLENDER METHOD PROGRESSION (WHEN TO ADVANCE)

**If Blender isn't working:**

```
Step 1: Start with SMALL INTERESTS
├─ Use 1-3 interests in 500K-3M range
├─ Stack with 1% lookalikes (no expansion)
└─ Run for 7 days; target 20+ conversions

Step 2: If Step 1 works
├─ Enable Detailed Targeting Expansion (now 2.5M reach)
├─ Keep interests same
└─ Scale budget 20% and run 7 more days

Step 3: If Step 2 works
├─ Replace pure interest layers with:
│  - 1% Lookalike only (most trained)
│  - 5% Lookalike
│  - 10% Lookalike (fully expanded)
└─ Remove interests entirely; now pure lookalike stack

Step 4: If Step 3 works
├─ Test open targeting (no interests, no lookalikes)
├─ Demographics only: Age/Gender/Location
└─ You've graduated from Blender to Simple/Crazy Method
```

**Progression Path Visual:**
```
Small Interests (500K) + 1% Lookalikes (no expansion)
        ↓ (If ROAS 1.5+)
Small Interests + 1% Lookalikes WITH expansion (2.5M)
        ↓ (If ROAS 1.5+)
1% + 5% + 10% Lookalikes (pure lookalike stack)
        ↓ (If ROAS 1.5+)
Open Targeting (demographics only)
        ↓ = Now ready for Simple/Crazy Method
```

---

## WHEN BLENDER WORKS WELL

### Scenario 1: New Account + New Pixel
- Account age: 0-6 months
- Conversions: 0-50
- Budget: $150-250/day
- **Use Blender:** Yes, perfect fit
- **Why:** Interests provide initial volume; lookalikes provide quality
- **Timeline:** 14-21 days to profitability
- **Upgrade path:** After 200+ conversions, move to Simple Method with open targeting

### Scenario 2: Account Existing + Stale Pixel
- Account age: 2+ years
- Conversions: None in last 6 months (dormant)
- Budget: $300-500/day
- **Use Blender:** Yes, as retraining vehicle
- **Why:** Account quality is intact; pixel just needs retraining
- **Timeline:** 10-14 days to profitability
- **Upgrade path:** After retraining, move to Simple Method

### Scenario 3: Niche Product + Cold Traffic
- Small audience (geographic constraint, niche interest)
- Normal audience: 2-5M total potential
- Budget: $100-200/day
- **Use Blender:** Maybe (but Crazy Method might work better)
- **Why:** Interest targeting ensures reach; lookalikes add quality
- **Timeline:** 14-21 days
- **Upgrade path:** Stay with Blender or move to Crazy Method with 30+ interest duplicates

---

## TROUBLESHOOTING BLENDER

### Problem: ROAS 1.2-1.5 (breakeven but not scaling)
**Diagnosis:** Either pixel is too weak OR interests are wrong
**Solution:**
1. Check pixel implementation (use Pixel Helper)
2. Swap interests: Try completely different 3M-10M interests
3. Try removing interests entirely; test 1% + 5% lookalikes only
4. Or: Increase budget 30% (sometimes needs volume to find pattern)

### Problem: Zero sales by Day 3
**Diagnosis:** Audience mismatch OR creative not resonating
**Solution:**
1. Verify creative is your best-performing version (not new test)
2. Check audience size (should see 20K+ impressions daily; if not, audience too small)
3. Lookalikes may not be built yet (takes 24-48 hours); give it Day 3-4
4. Increase budget 50% temporarily (might just need volume)

### Problem: Expansion didn't help (turned OFF → ON, ROAS dropped)
**Diagnosis:** Pixel not trained enough to handle expansion; expansion reaches bad traffic
**Solution:**
1. Turn expansion back OFF immediately
2. Run 7 more days with expansion OFF; accumulate 100+ conversions
3. Then retry expansion ON; pixel should be stronger
4. If still drops: Leave expansion OFF; your pixel may just not be trainable on lookalikes

### Problem: Interests are eating all budget; lookalikes ignored
**Diagnosis:** Interest size too large compared to lookalikes
**Solution:**
1. Check sizes: Lookalike 500K vs Interest 50M? That's mismatched.
2. Replace 50M interest with 5M-10M interest instead
3. Rebuild audience (pause → delete → recreate with correct sizing)
4. If still problematic: Remove interests; test pure lookalike stack (1% + 5% + 10%)

---

## BLENDER vs SIMPLE METHOD vs CRAZY METHOD

| Aspect | Blender | Simple | Crazy |
|--------|---------|--------|-------|
| **Maturity req'd** | New accounts OK | 2+ years | 1+ years |
| **Pixel training** | Light-to-medium | Heavy | Heavy |
| **Learning time** | 14-21 days | 7 days | 10-14 days |
| **Audience type** | Hybrid (lookalike + interest) | Open (demographics only) | Multiple (same interest duplicated) |
| **Risk** | Medium | Medium | Medium |
| **Setup complexity** | Medium (audience layering) | Low | High (50+ assets) |
| **When to use** | First-time, struggling | Mature catalog | Proven asset scaling |
| **Upgrade path** | → Simple Method | → Crazy Method | (final form) |

---

## BLENDER SUCCESS INDICATORS

✓ **Working if:**
- ROAS 1.5+ by Week 2
- 50+ conversions accumulated
- Can see interest audience getting picks (some spend distribution)
- Progression steps (small interests → expansion → lookalikes only) succeeding

✗ **Should be killed if:**
- ROAS < 1.2 after 21 days
- Still getting 0-5 sales/day after budget increases
- Interests and lookalikes both getting spend but low ROAS (audience quality poor)
- Pixel issues detected (no data recording)

---

## TRANSITION TO SIMPLE METHOD

**When you've mastered Blender:**

1. **After 500+ conversions in Blender campaign:**
   - Stop Blender
   - Create new Simple Method campaign (open targeting, no interests)
   - Age: Match Blender (demographic)
   - Budget: Match or 20% higher than Blender worked
   - Scale using Simple Method rules

2. **Expected difference:**
   - Blender: ROAS 1.8-2.2
   - Simple: ROAS 2.0-2.8 (usually higher due to better algorithm access)

3. **Duplication strategy:**
   - Keep Blender running if still profitable
   - Run Simple Method alongside
   - Eventually Simple will out-perform; then kill Blender
   - Use Simple as primary; Blender as supplementary

---

## KEY TAKEAWAYS

1. **Blender = Lookalikes + Interests layered together** for hybrid reach
2. **Sizing matters:** Don't mix 500K with 50M interests (small gets starved)
3. **Use 1% lookalikes for US; 5% for Europe** (accounts for audience size)
4. **Expansion should be unchecked for new pixels** (checked adds risk)
5. **Purpose is training ground** for moving to Simple/Crazy Method
6. **Progression path:** Small interests → Expansion ON → Lookalikes only → Open targeting
7. **Timeline: 14-21 days** to determine if it's working
8. **Upgrade to Simple Method** after 500+ conversions if ROAS sufficient
9. **Kill quickly** if ROAS < 1.2 after 3 weeks; don't let budget bleed
10. **Blender is bootstrap tool**, not long-term strategy
