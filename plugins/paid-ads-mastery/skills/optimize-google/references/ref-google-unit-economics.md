---
title: Unit Economics, POAS & Bottleneck Analysis
skill: optimize-google
usage: Load when user asks about break-even ROAS, POAS vs ROAS, profitability calculations, unit economics for e-commerce/lead gen/SaaS, value-based bidding for lead gen, or bottleneck analysis.
---

# Unit Economics, POAS & Bottleneck Analysis

## Why Unit Economics Come First

Unit economics determine campaign viability. They are the hidden foundation of successful advertising. Poor unit economics CANNOT be solved with in-platform Google Ads optimizations. Google Ads cannot scale a broken offer.

---

## E-Commerce Unit Economics

### Core Formulas
| Metric | Formula | Example |
|---|---|---|
| **AOV** | Revenue / Number of Orders | $50,000 / 500 = $100 |
| **Profit Margin** | (Revenue - COGS) / Revenue | ($100 - $40) / $100 = 60% |
| **Break-Even ROAS** | 1 / Profit Margin | 1 / 0.60 = 1.67x |
| **CAC** | (Cost of Sales + Marketing) / New Customers | ($5,000 + $10,000) / 200 = $75 |
| **LTV** | AOV x Purchase Frequency x Avg Customer Lifetime | $100 x 3 x 2 years = $600 |

### Break-Even ROAS by Margin

| Profit Margin | Break-Even ROAS | Reality Check |
|---|---|---|
| 80% | 1.25x | Excellent margins; easy to profit |
| 60% | 1.67x | Good margins; most e-com can work |
| 40% | 2.50x | Tight; need strong CVR and CTR |
| 25% | 4.00x | Very difficult; scaling limited |
| 12% | 8.33x | Nearly impossible -- fix margins first |

### Real Example: Why Margins Kill Campaigns
Client with $40.2K revenue, $3.3K ad spend, but only 12% gross margin:
- Contribution margin: just 4% ($1.7K euros)
- Average gross profit per order: $2.87
- Break-even ROAS needed: 7.58x (758%)
- **Completely unscalable.** No amount of Google Ads optimization fixes this.

### Order-Level Economics
For a $32 order:
- Product cost: $20.20
- Shipping: $6.50
- Payment fee: $1.00
- Gross profit: $4.64
- Break-even ROAS: 7.58x
- If allocating 75% of gross profit to ads: need 1000% ROAS target

**Lesson:** Know your per-order economics before launching any campaign.

---

## Lead Gen Unit Economics

### Core Formulas
| Metric | Formula | Example |
|---|---|---|
| **Average Deal Value** | Revenue / Closed Deals | $100K / 10 = $10K |
| **Lead-to-Sale Rate** | Closed Deals / Total Leads x 100 | 10 / 50 = 20% |
| **CPL** | Total Spend / Number of Leads | $5,000 / 50 = $100 |
| **CAC** | CPL / Lead-to-Sale Rate | $100 / 0.20 = $500 |
| **Break-Even CPL** | Profit Margin x Lead-to-Sale Rate | $3,000 x 0.20 = $600 |

### The Lead Value Cascade
```
100 leads --> 20 MQLs (20%) --> 10 SQLs (50%) --> 5 closed deals (50%)
Deal sizes: $5K to $25K
Average deal value: $12K
CPL: $100
CAC: $100 / 0.05 = $2,000
LTV: $12K (or more with renewals)
LTV:CAC ratio: 6:1 (healthy)
```

### Root Causes of Poor Lead Gen Economics
| Root Cause | Solutions |
|---|---|
| Poor lead quality | Pre-qualifying questions on forms, better content, improved targeting |
| Sales team not following up | Daily check-ins, lead scoring, automated nurture sequences |
| Low deal sizes | Focus higher-value services, create bundles, add upsell opportunities |
| Long sales cycles | Limited-time offers, faster proposal process, automated follow-ups |

---

## SaaS Unit Economics

### Core Formulas
| Metric | Formula | Example |
|---|---|---|
| **ARPU** | MRR / Paying Customers | $50K / 500 = $100/mo |
| **Customer Lifetime (months)** | 1 / Monthly Churn Rate | 1 / 0.05 = 20 months |
| **LTV** | ARPU x Lifetime x Margin | $100 x 20 x 0.70 = $1,400 |
| **Max CAC** | LTV / 3 | $1,400 / 3 = $467 |

