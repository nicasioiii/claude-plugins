---
name: Meta Ads Campaign Strategy
description: Meta/Facebook/Instagram campaign methodologies including Simple Method, Crazy Method, MOB Strategy, Blender Method, CBO vs ABO selection, scaling rules, optimization frameworks, attribution windows, audience targeting, cost caps, bid caps, and budget allocation. Use when planning Meta campaign structure, choosing a methodology, or making scaling decisions.
---

# Meta Ads Campaign Strategy

## Quick Navigation
- **Choosing a Methodology** → See Decision Tree below
- **Detailed SOP** → Reference files in `references/`
- **Scaling decisions** → See Scaling & Bell Theory section
- **Campaign setup questions** → See Campaign Structure section

---

## METHODOLOGY DECISION TREE

**Start here: What's your account maturity?**

### IF Account < 1 year old + New/Weak Pixel
→ Use **Blender Method** ([read full guide](./references/meta-blender-method.md))
- Combine lookalikes + interests for hybrid reach
- 1% lookalike (Purchase) + 1% lookalike (Add-to-Cart) + core interests
- Enable "Detailed Targeting Expansion" for new pixels only if trained; keep OFF for brand new pixels
- Creates 2.5M+ reach on smaller starting audiences

**Else IF:**  Account 1-2 years + Trained pixel + One working interest/audience
→ Use **Crazy Method** ([read full guide](./references/meta-crazy-method.md))
- Duplicate proven interest 30-50x in single CBO campaign
- Budget: $100-1,000/day across all duplicates
- Increases luck surface area for finding "hot pockets" within same audience
- Do NOT run 6+ Crazy Method campaigns simultaneously with identical creatives (cannibalization)

**Else IF:** Account 2+ years + Very strong trained pixel + High volume
→ Use **Simple Method** ([read full guide](./references/meta-simple-method.md))
- Single high-budget campaign with open targeting (demographics only, no interests)
- Catalog campaigns with dynamic product ads (DPA)
- 10% daily scaling after Learning Phase exit
- Minimum spend: (Target CPA × Desired sales) / Days
- Example: $15 CPA × 50 sales ÷ 7 days = $107 minimum daily

**Else IF:** Need cost control + volatile spend OK + Very trained pixel
→ Use **MOB Strategy** ([read full guide](./references/meta-mob-strategy.md))
- Manual bidding, ABO (Ad Set Budget), 1-day attribution
- Set cost caps 0.2-0.3 above target ROAS (accounts for daily variance ±0.2-0.3)
- Can run $1,000+ budgets with cost control; volatile daily spend ($977 → $7K possible)
- Best as supplementary strategy (adds 25-35% extra revenue alongside other campaigns)
- Requires 50+ assets; only 5-7 profitable

**Else IF:** Multiple lookalike sources + Want to combine them smartly
→ Use **Stacked Lookalike Method** ([read full guide](./references/meta-scaling-logic.md))
- Stack 1% Purchase + 1% Add-to-Cart + 1% Website Visitors at same tier
- Never mix 1% + 10% (small starves)
- Broader reach than single lookalike, quality higher than pure interests

---

## CAMPAIGN STRUCTURE FUNDAMENTALS

### CBO vs ABO: When to Use Each

| Aspect | CBO (Campaign Budget Optimization) | ABO (Ad Set Budget) |
|--------|----------------------------------|-------------------|
| **When** | Simple Method, Crazy Method, testing phase | MOB Strategy, manual bidding, budget control |
| **Budget control** | Facebook allocates across ad sets automatically | You control exact spend per ad set |
| **Best for** | Algorithmic optimization of multiple audiences | Predictable spending, manual bidding |
| **Scaling risk** | Lower (FB optimizes automatically) | Medium (depends on your bidding discipline) |

**Rule:** Don't mix CBO + ABO in same campaign. Choose one structure and commit.

