---
name: Excel for Finance
description: "Financial Excel formulas, pivot tables, What-If analysis, data validation, charts, conditional formatting, macros, named ranges, and formula auditing for CFO-level work. MANDATORY TRIGGERS: 'How do I do this in Excel', 'Excel formula help', 'What-If analysis', 'Goal Seek', 'Scenario Manager', 'Data tables', 'Named ranges', 'Formula auditing', 'Conditional formatting for finance', 'Excel shortcuts', 'Macros for finance'. FOR: Excel formula syntax, pivot table construction, What-If scenario tools, data validation setup, chart creation, conditional formatting rules, named range management, formula auditing/debugging, protection settings, paste special operations, keyboard shortcuts. Do NOT use for dashboard design or Power Query ETL (use dashboards-and-reporting), financial model architecture or DADA framework (use financial-modeling), or financial statement interpretation (use financial-diagnostics)."
---

# Excel for Finance

## Overview

This is the cross-cutting enablement skill for all CFO-level Excel work. Every other skill in this plugin eventually touches Excel -- this skill provides the formula mechanics, productivity techniques, and debugging tools that make everything else work.

**Core philosophy (Aharonoff):** Design for auditability. Every Excel file should be easy to follow for anyone who inherits it. Use named ranges, table references, and clear labeling. You are not the only person who will use this file.

**Three principles:**
1. **Tables over ranges, always** -- Ctrl+T auto-expands, uses readable syntax, integrates with Power Query and pivots
2. **Unpivot before analyze** -- convert cross-tab financial data to flat format before building anything analytical
3. **Protect your work** -- lock formula cells, protect sheets, validate inputs. Prevent accidental destruction of complex models.

> Cross-reference: This skill supports ALL other skills as a technical enablement layer. For dashboard-specific formulas (SUMPRODUCT universal formula, spill arrays for charts), see `dashboards-and-reporting`. For model-specific patterns (DADA framework, three-statement linking), see `financial-modeling`.

---

## Date Functions for Financial Reporting

### EOMONTH -- The Foundation of Financial Date Logic

`=EOMONTH(date, months)` returns the last day of a month offset by N months.

| Need | Formula |
|------|---------|
| End of current month | `=EOMONTH(A1, 0)` |
| First of current month | `=EOMONTH(A1, -1) + 1` |
| Next month end | `=EOMONTH(A1, 1)` |
| Prior month end | `=EOMONTH(A1, -1)` |
| Quarter end | `=EOMONTH(A1, 2)` (if A1 is quarter start) |
| Year end | `=EOMONTH(A1, 11)` (if A1 is January) |

### SEQUENCE -- Dynamic Date Generation

`=SEQUENCE(rows, [columns], [start], [step])`

**Finance power moves:**
- Generate N monthly dates: `=EOMONTH(DATE(2024, SEQUENCE(N), 1), 0)`
- Horizontal headers: `=TRANSPOSE(EOMONTH(DATE(2024, SEQUENCE(N), 1), 0))`
- Reference spill range: `=C1#` (hash suffix captures full output)

Build date axes with SEQUENCE, not by typing dates or dragging fill handles. Change one input and the entire model's date range updates.

### EDATE -- Period Offsets

`=EDATE(date, months)` returns the same day N months forward or back.
- Prior year: `=EDATE(Date, -12)`
- Variable offset: `=EDATE(Date, -MonthsToPlot)`

### Quarter Labels

`="Q" & ROUNDUP(MONTH(date)/3, 0) & " " & YEAR(date)` produces "Q1 2024"

> See `financial-formulas.md` for complete formula reference with syntax and finance examples.

---

## Lookup Functions

### INDEX MATCH -- Two-Dimensional Lookup

```
=INDEX(data_array, MATCH(row_lookup, row_range, 0), MATCH(col_lookup, col_range, 0))
```

Financial statements are inherently two-dimensional (accounts x periods). INDEX MATCH works in both directions simultaneously. VLOOKUP only looks vertically.

### XLOOKUP with Spill Arrays

One XLOOKUP formula can populate an entire P&L table:
```
=XLOOKUP(date_range# & account_range#, source_dates & source_accounts, source_values)
```
The `#` operator creates every combination of date + account, looks up each, returns all values. One formula replaces an entire grid of individual lookups.

---

## Aggregation Functions

### SUMIFS -- The Workhorse

Always use SUMIFS, never SUMIF (consistent syntax, extensible).

