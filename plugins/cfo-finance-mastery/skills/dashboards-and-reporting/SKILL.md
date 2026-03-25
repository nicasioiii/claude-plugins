---
name: Dashboards & Reporting
description: "Build Excel dashboards with Power Query data transformation, KPI cards, budget vs actuals, cash-out, break-even, spotlight, and pivot table dashboards. MANDATORY TRIGGERS: 'I need a dashboard', 'How do I monitor my business monthly', 'Budget vs actuals', 'KPI tracking', 'Cash runway visualization', 'Break-even chart', 'Power Query for finance'. FOR: building financial dashboards, setting up Power Query ETL, creating KPI cards, budget variance visualization, cash-out date tracking, management reports. Do NOT use for raw Excel formula help without dashboard context (use excel-for-finance), financial model construction (use financial-modeling), or presentation/communication strategy (use advisory-communication)."
---

# Dashboards & Reporting

## Overview

A dashboard is only as strong as the data feeding it. Most finance teams build dashboards backward -- they design the visual first, then hack data to fit. The correct approach is data-architecture-first: transform your data into machine-readable format, build a universal formula layer, then design the presentation on top.

**Core philosophy (Aharonoff):** Excel dashboards should look so good audiences cannot tell they are Excel. Invest in design the same way you invest in data accuracy.

**Three design truths:**
1. **Data layer = machine-readable** (tall/narrow tables, Power Query transformed)
2. **Formula layer = one formula fits all** (SUMPRODUCT with sum/index switching)
3. **Presentation layer = human-readable** (brand colors, KPI cards, gauge charts)

> Cross-reference: For Excel formula mechanics (SUMPRODUCT syntax, EOMONTH, named ranges), see `excel-for-finance`. For model outputs feeding dashboards, see `financial-modeling`. For presenting dashboard insights to stakeholders, see `advisory-communication`.

---

## Dashboard-First Data Architecture

### The Transformation Pipeline

Raw financial data (wide format with dates as columns) must be converted to tall/narrow format before any dashboard work begins. This unlocks SUMPRODUCT, pivot tables, and dynamic filtering.

**Six-step pipeline:**
1. **Add Summary Grouping column** to each financial statement (IS, BS, CF) -- maps accounts to summary categories. Never include total rows (causes double-counting).
2. **Create Aggregation Mapping table** -- two methods: "Sum" (IS/CF accounts, add values between dates) and "Index" (BS accounts, take value at end date only).
3. **Convert to Excel Tables** (Ctrl+T) -- auto-expanding references, structured syntax.
4. **Load into Power Query** -- unpivot each statement, add Financial Statement label column, load as connection only.
5. **Append Queries** -- stack IS + BS + CF into one combined query.
6. **Parse Dates + Merge Mapping** -- convert text dates to proper dates (EOMONTH), merge aggregation mapping on Account + Financial Statement.

**Refresh workflow:** Update source data, click Data > Refresh All. All queries cascade-refresh automatically. Validate by filtering blank aggregation -- should only show intentionally excluded total rows.

> See `power-query-workflow.md` for full step-by-step Power Query instructions.

---

## The Universal SUMPRODUCT Formula

The single most important formula for financial dashboards. One formula works for income statement (sum between dates) AND balance sheet (index at end date).

### How It Works

```
=SUMPRODUCT(
  (Data[Value]) *
  (Data[Summary Grouping] = $C8) *
  (Data[Date] >= IF(INDEX(Data[Aggregation],
    MATCH($C8, Data[Summary Grouping], 0)) = "Sum",
    StartDate, EndDate)) *
  (Data[Date] <= EndDate)
)
```

**The logic:** The IF/INDEX/MATCH checks the aggregation method for each account. If "Sum" (revenue, expenses), it sums the full date range. If "Index" (cash, debt, AR), it takes only the end-date value. Copy across hundreds of cells without modification.

### When to Use SUMPRODUCT vs SUMIFS

| Use Case | Formula | Why |
|----------|---------|-----|
| Dashboard calculations | SUMPRODUCT | Multi-criteria with date ranges, sum/index switching |
| Driver tab historicals | SUMIFS | Pulling from source tabs to driver structure |
| Simple conditional sums | SUMIFS | Structured data, single direction |
| Cross-tab lookups | SUMPRODUCT | Works on data in any orientation |

