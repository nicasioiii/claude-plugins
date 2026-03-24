---
name: Power Query & Dynamic Excel Dashboards
description: "Transform wide-format data into tall tables using Power Query, then build dynamic dashboards with automatic updates. MANDATORY TRIGGERS: 'I need a dashboard for my financials', 'How do I turn my model into something usable', 'I want real-time reporting', 'My dashboard is too manual'. Do NOT use for data architecture changes (that's data-engineering scope) or building the model itself (use financial-modeling-excel instead) — this skill is display layer only."
---

# Power Query & Dynamic Excel Dashboards

## Overview

Most financial dashboards fail because they're built on wide-format data (dates as columns). They're hard to filter, slow to calculate, and break when you add new dates.

Professional dashboards use tall tables (dates as rows) powered by Power Query. Change the source data, and dashboard updates automatically. No manual refreshes. No broken formulas.

This skill teaches you to build dashboards that stay current and professional.

---

## The Format Problem: Wide vs. Tall

### Wide Format (Human-Readable, Computer-Hostile)

```
Account       Jan 2024  Feb 2024  Mar 2024
Revenue       100,000   105,000   110,000
COGS           40,000    42,000    44,000
Gross Profit   60,000    63,000    66,000
```

**Problems:**
- To add April, you must insert a new column
- Formulas are hardcoded to columns ("Column E is February")
- Pivot tables can't filter easily
- Dashboards require complex INDEX/MATCH lookups

### Tall Format (Computer-Friendly, Less Human-Readable)

```
Account      Date        Amount
Revenue      2024-01-31  100,000
Revenue      2024-02-28  105,000
Revenue      2024-03-31  110,000
COGS         2024-01-31  40,000
COGS         2024-02-28  42,000
COGS         2024-03-31  44,000
```

**Benefits:**
- Add April as new row (no column insertion)
- Formulas filter by date dynamically
- Pivot tables work perfectly
- Dashboards use simple date range filters

**Rule:** All data for dashboards must be tall format. Use Power Query to convert wide → tall.

---

## The Dashboard Architecture

**Three-layer stack:**

**Layer 1: Data Table (tall format)**
- One row per account per date
- Columns: Account, Summary_Group, Financial_Statement, Date, Amount
- Updated by Power Query

**Layer 2: Summarization Layer (SUMPRODUCT formulas)**
- Pulls from Data Table
- Intelligently sums (Income Statement) or indexes (Balance Sheet)
- Respects date range filters

**Layer 3: Visualization (charts and KPIs)**
- References summarization formulas
- User selects date range
- Everything updates automatically

---

## Power Query Workflow (5 Steps)

### Table Requirements for Power Query (Non-Negotiable)
1. Headers in row 1 only (no merged cells in header)
2. No subtotal rows (Power Query treats them as data rows)
3. No blank rows or columns within data range
4. Consistent data types per column
5. No merged cells anywhere in table
If source data has these issues, clean them FIRST.

---

### Step 1: Prepare Source Data (Wide Format)

Your financial model or GL export:
```
Account       Jan 2024  Feb 2024  Mar 2024
Revenue       100,000   105,000   110,000
COGS           40,000    42,000    44,000
```

### Step 2: Convert to Excel Table

1. Select all source data
2. Ctrl+T (create table)
3. Name it: "IncomeStatementTable" (or similar)
4. Result: Table that auto-expands

### Step 3: Open Power Query

1. Data → Get Data → From Table or Range
2. Selects your table
3. Power Query Editor opens

### Step 4: Transform (Unpivot)

**In Power Query Editor:**

1. Select Account column (keep it selected)
2. Ctrl+Right-click → Unpivot Other Columns
3. Result: Date headers become rows

Before:
```
Account  Jan 2024  Feb 2024
Revenue  100,000   105,000
```

After:
```
Account  Attribute  Value
Revenue  Jan 2024   100,000
Revenue  Feb 2024   105,000
```

