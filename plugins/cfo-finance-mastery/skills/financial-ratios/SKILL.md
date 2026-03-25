---
name: Financial Ratios
description: "MANDATORY TRIGGERS: financial ratio, current ratio, quick ratio, gross margin ratio, operating margin, net margin, debt-to-equity, interest coverage, ROA, ROE, inventory turnover, AR turnover, AP turnover, DSO, DIO, DPO, cash conversion cycle, CCC, DSCR, debt service coverage, leverage ratio, lending ratio, liquidity ratio, profitability ratio, efficiency ratio, return ratio, working capital ratio, ratio analysis, ratio benchmark, ratio red flag. FOR: Anyone who needs to calculate, interpret, or benchmark financial ratios -- liquidity, profitability, efficiency, leverage, return, working capital, or lending ratios. Includes targets, interpretation guidance, and red flag triggers. Do NOT use for: [reading/diagnosing financial statements (qualitative)] use financial-diagnostics; [AR/AP/inventory management tactics] use working-capital; [evaluating financing options] use financing-strategy; [building ratio dashboards in Excel] use dashboards-and-reporting + excel-for-finance."
---

# Financial Ratios

You are a financial ratio analyst. Your job is to help users calculate, interpret, and act on financial ratios. Every ratio must be paired with a target, context for interpretation, and a recommended action if the ratio is outside healthy range.

**Core philosophy:** Ratios are diagnostic tools, not answers. A single ratio in isolation is meaningless. Compare ratios against: (1) industry benchmarks, (2) the same business over time, (3) targets set in the forecast. The trend matters more than the snapshot.

**Source:** Leikauf (CFO Mastery, Section 4) provides all ratio definitions, targets, and lending ratio thresholds. CCC was described as "the instructor's favorite ratio" and receives special treatment.

---

## Liquidity Ratios

Measure the ability to meet short-term obligations.

| Ratio | Formula | Target | Interpretation |
|-------|---------|--------|---------------|
| **Current Ratio** | Current Assets / Current Liabilities | > 1.5 preferred | Below 1.0 = cannot cover short-term debts. Above 3.0 = may have idle assets. |
| **Quick Ratio** | (Current Assets - Inventory) / Current Liabilities | > 1.0 | Stricter test -- excludes inventory (may be hard to liquidate quickly). |

**When current ratio is low but quick ratio is acceptable:** Inventory is the issue. Investigate slow-moving stock.
**When both are low:** Genuine liquidity crisis. Immediate working capital intervention needed.

---

## Profitability Ratios

Measure how efficiently the business generates profit.

| Ratio | Formula | Interpretation |
|-------|---------|---------------|
| **Gross Margin** | Gross Profit / Revenue | Production efficiency and pricing power. Industry-specific benchmarks critical. |
| **Operating Margin** | Operating Income / Revenue | Core business profitability after overhead. Shows management efficiency. |
| **Net Profit Margin** | Net Income / Revenue | Bottom-line after all costs including interest and taxes. |

**Margin cascade analysis:** If gross margin is healthy but net margin is thin, the problem is in SG&A (overhead too high). If gross margin itself is weak, the problem is COGS or pricing. Work from top to bottom.

---

## Efficiency Ratios

Measure how well the business uses its assets.

| Ratio | Formula | Direction |
|-------|---------|-----------|
| **Inventory Turnover** | COGS / Average Inventory | Higher = better (selling faster) |
| **AR Turnover** | Net Credit Sales / Average AR | Higher = better (collecting faster) |
| **AP Turnover** | Total Purchases / Average AP | Lower = better (paying slower, preserving cash) |

**Turnover to days conversion:**
```
Days = 365 / Turnover Ratio
```

---

## Leverage Ratios

Measure financial risk from debt usage.

| Ratio | Formula | Target | Interpretation |
|-------|---------|--------|---------------|
| **Debt-to-Equity** | Total Debt / Total Equity | Industry-dependent | Higher = more leveraged. Above 2.0 signals high risk for most industries. |
| **Interest Coverage** | EBITDA / Interest Expense | > 3.0 | Below 1.5 = struggling to service debt. Below 1.0 = cannot cover interest. |

---

## Return Ratios

Measure return generated on invested capital.

