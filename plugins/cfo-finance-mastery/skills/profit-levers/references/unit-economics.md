---
name: Unit Economics & Profitability Analysis
---

# Unit Economics & Profitability Analysis

## What Is Unit Economics?

Unit economics = **profit per customer or per product unit** sold. It answers: "Is this customer/product fundamentally profitable?"

**Formula:**
```
Unit Profit = (Revenue per Unit × Gross Margin %) - (CAC / Customer Lifespan)
```

If unit economics are negative, scaling loses money. Fix the unit first, then scale.

---

## Core Components

### Gross Margin Per Unit (or Customer)

**Product/Unit-Based:**
```
Gross Margin per Unit = Sale Price - Direct COGS
Example: $100 product - $35 COGS = $65 gross profit per unit
Gross Margin % = $65 / $100 = 65%
```

**Customer/Subscription-Based:**
```
Monthly Gross Margin per Customer = Monthly Subscription - Variable COGS
Example: $500/month SaaS subscription - $75 hosting/support = $425 gross margin
Gross Margin % = $425 / $500 = 85%
```

### Customer Acquisition Cost (CAC)

**Formula:**
```
CAC = Total Marketing & Sales Spend / New Customers Acquired

Example:
- Monthly marketing budget: $25K
- New customers acquired: 50
- CAC = $25K / 50 = $500 per customer
```

