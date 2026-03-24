---
name: Stress-Testing Assumptions & Second-Order Effects
---

# Stress-Testing Assumptions & Second-Order Effects

## Why Stress-Test?

A forecast is only as good as its assumptions. Stress-testing systematically challenges assumptions to find **hidden risks and second-order consequences** you might miss.

**Example of missed second-order effect:**
"We'll cut COGS 10% by switching to cheaper suppliers."
- First-order effect: ✓ COGS down 10%, margin up
- Second-order effect: ✗ Cheaper materials → more returns/chargebacks → customer service costs up 15%
- Third-order effect: ✗ Returns increase → damage to brand reputation → repeat purchase rate down 5%
- Net result: Margin improved less than expected, customer lifetime value declined

Stress-testing surfaces these hidden consequences **before** you commit to change.

---

## The Stress-Testing Process

### Step 1: Identify Critical Assumptions

List every major assumption in your forecast:

```
Revenue Assumptions:
- Customer acquisition: +25 new customers/month (rate continues from historical)
- Churn: 3% monthly (normal rate; no surprises)
- ARPU: $500/month per customer (stable; no price change)
- Seasonal adjustment: Q4 1.4x, Q1 0.7x (repeats historical pattern)

Cost Assumptions:
- COGS: 35% of revenue (supplier costs stable, no inflation)
- Labor: 6 FTE, $25/hour average (+4% annual raise)
- Rent: $4,000/month (locked 2-year lease)
- Marketing: $80K annually (current spend; ROI 3:1)

Execution Assumptions:
- No key staff departures
- No major system/product failures
- No regulatory changes
- Competitive intensity stays constant
```

### Step 2: Rank Assumptions by Impact

Which assumptions, if wrong, have the **biggest impact on net income**?

Use this framework:

```
Assumption                    If Wrong By:    Impact on Net Income
Customer acquisition          -10 customers  -$60K/year (10 customers × $500 × 12 months, less 35% COGS)
Churn rate                     +2% monthly   -$100K/year (12% annual vs. 36% baseline; customer loss)
ARPU                           -$50/customer -$30K/year revenue impact
Seasonal Q4 multiplier         -0.2x         -$80K/year (less revenue concentration)
COGS                           +2%           -$25K/year
Labor costs                    +20%          -$120K/year (6 FTE at $60K avg = $360K → $432K)
Rent increase                  +$500/month   -$6K/year
Competitive intensity          Increased     -$50K–100K (pricing pressure, CAC up, churn up)
```

**Priority assumptions (top 3 by impact):**
1. Customer acquisition and churn (combined $160K exposure)
2. Labor costs (+$120K exposure)
3. Competitive intensity (+$100K exposure)

**Focus your stress-testing on these.**

### Step 3: Stress Each Assumption

For each critical assumption, run a scenario:

**Format:**
```
ASSUMPTION: [Description]

BASE CASE: [What we assume]
Impact on forecast: [Quantified]

STRESS CASE 1: [Upside if assumption is better than expected]
Impact on forecast: [Quantified]

STRESS CASE 2: [Downside if assumption worse than expected]
Impact on forecast: [Quantified]

SECOND/THIRD-ORDER EFFECTS: [Ripple consequences]

EARLY WARNINGS: [What signals this assumption is wrong?]
```

**Example: Customer Acquisition Stress Test**