| Ratio | Formula | Interpretation |
|-------|---------|---------------|
| **ROA** (Return on Assets) | Net Income / Total Assets | How efficiently assets generate profit. Higher = better asset utilization. |
| **ROE** (Return on Equity) | Net Income / Shareholder Equity | Return to owners. High ROE with high D/E = leveraged return (risky). |

**DuPont decomposition of ROE:**
```
ROE = Net Margin x Asset Turnover x Equity Multiplier
    = (Net Income/Revenue) x (Revenue/Assets) x (Assets/Equity)
```
This reveals WHETHER high ROE comes from profitability, efficiency, or leverage.

---

## Working Capital Ratios

Measure how fast cash moves through the business.

| Ratio | Formula | Goal |
|-------|---------|------|
| **DSO** (Days Sales Outstanding) | (AR / Revenue) x 365 | Lower = collecting faster |
| **DIO** (Days Inventory Outstanding) | (Inventory / COGS) x 365 | Lower = selling faster |
| **DPO** (Days Payable Outstanding) | (AP / COGS) x 365 | Higher = paying slower (preserving cash) |

### Cash Conversion Cycle (CCC)

**The instructor's favorite ratio** (Leikauf). Measures how fast a dollar invested turns back into more dollars.

```
CCC = DSO + DIO - DPO
```

**Interpretation:**
- Lower CCC = healthier cash cycle
- Negative CCC = the business collects cash before paying suppliers (ideal -- Amazon model)
- High CCC = cash is trapped in operations

**Example:**
```
DSO = 45 days (collecting in 45 days)
DIO = 30 days (inventory sits 30 days)
DPO = 60 days (paying suppliers in 60 days)
CCC = 45 + 30 - 60 = 15 days
```

**CCC improvement levers:**
1. Reduce DSO: Tighten payment terms, automate collections -> working-capital
2. Reduce DIO: Better inventory management, ABC analysis -> working-capital
3. Increase DPO: Negotiate longer payment terms -> working-capital

---

## Lending Ratios

Critical for financing decisions and lender presentations.

| Ratio | Formula | Target | Notes |
|-------|---------|--------|-------|
| **DSCR** (Debt Service Coverage) | EBITDA / Total Annual Debt Service | > 1.25 | Most important lending ratio. Higher = safer. |
| **Leverage Ratio** | Total Debt / EBITDA (or Cash Flow or Equity) | Lower is better | Varies by lender definition. Always ask how the lender calculates it. |
| **Current Ratio** | Current Assets / Current Liabilities | > 1.5 for lending | Lenders want higher threshold than operational minimum. |
| **Quick Ratio** | (CA - Inventory) / CL | > 1.0 | Stricter liquidity test for lending. |

### Red Flags for Lenders (Leikauf)
- DSCR below 1.25
- High debt-to-equity (above industry norms)
- Poor current ratio (below 1.5)
- Unexplained financial fluctuations
- Off-balance sheet obligations or lack of transparency
- Declining trends in any key ratio

### Improving Lending Position
- **Improve DSCR:** Cut costs, boost profit, or refinance to lower debt service
- **Reduce leverage:** Pay down debt, raise equity
- **Improve working capital ratios:** Collect AR faster, manage inventory tighter
- **Clean financials:** Organized, accurate numbers with clear justifications

---

## Ratio Analysis Process

1. **Calculate all relevant ratios** for current period
2. **Compare to prior periods** (trend analysis -- minimum 6-12 months)
3. **Compare to industry benchmarks** (if available)
4. **Compare to budget/forecast targets**
5. **Identify outliers** -- any ratio significantly above or below expected range
6. **Investigate root causes** -- ratios tell you WHERE the problem is, not WHY
7. **Recommend actions** -- every finding needs a next step

---

## Cross-References

- **Financial statement data for ratio inputs** -> `financial-diagnostics` (P&L, BS, CF interpretation)
- **Working capital management to improve CCC** -> `working-capital` (AR/AP/inventory tactics)
- **Lending ratio improvement for financing** -> `financing-strategy` (Five Cs, lender relationships)
- **Profit margin improvement** -> `profit-optimization` (pricing, cost reduction, revenue levers)
- **Ratio dashboards** -> `dashboards-and-reporting` (KPI cards, gauge charts)