> Cross-reference: For SUMIFS syntax and locking patterns, see `excel-for-finance > financial-formulas.md`.

---

## Date Architecture (Three Tiers)

Every dashboard needs a date structure supporting annual, quarterly, and monthly views.

| Tier | Start Date | End Date | Display Format |
|------|-----------|----------|----------------|
| Annual | 1/1/YYYY | EOMONTH(Start, 11) | YYYY |
| Quarterly | First of quarter | EOMONTH(Start, 2) | "Q" & ROUNDUP(MONTH/3, 0) |
| Monthly | First of month | EOMONTH(Start, 0) | mmm-yy |

**Actuals vs Projections label:**
```
=IF(EndDate > LatestMonthOfActuals, "Projected", "Actual")
```

**Layout best practices:** Column A = padding, Column B = headers, Column C = account names (wide), Column D = padding before dates. Remove gridlines, group columns by period type (Alt+A+G), freeze panes at date boundary.

---

## Dashboard Types

### 1. Summarized Financial Reports
The foundation layer. Formula-driven P&L, BS, and CF statements with period-over-period change columns. Uses the universal SUMPRODUCT formula across all rows and date columns. Delta columns show dollar change and percentage change.

**Calculated lines in the dashboard (not from source data):**
- Gross Profit = Revenue - COGS
- Gross Margin = IFERROR(GrossProfit / Revenue, 0)
- Net Operating Income = Gross Profit - Total Operating Expenses
- Net Income = Net Operating Income + Net Other Income
- BS check: Total Assets - (Total Liabilities + Total Equity) = 0
- Cash Burn = Cash from Operating + Cash from Investing

**Period-over-period change rules:**
- Dollar change: `=CurrentPeriod - PriorPeriod`
- Percentage change: `=IFERROR(DollarChange / ABS(PriorPeriod), 0)` -- always ABS() in denominator
- Group delta columns (Alt+A+G) for collapsible view

### 2. KPI Card Dashboard
Grid-based layout (all rows 10.5, all columns 1.29) with branded KPI cards. Each card shows: metric name, current value, comparison value, date range, and percentage change with directional arrow (Alt+30 up, Alt+31 down). Uses Data Validation dropdowns for date selectors and metric selection.

**KPI Selection Guidance by Audience:**

| Audience | Recommended KPIs |
|----------|-----------------|
| Owner/CEO | Revenue, Net Income, Ending Cash, Cash Burn, Gross Margin |
| Board | Revenue Growth %, Net Margin %, Cash Runway, Headcount |
| Operations | COGS %, OpEx by category, Revenue per Employee |
| Lenders | DSCR, Debt/Equity, Current Ratio, Cash Balance |

> Cross-reference: For ratio definitions and benchmarks, see `financial-ratios`. For CCC and working capital KPIs, see `working-capital`.

### 3. Budget vs Actuals Dashboard
Dual data source (actuals + budget). Import budget as separate Power Query data table with identical structure. Use Find & Replace ("Data" to "Budget") to migrate formulas.

**Variance direction rules (contrarian -- do NOT use consistent formula direction):**

| Line Item | Formula | Logic |
|-----------|---------|-------|
| Revenue | Actual - Budget | Higher actual = favorable = positive |
| COGS / Expenses | Budget - Actual | Lower actual = favorable = positive |
| Gross Margin % | Actual - Budget | Direct subtraction |
| Net Income | Actual - Budget | Higher = favorable |
| Cash Burn | Budget - Actual | Less burn = favorable |
| Ending Cash | Actual - Budget | More cash = favorable |

**Percentage:** `=IFERROR(DollarVariance / ABS(BudgetValue), 0)` -- ABS() prevents sign-flip.

Gauge/donut charts visualize variance magnitude. Four-column data setup auto-switches between positive (green) and negative (warning color) display.

### 4. Management Report
Multi-comparison: Actual | vs Budget ($ and %) | vs Prior Year ($ and %) | vs Prior Period ($ and %). Uses EDATE for prior year offset (`=EDATE(StartDate, -12)`). Center Across Selection for header groupings (never Merge & Center -- merged cells break column selection and sorting).

