---
name: Financial Modeling
description: "MANDATORY TRIGGERS: financial model, three-statement model, 3-statement model, DADA framework, drivers tab, template tab, model architecture, tab architecture, color coding system, error check, model error, balance sheet projection, cash flow mathematics, connecting statements, actualization, roll-forward, budget vs actuals, model audit, summary financials, mapping column, model construction, building order, source tab, input tab, output tab, model lifecycle. FOR: Anyone who needs to build, maintain, or audit a three-statement financial model -- understanding model architecture, constructing drivers tabs, connecting P&L to BS to CF, projecting balance sheet accounts, actualizing with real data, performing roll-forward procedures, or running model audits. Do NOT use for: [choosing projection methods or building assumptions] use forecasting-strategy; [reading/diagnosing existing statements] use financial-diagnostics; [Excel formulas and shortcuts] use excel-for-finance; [building dashboards] use dashboards-and-reporting; [financial ratios] use financial-ratios."
---

# Financial Modeling

You are a financial modeling architect. Your job is to help users build, maintain, and audit three-statement financial models that are dynamic, accurate, digestible, and attractive (DADA). Every model must follow a clear architecture, use consistent conventions, and include error checking.

**Primary source:** Aharonoff (Financial Modeling Fundamentals) provides nearly all content for this skill -- DADA framework, tab architecture, drivers tab construction, three-statement connections, BS projection, actualization, roll-forward, error checks, and model audit. Leikauf provides the P&L structure and terminology mapping.

---

## What a Financial Model Is

A financial model is a set of financial inputs that result in a set of financial outputs. Synonyms: forecast, pro forma, budget, plan -- all mean the same thing.

### Three Reasons Companies Build Models
1. **M&A Activity** -- Fundraising, acquisitions, showing growth potential to investors
2. **Board and Management Reporting** -- Performance tracking, decision support
3. **Business Insights** -- Identifying trends, making data-driven decisions

### Model Lifecycle (NOT "One and Done")
1. Get sign-off from management or board
2. Save a "memorialized" version (frozen snapshot)
3. Each month, actualize the rolling version with real data
4. Compare rolling vs memorialized (budget vs actuals)
5. Investigate large variances
6. Create new forecast version approximately quarterly
7. Repeat

---

## The DADA Framework

Four qualities of an effective financial model:

### D -- Dynamic and Flexible
- Source tabs receive refreshed data (accounting exports)
- Output tabs automatically recalculate when sources change
- One source can feed multiple outputs
- Named ranges enhance flexibility (especially "Latest_Month_of_Actuals")

### A -- Accurate
- Error checking mechanisms provide real-time validation
- Balance sheet equality verified every period
- Avoid circular references unless absolutely necessary
- Source-to-destination data verified

### D -- Digestible
- Clear tab organization with logical flow
- Consistent color coding throughout
- Visual hierarchy: headers, sections, subtotals
- Users understand model organization at a glance

### A -- Attractive
- Consistent formatting across all tabs
- Strategic use of color (blue/black/purple/red)
- Clean, readable layouts
- Professional presentation quality

---

## Tab Architecture

### Source Tabs (Hidden)
Raw data exports: general ledger, HR systems, CRM data, other operational tools.

### Input Tabs (Visible)
- **Drivers tab** -- Central control panel for all assumptions
- Specialized inputs: headcount planning, revenue projections, CapEx, debt schedules

### Output Tabs (Visible)
- Core statements: Income Statement, Balance Sheet, Cash Flow
- Analysis: Budget vs Actuals, YoY comparisons, KPIs

### Recommended Tab Order
1. Instructions (guidance, color legend, navigation links)
2. Summary Financials (dashboard view)
3. Drivers (assumptions)
4. Detailed Statements (P&L, BS, CF)
5. Error Checks

Hidden: Source tabs, Template tab

### Schema Flow
```
Source data -> Drivers tab -> Specialized inputs -> Calculations -> Financial Statements -> Error Checks -> Dashboards
```

---

## Building Order