### Golden Rule: LTV:CAC Must Be at Least 3:1
- 3:1 = healthy, sustainable growth
- 5:1+ = very profitable, may be under-investing in growth
- Below 3:1 = unprofitable; fix churn, ARPU, or reduce CAC

---

## POAS vs. ROAS (Profit on Ad Spend)

### The Problem with ROAS
ROAS (Revenue on Ad Spend) treats all revenue equally, but revenue is NOT profit:

| Product Type | Revenue | COGS | Margin | Break-Even ROAS |
|---|---|---|---|---|
| High-margin product | $100 | $37 | 63% | 159% |
| Low-margin product | $100 | $78 | 22% | 455% |
| Discounted product | $80 | $50 | 37.5% | 267% |

If you set Target ROAS at 455% (to protect low-margin products), you lose all growth opportunity on 159% products. If you set it at 200%, you lose money on every low-margin sale.

### The Average ROAS Trap
- Different products have different margins but bidding uses one average target
- Cross-selling effects completely ignored (customer clicks Product A, also buys Product B)
- ROAS does not account for shipping, fulfillment, payment fees

### How POAS Fixes This
- Set minimum PROFIT per ad dollar (not revenue per ad dollar)
- Algorithm promotes products based on expected profitability
- Upload gross profit at order level to Google Ads
- Each product automatically gets the right bidding aggression based on its margin

### POAS Implementation
1. Calculate gross profit per product (revenue - COGS - shipping - payment fees)
2. Set up conversion tracking with cart-level data
3. Import COGS data into Google Ads (tools: ProfitMetrics, custom solutions)
4. Switch bidding to optimize for profit value instead of revenue value
5. Set minimum POAS target (e.g., 100% POAS = $1 profit per $1 ad spend)

---

## Value-Based Bidding (VBB) for Lead Gen

### Core Principle
Not all leads are equal. A $25K deal is worth more than a $5K deal, so the algorithm should bid more aggressively for high-value leads.

### Implementation Steps
1. Set up Offline Conversion Tracking (OCT)
2. Track beyond form submissions: MQLs, SQLs, Closed Deals, Deal Values
3. Upload deal-specific conversion values for closed deals
4. Assign average conversion values for intermediate steps
5. Regularly recalculate averages as deal values change
6. Transition from Target CPA to Target ROAS (maximize conversion value)

---

## Bottleneck Analysis System

### Systems Thinking Applied to Google Ads
Your account is a system. Output is limited by the WEAKEST LINK.

### The Conversion Chain
```
Impressions --> Clicks --> Leads/Sales --> Customers --> Revenue --> Profit
     |              |           |              |             |          |
    CTR           CVR      Close Rate    Deal Value      Margins
```

### Bottleneck Identification Process

**Step 1: Map the Chain**
Document each stage with current metrics:
- Impressions: [number]
- CTR: [%]
- Clicks: [number]
- CVR: [%]
- Conversions: [number]
- Average value: [$]
- Revenue: [$]
- Costs: [$]
- Profit: [$]

**Step 2: Identify the Weakest Link**
Compare each metric to industry benchmarks and your own historical averages:
- CTR below benchmark? Problem is ad copy/creative
- CVR below benchmark? Problem is landing page/offer
- Close rate below benchmark? Problem is sales process
- Deal value below benchmark? Problem is pricing/upselling
- Margin below benchmark? Problem is cost structure

**Step 3: Fix the Weakest Link FIRST**
Do not optimize strong links before fixing the weak one. A 50% improvement to the bottleneck has more impact than a 100% improvement to a non-bottleneck.

### Warning Signs of Poor Unit Economics
- Unable to bid competitively in your industry
- Forced to target only bottom-of-funnel keywords
- Cannot afford upper-funnel campaigns
- Over-optimizing for efficiency instead of growth
- Clients saying "you cannot exceed this target CPA" at very low levels

---

## Budget Calculation Formulas

### CPA-Based
**Required Monthly Budget = Target Monthly Conversions x Target CPA**
- Example: 100 leads x $50 CPA = $5,000/month = $164/day

### ROAS-Based
**Required Monthly Budget = Target Monthly Revenue / Target ROAS**
- Example: $400K Q4 revenue / 350% ROAS = $114K spend = ~$1,250/day

### Budget Validation Checklist
- Is there enough search volume / market potential?
- Is there room in search impression share?
- What is competition level per market segment?
- Historical CPA/ROAS trends during scaling phases?
- Will conversion rate hold when scaling?