```
ASSUMPTION: Customer acquisition = +25 new customers/month

BASE CASE: +25 customers/month
Annualized new customers: 300
Total customers by EOY: 500 (starting 200)
Revenue from new customers: 300 × $500/month × 12 = $1.8M
Contribution: $1.8M × 65% (gross margin) = $1.17M gross profit

STRESS CASE 1 (Optimistic):
Marketing optimization improves CAC ROI by 15%
New customers: +29/month (+25%)
Annualized: 348 new customers
Revenue: $2.1M from new customers
Contribution: $1.37M gross profit (+$200K vs. base)

STRESS CASE 2 (Pessimistic):
Market saturation, CAC rises 30% (requires more ad spend to acquire same customers)
New customers: +19/month (-24%)
Annualized: 228 new customers
Revenue: $1.37M from new customers
Contribution: $0.89M gross profit (-$280K vs. base)

SECOND-ORDER EFFECTS:
If CAC rises (pessimistic): Sales/marketing staff may need to work smarter (efficiency squeeze, burnout risk)
If CAC drops (optimistic): Need to scale marketing operations (hiring, systems, training required)
If churn accelerates with higher CAC customers: LTV calculation changes (newer, lower-quality customers)

THIRD-ORDER EFFECT:
If churn rises due to lower-CAC customer quality:
- Repeat purchase rate declines 5%
- CLV drops $500 → $475/customer
- This compounds over time; retention becomes critical cost lever

EARLY WARNINGS:
- Monitor monthly customer acquisition trend (if declining 2+ consecutive months, assume saturation)
- Track CAC trend (if rising >5% MoM, market shifting)
- Monitor churn by customer cohort (if newer cohorts churn faster, quality issue)
- Competitor ad activity (if competitors raise spend, expect CAC pressure)

If acquisition drops below 20/month OR CAC exceeds $180, reforecast.
```

---

## Common Second and Third-Order Effects

### Pricing Changes

**Decision:** Raise prices 10%

**First-order effect:** Revenue up 10% (assuming no volume change)

**Second-order effect:** Customer volume down 5–8% (some customers defect)
- Net revenue: +2–5% (instead of +10%)

**Third-order effect:** Lower-value customers defect; higher-value customers remain
- Unit economics shift: mix changes, LTV increases but CAC relative to LTV declines
- Churn monitoring shows cohort-level variation

**Fourth-order effect:** Quality of customer base improves
- NPS may increase (better customers more satisfied)
- Referral rates may improve (high-value customers refer peers)

**Reforecasting checkpoint:** If actual volume down >10%, reforest margin assumptions (mix shift may not hold).

---

### Cost Reduction (COGS or Labor)

**Decision:** Reduce COGS 10% via cheaper supplier

**First-order effect:** COGS down, margin up 10%

**Second-order effects:**
- Product quality may decline slightly → returns increase 3–5%
- Chargebacks increase (cheaper payment processing)
- Customer service costs rise (handling complaints)

**Third-order effect:**
- Customer satisfaction (NPS) declines 5–10 points
- Churn increases 1–2%
- Repeat purchase rate down 5%
- CLV declines despite cost savings

**Net impact:** Margin improves less than expected; customer lifetime value declines.

**Stress test:** If returns increase by >5% (observable within 2 months), revert supplier change.

---

### Hiring or Staffing Changes

**Decision:** Hire 2 additional sales reps (cost +$120K/year)

**First-order effect:** Sales capacity increases; revenue up $300K (assumed productivity $150K per rep)

**Second-order effects:**
- Ramp-up time: New reps at 60% productivity month 1, ramping to 100% by month 4
- Actual Year 1 impact: 9 months of ramp = $180K revenue instead of $300K
- Onboarding costs (training, systems) add $20K

**Third-order effect:**
- New reps may displace existing reps in compensation (commissions, territories)
- Existing reps feel crowded; one departs
- Loss of top performer costs $200K in revenue

**Net Year 1 impact:**
- Expected: +$300K revenue, -$120K cost = +$180K net
- Actual: +$180K revenue - $120K cost - $20K onboarding + $200K loss from departing rep = -$160K (loss!)

**Stress test:** Before hiring, document ramp-up timeline and assume 60% Year 1 productivity.

---

### Market Changes (Competitive, Regulatory, Macro)

**Decision:** Major competitor enters market; you forecast 15% share loss

**First-order effect:** Revenue down 15%

**Second-order effect:**
- You cut prices to compete; margin compression 2–3%
- CAC rises as you fight for customers; marketing spend +20%

**Third-order effect:**
- Customers consolidate purchases (fewer suppliers); your share loss >15% as customers cut vendor count
- Remaining customers are lower-margin (price-driven vs. relationship-driven)
- LTV declines further

