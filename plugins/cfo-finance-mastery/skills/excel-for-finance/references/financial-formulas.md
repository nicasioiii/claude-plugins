---
name: Financial Excel Formulas Reference
description: Complete reference for date functions (EOMONTH, SEQUENCE, EDATE), lookup functions (INDEX MATCH, XLOOKUP spill), aggregation (SUMIFS, COUNTIFS, SUBTOTAL, SUMPRODUCT), What-If analysis (Scenario Manager, Goal Seek, Data Tables), and custom number formatting.
---

# Financial Excel Formulas Reference

## Date Functions

### EOMONTH -- End of Month

**Syntax:** `=EOMONTH(start_date, months)`

| Application | Formula | Result |
|------------|---------|--------|
| End of current month | `=EOMONTH(A1, 0)` | Last day of month containing A1 |
| First of current month | `=EOMONTH(A1, -1) + 1` | Add 1 to prior month's end |
| End of next month | `=EOMONTH(A1, 1)` | Next month's last day |
| End of quarter | `=EOMONTH(A1, 2)` | Three months forward (from quarter start) |
| End of year | `=EOMONTH(A1, 11)` | Twelve months forward (from January) |

**Why this matters:** Every financial report needs date boundaries. EOMONTH eliminates hardcoded date errors in monthly close packages, rolling forecasts, and board decks.

### SEQUENCE -- Dynamic Date Generation

**Syntax:** `=SEQUENCE(rows, [columns], [start], [step])`

**Finance power patterns:**
- N monthly dates from one cell: `=EOMONTH(DATE(2024, SEQUENCE(N), 1), 0)`
- Horizontal P&L headers: `=TRANSPOSE(EOMONTH(DATE(2024, SEQUENCE(N), 1), 0))`
- Reference full spill output: `=C1#` (hash suffix)
- Dynamic calendar grid: `=SEQUENCE(rows, 7, start_date, 1)` (payroll date planning)

Change N and entire date axis updates -- column headers, formulas, chart labels, everything.

### EDATE -- Same Day, Different Month

**Syntax:** `=EDATE(start_date, months)`

| Application | Formula |
|------------|---------|
| 12 months prior | `=EDATE(Date, -12)` |
| Variable months back | `=EDATE(Date, -MonthsToPlot)` |
| 3 months forward | `=EDATE(Date, 3)` |

### Quarter Label Generation
```
="Q" & ROUNDUP(MONTH(date)/3, 0) & " " & YEAR(date)
```
ROUNDUP(month/3, 0) maps Jan=1, Apr=2, Jul=3, Oct=4.

---

## Lookup Functions

### INDEX MATCH -- Two-Dimensional Lookup
```
=INDEX(data_array,
  MATCH(row_lookup, row_range, 0),
  MATCH(col_lookup, col_range, 0))
```

**Applied to P&L:**
- Array = entire P&L data block (values only, no headers)
- Row match = find "Gross Profit" in account column
- Column match = find "Apr 2023" in date row
- 0 = exact match

### XLOOKUP with Spill Arrays
```
=XLOOKUP(date_range# & account_range#,
  source_dates & source_accounts,
  source_values)
```
One formula populates an entire table. The `#` operator on spill ranges creates every date + account combination. Change periods and table dynamically resizes.

### INDEX for Balance Sheet Lookups (in Driver Tabs)
```
=INDEX(source_range, MATCH(account, account_range, 0), MATCH(date, date_range, 0))
```
Balance sheet accounts need point-in-time values, not sums. INDEX retrieves the value at a specific intersection. Used in driver tabs for BS line items.

---

## Aggregation Functions

### SUMIFS -- Multi-Criteria Sum
```
=SUMIFS(sum_range, criteria_range1, criteria1, criteria_range2, criteria2, ...)
```

**Locking pattern for financial dashboards:**
- Sum range: `$C$2:$C$100` (fully locked)
- Criteria ranges: `$A$2:$A$100` (fully locked)
- Row lookup: `$A5` (column locked, row free -- changes as you drag down)
- Column lookup: `B$1` (row locked, column free -- changes as you drag right)

**Always SUMIFS, never SUMIF.** Even for single criteria. Consistent syntax, extensible.