4. Rename "Attribute" column to "Date"
5. Add custom column "FinancialStatement" = "IncomeStatement"
6. Add custom column "SummaryGroup" = corresponding category

### CRITICAL: Validate Date Format in Power Query
After unpivoting, select the Date column → Right-click → Change Type → Date.
If dates appear as decimals (44927) or text, fix here before loading.
⚠️ Most dashboard problems stem from date columns being text instead of date type.

### Step 5: Load to Excel

1. Close & Load
2. Choose: Load to Table
3. Result: Tall table with Date as rows, ready for dashboard

---

## Building the Summarization Layer

**Create sheet: "Dashboard"**

**Add date filter cells:**
```
Start Date:  [user input cell]  E.g., 1/1/2024
End Date:    [user input cell]  E.g., 12/31/2024
```

**Use SUMPRODUCT to aggregate:**

```
=SUMPRODUCT(
  (DataTable[Amount])
  * (DataTable[SummaryGroup] = "Revenue")
  * (DataTable[Date] >= StartDate)
  * (DataTable[Date] <= EndDate)
)
```

**This formula says:** Sum amounts from DataTable WHERE group = "Revenue" AND date is between start and end.

Change start/end date, formula updates automatically.

---

## Balance Sheet vs Income Statement Aggregation (Critical Difference)

**Income Statement:** SUM all values in date range (SUMPRODUCT works)

**Balance Sheet:** Get ENDING BALANCE only — do NOT sum.
For balance sheet accounts, filter to the ending date only:
=INDEX(DataTable[Amount], MATCH(1, (DataTable[Account]="Cash")*(DataTable[Date]=EndDate), 0))

Getting this wrong means your balance sheet dashboard shows cumulative nonsense.

---

## Real Dashboard Example

**Income Statement Dashboard:**

```
Period: Jan 1 - Mar 31, 2024

                        Amount      % of Revenue
Revenue                 $315,000    100.0%
  Product Sales         $310,000     98.4%
  Service Revenue       $  5,000      1.6%

COGS                   $126,000     40.0%
Gross Profit           $189,000     60.0%

Operating Expenses:
  Payroll              $ 60,000     19.0%
  Marketing            $ 25,500      8.1%
  Software             $  9,000      2.9%
  Rent                 $  9,000      2.9%
  Other                $  4,500      1.4%
Total OpEx             $108,000     34.3%

Operating Income       $ 81,000     25.7%
Net Income             $ 60,750     19.3%
```

**All numbers pull from Power Query data table using SUMPRODUCT. Change date filters and everything updates.**

---

## Advanced Features

### Budget vs. Actual Reporting

**If you have two data tables (Actual + Budget):**

1. Unpivot both
2. Add column "Type" = "Actual" or "Budget"
3. Combine both into single tall table (append)
4. In dashboard, create two SUMPRODUCT columns (Actual + Budget)
5. Add variance column (Actual - Budget)

### Period-over-Period Comparison

```
Start Date Period 1: Jan 1, 2024
End Date Period 1:   Mar 31, 2024

Start Date Period 2: Jan 1, 2023
End Date Period 2:   Mar 31, 2023

Create two SUMPRODUCT formulas with different date ranges.
Show Period 1 | Period 2 | Variance (%).
```

### Interactive Date Slicer

Power Query tables can have slicers (visual date filters):

1. Select Data table
2. Insert → Slicer
3. Choose Date column
4. Dashboard automatically filters based on slicer selection

### Pivot Table Dashboard (Alternative to SUMPRODUCT)

1. Build tall table in Power Query
2. Insert → Pivot Table
3. Drag fields to rows/columns/values
4. Result: Instant dashboard that updates when data refreshes

---

## When to Read Reference Files

**Read "Power Query Workflow"** when:
- You're unpivoting for the first time
- You need step-by-step instructions to transform data
- You're adding custom columns in Power Query

**Read "Table Structure"** when:
- You're designing the data model
- You need to understand Excel tables and naming conventions
- You're deciding between tables vs ranges