**Key locking pattern:**
- Sum range: fully locked (`$C$2:$C$100`)
- Criteria ranges: fully locked (`$A$2:$A$100`)
- Lookup values: lock column not row (`$A5`) -- dragging down changes account, dragging right stays on lookup column

### COUNTIFS -- Detecting New Accounts

Compare two P&L periods: `=COUNTIFS(jan_accounts, feb_account_cell) > 0`. FALSE rows = new accounts added. Essential for month-end close to flag new chart-of-account additions.

### SUBTOTAL -- Ignoring Subtotals in Grand Totals

`=SUBTOTAL(9, range)` where 9 = SUM. SUBTOTAL ignores other SUBTOTAL cells, preventing double-counting when your P&L has section subtotals (Gross Profit, Net Operating Income) plus detail lines.

### SUMPRODUCT -- Multi-Criteria Aggregation

Multiplying (*) = AND logic. Adding (+) = OR logic (in extra parentheses).

```
=SUMPRODUCT(
  (values) *
  (dates > start_date) * (dates <= end_date) *
  ((accounts = "Account1") + (accounts = "Account2"))
)
```

**When SUMPRODUCT beats SUMIFS:** Cross-tab data, OR conditions, multi-directional lookups. **When SUMIFS is better:** Structured vertical data, simple conditional sums, driver tab pulls.

---

## What-If Analysis Tools

### Scenario Manager
Data > What-If Analysis > Scenario Manager. Create named scenarios (Ceiling, Base, Floor) with different assumption values. Click Show to toggle between scenarios instantly. Board presentation ready.

### Goal Seek -- Reverse-Engineering Targets
Data > What-If Analysis > Goal Seek. "Set this cell to this value by changing that cell." Excel solves backward.

**Examples:**
- "What COGS achieves 65% gross margin?" Set margin cell to 0.65 by changing COGS.
- "What conversion rate brings 20 customers with $4K budget?" Set customer cell to 20 by changing conversion rate.

### Data Tables -- Multiple Scenarios Simultaneously

Data > What-If Analysis > Data Table. See output under many scenarios at once (not just toggle between them).

**Setup:** Link top-right cell to output, list scenario inputs below, select range, set column input cell.

**Critical performance note:** Data tables cause significant slowdown. Always set Formulas > Calculation Options > **Automatic Except for Data Tables**. Normal formulas instant; data tables recalculate only on F9.

> See `financial-formulas.md` for detailed What-If setup steps.

---

## Tables -- The Backbone of Structured Data

### Why Tables Beat Ranges
Convert with Ctrl+T. Tables provide:
- Auto-expanding references (add row, formulas include it)
- Structured reference syntax: `=TableName[ColumnName]`
- Built-in filter dropdowns and total row
- Direct integration with Power Query, pivot tables, charts

**Naming:** Cannot start with number or contain spaces. Use descriptive: `tblProfitLoss`, `tblBudget`.

### Slicers on Tables
Table Design > Insert Slicer. Button-style filters for any column. Remove header and borders for dashboard-clean look.

---

## Conditional Formatting for Finance

### Built-in Rules Quick Reference

| Rule | Finance Use |
|------|------------|
| Highlight above/below value | Flag contracts above threshold |
| Highlight duplicates | Detect duplicate accounts in trial balance |
| Positive vs negative | Color-code budget variances |
| Top/Bottom N% | Highlight top 20% sales months |
| Color scales | Heat map of monthly performance |
| Data bars | In-cell magnitude comparison |
| Icon sets | Directional arrows on variance reports |

### Custom Formula Rules

```
=AND(date_cell > start_date, date_cell <= end_date,
  OR(account_cell = account1, account_cell = account2))
```

Think about what the TOP-LEFT cell of your range evaluates to. Use mixed references (lock rows for dates, lock columns for accounts).

---

## Named Ranges

### Creation Methods
- Formulas > Define Name (or type in Name Box)
- Bulk: Select labels + values range > Formulas > Create from Selection > Left Column

**Finance use case:** Select assumptions block (Start Date, End Date, Growth Rate, Discount Rate) and create all named ranges in one click.

### Scoping
Workbook-wide or sheet-specific. Use sheet-specific when the same name (e.g., "StartDate") exists on multiple dashboard tabs.

### Dynamic Dropdowns
Tables cannot be referenced directly in Data Validation. Create a named range pointing to the table column: `=DateTable[Date]`. Use the named range in Data Validation > List.