### Learning Phase Management
- **What it is:** Facebook requires ~50 purchases before full optimization (varies by objective)
- **Cost impact:** Higher CPA/CPM during this phase
- **Exit criteria:** 7 days with 50+ conversions, stable ROAS readings
- **Re-entry risk:** Budget increases >20% in one jump, major targeting changes, or daily scaling interruptions can force re-entry
- **Minimize risk:** Scale 10% daily (not 20%+), use cost caps, avoid frequent pauses

**Bell Theory Connection:** [See meta-scaling-logic.md](./references/meta-scaling-logic.md) — The Learning Phase is the first "bell" (difficulty peak); scaling creates new bells

### Optimization Event Selection
**CRITICAL RULE:** Always optimize for your bottom funnel event, not traffic

| Event | Quality | When to Use |
|-------|---------|------------|
| **Purchase** | Highest (most data about buyers) | Any e-commerce account |
| **Value** | High (tracks actual $ spent) | When pixel is trained on value events |
| **Add-to-Cart** | Medium | Rare; only if purchases too sparse |
| **Lead** | Medium | Lead gen / SaaS |
| **Traffic** | Lowest (just clicks, no commitment) | NEVER; wastes budget |

**Why it matters:** Meta has 3x more historical data on purchasers than clickers. Platform learns better from purchase behavior.

### Attribution Windows & 1-Day vs 7-Day

**Post-iOS 14.5 Environment (Current):**
- **7-day attribution:** More data, less volatile, easier to read trends
  - Use: Stable, mature campaigns; large budgets; trend analysis
  - Drawback: Lags behind reality

- **1-day attribution:** More volatile, but real-time accuracy
  - Use: MOB Strategy; testing new ideas; cash-constrained accounts
  - Drawback: Daily variance ±20-30% normal

**Recommendation:** Start with 7-day for stable reading. Switch to 1-day only if using MOB Strategy.

---

## TARGETING FRAMEWORKS

### Open Targeting (No Interests)
**Requirements (ALL must be true):**
- 2+ years account history
- Very strong trained pixel (understands full buyer journey)
- Mature audience (100M+ potential reach in target country)
- Demographics-only targeting: Age/Gender/Location
- Example reach: 100M+ people with age/gender targeting alone

**Advantage:** Massive scale potential, algorithm has most freedom
**Risk:** Poor accounts or weak pixels will burn budget on bad traffic
**Only use if:** Your numbers are good AND pixel is proven

