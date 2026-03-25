---
name: "Complete Ratio Reference"
description: "All financial ratio formulas, targets, interpretation guidance, CCC deep dive, lending ratio thresholds, DuPont analysis, red flag triggers, and ratio-based decision frameworks."
when_to_read: "When the user needs specific ratio formulas, benchmark targets, CCC optimization guidance, lending ratio thresholds, or DuPont decomposition."
---

# Complete Ratio Reference

## All Ratios -- Quick Reference Table

### Liquidity Ratios
| Ratio | Formula | Target | Red Flag |
|-------|---------|--------|----------|
| Current Ratio | Current Assets / Current Liabilities | > 1.5 | < 1.0 |
| Quick Ratio | (Current Assets - Inventory) / CL | > 1.0 | < 0.5 |
| Cash Ratio | Cash / Current Liabilities | > 0.2 | < 0.1 |

### Profitability Ratios
| Ratio | Formula | Benchmark | Red Flag |
|-------|---------|-----------|----------|
| Gross Margin | Gross Profit / Revenue | Industry-dependent | Declining trend |
| Operating Margin | EBIT / Revenue | Industry-dependent | < 5% for most |
| Net Margin | Net Income / Revenue | Industry-dependent | Negative or declining |
| EBITDA Margin | EBITDA / Revenue | Industry-dependent | < Operating Margin (impossible -- signals calculation error) |

### Efficiency Ratios
| Ratio | Formula | Goal | Red Flag |
|-------|---------|------|----------|
| Inventory Turnover | COGS / Avg Inventory | Higher is better | < 4x for most retail |
| AR Turnover | Net Credit Sales / Avg AR | Higher is better | < 6x (60+ day collections) |
| AP Turnover | Purchases / Avg AP | Lower preserves cash | Extremely low may damage vendor relationships |
| Asset Turnover | Revenue / Total Assets | Higher is better | Declining = asset bloat |

### Leverage Ratios
| Ratio | Formula | Target | Red Flag |
|-------|---------|--------|----------|
| Debt-to-Equity | Total Debt / Total Equity | < 2.0 for most | > 3.0 |
| Interest Coverage | EBITDA / Interest Expense | > 3.0 | < 1.5 |
| Debt-to-Assets | Total Debt / Total Assets | < 0.5 | > 0.7 |

### Return Ratios
| Ratio | Formula | Benchmark | Red Flag |
|-------|---------|-----------|----------|
| ROA | Net Income / Total Assets | > 5% | < 2% |
| ROE | Net Income / Equity | > 15% | Negative |
| ROIC | NOPAT / Invested Capital | > WACC | Below cost of capital |

### Working Capital Ratios
| Ratio | Formula | Goal | Red Flag |
|-------|---------|------|----------|
| DSO | (AR / Revenue) x 365 | < Payment terms | > 2x payment terms |
| DIO | (Inventory / COGS) x 365 | Industry-dependent | > 90 days for most |
| DPO | (AP / COGS) x 365 | Higher preserves cash | > 90 days risks vendor damage |
| CCC | DSO + DIO - DPO | Lower is better | > 90 days |

### Lending Ratios
| Ratio | Formula | Lender Target | Danger Zone |
|-------|---------|--------------|-------------|
| DSCR | EBITDA / Annual Debt Service | > 1.25 | < 1.0 (cannot cover) |
| Leverage | Total Debt / EBITDA | < 3.0x | > 5.0x |
| Current (lending) | CA / CL | > 1.5 | < 1.0 |
| Quick (lending) | (CA - Inv) / CL | > 1.0 | < 0.5 |

---

## CCC Deep Dive

### The Formula
```
CCC = DSO + DIO - DPO
```

### Component Calculation
```
DSO = (Accounts Receivable / Annual Revenue) x 365
DIO = (Average Inventory / Annual COGS) x 365
DPO = (Accounts Payable / Annual COGS) x 365
```

For monthly calculation, substitute 30 (or actual days in month) for 365 and use monthly figures.