### COUNTIFS -- Account Change Detection
```
=COUNTIFS(prior_period_accounts, current_account_cell) > 0
```
FALSE = new account added. Essential for month-end close to flag chart-of-account changes.

### SUBTOTAL -- No Double-Counting
```
=SUBTOTAL(9, range)
```
Function 9 = SUM. SUBTOTAL ignores other SUBTOTAL cells. Use for section subtotals (Gross Profit, Net Operating Income) so grand total only sums detail lines.

### SUMPRODUCT -- Conditional Aggregation Engine

**AND logic (multiply):**
```
=SUMPRODUCT((values) * (dates > start) * (dates <= end) * (dept = "Sales"))
```

**OR logic (add in parentheses):**
```
=SUMPRODUCT((values) * (dates > start) * (dates <= end) *
  ((acct = "Revenue") + (acct = "Other Income")))
```

**Debugging:** Formulas > Evaluate Formula steps through each array multiplication showing which rows resolve to TRUE at each step.

**SUMPRODUCT vs SUMIFS decision:**

| Scenario | Use |
|----------|-----|
| Vertical structured data | SUMIFS |
| Cross-tab data (accounts x dates) | SUMPRODUCT |
| OR conditions needed | SUMPRODUCT |
| Simple single-direction pull | SUMIFS |
| Dashboard with sum/index switching | SUMPRODUCT |
| Driver tab historical pulls | SUMIFS |

---

## What-If Analysis Tools

### Scenario Manager
1. Data > What-If Analysis > Scenario Manager > Add
2. Name scenario (e.g., "Ceiling")
3. Select changing cells (assumption inputs)
4. Enter values for that scenario
5. Repeat for "Base" and "Floor"
6. Click Show to toggle between scenarios

**Finance use:** Three-scenario revenue forecast. Ceiling = 10% above, Base = current trajectory, Floor = 50% of base.

### Goal Seek
1. Data > What-If Analysis > Goal Seek
2. Set cell = target output cell
3. To value = desired result
4. By changing cell = the input to solve for

**Example:** "What COGS achieves 65% gross margin?" Set margin cell to 0.65 by changing COGS cell. Excel calculates COGS = $17,500.

**Limitation:** 100 iterations by default. Reports failure if no solution exists.

### Data Tables
1. Link top-right cell to output you want to track (e.g., total annual revenue)
2. List scenario inputs in column below (e.g., -5%, 0%, 5%, 10%)
3. Select entire range including linked cell and inputs
4. Data > What-If Analysis > Data Table
5. Column input cell = the assumption cell driving your model

**Result:** See output under all scenarios simultaneously.

**Performance:** Always set Formulas > Calculation Options > **Automatic Except for Data Tables**. Data tables only recalculate on F9.

**Limitations:** Cannot edit individual cells (array formula). Must delete entire range to remove. Heavy processing.

---

## Custom Number Formatting

### Four-Section Format Code
`positive;negative;zero;text`

| Purpose | Format Code |
|---------|-------------|
| Standard financial | `#,##0;(#,##0);"-"` |
| Currency no decimals | `$#,##0;($#,##0);"-"` |
| Month labels | `"Month "#;# " months before";"Same Month"` |
| Variance direction | `Alt+30 0% "increase";Alt+31 0% "decrease";` |
| Savings/miss | `0% "savings";0% "miss";"-"` |
| Number abbreviation | Custom codes for K/M display |

The underlying value remains numeric. Formulas still work. Only the display changes.

### IFERROR for Safe Division
```
=IFERROR(Numerator / ABS(Denominator), 0)
```
Wrap every division in IFERROR. ABS() in denominator prevents sign-flip when dividing negative by negative.

---

## Conditional Data Validation for Dashboards
```
=IF(SourceType = "Accounts", AccountNames, SummaryGroupingAccounts)
```
First dropdown: manual list ("Accounts" or "Summary Groupings"). Second dropdown: conditional named range based on first selection. Press F3 to browse named ranges while building.

> Cross-reference: For the universal SUMPRODUCT formula used in dashboards, see `dashboards-and-reporting > formulas-and-charts.md`. For driver tab SUMIFS patterns, see `financial-modeling > drivers-tab.md`.
