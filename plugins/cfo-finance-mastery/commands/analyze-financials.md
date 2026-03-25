---
name: Analyze Financials
description: Guided diagnosis of P&L, balance sheet, and cash flow statements. Runs vertical, horizontal, and variance analysis. Identifies profit leaks, red flags, and misclassifications. Activates financial-diagnostics skill with cross-references to financial-ratios.
---

# /analyze-financials -- Financial Statement Diagnosis

## Step 1: Gather Financial Data

Ask the user:

1. **Which statements do you have?** P&L / Balance Sheet / Cash Flow / All three?
2. **Time period:** How many months or years of data? (Minimum 6 months recommended for trend analysis)
3. **Business type:** What industry? (Needed for benchmark comparison)
4. **Accounting basis:** Cash or accrual?
5. **Specific concerns:** Any known issues or areas of focus?

## Step 2: P&L Diagnosis (if provided)

Run these analyses in order:

### A. Structure Check
- Verify COGS vs SG&A classification is correct
- Check for missing items (depreciation, amortization commonly missing)
- Confirm revenue recognition method

### B. Vertical Analysis
- Calculate every line item as % of revenue
- Flag items that deviate > 5% from industry benchmarks
- Identify the largest expense categories

### C. Horizontal Analysis
- Compare periods (MoM or YoY depending on data available)
- Calculate $ change and % change for each line
- Flag items with unusual spikes or declines

### D. Margin Analysis
- Calculate gross margin, operating margin, net margin
- Assess the margin cascade (where is profit being lost?)
- Compare to industry benchmarks from financial-ratios/ratio-reference.md

### E. Profit Leak Identification
- Identify top 3-5 areas where margin is being eroded
- Prioritize by dollar impact
- Provide actionable recommendation for each

## Step 3: Balance Sheet Diagnosis (if provided)

- Check the BS equation (Assets = L + E)
- Scan for common small business errors (9-item checklist from financial-diagnostics)
- Assess liquidity (current assets vs current liabilities)
- Check asset-liability matching
- Identify unusual balances or trends

## Step 4: Cash Flow Diagnosis (if provided)

- Assess operating cash flow vs net income gap
- Check for red flags (financing propping up operations, negative OCF with positive NI)
- Identify cash flow improvement opportunities
- Assess whether the business generates cash from operations (healthy pattern)

## Step 5: Summary and Recommendations

Deliver findings using the Recommendation-Data-Recommendation format:

1. **Lead with the top finding** (most impactful issue)
2. **Support with specific numbers** (the data)
3. **Close with prioritized action items** (1-3 next steps)

Suggest follow-up commands:
- `/ratio-analysis` if ratios would deepen the diagnosis
- `/build-forecast` if the user wants to project improvements
- `/optimize-profit` if profit leaks were identified
