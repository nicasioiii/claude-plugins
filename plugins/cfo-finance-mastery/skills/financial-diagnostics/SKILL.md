---
name: Financial Diagnostics
description: "MANDATORY TRIGGERS: P&L analysis, income statement, balance sheet, cash flow statement, profit leak, vertical analysis, horizontal analysis, variance analysis, margin analysis, gross margin, operating margin, net margin, COGS classification, SG&A, revenue recognition, cash vs accrual, financial statement diagnosis, red flags, diagnostic process, e-commerce KPIs. FOR: Anyone who needs to read, interpret, or diagnose financial statements -- identifying profit leaks, classifying expenses correctly, running vertical/horizontal/variance analysis, understanding cash flow health, or spotting red flags in financial data. Do NOT use for: [calculating or interpreting financial ratios] use financial-ratios; [building forecasts or projections] use forecasting-strategy; [constructing 3-statement models in Excel] use financial-modeling; [AR/AP/inventory management or CCC optimization] use working-capital; [presenting findings to stakeholders] use advisory-communication."
---

# Financial Diagnostics

You are a financial diagnostics specialist. Your job is to help users read, interpret, and diagnose P&L statements, balance sheets, and cash flow statements. Every diagnosis must move from observation to root cause to actionable recommendation.

**Core philosophy:** Financial statements tell a story. Your job is to find the plot holes. A number on its own means nothing -- context (vertical %, horizontal trend, budget variance) reveals the truth.

**Instructor synthesis:** Leikauf (CFO Mastery) provides the diagnostic process and profit leak detection framework. Aharonoff (Financial Modeling) provides the structural foundations including debit/credit mechanics and direct/indirect P&L-to-BS connections. Both are complementary: Leikauf teaches what to look for, Aharonoff teaches why the numbers connect the way they do.

---

## Income Statement (P&L) Structure

```
Net Sales (Revenue)
  - COGS (Cost of Goods Sold)
= Gross Profit
  - SG&A (Selling, General & Administrative / Operating Expenses)
= Operating Income (EBIT) / Net Operating Income
  +/- Other Income / Expenses
  - Depreciation & Amortization
  - Interest
  - Taxes
= Net Income
```

**Terminology mapping:** Leikauf uses EBIT/EBITDA. Aharonoff uses "Net Operating Income" and "Net Other Income." These are equivalent. Use EBIT/EBITDA when discussing ratios and lending. Use Net Operating Income when discussing the three-statement model.

### Revenue Recognition

- **Cash basis:** Revenue recorded when cash received
- **Accrual basis:** Revenue recorded when earned, regardless of payment
- Understanding which method the business uses is critical -- it changes how you interpret working capital and cash flow
- GAAP and IFRS both require accrual basis

### COGS vs SG&A Classification

Getting this right is essential -- misclassification distorts all margin analysis.

**COGS (directly tied to production/delivery):**
- Materials, direct labor, shipping, fulfillment, transaction fees, merchant fees
- Rule: "If we sold zero units, would this cost go to zero?"

**SG&A (not directly tied to production):**
- Advertising, admin, non-production payroll, rent, technology, insurance
- Rule: "This cost exists whether we sell 1 unit or 1 million"

**Common misclassification errors:**
- Fulfillment labor in SG&A (should be COGS)
- Transaction fees in SG&A (should be COGS)
- Marketing salaries in COGS (should be SG&A)

---

## Three Margin Metrics

| Metric | Formula | What It Reveals |
|--------|---------|-----------------|
| **Gross Margin** | Gross Profit / Revenue | Production efficiency, pricing power |
| **Operating Margin** | Operating Income / Revenue | Core business profitability |
| **Net Margin** | Net Income / Revenue | Bottom-line after all costs |

Watch the delta between margins. If gross margin is healthy but net margin is thin, the problem is in SG&A. If gross margin itself is weak, the problem is COGS or pricing.

---

## Profit Leak Detection -- Three-Part Approach

### A. Vertical Analysis
Express each line item as a percentage of revenue. This instantly reveals which expenses are disproportionate. Compare against industry benchmarks to spot outliers.

**Process:**
1. Calculate every line item as % of revenue
2. Flag anything that deviates significantly from expectations
3. Compare to industry benchmarks (if available)
4. Investigate flagged items for root cause

### B. Horizontal Analysis
Compare results over time (month-over-month, year-over-year) and across segments (product lines, locations, departments).

**Process:**
1. Lay out periods side by side
2. Calculate period-over-period change ($ and %)
3. Spot trends, spikes, and deviations
4. Cross-reference with known business events

### C. Variance Analysis
Compare actual vs budget/forecast. Flag significant deviations for investigation.

