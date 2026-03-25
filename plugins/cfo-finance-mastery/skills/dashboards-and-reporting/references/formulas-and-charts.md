---
name: Dashboard Formulas & Chart Techniques
description: Universal SUMPRODUCT formula variants, date architecture formulas, spill arrays for dashboards, named range bridging for charts, combo charts, sparklines, and pivot table chart techniques.
---

# Dashboard Formulas & Chart Techniques

## The Universal SUMPRODUCT Formula Family

### Base Formula (Income Statement Only)
```
=SUMPRODUCT(
  (Data[Value]) *
  (Data[Summary Grouping] = $C8) *
  (Data[Date] >= E$2) *
  (Data[Date] <= E$3)
)
```
- `Data[Value]` = value column in combined data table
- `$C8` = summary grouping name (row-locked, column-locked)
- `E$2` = Start Date (row-locked), `E$3` = End Date (row-locked)

### Dynamic Sum/Index Formula (All Statements)
```
=SUMPRODUCT(
  (Data[Value]) *
  (Data[Summary Grouping] = $C8) *
  (Data[Date] >= IF(INDEX(Data[Aggregation],
    MATCH($C8, Data[Summary Grouping], 0)) = "Sum",
    E$2, E$3)) *
  (Data[Date] <= E$3)
)
```
The IF/INDEX/MATCH: looks up aggregation method. If "Sum", lower bound = Start Date (full range). If "Index", lower bound = End Date (single point). One formula for revenue (sum), COGS (sum), cash (index), debt (index).

### KPI Card Formula (With Named Ranges)
```
=SUMPRODUCT(
  (Data[Value]) *
  (Data[Date] >= IF(INDEX(Data[Aggregation],
    MATCH(KPIName, Data[Summary Grouping], 0)) = "Sum",
    StartDate, EndDate)) *
  (Data[Date] <= EndDate) *
  (Data[Summary Grouping] = KPIName)
)
```
KPIName cell has Data Validation dropdown. Comparison value uses same formula with Comparison Start/End dates.

### Spotlight Formula (Dynamic Column Switching)
```
=SUMPRODUCT(
  (Data[Value]) *
  (IF(SourceCell = "Accounts", Data[Account],
    Data[Summary Grouping]) = MetricName) *
  (Data[Date] >= IF(INDEX(Data[Aggregation],
    MATCH(MetricName,
      IF(SourceCell="Accounts", Data[Account],
        Data[Summary Grouping]), 0))
    = "Sum", StartDate, EndDate)) *
  (Data[Date] <= EndDate)
)
```
Dynamically switches between Account and Summary Grouping lookup based on dropdown selection.

---

## Date Architecture Formulas

### Date Header Generation
| Need | Formula |
|------|---------|
| Quarter label | `="Q" & ROUNDUP(MONTH(StartDate)/3, 0)` |
| Year | `=YEAR(StartDate)` |
| Next start date | `=PreviousEndDate + 1` |
| Monthly end date | `=EOMONTH(StartDate, 0)` |
| Quarterly end date | `=EOMONTH(StartDate, 2)` |
| Annual end date | `=EOMONTH(StartDate, 11)` |
| Prior year start | `=EDATE(StartDate, -12)` |
| Prior year end | `=EDATE(EndDate, -12)` |

### Actuals vs Projections
```
=IF(EndDate > LatestMonthOfActuals, "Projected", "Actual")
```
LatestMonthOfActuals is a named range (e.g., 12/31/2022). Apply across all date columns.

---

## Calculated Line Items

Standard financial calculations in the dashboard layer (not in source data):

```
Gross Profit        = Revenue - COGS
Gross Margin        = IFERROR(GrossProfit / Revenue, 0)
Total OpEx          = SUM(all expense lines)
Net Operating Income = Gross Profit - Total OpEx
Net Other Income    = Other Income - Other Expense
Net Income          = Net Operating Income + Net Other Income
```

**Balance Sheet check:** `=TotalAssets - (TotalLiabilities + TotalOwnersEquity)` -- should equal zero across all columns.

**Cash Flows:**
- Beginning Cash references prior period end date
- Cash Burn = Cash from Operating + Cash from Investing (excludes Financing)
- Ending Cash = Beginning Cash + Total Cash Flows

---

## Period-over-Period Change Formulas

### Dollar Change
```
=CurrentPeriod - PriorPeriod
```