**Fourth-order effect:**
- Margin decline makes it harder to invest in innovation
- Market share loss accelerates (falling behind on product)

**Reforecasting checkpoint:** If revenue down >15% for 3 consecutive months, accept that market share loss is permanent and replan business model.

---

## Stress-Test Template for Decision-Making

Use this template when considering major decisions:

```
DECISION: [What are you considering?]

DIRECT IMPACT:
- Primary benefit: [e.g., revenue up $X]
- Primary cost: [e.g., cost up $Y]
- Net direct impact: [Net of primary]

SECOND-ORDER EFFECTS:
Effect 1: [e.g., if price up, customer churn up]
  Impact: [e.g., volume down 8%]
Effect 2: [e.g., if cost cuts, quality down]
  Impact: [e.g., returns up 5%]
Effect 3: [e.g., if hiring, culture changes]
  Impact: [e.g., productivity varies by team]

COMBINED IMPACT:
Direct: +$X
Secondary: -$Y
Net: $(X-Y)

EARLY WARNINGS (Observable within 30–60 days):
[What signals would tell you the assumption is wrong?]

GO/NO-GO DECISION:
- If we see [warning 1], we'll [contingency action 1]
- If we see [warning 2], we'll [contingency action 2]
- Otherwise, proceed as planned
```

---

## Running Stress Tests Across Multiple Scenarios

Combine stress-testing with scenario planning:

```
BASE CASE FORECAST (before stress):
Revenue: $1M
Net Income: $250K

STRESS TEST 1: Acquisition slows
New forecast: Revenue $950K, Net Income $230K
Change: -$20K

STRESS TEST 2: COGS inflation
New forecast: Revenue $1M, Net Income $220K
Change: -$30K

STRESS TEST 3: Labor cost inflation
New forecast: Revenue $1M, Net Income $200K
Change: -$50K

STRESS TEST 4: Competitive price pressure
New forecast: Revenue $900K, Net Income $190K
Change: -$60K

COMBINED (All stresses hit):
Revenue: $855K
Net Income: $125K
Change: -$125K (-50% margin compression)

Question: Can we operate at $125K net income? Is this downside acceptable?
If not: Plan contingencies now (cost reduction targets, pricing power analysis, etc.)
```

---

## Red Flags: When Forecast Assumptions Are Fragile

1. **Assumption relies on "everything stays same"** → Unrealistic. Assume some change.
2. **No early warning system** → You'll be blindsided. Define triggers now.
3. **Assumption is outside your control** → You can't forecast macro (but you can stress for it).
4. **Multiple assumptions must all be true** → Compound probability drops. Stress the combination.
5. **Assumption not observable until too late** → "Customer satisfaction" hard to measure. Use leading indicators instead (NPS, repeat purchase rate).

---

## Monitoring & Reforecasting Based on Stress Tests

Set up **monthly/quarterly monitoring** of key assumptions:

```
Assumption: Customer Acquisition (target: 25/month)
Actual (Month 1): 23/month ✓ (within tolerance)
Actual (Month 2): 18/month ⚠ (yellow flag)
Actual (Month 3): 16/month 🚨 (RED FLAG - trigger reforecast)

Action: Reforest assuming +18/month acquisition, not +25/month
Update revenue forecast down accordingly
```

---

## Stress-Testing Checklist

Before finalizing your forecast, run through:

- [ ] Identified top 5 assumptions by impact
- [ ] Stress-tested each: upside, downside, second/third-order effects documented
- [ ] Early warning indicators defined for each (what signals assumption is breaking?)
- [ ] Contingency actions defined (if warning hits, what do we do?)
- [ ] Stress-tested combinations (what if multiple stresses hit together?)
- [ ] Acceptable downside defined (can we operate in pessimistic scenario?)
- [ ] Monitoring cadence set (monthly/quarterly reviews)
- [ ] Team aligned on assumptions and triggers for reforecasting

Done well, stress-testing transforms a fragile forecast into a **robust planning tool** that keeps you prepared for surprises.