**By Channel (typical):**
- Organic/Referral: $0–100 (nearly free, if it's working)
- Content marketing: $100–300 (long tail, builds over time)
- Paid ads: $200–1,000+ (depends on competition, conversion rate)
- Sales team: $1,000–5,000+ (B2B, high-touch)

### Customer Lifespan / Lifetime Value

**Subscription/Recurring:**
```
Lifespan = 1 / Monthly Churn Rate
Example: 5% monthly churn = 1 / 0.05 = 20 months lifespan
```

**LTV = (Monthly Gross Margin) × (Lifespan in months)**
```
Example:
- Monthly gross margin: $425
- Customer lifespan: 20 months
- LTV = $425 × 20 = $8,500
```

**One-Time Purchase:**
```
LTV = (Purchase Price × Gross Margin %) + (Repeat Purchase Rate × Average Repeat Value)
Example:
- First purchase: $200 sale, 65% margin = $130 gross profit
- 40% of customers buy again (repeat rate)
- Repeat purchase value: $150 average, 65% margin = $97.50
- LTV = $130 + (0.40 × $97.50) = $130 + $39 = $169 per customer
```

---

## Unit Profit Calculation: The Full Picture

**SaaS Example:**
```
Monthly Subscription: $500
Gross Margin: 85% → $425/month per customer
CAC: $3,000
Customer Lifespan: 12 months (20% monthly churn)

Unit Profit = ($425 × 12) - $3,000 = $5,100 - $3,000 = $2,100 per customer

CAC Payback: $3,000 / $425 = 7 months
(Takes 7 months of gross margin to recover acquisition cost)

LTV:CAC Ratio: $5,100 / $3,000 = 1.7x
(For every $1 spent acquiring, customer generates $1.70 lifetime)

Profitability threshold: LTV:CAC ratio should be >3x for healthy SaaS business
This company is at 1.7x → **PROBLEM:** Not enough LTV to justify CAC
```

**How to fix:**
1. Lower CAC (more efficient marketing, organic growth)
2. Raise subscription price (increase monthly margin)
3. Reduce churn (improve customer retention, extend lifespan)
4. Reduce COGS (improve gross margin %)

**E-Commerce Example:**
```
Product Sale Price: $100
COGS: $35
Gross Margin: $65 (65%)
CAC (blended across channels): $25
Repeat Purchase Rate: 25% (1 in 4 customers buy again)
Average Repeat Value: $120 (customer buys bigger next time)

LTV = ($100 × 65%) + (25% × $120 × 65%) = $65 + $19.50 = $84.50 per customer
Unit Profit = $84.50 - $25 = $59.50 per customer

LTV:CAC Ratio: $84.50 / $25 = 3.4x
(For every $1 spent on acquisition, customer generates $3.40 lifetime profit)

Profitability threshold: LTV:CAC >2x for e-commerce (lower than SaaS because repeat is harder)
This company is at 3.4x → **HEALTHY:** Good profitability, can scale acquisition
```

---

## Unit Economics by Business Model

### SaaS (Monthly Recurring Revenue)

**Target Unit Economics:**
- CAC Payback: <12 months (ideally <6)
- LTV:CAC Ratio: >3x
- Annual retention: >90% (monthly churn <10%)

**Key drivers:**
- Monthly churn rate (biggest lever; small improvements compound)
- Average selling price / ARPU (higher price = lower CAC relative to LTV)
- Gross margin % (improve with scale)

**Example:** Twilio has CAC payback of ~8 months, LTV:CAC of 5x+ (excellent).

### E-Commerce (One-Time + Repeat)

**Target Unit Economics:**
- CAC Payback: <6 months (from repeat purchases + first-time margins)
- LTV:CAC Ratio: >2x
- Repeat purchase rate: >20% (varies by category)

**Key drivers:**
- Repeat purchase rate (customer loyalty, quality of product)
- Gross margin (product sourcing, channel mix)
- CAC efficiency (organic vs. paid mix)

**Example:** Warby Parker has strong repeat (glasses, contacts, exams) + high margin → healthy LTV:CAC.

### Marketplaces (Commission-Based)

**Target Unit Economics:**
- Gross margin: >20% (commission on transaction)
- CAC Payback: Varies (depends on seller stickiness)
- LTV:CAC Ratio: >2x

**Key drivers:**
- Take rate / commission % (higher commission = higher per-transaction margin, but may reduce volume)
- Seller retention (how long sellers stay active)
- Transaction frequency (transactions per seller per month)

### Services / Professional Services

**Target Unit Economics:**
- Gross margin: >60% (high-touch services naturally high margin)
- CAC Payback: <12 months
- LTV:CAC Ratio: >3x

**Key drivers:**
- Utilization rate (% of billable hours / total hours)
- Engagement duration (how long clients stay)
- Upsell rate (ability to sell additional services)

---

## Segment-Level Unit Economics

Different customer segments may have vastly different profitability:

**Example: SaaS with Three Customer Segments**

```
Segment          CAC    Monthly Margin   Lifespan   LTV      LTV:CAC Ratio
Startup          $800   $200             8 months   $1,600   2x (MARGINAL)
Mid-Market       $2,000 $800             30 months  $24,000  12x (EXCELLENT)
Enterprise       $5,000 $1,500           36 months  $54,000  10.8x (EXCELLENT)
```

**Insights:**
- Startups barely profitable (2x ratio)
- Mid-market and enterprise highly profitable
- Decision: Focus growth on mid-market/enterprise; deprioritize startup sales

**Implementation:**
- Raise prices for startup tier (may reduce volume, but improve margin)
- Reduce sales spend on startup outbound (shift to self-serve)
- Invest in enterprise sales (highest ROI)

---

## Using Unit Economics to Make Decisions

**Decision 1: Launch New Product**
```
Existing Product Unit Economics:
- CAC: $300
- Gross Margin: 70%
- Lifespan: 24 months
- LTV: $5,000

New Product Assumptions:
- CAC: $500 (new market, higher customer education)
- Gross Margin: 75% (better-engineered product)
- Lifespan: 18 months (newer category, higher churn)
- LTV: $4,050

Profitability: LTV $4,050 - CAC $500 = $3,550 per customer (positive, but lower than existing product)

Decision: Launch, but:
1. Reduce CAC through word-of-mouth / organic
2. Improve retention (3-month churn is highest risk)
3. Monitor closely; shut down if LTV drops below $3x CAC
```

**Decision 2: Increase Prices**
```
Current: $99/month, 80% margin, 10% monthly churn
Proposed: $149/month (+50%), expect 8% monthly churn (slight erosion)

Margin per month: $99 × 70% = $69.30 → $149 × 75% = $111.75 (+$42 or +61%)
Lifespan: 1 / 10% churn = 10 months → 1 / 8% churn = 12.5 months (+2.5 months)
LTV change: ($69.30 × 10) = $693 → ($111.75 × 12.5) = $1,397 (+$704 or +102%)

Decision: Raise prices (LTV more than doubles despite slight churn increase)
```

**Decision 3: Cut CAC Spend vs. Maintain Growth**
```
Current State:
- CAC: $500 (paid ads)
- LTV: $5,000
- New customers/month: 20 (from $10K ad spend)
- Revenue: $100K/month

Scenario A (Maintain Growth):
- Keep $10K ad spend
- 20 new customers/month × $2,500 LTV = $50K monthly contribution
- Ad spend: $10K
- Net: +$40K monthly from new customers

Scenario B (Cut Spend):
- Reduce to $5K ad spend
- 10 new customers/month × $2,500 LTV = $25K monthly contribution
- Ad spend: $5K
- Net: +$20K monthly from new customers (half)
- Savings: $5K/month

Decision: Maintain growth (Scenario A). CAC is still well below LTV (5x ratio).
Only cut if CAC rises above $1,200 or LTV drops below $3,000.
```

---

## Red Flags: Unit Economics That Signal Problems

1. **LTV:CAC Ratio <2x** (especially <1.5x) → Not enough lifetime value to justify acquisition. Business unsustainable at scale.

2. **CAC Payback >18 months** → Takes too long to recover acquisition cost. Very risky if churn accelerates.

3. **Rising CAC with flat or falling conversion** → Market saturation or competitive pressure. Need new channels or messaging.

4. **Churn accelerating (month-over-month increasing)** → Product or market issue. Extending lifespan difficult; focus on retention.

5. **Gross margin declining with scale** → Scaling inefficiently (COGS too high, discounting too much). Reevaluate unit model.

6. **Repeat purchase rate flat or declining** → Customer satisfaction issue or market saturation. Product quality at risk.

---

## Monitoring Unit Economics Monthly

Track by segment and channel:

| Metric | Formula | Current | Target | Trend |
|--------|---------|---------|--------|-------|
| CAC | Marketing spend / New customers | $400 | <$500 | Up (🚨) |
| LTV | Gross margin × Lifespan | $5,000 | >$4,000 | Stable (✓) |
| LTV:CAC | LTV / CAC | 12.5x | >3x | Stable (✓) |
| Monthly Churn | Customers lost / Start of month | 5% | <6% | Stable (✓) |
| CAC Payback | CAC / Monthly gross margin | 6 months | <12 | Stable (✓) |

If CAC rises above target or churn exceeds 6%, trigger analysis and course correction.

---

## Conclusion

Unit economics is the **foundation of all profit decisions**. Know your unit economics cold. They dictate:
- Whether to scale (positive LTV:CAC ratio)
- Which channels to invest in (compare CAC by channel)
- Which customer segments to focus on (compare LTV by segment)
- Whether to raise prices (impact on churn vs. margin tradeoff)

Never scale a bad unit. Fix the unit first, then scale.
