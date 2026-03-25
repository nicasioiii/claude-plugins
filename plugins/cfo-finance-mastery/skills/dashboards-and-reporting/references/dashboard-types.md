---
name: Dashboard Types -- Construction Guide
description: Step-by-step construction for each financial dashboard type including KPI cards, budget vs actuals, cash-out, break-even, spotlight, pivot table dashboards, and management reports.
---

# Dashboard Types -- Construction Guide

## KPI Card Dashboard

### Grid Setup (Foundation for All Dashboards)
1. Set ALL row heights to 10.5 (Alt+H+O+H)
2. Set ALL column widths to 1.29 (Alt+H+O+W)
3. Ultra-narrow columns enable pixel-precise positioning via merge ranges
4. This grid is the foundation for professional dashboard layout

### Date Selectors
Create named ranges from table columns (required for Data Validation lists):
- `StartDates` = Dates[Start]
- `EndDates` = Dates[End]
- `AccountNames` = Accounts[Account]
- `SummaryGroupingAccounts` = SummaryGroupings[Summary Grouping]

Data Validation > List > reference named range. Create two date selector pairs: Period (Start/End) + Comparison (Start/End).

### KPI Card Design
- **KPI name:** size 16, bold, left-aligned, brand color
- **Value:** size 16, currency format, bold
- **Comparison value:** size 6.5, currency format
- **Date display:** `=TEXT(StartDate, "m/d/yy") & " - " & TEXT(EndDate, "m/d/yy")` size 7, gray
- **Percentage change custom format:** `Alt+30 0% "increase";Alt+31 0% "decrease";` (up/down triangles)

### KPI Card Visual Border
1. Insert Shape > Rectangle with Rounded Corners (outer border, no fill, brand color outline)
2. Insert Shape > Rectangle with Top Corners Rounded (header bar, brand color fill, no outline)
3. Group shapes together
4. Remove cell borders: Alt+H+B+N

---

## Budget vs Actuals Dashboard

### Data Setup
- Import budget as separate data table (same Power Query structure as actuals)
- Column structure: Line Item | Actual | Budget | Dollar Variance | Percentage Variance

### Variance Direction Rules (Contrarian)

**Do NOT use consistent formula direction.** Make favorable always positive, unfavorable always negative:

| Line Item | Favorable Formula | Logic |
|-----------|------------------|-------|
| Revenue | Actual - Budget | Higher actual = good |
| COGS / Expenses | Budget - Actual | Lower actual = good |
| Gross Margin % | Actual - Budget | Direct subtraction |
| Net Income | Actual - Budget | Higher actual = good |
| Cash Burn | Budget - Actual | Less burn = good |
| Ending Cash | Actual - Budget | More cash = good |

**Percentage variance:** `=IFERROR(DollarVariance / ABS(BudgetValue), 0)` -- always ABS() the denominator.

### Gauge/Donut Charts for Variance

**Data setup (four columns):**
- Negative Value: `=IF(variance < 0, ABS(variance%), 0)`
- Negative Remainder: `=IF(variance < 0, 1 - ABS(variance%), 0)`
- Positive Value: `=IF(variance >= 0, ABS(variance%), 0)`
- Positive Remainder: `=IF(variance >= 0, 1 - ABS(variance%), 0)`

**Chart construction:**
1. Select all four columns > Insert > Pie Charts > Donut
2. Remove title and legend, transparent background
3. Maximize donut hole size (thin ring)
4. Color: negative segment = warning color, positive = primary color, remainders = light gray
5. Position over variance text value
6. Chart auto-switches which series displays when value flips sign

### Variance Text Custom Formats
- Dollar: `#,##0;(#,##0);"-"`
- Percentage: `0% "savings";0% "miss";"-"`

---

## Management Report

### Structure
Actual | vs Budget ($ and %) | vs Prior Year ($ and %) | vs Prior Period ($ and %)

### Prior Year Comparison
Use EDATE to offset dates:
```
=EDATE(StartDate, -12)  -- prior year start
=EDATE(EndDate, -12)    -- prior year end
```
Copy the Actual SUMPRODUCT formula, replace date references with EDATE versions. Same formula structure works for any period offset.

### Scalable Column Copying
1. Lock the Actual column reference: change `D$2` to `$D$2`
2. Copy entire formula block to new comparison column
3. Find & Replace data source (e.g., "Data" to "Budget") via Ctrl+H > Replace All
4. Use Center Across Selection (Ctrl+1 > Alignment > Horizontal) for grouped headers like "vs Budget"

---

## Cash-Out Dashboard

### Finding the Cash-Out Date
```
=INDEX(
  FILTER(Data[Date],
    (Data[Value] < 0) *
    (Data[Summary Grouping] = "Ending Cash")
  ),
  1
)
```
FILTER returns all dates where ending cash is negative. INDEX with row 1 gets the first such date. Display in merged cell, bold, size 26.

