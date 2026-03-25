---
name: Model Building Patterns in Excel
description: Table-driven architecture, Find & Replace for formula migration, named range bridging, progressive complexity, reference locking patterns, circular reference handling, and calculation options management.
---

# Model Building Patterns in Excel

## Table-Driven Architecture

The foundation of scalable financial models in Excel.

### The Pattern
1. All raw data lives in Excel Tables (Ctrl+T)
2. All transformations happen in Power Query
3. All dashboards/outputs reference the Power Query output table
4. Named ranges bridge tables to Data Validation and Charts
5. Single refresh (Data > Refresh All) cascades through entire system

### Why Tables Over Ranges
- Ranges break when data grows (formula references don't expand)
- Tables auto-expand (add a row and everything updates)
- Table syntax is readable: `=tblProfitLoss[Revenue]` vs `$C$2:$C$100`
- Tables integrate natively with Power Query, pivot tables, charts, and slicers

### Naming Convention
Use descriptive, consistent names:
- Source data: `tblIncomeStatement`, `tblBalanceSheet`, `tblCashFlows`
- Mapping: `tblAggregationMapping`, `tblAccountMapping`
- Budget: `tblBudget`, `tblBudgetDrivers`
- Output: `tblConsolidatedData`

---

## Find & Replace for Formula Migration

### The Problem
You have a working formula block referencing one data source. You need the same formulas referencing a different source (e.g., Budget instead of Actual).

### The Solution
1. Copy the entire formula block to the new location
2. Ctrl+H (Find & Replace)
3. Find: `Data` (the original table name)
4. Replace: `Budget` (the new table name)
5. Replace All

### Before Copying: Lock References
If the formulas will be in a different column position, lock absolute references first:
- Find: `D$2` → Replace: `$D$2` (lock the Actual column before copying)
- Then copy to the new location
- Then Find & Replace the data source name

### Common Replacements

| Find | Replace | Purpose |
|------|---------|---------|
| `Data` | `Budget` | Switch from actuals to budget |
| `C$2` | `$C$2` | Lock column before copying |
| `E$2` | `$F$2` | Shift date reference to new column |
| `"Income Statement"` | `"Balance Sheet"` | Switch financial statement context |

This is faster than manually editing formulas. One Replace All can update hundreds of cells simultaneously.

---

## Named Range Bridging

### Problem
Several Excel features cannot directly reference dynamic content:
- Charts cannot use spill array `#` references
- Data Validation cannot reference table columns directly
- Some functions cannot accept structured references

### Solution: Named Range Bridge
1. Create a Named Range pointing to the dynamic content
2. Reference the Named Range where needed

**For spill arrays:**
- Name: `ChartDates`, Reference: `=Sheet1!$A$14#` (with hash)
- Chart series category: `=ChartDates`

**For table columns:**
- Name: `DateList`, Reference: `=DateTable[Date]`
- Data Validation source: `=DateList`

**For cross-tab references:**
- Name: `StartDate`, Reference: `=Assumptions!$B$2`
- Use `StartDate` in any formula on any sheet

---

## Progressive Complexity

Build models and dashboards in layers, each building on prior patterns.

### Dashboard Progression
```
Level 1: Summarized Financials
  Skills: SUMPRODUCT formula, date architecture, table references

Level 2: KPI Dashboards
  New skills: Data Validation dropdowns, named ranges, card design

Level 3: Budget vs Actuals
  New skills: Dual data sources, Find & Replace migration, gauge charts

Level 4: Management Report
  New skills: EDATE period offsets, Center Across Selection, multi-comparison

Level 5: Cash-Out / Break-Even
  New skills: FILTER + INDEX, spill arrays, named range bridging for charts

Level 6: Spotlight
  New skills: Conditional Data Validation, dynamic column switching in SUMPRODUCT

Level 7: Pivot Tables
  New skills: Custom sort order, Timeline slicer, pivot charts
```

### Model Progression
```
Level 1: P&L Only
  Skills: SUMIFS, basic structure, one tab

Level 2: P&L + Drivers
  New skills: Driver tab, SUMIFS for historicals, named ranges

Level 3: Three-Statement
  New skills: BS projection formulas, CF mathematics, linking

Level 4: Actualization
  New skills: Named range for latest actuals, IF switching, roll-forward

Level 5: Error Checks + Audit
  New skills: BS balance check, sign checks, model audit checklist
```

---

## Reference Locking Patterns

### The F4 Cycle
Press F4 while editing a cell reference:
1. `$A$1` -- fully locked (column AND row)
2. `A$1` -- row locked only (column free to change)
3. `$A1` -- column locked only (row free to change)
4. `A1` -- no locks (fully relative)

### Financial Model Locking Rules

| Reference Type | Lock Pattern | When to Use |
|---------------|-------------|-------------|
| Account name (row header) | `$C8` | Column locked, row changes as you drag down |
| Date (column header) | `E$2` | Row locked, column changes as you drag right |
| Assumption cell | `$B$5` | Fully locked (one value used everywhere) |
| Named range | `StartDate` | No locking needed (inherently absolute) |
| Table column | `Data[Value]` | No locking needed (structured reference) |

### Grid Formula Pattern
For a P&L grid where accounts go down and dates go across:
```
=SUMIFS($Values, $Accounts, $C8, $Dates, E$2)
```
- `$Values`, `$Accounts`, `$Dates` = fully locked ranges
- `$C8` = account changes per row
- `E$2` = date changes per column

Copy one formula across entire grid.

---

## Circular Reference Handling

### When Circular References Are Intentional

Common in three-statement models:
- Interest expense depends on average debt balance
- Debt balance depends on cash flow (debt draw/repayment)
- Cash flow depends on interest expense

### Setup
File > Options > Formulas:
- Check "Enable iterative calculation"
- Maximum iterations: 100 (default)
- Maximum change: 0.001 (default)

### Risks
- Values may not converge (especially with large circular dependencies)
- Model becomes order-dependent (which formula calculates first matters)
- Debugging is harder (Evaluate Formula may not show expected results)

### Best Practice
Minimize circular references. If possible, use prior period values instead:
```
=PriorPeriodDebtBalance * AnnualInterestRate / 12
```
This breaks the circularity by using last month's debt for this month's interest. Small approximation but eliminates convergence risk.

---

## Calculation Options Management

### Three Modes

| Mode | Behavior | When to Use |
|------|----------|-------------|
| Automatic | Every change recalculates everything | Small models |
| Automatic Except Data Tables | Normal formulas instant, data tables wait for F9 | Models with What-If data tables |
| Manual | Nothing updates until F9 | Very large models (risk: forgetting to calculate) |

### Performance Tips
- Data tables are the biggest performance drain -- always use "Automatic Except Data Tables"
- Large SUMPRODUCT formulas across thousands of rows slow calculation
- Volatile functions (NOW, TODAY, INDIRECT, OFFSET) recalculate on every change
- Consider converting INDIRECT to INDEX MATCH for performance
- Binary format (`.xlsb`) loads faster than `.xlsx` for large files

---

## Paste Special Patterns for Model Building

### Converting Formulas to Values
After building a model output for distribution:
1. Select all formula cells
2. Ctrl+C
3. Ctrl+Alt+V > Values
4. Protects model logic (recipient sees values, not formulas)

### Currency Conversion via Paste Special
1. Enter exchange rate in an empty cell (e.g., 1.35 for USD to CAD)
2. Ctrl+C that cell
3. Select all USD values
4. Ctrl+Alt+V > Multiply
5. All values converted in place

### Transposing Financial Data
Copy horizontal date headers > Ctrl+Alt+V > Transpose. Converts row to column (or vice versa). Useful for reformatting data exports from accounting systems.

> Cross-reference: For the DADA framework and model tab architecture, see `financial-modeling > dada-framework.md`. For Power Query transformation pipeline, see `dashboards-and-reporting > power-query-workflow.md`. For the universal SUMPRODUCT formula, see `dashboards-and-reporting > formulas-and-charts.md`.