For spill range dropdowns: point data validation to `=C1#`. Dropdown auto-updates when the spill output changes.

---

## Formula Auditing

### Trace Precedents / Dependents
- **Trace Precedents:** arrows pointing TO selected cell from its inputs
- **Trace Dependents:** arrows FROM selected cell to cells that reference it

**Before deleting any cell:** Trace Dependents first. If arrows appear, those formulas will break with #REF! errors.

### Evaluate Formula
Formulas > Evaluate Formula. Steps through each sub-expression showing intermediate results. Essential for debugging SUMPRODUCT and nested IFs.

### Show Formulas Mode
Ctrl+` (backtick). Shows formulas instead of values. Instantly audit which cells are hardcoded vs formula-driven.

### Circular Reference Detection
Formulas > Error Checking > Circular References. Lists all circular refs.

**When acceptable:** Interest expense depends on debt balance depends on cash flow depends on interest expense. Enable iterative calculation: File > Options > Formulas > Enable Iterative Calculation. Warning: values may not converge correctly.

### Watch Window
Formulas > Watch Window > Add Watch. Pin any cell to a floating window. Monitor while editing other sheets. Essential for watching KPI impact when changing assumptions on a different tab.

> See `excel-productivity.md` for auditing workflows and protection setup.

---

## Protection for Shared Models

### Sheet Protection
Review > Protect Sheet. Lock all formula cells, leave assumption inputs unlocked. Users change assumptions but cannot break formulas.

### Allow Edit Ranges
Define specific ranges that remain editable even when protected. Different ranges can have different passwords for different user groups.

### Workbook Protection
Prevents adding, deleting, or renaming sheets. Protects structural layout of multi-tab models.

---

## Charts for Financial Reporting

| Chart | Finance Use |
|-------|------------|
| Combo (bar + line) | Revenue bars + margin line on secondary axis |
| Waterfall | MRR/ARR bridge, cash flow bridge |
| Sparklines (Win/Loss) | BvA by month next to account names |
| Bar/Column (stacked) | Revenue by department composition |
| Line (dual series) | Break-even analysis (intersection) |
| Treemap | Expense breakdown hierarchy |

Hold Alt while dragging charts to snap to cell grid.

---

## Macros and VBA Basics

### Recording Macros
Developer > Record Macro. "Use Relative References" toggle: ON = works from any position, OFF = absolute positions.

**Finance use case:** Record month-end formatting steps (remove columns, apply formats, add headers, set print area). Run with one click each month.

### Form Controls
Developer > Insert > Form Controls. Add buttons, checkboxes, dropdowns. Assign macros to buttons. Use for month-end close checklists.

### File Extensions
- `.xlsx` -- standard (no macros)
- `.xlsm` -- macro-enabled (required for VBA)
- `.xlsb` -- binary (smaller for large models)

---

## Keyboard Shortcuts Reference

### Essential Finance Shortcuts (Windows)

| Action | Shortcut |
|--------|----------|
| Convert to table | Ctrl+T |
| Format cells dialog | Ctrl+1 |
| Bold | Ctrl+B |
| Show formulas | Ctrl+` |
| Paste special | Ctrl+Alt+V |
| Cycle reference locking | F4 |
| Insert column | Alt+H+I+C |
| Insert row | Alt+H+I+R |
| Set row height | Alt+H+O+H |
| Set column width | Alt+H+O+W |
| Auto-fit column | Alt+H+O+I |
| Group rows/columns | Alt+A+G |
| Data validation | Alt+A+V |
| Currency format | Alt+H+K |
| Percentage format | Alt+H+P |
| Decrease decimals | Alt+H+9 |
| All borders | Alt+H+B+S |
| No borders | Alt+H+B+N |
| Paste as picture | Alt+E+S+U |
| Merge & center | Alt+H+M+C |
| Paste formatting | Alt+H+V+R |
| Paste values | Alt+H+V+V |
| Delta symbol (up) | Alt+30 (keypad) |
| Delta symbol (down) | Alt+31 (keypad) |

> Cross-reference: For model-specific patterns (color coding, tab architecture), see `financial-modeling > dada-framework.md`. For dashboard-specific formulas (universal SUMPRODUCT, spill arrays), see `dashboards-and-reporting`. For model building Excel patterns, see `model-building-patterns.md`.