### Dynamic Months-to-Plot

**Date array (leading up to cash-out):**
```
=SORT(UNIQUE(FILTER(Data[Date],
  (Data[Date] > EDATE(CashOutDate, -MonthsToPlot)) *
  (Data[Date] <= CashOutDate)
)))
```
MonthsToPlot is a user-editable cell (e.g., 12, 7, 6).

**Value array:**
```
=FILTER(Data[Value],
  (Data[Date] > EDATE(CashOutDate, -MonthsToPlot)) *
  (Data[Date] <= CashOutDate) *
  (Data[Summary Grouping] = "Ending Cash")
)
```

### Chart Setup
1. Define Named Ranges with hash suffix: `CashOutDates = =Sheet!$Cell#`, `CashOutValues = =Sheet!$Cell#`
2. Insert Bar Chart, set series to named ranges
3. Add data labels, vertical gridlines at 50% transparency
4. Format dates as mmm-yy

---

## Break-Even Dashboard

### Finding Break-Even Date
```
=INDEX(
  FILTER(Data[Date],
    (Data[Value] > 0) *
    (Data[Account] = "Net Operating Income")
  ),
  1
)
```
Uses Account (not Summary Grouping) for Net Operating Income. Refresh data after changing projections.

### Dual-Series Line Chart
1. Create three named spill ranges: BreakEvenDates, BreakEvenGrossProfit, BreakEvenExpenses
2. Insert Line Chart with two series
3. Smooth lines, brand colors, synced Y-axis maximum
4. Intersection of the two lines = break-even date

---

## Spotlight Dashboard

### Dynamic Conditional Data Validation
- First dropdown: "Accounts" or "Summary Groupings" (manual list)
- Second dropdown: `=IF(SourceCell = "Accounts", AccountNames, SummaryGroupingAccounts)`
- Press F3 to browse named ranges while building formulas

### Universal Formula (Account OR Summary Grouping)
```
=SUMPRODUCT(
  (Data[Value]) *
  (IF(SourceCell = "Accounts", Data[Account], Data[Summary Grouping]) = MetricName) *
  (Data[Date] >= IF(INDEX(Data[Aggregation],
    MATCH(MetricName, IF(SourceCell="Accounts", Data[Account], Data[Summary Grouping]), 0))
    = "Sum", StartDate, EndDate)) *
  (Data[Date] <= EndDate)
)
```
Replace BOTH the match criteria AND the aggregation lookup with the IF switch.

### Design Elements
- Metric name: size 20, bold, brand font
- Value: size 48, brand color
- Date: size 10, dark gray
- Import cloud/arrow icons from flaticon.com
- Rounded rectangle border shape
- Background fill matching icon colors

---

## Pivot Table Dashboard

### Data Preparation
Create two-level hierarchy: Summary Grouping 1 (high level) and Summary Grouping 2 (detail). Where no sub-grouping exists, fill SG2 = SG1. Load through Power Query with same unpivot workflow.

### Custom Sort Order
File > Options > Advanced > Edit Custom Lists. Enter financial statement order:
Income, Cost of Goods Sold, Gross Profit, Operating Expenses, Net Operating Income, Other Income, Other Expense, Net Other Income, Net Income

### Interactive Elements
- **Timeline Slicer:** PivotTable Analyze > Insert Timeline > Date field. Visual date range selection.
- **Category Slicer:** PivotTable Analyze > Insert Slicer > Summary Grouping 1. Ctrl-click to multi-select.
- **Pivot Charts:** Created from pivot table, inherit all slicer/timeline interactivity.

### Formatting
- Remove Grand Total for rows (nonsensical for P&L)
- Keep Grand Total for columns (period totals)
- Remove subtotals for cleaner appearance
- Custom date format: mmm-yy
- Replace "Row Labels"/"Column Labels" with spaces
- Filter out blank Summary Grouping 1 rows in Power Query (not in pivot)

---

## Period-over-Period Change Report

### Structure
Insert 3-4 columns after each date column: Delta ($), Delta (%), padding.

### Formulas
- Dollar change: `=CurrentPeriod - PriorPeriod`
- Percentage change: `=IFERROR(DollarChange / ABS(PriorPeriod), 0)`
- Delta symbol: Alt+30 (keypad) for up triangle, Alt+31 for down

### Efficiency
- Group delta columns: Alt+A+G (collapsible)
- Copy first comparison column, replicate for subsequent periods
- Use Find & Replace to fix column references when copying

> Cross-reference: For spill array mechanics and named range creation, see `excel-for-finance > financial-formulas.md`. For the universal SUMPRODUCT formula, see the parent SKILL.md.