### Percentage Change (with ABS Protection)
```
=IFERROR(DollarChange / ABS(PriorPeriod), 0)
```
Always ABS() the denominator. Without it, dividing negative by negative produces a positive result -- an operating loss getting worse would incorrectly show as positive improvement.

### Percentage Change with Directional Formatting
Custom number format: `Alt+30 0% "increase";Alt+31 0% "decrease";`
- Positive: up triangle + percentage + "increase"
- Negative: down triangle + percentage + "decrease"
- Zero: blank

---

## Spill Array Patterns for Dashboards

### Filtered Date Range
```
=SORT(UNIQUE(FILTER(Data[Date],
  (Data[Date] >= StartDate) *
  (Data[Date] <= EndDate)
)))
```

### Filtered Value Array
```
=FILTER(Data[Value],
  (Data[Date] >= StartDate) *
  (Data[Date] <= EndDate) *
  (Data[Summary Grouping] = "Revenue")
)
```
For Account-level items (e.g., Gross Profit), use `Data[Account]` instead.

### Cash-Out Date Array
```
=SORT(UNIQUE(FILTER(Data[Date],
  (Data[Date] > EDATE(CashOutDate, -MonthsToPlot)) *
  (Data[Date] <= CashOutDate)
)))
```

### Referencing Spill Ranges
Use `=CellReference#` (hash suffix) to capture full spill output. If a cell blocks the spill range, Excel shows #SPILL! error -- clear the blocking cell.

---

## Named Range Bridging for Charts

**Problem:** Charts cannot directly reference spill ranges with `#` syntax.

**Solution:**
1. Select first cell of spill array
2. Formulas > Define Name
3. Name: `SelectionDates`, Reference: `=Sheet!$AY$14#` (with hash)
4. Repeat for each data series: `SelectionRevenue`, `SelectionExpenses`
5. In chart Select Data, replace cell references with named range names

Create separate named ranges for Comparison period charts. This pattern is required for any chart connected to dynamic spill arrays.

---

## Chart Types and Construction

### Combo Chart (CFO's Go-To)
1. Select data with dollar and percentage series
2. Insert > Recommended Charts > All Charts > Combo
3. Set percentage series to Secondary Axis
4. Dollar series = Clustered Column, percentage = Line
5. Remove gridlines, smooth line, apply brand colors
6. Hold Alt while dragging to snap to cell grid

### Gauge/Donut Chart (Variance)
See `dashboard-types.md > Budget vs Actuals` for full data setup. Four-column data structure with auto-switching between positive and negative display.

### Sparklines (In-Cell Mini Charts)
Three types: Line, Column, Win/Loss.

**Finance application:** Win/Loss sparkline for budget vs actual by month. Each month that hits target shows positive bar, each miss shows negative. Place next to account name in P&L for instant visual performance indicator.

### Bar Chart with Reverse Order
For waterfall-style KPI ranking: Format Axis > Reverse Order. Revenue appears on top. Labels set to "High" position (appears at bottom due to reverse).

---

## Pivot Table Chart Techniques

### Setup
Created directly from pivot tables. Inherit all slicer and timeline interactivity. Filter changes on pivot table automatically reflect in chart.

### Custom Sort for Financial Order
Pivot tables sort alphabetically by default. Fix: File > Options > Advanced > Edit Custom Lists. Create list in financial statement order. Right-click pivot field > Sort > uses custom list.

### Timeline and Category Slicers
- Timeline: visual date slider (months, quarters, years)
- Category Slicer: multi-select with Ctrl-click for instant filtering
- Both connected to pivot chart for interactive dashboard experience

---

## Custom Number Formatting for Dashboards

| Purpose | Format Code |
|---------|-------------|
| Standard financial | `#,##0;(#,##0);"-"` |
| Currency no decimals | `$#,##0;($#,##0);"-"` |
| Percentage with direction | `Alt+30 0% "increase";Alt+31 0% "decrease";` |
| Variance savings/miss | `0% "savings";0% "miss";"-"` |
| Dollar variance | `#,##0;(#,##0);"-"` |

**Four-section format:** `positive;negative;zero;text` -- underlying value stays numeric for formulas while display is customized.

> Cross-reference: For SUMIFS vs SUMPRODUCT decision guide, see parent SKILL.md. For formula auditing techniques, see `excel-for-finance > excel-productivity.md`. For the financial model that produces dashboard data, see `financial-modeling`.