**Scalable column copying pattern:**
1. Lock Actual column reference (`$D$2`)
2. Copy formula block to new comparison column
3. Find & Replace data source name (e.g., "Data" to "Budget")
4. Same formula structure works for any comparison period

### 5. Cash-Out Dashboard
Shows the date when cash goes negative. Uses FILTER + INDEX to find first negative ending cash date. Dynamic spill arrays plot N months leading up to cash-out. Named range bridging connects spill arrays to charts.

### 6. Break-Even Dashboard
Shows when Net Operating Income first turns positive. Plots Gross Profit vs Total Expenses as dual-series line chart. Intersection = break-even date. Uses FILTER on Account (not Summary Grouping) for Net Operating Income.

### 7. Spotlight Dashboard
Single-metric deep dive with dynamic dropdown switching between Summary Grouping and Account detail. Uses conditional Data Validation (IF formula switching named ranges). Modified SUMPRODUCT formula dynamically switches lookup columns.

### 8. Pivot Table Dashboard
Two-level summary grouping hierarchy for drill-down. Custom sort order (File > Options > Edit Custom Lists) for financial statement ordering. Timeline slicers for date filtering, category slicers for metric filtering. Pivot charts inherit all interactivity.

### 9. Cover Page
Professional cover using Excel shapes, brand colors, company logo, and royalty-free images. First tab in the workbook. Copy as picture (Alt+E+S+U) for PowerPoint.

> See `dashboard-types.md` for detailed construction steps for each dashboard type.

---

## Chart Types for Finance

| Chart | Best For | Setup Notes |
|-------|----------|-------------|
| Combo (bar + line) | Revenue bars + margin line on secondary axis | The CFO's go-to chart |
| Gauge/Donut | Variance visualization (BvA) | Dual series, thin ring, auto-switching |
| Sparklines | In-cell trend indicators | Win/Loss for BvA by month |
| Waterfall | MRR/ARR bridge, cash flow bridge | Built-in waterfall chart type |
| Line (dual series) | Break-even analysis | Intersection = break-even date |
| Bar (reverse order) | Revenue waterfall, KPI ranking | Format Axis > Reverse Order |

**Named range bridging for charts:** Charts cannot reference spill arrays directly. Create Named Ranges pointing to `=Sheet!$Cell#` (with hash suffix). Use named range names in chart series/category references.

> See `formulas-and-charts.md` for chart formulas, spill array patterns, and named range bridging details.

---

## Brand Guidelines for Dashboards

Every dashboard needs a formal brand guideline:
1. **Logo** -- two types: icon/circular + full company name/rectangular
2. **Primary + secondary fonts** (Poppins primary, Calibri secondary is a strong default)
3. **Color palette** derived from logo colors (use coolors.co to generate)
4. **Icon library** -- flaticon.com for professional icons
5. **Royalty-free images** -- unsplash.com for backgrounds

**Color picker tool:** Win+Shift+C (or third-party picker) to match exact colors from icons and logos.

---

## Contrarian Positions (Aharonoff)

These positions may contradict common practice but are backed by the instructor's experience:

- **SUMPRODUCT over SUMIFS for dashboards** -- more flexible for multi-criteria with date logic
- **Transform wide to narrow format first** -- most accountants keep data wide; narrow unlocks everything
- **Always ABS() in percentage-change denominators** -- prevents sign-flip when dividing negative by negative
- **Favorable variances always positive, unfavorable always negative** -- do NOT use consistent formula direction
- **Center Across Selection, never Merge & Center** -- merged cells break formulas and sorting
- **Excel dashboards should be visually stunning** -- invest in design like you invest in accuracy

---

## Progressive Complexity Path

Build dashboards in this order, each building on prior skills:

```
1. Summarized Financials (formula-driven foundation)
2. KPI Dashboards (formula + design)
3. Budget vs Actuals (dual data source)
4. Management Report (multi-comparison)
5. Cash-Out / Break-Even (spill arrays + named ranges + charts)
6. Spotlight (conditional formulas + icons)
7. Pivot Tables (alternative flexible approach)
```

> Cross-reference: For the three-statement model that feeds dashboard data, see `financial-modeling`. For financial ratio KPIs to track, see `financial-ratios`. For communicating dashboard insights, see `advisory-communication`.