### Interest Targeting (Detailed Targeting)
**Safe approach for most accounts:**
- 3-8 core interests that define your customer
- Keep interests 500K-20M range (don't mix tiny 50K with 100M interests)
- Enable "Detailed Targeting Expansion" only if pixel is trained; leave OFF for new pixels
- Test interest sizing: Broad interests (Entertainment, Family, 30M+) vs Narrow (10M range)

**Lookalike Rules:**
- Window: 180-day (captures seasonal patterns)
- Percentage: 1% for trained pixels; 5% for smaller countries (EU)
- Stack lookalikes only at same tier (don't mix 1% + 5%)
- Best source: Purchase events (most predictive)

### Audience Exclusions (Whom NOT to Target)
- Always exclude: Past customers (retarget separately), email list (if you have it)
- Never exclude: Interests that might contain customers (too restrictive)
- Test exclusions: If excluding "already bought," measure impact over 2 weeks

---

## BUDGET ALLOCATION & ROAS LOGIC

### Know Your Numbers (MANDATORY BEFORE SCALING)

Calculate these before running ANY campaign:

| Metric | Formula | Example |
|--------|---------|---------|
| **Profit Margin %** | (AOV - Cost) / AOV × 100 | ($80 - $30) / $80 = 62.5% |
| **Break-Even ROAS** | 1 / Profit Margin % | 1 / 0.625 = 1.6 ROAS |
| **Target ROAS (with buffer)** | Break-Even ROAS × 1.3-1.5 | 1.6 × 1.3 = 2.1 ROAS |
| **Safe Minimum ROAS** | Anything below this = unprofitable | 2.0+ (with 30% buffer) |

**Meaning:**
- At 1.6 ROAS: You make $0 profit (all margin consumed)
- At 2.0 ROAS: You make 20-30% profit (small but sustainable)
- At 3.0+ ROAS: You make 50%+ profit (ideal scaling zone)

**If numbers don't work:**
- AOV < $40: Won't scale (margin too tight)
- Cost > AOV - $25: Unviable (margins too low)
- Fix this FIRST, then run ads

### Scaling Rules & Daily Loop Theory

**10% Daily Scaling (Default Safe Rule)**
- Increase budget 10% every day IF performance stable
- Example: $150 → $165 → $182 → $200 → $220 (5 days)
- Why 10%? Reduces re-entry risk while reaching scale
- When it breaks: ROAS drops 20%+, CPA rises sharply, spend inconsistent

**20% Weekly Scaling (Aggressive)**
- Increase budget 20% once per week, not daily
- Only use if account is battle-tested and ROAS consistent
- Higher re-entry risk; don't use during Learning Phase

**Saturation Detection** (When to pause scaling)
- CPA rising week-over-week (5%+ increase per week)
- ROAS dropping (target 2.0 → trending 1.8 → 1.6)
- Cost Per Click (CPC) rising (indicates audience fatigue)
- Reach plateau (same # people targeted but lower performance)

### Bell Theory & Daily Loop Theory

**Bell Theory:** Every scaling creates new difficulty peaks
- Initial phase (sales at lower budget) = first "bell"
- Scaling to 2x = second bell (harder to maintain ROAS)
- Scaling to 3x = third bell
- Each requires different strategy; expect performance dips

**Daily Loop Theory:** Spend patterns create opportunity
- Morning: Cheaper traffic, lower initial bid response
- Evening: Higher demand, bid wars accelerate
- Run campaigns continuously; daily optimization cycles create patterns
- Track morning (8am-12pm) vs evening (4pm-8pm) performance separately

**Pie Theory:** Market share is fixed pie
- 100% of market demand per category is fixed
- As you scale 1 campaign, you eat into available demand
- Eventually hit saturation (can't go 10x regardless of budget)
- Counter: Introduce new creative angles, audiences, or product line

**Seasonal Attack Periods:** Exploit demand spikes
- Holiday season: 30-50% ROAS improvements possible
- Back-to-school: 20-30% boosts
- New Year: Diet/fitness products spike
- Plan 2-3 months ahead; pre-test creatives before surge

---

## COST CAPS & BID CAPS STRATEGY

**Cost Cap (Primary Tool)**
- Sets maximum cost per result (purchase, lead, etc.)
- Example: Cost cap $25 = max $25 per purchase
- Use when: Pixel is trained, you know your target CPA
- Benefit: Hard ceiling on spend efficiency; volatility lower
- Drawback: May limit scale (FB stops spending at limit)

**Bid Cap (Secondary Tool)**
- Sets maximum per-click bid (if using manual CPC)
- Example: Bid cap $1.50 = max $1.50 per click
- Use when: Manual bidding (MOB Strategy primarily)
- Benefit: Precise budget control
- Drawback: Less algorithmic freedom; CPA will be higher

**3-Tier Cost Cap Testing** [See meta-cost-caps.md](./references/meta-cost-caps.md)
1. **Tier 1 (Aggressive):** Cost cap 20% below target CPA
   - Example: Target $25 CPA → Set $20 cap
   - Result: Tight control, limited scale

2. **Tier 2 (Balanced):** Cost cap at target CPA (or 10% above)
   - Example: Target $25 CPA → Set $26-27 cap
   - Result: Good balance of scale + efficiency

3. **Tier 3 (Loose):** Cost cap 20-30% above target CPA
   - Example: Target $25 CPA → Set $30-32 cap
   - Result: Maximum scale, lower efficiency

**Test all three simultaneously; see which scales best without destroying ROAS.**

---

## ANTI-PATTERNS & WHAT NOT TO DO

| Anti-Pattern | Why It Fails | What to Do Instead |
|---|---|---|
| Scaling 20%+ daily | Re-enters Learning Phase constantly | Use 10% daily scaling |
| Running 6+ Crazy Method campaigns with same asset | Cannibalization destroys performance | Max 2-3 duplicated campaigns simultaneously |
| Mixing CBO + ABO in same campaign | Conflicting optimization logic | Pick one; commit |
| Optimizing for Traffic instead of Purchase | Algorithm has poor buyer data | Always optimize for bottomfunnel event |
| Switching audiences daily | Prevents Learning Phase; wastes data | Run 7+ days minimum before changes |
| Using 28-day attribution | iOS 14.5 reality: only see 7-day | Use 7-day or 1-day; 28-day is fantasy |
| Building lookalikes from add-to-cart only | Weak signal; include purchases | Use Purchase Lookalike primary |
| Testing 20 audiences at once on small budget | Starves all audiences | Test 2-3 audiences max; let each get 50+ conversions |

---

## QUICK REFERENCE: FORMULAS & NUMBERS

**Crazy Method Asset Count Formula:**
```
Number of Assets = Daily Spend ÷ Target Cost Per Purchase
Example: $200/day ÷ $30 CPA = 6-7 assets
```

**Simple Method Minimum Daily Budget:**
```
Minimum = (Target CPA × Desired Sales) ÷ Days
Example: ($15 CPA × 50 sales) ÷ 7 days = $107/day
```

**Learning Phase Expected Cost:**
```
Learning Cost ≈ 50 conversions × (150% of target CPA)
Example: 50 × ($25 × 1.5) = $1,875 to exit
```

**Saturation Signal Thresholds:**
- CPA increase: >5% week-over-week = investigate
- ROAS drop: >10% from peak = consider pause
- CPC increase: >15% consecutive days = audience fatigue
- Reach plateau: Same audience reach, declining conversions = scaling limits

---

## NEXT STEPS: DETAILED REFERENCES

Each methodology has a complete SOP in the `references/` folder:

1. **[meta-simple-method.md](./references/meta-simple-method.md)** — Complete Simple Method workflow with budget calc, daily scaling, monitoring checklist

2. **[meta-crazy-method.md](./references/meta-crazy-method.md)** — Crazy Method asset requirements, hot pockets theory, when to duplicate

3. **[meta-mob-strategy.md](./references/meta-mob-strategy.md)** — MOB setup, manual bidding best practices, cost cap vs bid cap, supplementary positioning

4. **[meta-blender-method.md](./references/meta-blender-method.md)** — Blender audience combinations, expansion settings, new pixel training

5. **[meta-stacked-lookalike.md](./references/meta-stacked-lookalike.md)** — Stacking multiple lookalikes, sizing rules, when each audience tier works

6. **[meta-scaling-logic.md](./references/meta-scaling-logic.md)** — Full scaling formula, saturation detection, Bell Theory, Daily Loop Theory, Pie Theory, seasonal attack planning

7. **[meta-cost-caps.md](./references/meta-cost-caps.md)** — Cost cap vs bid cap strategy, 3-tier testing methodology, when to adjust caps

---

## For Help With:
- **"My pixel isn't trained"** → See [meta-blender-method.md](./references/meta-blender-method.md)
- **"Should I scale?"** → See [meta-scaling-logic.md](./references/meta-scaling-logic.md)
- **"ROAS dropped 20%"** → Check saturation signals above + [meta-scaling-logic.md](./references/meta-scaling-logic.md)
- **"When to kill a campaign?"** → See Kill Criteria in [meta-scaling-logic.md](./references/meta-scaling-logic.md)
- **"Budget control matters"** → Use MOB Strategy; see [meta-mob-strategy.md](./references/meta-mob-strategy.md)