**Read "Date Transformation"** when:
- Your dates are text format (not actual dates)
- You're converting wide dates to tall dates
- You're handling month-end standardization

**Read "Summarized Statements"** when:
- You're building P&L, balance sheet, or cash flow summaries
- You need SUMPRODUCT formulas for smart aggregation
- You're creating budget vs. actual reports

**Read "Dashboard Design"** when:
- You're building the visual layer
- You want professional formatting and color schemes
- You're deciding on chart types and visual hierarchy

**Read "Dynamic Filters"** when:
- You're building date range selectors
- You want period-over-period comparisons
- You're adding interactive elements (slicers)

---

## Cross-References

**→ financial-modeling-excel** before this skill. Build your model first; Power Query consumes the model output (usually the Drivers or Summary tabs).

**→ financial-diagnostics** to interpret dashboard results. The dashboard shows numbers; diagnostics explains what they mean.

**→ forecasting-strategy** once dashboard shows historical performance and actuals. Use diagnostics and dashboards to inform forecasts.

---

## Quick Checklist: Dashboard Quality

Before considering dashboard complete:

- [ ] **Data is tall format** (dates in rows, not columns)
- [ ] **Power Query refreshes source data** (not manual updates)
- [ ] **Formulas use SUMPRODUCT** (not INDEX/MATCH or hardcoded)
- [ ] **Date filters work** (change dates, all numbers update)
- [ ] **Color scheme is consistent** (header colors, font styles)
- [ ] **Margins and percentages calculate** (% of revenue, margins)
- [ ] **Charts update dynamically** (when data changes)
- [ ] **Professional formatting** (no random decimals, proper alignment)
- [ ] **Instructions visible** (tell user what to filter, what it means)
- [ ] **Error-free** (no #VALUE!, #DIV/0!, or #REF! errors)

---

## Real-World Example: Monthly Management Dashboard

```
Dashboard View (shown to business owner):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Period: Jan - Mar 2024  [Pick Date Range]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

INCOME STATEMENT
Revenue:      $315K  (100.0%)
COGS:        ($126K) (40.0%)
─────────────────────────────────
Gross Profit: $189K  (60.0%)
OpEx:        ($108K) (34.3%)
─────────────────────────────────
Net Income:    $81K  (25.7%)

BALANCE SHEET SUMMARY
Cash:              $50K
AR:                $75K
Inventory:        $60K
─────────────────────────────────
Total Assets:     $185K

AP:                $35K
Debt:              $50K
─────────────────────────────────
Total Liab+Eq:    $185K  ✓ Balanced

KEY METRICS
Gross Margin:     60.0%
Operating Margin: 25.7%
DSO:              30 days
DIO:              20 days
DPO:              30 days
Cash Conversion:  20 days

CASH FLOW
Operating CF:     $75K
Investing CF:    ($10K)
Financing CF:    ($15K)
─────────────────────────────────
Net Change:       $50K
```

**All numbers update when user changes date filter. No manual work. Professional appearance.**

---

## Monthly Refresh (5 minutes)
1. Paste new data into original source table (wide format)
2. Data → Refresh All (Power Query re-processes automatically)
3. Dashboard SUMPRODUCT formulas recalculate instantly

---

## Dashboard Maintenance

**Monthly refresh process:**

1. Export new GL data (Jan-Mar + Apr)
2. Paste into IncomeStatementTable (wide format)
3. Power Query auto-detects new data
4. Right-click table → Refresh
5. Dashboard numbers update automatically

**Time required:** 2 minutes. No formula rewriting. No manual updates.

---

## Key Principles

1. **Tall format is non-negotiable.** Wide format breaks when you add dates.
2. **Power Query handles transformation.** Don't do manual column insertions.
3. **SUMPRODUCT aggregates intelligently.** It respects date ranges and categories.
4. **Date filters drive everything.** Select period, all charts update.
5. **Professional formatting matters.** Credibility increases with polish.
6. **Dashboards are display layer.** Models provide data; dashboards display it beautifully.

