---
name: Financial Formulas & Tracking Templates Reference
description: >
  All financial formulas (CLV, CPA, break-even, contribution margin, CCC).
  LifeBoost revenue timeline and LTV progression. Business valuation multiples.
  Daily ad tracking report template. Credit card stacking for cash flow.
  Donation tax deduction strategy. Storage multiplier concept.
---

# Financial Formulas & Tracking Templates Reference

---

## CORE FINANCIAL FORMULAS

### Profitable Ad Spend Formula (Matt Clark)
```
Revenue = Units Sold x Price
COGS = Units Sold x (Cost + Shipping)
Gross Profit = Revenue - COGS
Profit per Sale = Revenue - COGS

To be profitable: Cost per Sale (ad spend) < Profit per Sale

Example:
  Product price: $79.99
  COGS: $20
  Profit per sale: $59.99
  If CAC = $20: Net profit = $39.99/sale (66.7% margin after ads)
```

### CLV Calculation Formula (Matt Clark)
```
CLV = AOV x (1 + Repeat Purchase Rate) x Average Lifetime (years) x Gross Margin %

Example:
  $79.99 x 1.3 x 3 x 0.65 = $203 lifetime profit
  CAC should be <20% of CLV = <$40 to be healthy
```

### Break-Even CPA Formula
```
Break-Even CPA = AOV x Gross Margin %

Example:
  $70 AOV x 50% margin = $35 break-even CPA
  If CPA < $35: making money on day one
  If CPA > $35: losing money upfront (normal when starting)
```

### Contribution Margin Formula (Jason Wong)
```
Contribution Margin = Revenue - Variable Costs
(Where variable costs = COGS + freight + receiving + transaction + fulfillment + postage)
```

### CAC Payback Period Formula
```
CAC Payback Period = CAC / Monthly Contribution Margin per Customer
```

### LTV:CAC Ratio
```
Target: 3:1 or higher
LTV:CAC = Customer Lifetime Value / Customer Acquisition Cost
```

### Gross Profit Margin
```
GPM = (Revenue - COGS) / Revenue x 100

Targets:
  Minimum: 30%
  Ideal: 60%
  Jason Wong benchmark: 25% gross profit as % of total revenue
```

### Cash Conversion Cycle
```
CCC = DIO + DSO - DPO

DIO = (Average Inventory / COGS) x 365
DSO = (Accounts Receivable / Revenue) x 365
DPO = (Accounts Payable / COGS) x 365

Benchmarks:
  Typical DTC: 40-100 days
  Gymshark: negative 101 days
  At $3K/day sales, CCC of 100 days = $300K cash stuck in ops
```

### Three CCC Improvement Levers
1. **Increase AP:** Negotiate net-30, net-60 payment terms with suppliers
2. **Reduce AR:** Set Shopify payouts to daily; use pre-orders for negative AR
3. **Reduce inventory:** Audit underperforming SKUs; ask vendors to hold stock

---

## JASON WONG'S PRICING FORMULA (3-Step Method)

### Step 1: Calculate All Variable Costs
```
Example breakdown:
  COGS:                  $3.25
  Production time:       $2.00
  Packaging:             $1.78
  Promotional materials: $0.75
  Shipping:              $4.50
  TOTAL per unit:       $12.28
```

### Step 2: Determine Target Cost Percentage
```
If product cost should be 20% of final price:
  $12.28 / 0.20 = $61.40 base retail price
  (Multiply cost by 5)
```

### Step 3: Verify Fixed Cost Coverage
Ensure total sales at projected volume cover rent, software, insurance, labor.

---

## LIFEBOAT REVENUE TIMELINE (Matt Clark -- Exact Numbers)

| Month | Revenue | Ad Spend | Ad % of Revenue |
|---|---|---|---|
| January 2019 | $16K-$17K | $2,500 | 15% |
| February 2019 | $30K | $19,000 | 65% (losing money -- testing phase) |
| March 2019 | $76K | $11,000 | 15% |
| January 2020 | $600K+ | $190,000 | 30% |
| Current (2022) | $2.6M/month | ~$910K | ~35% |

- About half of revenue is subscription
- Target ad spend: 35% of revenue
- Gross margin: ~50%
- At 50% gross margin and 35% ad spend: 15% left for operating expenses + compensation

---

## LIFEBOAT LTV PROGRESSION (Matt Clark -- Exact Data)

| Month | Cumulative LTV | Incremental Value |
|---|---|---|
| Month 1 | $70 | Base AOV |
| Month 2 | $82 | +$12 from reorders |
| Month 6 | $122 | +$40 from months 3-6 |
| Month 12 | $166 | +$44 from months 7-12 |
| Month 24 | $240 | +$74 from months 13-24 |