### CCC by Business Type
| Business Type | Typical CCC | Key Driver |
|--------------|------------|------------|
| E-commerce (dropship) | Negative to 10 days | No inventory, fast collection |
| SaaS | Negative (prepaid subscriptions) | Collect before delivering |
| Retail | 30-60 days | Inventory turnover |
| Manufacturing | 60-120 days | Long production cycles |
| Construction | 90-180 days | Long project timelines, slow collection |
| Professional services | 30-60 days | No inventory, but slow AR |

### CCC Improvement Actions
**Reduce DSO (collect faster):**
- Bill every 28 days instead of monthly (Leikauf contrarian -- adds extra billing cycle per year)
- Offer small discounts for early payment (only if > 30% annualized return)
- Automate invoicing and follow-up
- Require deposits or progress billing

**Reduce DIO (turn inventory faster):**
- ABC analysis to focus on high-value items
- JIT ordering
- Clear slow-moving stock with promotions
- Negotiate consignment arrangements

**Increase DPO (pay slower):**
- Negotiate Net 45 or Net 60 with vendors
- Use volume leverage to get better terms
- Automate payments to pay on the due date, never early
- Skip early-pay discounts unless they beat 30% annualized (Leikauf)

---

## DuPont Analysis

Decomposes ROE into three drivers:

```
ROE = Net Margin x Asset Turnover x Equity Multiplier
    = (Net Income / Revenue) x (Revenue / Total Assets) x (Total Assets / Equity)
```

### Interpretation
| Driver | What It Measures | If This Is High |
|--------|-----------------|----------------|
| Net Margin | Profitability | Business is profitable per dollar of revenue |
| Asset Turnover | Efficiency | Business generates revenue efficiently from assets |
| Equity Multiplier | Leverage | Business uses significant debt financing |

**High ROE from leverage alone is risky.** A 25% ROE driven by 5x leverage is far riskier than 25% ROE driven by strong margins and efficiency.

---

## Industry Benchmark Guidelines

These are rough guides. Always validate with current industry data.

| Industry | Gross Margin | Operating Margin | Current Ratio | D/E |
|----------|-------------|-----------------|---------------|-----|
| SaaS | 70-85% | 15-25% | 1.5-3.0 | 0.5-1.5 |
| E-commerce | 30-60% | 5-15% | 1.2-2.0 | 0.5-2.0 |
| Professional Services | 50-70% | 15-30% | 1.5-3.0 | 0.2-1.0 |
| Manufacturing | 25-45% | 8-15% | 1.5-2.5 | 1.0-2.5 |
| Construction | 20-35% | 5-12% | 1.2-1.8 | 1.0-3.0 |
| Restaurant | 60-70% | 5-15% | 0.8-1.5 | 1.0-3.0 |
| Healthcare | 40-60% | 10-20% | 1.5-2.5 | 0.5-1.5 |

---

## Ratio Red Flag Summary

### Immediate Action Required
- Current ratio < 1.0 (cannot pay short-term obligations)
- DSCR < 1.0 (cannot service debt)
- Interest coverage < 1.0 (cannot pay interest)
- Negative equity (liabilities exceed assets)

### Investigation Required
- Any ratio declining for 3+ consecutive periods
- Gross margin declining while revenue grows (pricing or COGS issue)
- DSO > 2x stated payment terms (collection problem)
- Inventory turnover declining (demand drop or overstocking)
- D/E increasing without corresponding revenue growth

### Monitor Closely
- CCC increasing (cash cycle slowing)
- ROE increasing due to leverage only (DuPont reveals)
- Operating margin flat while revenue grows (scaling costs not controlled)

---

## Cross-References

- **Statement data needed for calculations** -> `financial-diagnostics` (P&L, BS structure)
- **Working capital improvement tactics** -> `working-capital/ar-ap-inventory.md`
- **Lending ratio preparation** -> `financing-strategy/five-cs-and-lending.md`
- **Margin improvement** -> `profit-optimization/profit-levers.md`