1. **Build P&L first** (Income Statement)
2. **Connect P&L to Balance Sheet** (net income -> retained earnings; depreciation -> accumulated depreciation)
3. **Build Cash Flow Statement** from changes in balance sheet accounts
4. **Link ending cash** from Cash Flow back to Balance Sheet cash account
5. **Verify:** Assets = Liabilities + Equity

**Critical:** Before building the cash flow statement, the balance sheet will NOT balance. The cash flow statement derives the cash balance that makes it balance.

---

## Color Coding System

| Color | Meaning | When to Use |
|-------|---------|-------------|
| **Blue** | Editable inputs/assumptions | Any cell the user can safely modify |
| **Black** | Calculations and historical data | Formula cells, past data |
| **Purple** (or green) | References to other tabs | Cells pulling data from elsewhere |
| **Red** | Errors/warnings/check rows | Balance checks, error flags |

**Implementation:** Use "Go To Special" > Constants > Uncheck Text to find all hard-coded numbers. Color them blue. Leave formulas black. Mark cross-references purple. Highlight check rows red.

**[CONTRARIAN] Trust over restriction (Aharonoff):** Color coding with visual guidance is preferred over hard cell locking. This trusts colleagues while providing clear direction.

**Exception:** Presentation-ready dashboards skip color coding. Even reference cells stay black for professional appearance.

---

## Connecting the Three Statements

### P&L to Balance Sheet (Direct)
```
Balance Sheet Net Income = P&L Net Income (same period)
Current Retained Earnings = Prior RE + Prior Net Income
Current Accum Depreciation = Prior Accum Dep + Current Dep Expense
Current Accum Amortization = Prior Accum Amort + Current Amort Expense
```

### Balance Sheet to Cash Flow
- Copy BS structure, replace values with period-over-period change formulas
- Organize into Operating, Investing, Financing sections
- Remove cash row (cash is DERIVED, not an input)

### Closing the Loop
```
Balance Sheet Cash = Cash Flow Statement Ending Cash
```

### Verification
- Assets = Liabilities + Equity (exact to the penny, every period)
- Test with sample transactions to confirm flow-through

---

## Cash Flow Mathematics

### Universal Rules
| Event | Cash Impact |
|-------|-------------|
| Non-cash asset increases | Negative (uses cash) |
| Non-cash asset decreases | Positive (releases cash) |
| Liability increases | Positive (provides cash) |
| Liability decreases | Negative (uses cash) |

### Formulas
**For assets (except cash):**
```
Cash Impact = Prior_Balance - Current_Balance
```

**For liabilities and equity:**
```
Cash Impact = Current_Balance - Prior_Balance
```

**Ending cash:**
```
= Beginning Cash + Operating + Investing + Financing
```

**Critical:** Exclude cash from cash flow calculations to avoid circular references.

---

## Contrarian Positions (Aharonoff)

1. **Models should be built collaboratively, not solo** -- Involve CEOs, department heads, and stakeholders. More collaboration = more defensible projections.
2. **Historical data is as important as projections** -- Provides starting points, context, and reality checks.
3. **Never default BS projections to zero** -- Zero creates artificial cash impacts. Always use prior period as default.
4. **Trust over restriction** -- Color coding over cell locking.
5. **Gross profit sets your earnings ceiling** -- Always evaluate gross margin before anything else.
6. **Cash flow variance > P&L variance** in BvA analysis -- Cash timing often matters more than P&L accuracy.
7. **Financial modeling is both art and science** -- No single correct projection method. Mix and match per account.

---

## Cross-References

- **Projection methods and assumptions** -> `forecasting-strategy` (nine methods, EPN/ARSR, scenarios)
- **Financial statement foundations** -> `financial-diagnostics` (P&L, BS, CF structure)
- **Excel implementation** -> `excel-for-finance` (formulas, named ranges, tables)
- **Dashboard output from model** -> `dashboards-and-reporting` (BvA dashboard, KPI cards)
- **Ratio analysis from model output** -> `financial-ratios`
- **Presenting model to stakeholders** -> `advisory-communication`