**Implication:** At 50% margin, month-1 profit per customer = $35. But 12-month profit = $83. Can spend up to $83/customer and break even in 12 months.

---

## DAILY AD TRACKING REPORT TEMPLATE (Matt Clark)

### Store-Level Daily Fields
| Field | Source | Formula |
|---|---|---|
| Total Shopify sales | Shopify | Manual or API |
| Number of orders | Shopify | Manual |
| AOV | Calculated | Sales / Orders |
| Estimated gross profit % | Calculated | (Sales - COGS) / Sales |
| Total ad spend | Sum | Sum of all channel spends |

### Per-Channel Fields (Repeat for Each Platform)
| Field | Source | Notes |
|---|---|---|
| Daily spend | Ad platform | Facebook, Google, TikTok, etc. |
| Clicks | Ad platform | |
| Cost per click | Calculated | Spend / Clicks |
| Orders (platform-reported) | Ad platform | Subject to attribution window |
| Orders (third-party tracking) | Affiliatly or similar | More accurate |
| Revenue | Ad platform | |
| AOV per channel | Calculated | Revenue / Orders |
| CPA | Calculated | Spend / Orders |
| Profit/Loss | Calculated | (Revenue x Gross Margin %) - Ad Spend |

### Tracking Discrepancy Management
- Compare platform-reported vs. third-party tracking
- Consistent directional difference: investigate (attribution model issue)
- Random bouncing: less concerning (timing differences)
- "You can't ever fully trust platform data" -- always use third-party verification

---

## BUSINESS VALUATION MULTIPLES

| Business Type | Multiple Range | Basis |
|---|---|---|
| Basic e-commerce | 3x-5x | Annual profit (EBITDA) |
| Strong brand with IP | 5x-10x | Annual profit |
| Subscription/high LTV | 10x-20x | Annual profit |
| Revenue-based (growth stage) | 2x-3x | Annual revenue |
| DTC brand (broker valuation) | 2-3x more than Amazon-only | Multiple premium |

**Key factors increasing multiples:** YoY trajectory, documented SOPs, clean financials, brand assets, IP (patents/trademarks), subscription revenue, diversified channels.

---

## CREDIT CARD STACKING FOR CASH FLOW

### PPC Billing Threshold Hack
- Request Amazon increase PPC billing threshold to $10,000
- Use credit cards that earn maximum rewards on ad spend
- AMEX Gold: 4x points on advertising spend
- Chase Business: rotating category bonuses
- AMEX Plum: 1.5% early payment discount or net-60 terms

### Supplier Payment via Melio
- Pay suppliers by credit card through Melio (even if supplier only accepts wire/ACH)
- Extends effective payment terms by credit card billing cycle (30-45 days)
- Earn credit card rewards on supplier payments
- Particularly useful for bridging cash conversion cycle gaps

---

## DONATION TAX DEDUCTION STRATEGY (Tony Brink)
- Most sellers dispose of returns = throwing money away
- Example: 100K units/year at 5% return rate = 5,000 units disposed = $75K loss
- Strategy: donate returns to charity instead of disposing
- Tax deduction = units x retail value (e.g., 5,000 x $30 = $150K deduction)
- Turns a complete loss into a significant tax benefit

---

## STORAGE MULTIPLIER CONCEPT (Chelsea Cohen)
- Excess inventory ties up capital AND incurs storage fees
- Storage fees compound: longer storage = higher per-unit fees (Amazon long-term storage)
- Calculate true cost of holding inventory = storage fee + opportunity cost of locked capital
- Use demand forecasting to right-size inventory orders

---

## KEY FINANCIAL BENCHMARKS

| Category | Metric | Value | Source |
|---|---|---|---|
| Startup investment | Total to launch | $3,000-$10,000 | Matt Clark |
| Initial inventory | First order | $3,000-$5,000 | All |
| Year 1 target | Revenue | $50,000-$100,000 | Matt Clark |
| Break-even timeline | First profit | 4-6 weeks of traffic | Matt Clark |
| Profit per unit | Minimum | $10-$50+ | All |
| Healthy margins | After all costs | 50-70% | All |
| Ad spend (testing) | Daily per platform | $5-$10 | Matt Clark |
| Ad spend (long-term) | % of revenue | 30-35% | Matt Clark |
| LTV:CAC ratio | Target | 3:1+ | Jason Wong |
| Employee true cost | Multiplier | 1.5x base salary | Jason Wong |
| Supplier discount | Annual commitment | ~10% cost reduction | Jason Wong |
| CCC | Target range | 40-100 days (lower is better) | Jason Wong |
