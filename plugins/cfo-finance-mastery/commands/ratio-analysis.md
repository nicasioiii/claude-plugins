---
name: Ratio Analysis
description: Calculate and interpret key financial ratios from user-provided data. Covers liquidity, profitability, efficiency, leverage, return, working capital, and lending ratios. Activates financial-ratios skill.
---

# /ratio-analysis -- Financial Ratio Analysis

## Step 1: Gather Data

Ask the user:

1. **What data do you have?** P&L, Balance Sheet, or both?
2. **Time periods:** How many periods? (Trend analysis requires minimum 3)
3. **Industry:** What sector? (Needed for benchmark comparison)
4. **Purpose:** General health check, lending preparation, or specific concern?
5. **Existing debt:** Any current debt service payments? (Needed for DSCR)

## Step 2: Calculate Core Ratios

Based on available data, calculate all applicable ratios:

### Liquidity (from Balance Sheet)
- Current Ratio
- Quick Ratio

### Profitability (from P&L)
- Gross Margin %
- Operating Margin %
- Net Margin %

### Efficiency (from P&L + BS)
- Inventory Turnover (if applicable)
- AR Turnover
- AP Turnover

### Working Capital (from P&L + BS)
- DSO, DIO, DPO
- Cash Conversion Cycle (CCC)

### Leverage (from BS)
- Debt-to-Equity
- Interest Coverage

### Return (from P&L + BS)
- ROA
- ROE

### Lending (if purpose = lending)
- DSCR
- Leverage Ratio

## Step 3: Interpret Results

For each ratio:
1. **State the number** with the formula used
2. **Compare to target/benchmark** from ratio-reference.md
3. **Assess trend** (improving, declining, or stable across periods)
4. **Flag red flags** if any ratio is in danger zone

## Step 4: CCC Deep Dive (if applicable)

If working capital data is available:
- Calculate DSO, DIO, DPO individually
- Calculate CCC
- Compare to industry typical range
- Identify which component has the most room for improvement

## Step 5: Summary Dashboard

Present a ratio scorecard:

| Category | Ratio | Value | Target | Status |
|----------|-------|-------|--------|--------|
| Liquidity | Current | X.X | >1.5 | OK/Warning/Critical |
| ... | ... | ... | ... | ... |

## Step 6: Recommendations

- Prioritize the 2-3 most actionable ratio improvements
- Suggest follow-up commands:
  - `/working-capital` if CCC needs improvement
  - `/optimize-profit` if margins need improvement
  - `/financing-decision` if lending ratios need strengthening
