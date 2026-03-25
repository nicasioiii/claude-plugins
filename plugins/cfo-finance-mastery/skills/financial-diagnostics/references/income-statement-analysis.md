---
name: "Income Statement Analysis"
description: "P&L structure, three margin metrics, profit leak detection via vertical/horizontal/variance analysis, e-commerce KPIs, diagnostic process, COGS vs SG&A classification rules."
when_to_read: "When the user needs detailed P&L analysis guidance, margin calculation help, expense classification rules, or the full diagnostic process with examples."
---

# Income Statement Analysis -- Deep Reference

## P&L Structure Variants

### Leikauf Structure (Lending/Ratio Context)
```
Net Sales (Revenue)
  - COGS
= Gross Profit (Gross Margin %)
  - SG&A / Operating Expenses
= Operating Income (EBIT)
  - Depreciation & Amortization
= EBITDA (add back D&A)
  - Interest Expense
  - Income Taxes
= Net Income
```

### Aharonoff Structure (Three-Statement Model Context)
```
Revenue
  - Cost of Goods Sold
= Gross Profit
  - Operating Expenses (SG&A)
= Net Operating Income
  +/- Other Income / Other Expenses
= Net Other Income
= Net Income (before or after tax)
```

**Mapping:** Operating Income = EBIT = Net Operating Income. Use Leikauf's terms in banking/lending contexts, Aharonoff's terms in modeling contexts.

### COGS Classification by Business Type
| Business Type | COGS Includes | Often Misclassified |
|--------------|---------------|---------------------|
| **E-commerce** | Product cost, shipping, fulfillment, transaction fees, merchant fees | Warehouse rent (should be COGS if dedicated) |
| **Service** | Direct labor, subcontractors, project materials | Sales team salaries (SG&A, not COGS) |
| **Manufacturing** | Raw materials, direct labor, factory overhead | R&D labor (usually SG&A) |
| **SaaS** | Hosting, customer support, payment processing | Engineering salaries (SG&A) |
| **Restaurant** | Food cost, kitchen labor, disposables | Front-of-house labor (can be either -- be consistent) |

### Revenue Recognition Impact
- **Cash basis:** Revenue appears when payment lands. Can create lumpy P&Ls that do not reflect actual business activity.
- **Accrual basis:** Revenue appears when earned. Creates smoother P&Ls but requires monitoring AR to ensure collection.
- **Mixed signals:** A business on cash basis may show great revenue in Month 1 (prepayments collected) and terrible revenue in Month 2 (services delivered, no new collections). Always ask which basis.

---

## Margin Analysis Framework

### Gross Margin Deep Dive
```
Gross Margin % = Gross Profit / Revenue
```

**What drives gross margin:**
- Pricing power (can you charge more?)
- Input costs (materials, labor, freight)
- Product mix (high-margin vs low-margin products)
- Volume discounts (buying power on COGS)
- Fulfillment efficiency

**Gross margin benchmarks (rough guides):**
| Industry | Typical Gross Margin |
|----------|---------------------|
| SaaS | 70-85% |
| Professional services | 50-70% |
| E-commerce (own products) | 40-65% |
| E-commerce (reseller) | 25-40% |
| Manufacturing | 25-45% |
| Restaurant | 60-70% (food cost 28-35%) |
| Construction | 20-35% |

**[CONTRARIAN] Aharonoff: Gross profit sets your earnings ceiling.** Your gross profit is the maximum possible amount available to cover all other expenses. If gross profit is $600 on a $1,000 sale, that $600 must cover ALL operating expenses, other expenses, and still leave net income. Always evaluate gross margin first.

### Operating Margin Deep Dive
```
Operating Margin % = Operating Income / Revenue
```

Gap between gross margin and operating margin reveals SG&A burden. If gross margin is 60% but operating margin is 5%, overhead is consuming nearly all production profit.

**Key SG&A categories to examine:**
- Personnel costs (largest for most businesses)
- Marketing/advertising spend
- Rent and occupancy
- Technology and software
- Professional services (legal, accounting)
- Insurance

### Net Margin
```
Net Margin % = Net Income / Revenue
```

Below-the-line items (interest, taxes, D&A) create the final margin. For heavily leveraged businesses, the gap between operating and net margin reveals debt burden.

---

## Vertical Analysis Execution

For each line item: `Amount / Revenue x 100 = % of Revenue`

**Example layout:**
| Line Item | Amount | % of Revenue | Benchmark | Variance |
|-----------|--------|-------------|-----------|----------|
| Revenue | $1,000,000 | 100% | -- | -- |
| COGS | $400,000 | 40% | 35% | +5% (investigate) |
| Gross Profit | $600,000 | 60% | 65% | -5% |
| SG&A | $450,000 | 45% | 40% | +5% (investigate) |
| Operating Income | $150,000 | 15% | 25% | -10% |

**Red flag thresholds:** Flag any line item where actual % deviates more than 3-5 percentage points from benchmark or prior period.

---

## Horizontal Analysis Execution

**Month-over-month:**
```
Change $ = Current Month - Prior Month
Change % = (Current - Prior) / ABS(Prior)
```

**Year-over-year (preferred for seasonal businesses):**
```
Change $ = Current Month - Same Month Prior Year
Change % = (Current - Prior Year Same Month) / ABS(Prior Year Same Month)
```

**Always use ABS() in the denominator** for percentage change to handle negative base numbers correctly (Aharonoff).

---

## Variance Analysis Execution

```
Variance $ = Actual - Budget
Variance % = (Actual - Budget) / ABS(Budget)
```

**Direction convention (Aharonoff):**
- Favorable variances always positive (revenue above budget, expenses below budget)
- Unfavorable variances always negative (revenue below budget, expenses above budget)
- For expense lines, reverse the sign: `Budget - Actual` (so underspend shows positive)
- Do NOT use a consistent formula direction for all lines -- match direction to favorability

**Materiality thresholds:**
- Revenue lines: investigate any variance > 5%
- Large expense lines (>10% of revenue): investigate > 10% variance
- Small expense lines (<2% of revenue): investigate > 25% variance or unusual patterns

---

## E-Commerce P&L KPIs

| KPI | Formula | Benchmark Range |
|-----|---------|----------------|
| **ROAS** | Revenue / Ad Spend | 3x-5x+ (varies by margin) |
| **Chargeback Rate** | Chargebacks / Revenue | < 1% |
| **Transaction Fee %** | Merchant Fees / Revenue | 2.5-3.5% |
| **Refund Rate** | Refunds / Gross Revenue | < 5% |
| **Shipping % of Revenue** | Shipping Cost / Revenue | 8-15% |
| **Customer Acquisition Cost** | Marketing / New Customers | Varies by CLV |

---

## Cross-References

- **Ratio calculations from P&L data** -> `financial-ratios/ratio-reference.md`
- **Building a forecast from diagnostic findings** -> `forecasting-strategy/projection-methods.md`
- **Presenting P&L analysis to stakeholders** -> `advisory-communication/communication-frameworks.md`