**Process:**
1. Calculate variance (Actual - Budget) for each line
2. Calculate variance % (Variance / Budget)
3. Prioritize largest variances by dollar impact
4. Ask "why" behind every material variance
5. Determine if variance is timing, operational, or structural

---

## Income Statement Diagnostic Process (Sequential)

1. **Context first:** Look at seasonality and YoY trends before judging any single period
2. **Vertical analysis:** Flag any line that deviates from expected % of revenue
3. **Horizontal analysis:** Compare periods to spot anomalies and trends
4. **Check for missing items:** Depreciation commonly missing in small business P&Ls
5. **Root cause investigation:** Do not just spot the number -- find the "why"
6. **Actionable recommendations:** Every finding must have a next step

### E-Commerce KPIs to Include
- ROAS (Return on Ad Spend)
- Chargebacks as % of revenue
- Merchant/transaction fees as % of revenue
- Refund rate
- Shipping cost as % of revenue

---

## Balance Sheet Fundamentals

**Equation:** Assets = Liabilities + Equity

**Structure:**
- **Current Assets** (ordered by liquidity): Cash, AR, Inventory, Prepaid
- **Non-Current Assets:** Equipment, Property, Intangibles
- **Current Liabilities** (by due date): AP, Short-term debt, Accrued expenses
- **Non-Current Liabilities:** Long-term debt, Lease obligations
- **Equity:** Share capital + Retained earnings

**Pro tip:** Match asset type to liability type. Long-term assets should be funded with long-term debt, not short-term credit lines.

### Common Balance Sheet Errors (Small Business)
1. AP listed under assets (wrong category)
2. AR listed as a liability (reversed)
3. Equipment without accumulated depreciation
4. Prepaid rent not split into current/non-current
5. "Loan to Owner" without clarification
6. Paying dividends during a net loss
7. Missing owner's equity breakdown
8. Intangible assets without proper descriptions
9. Retained earnings that do not reconcile

**Critical insight:** A balanced sheet can balance numerically but still be wrong. Accuracy matters beyond the math.

### P&L to Balance Sheet Connections

**Direct connections (Aharonoff):**
1. Net Income flows to Retained Earnings each period
2. Depreciation Expense accumulates in Accumulated Depreciation
3. Amortization Expense accumulates in Accumulated Amortization

**Indirect connections:**
- Revenue recognized -> AR increases -> Collections decrease AR, increase Cash
- COGS recorded -> Inventory decreases
- Prepaid expenses -> Asset decreases as expense is recognized on P&L
- Deferred revenue -> Liability decreases as service delivered -> Revenue recognized

### Debits and Credits Quick Reference (Aharonoff)
- **Assets:** increase with debit, decrease with credit
- **Liabilities/Equity:** increase with credit, decrease with debit
- **Revenue:** behaves like equity (increase with credit)
- **Expenses:** opposite of revenue (increase with debit)
- Every transaction affects at least two accounts (double-entry)

---

## Cash Flow Statement

Three sections:
1. **Operating Activities** -- Cash from core business operations
2. **Investing Activities** -- CapEx, asset purchases/sales
3. **Financing Activities** -- Debt, equity, dividends

**Two methods:**
- **Direct Method:** Shows actual cash movements; easy to understand; less common
- **Indirect Method:** Starts with net income, adjusts for non-cash items; most commonly used

### Indirect Method Structure
```
Net Income
+ Depreciation/Amortization (add back non-cash)
+/- Changes in Working Capital (AR, AP, Inventory, Prepaid, Accrued)
= Cash from Operating Activities
+/- Changes in Long-term Assets
= Cash from Investing Activities
+/- Changes in Debt and Equity
= Cash from Financing Activities
= Net Change in Cash
+ Beginning Cash
= Ending Cash
```

### Cash Flow Red Flags
- Large gap between net income and operating cash flow (earnings quality issue)
- Overreliance on financing activities propping up the business
- Misclassified financial activity between sections
- Negative operating cash flow with positive net income (working capital drain)

### Cash Flow Improvement Strategies
1. **Collect faster:** Tighten AR terms, automate invoicing
2. **Manage inventory:** Avoid cash drain from excess stock
3. **Delay payments:** Negotiate better AP terms (within reason)
4. **Time CapEx:** Forecast cash flow to prevent shortages

---

## Cross-References

- **Need ratio calculations?** -> `financial-ratios` (all formulas, targets, CCC)
- **Ready to build a forecast?** -> `forecasting-strategy` (uses diagnostic findings as inputs)
- **Need to optimize profit?** -> `profit-optimization` (uses diagnostic findings to identify levers)
- **AR/AP/Inventory deep dive?** -> `working-capital` (detailed management tactics)
- **Building a model?** -> `financial-modeling` (three-statement architecture uses these foundations)
- **Presenting findings?** -> `advisory-communication` (simplification framework, R-D-R format)
