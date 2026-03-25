---
name: Excel Help
description: "Get help with any Excel technique for finance work -- formulas, pivot tables, What-If analysis, data validation, charts, conditional formatting, named ranges, formula auditing, macros, and keyboard shortcuts."
---

# /excel-help

I can help with any Excel technique for finance work. Tell me what you're trying to do and I'll give you the exact formula, technique, or step-by-step walkthrough.

**What kind of help do you need?**

**Formulas & Lookups**
- Date functions (EOMONTH, SEQUENCE, EDATE, quarter labels)
- Lookup functions (INDEX MATCH, XLOOKUP with spill arrays)
- Aggregation (SUMIFS, COUNTIFS, SUBTOTAL, SUMPRODUCT)
- Safe division (IFERROR with ABS denominator)
- Custom number formatting (financial display, directional arrows)

**What-If Analysis & Scenarios**
- Scenario Manager (toggle between best/base/worst cases)
- Goal Seek (reverse-engineer a target -- "what COGS gives me 65% margin?")
- Data Tables (see output under many scenarios simultaneously)

**Data Management**
- Tables (Ctrl+T, structured references, auto-expand)
- Named ranges (creation, bulk, dynamic dropdowns, bridging for charts)
- Data validation (dropdowns, input restrictions, conditional lists)
- Power Query basics (unpivot, merge, append, refresh)

**Visualization**
- Charts (combo, waterfall, sparklines, gauge/donut)
- Conditional formatting (built-in rules, custom formula rules)
- Dashboard layout techniques (grid setup, KPI card borders)

**Productivity & Debugging**
- Formula auditing (trace precedents/dependents, Evaluate Formula, Watch Window)
- Circular reference handling (when intentional, iterative calculation setup)
- Protection (sheet, workbook, allow edit ranges)
- Paste special (values, formats, transpose, math operations)
- Macros basics (recording, relative references, form controls)
- Keyboard shortcuts for finance workflows

**Model Patterns**
- Reference locking (F4 cycle, grid formula patterns)
- Find & Replace for formula migration across data sources
- Named range bridging for charts and spill arrays
- Table-driven architecture for scalable models
- Calculation options (when to use manual vs automatic)

---

## Quick Examples

**"How do I calculate quarter from a date?"**
```
="Q" & ROUNDUP(MONTH(date)/3, 0) & " " & YEAR(date)
```

**"How do I look up a value in my P&L by account and date?"**
```
=INDEX(data_array, MATCH("Gross Profit", account_range, 0), MATCH(date, date_range, 0))
```

**"How do I make favorable variances positive and unfavorable negative?"**
- Revenue: `=Actual - Budget` (higher actual = good)
- Expenses: `=Budget - Actual` (lower actual = good)
- Always use `ABS()` in percentage denominator

**"How do I see the impact of different growth rates?"**
Use Data Tables: link output cell, list growth rates, Data > What-If > Data Table. Set Calculation Options to "Automatic Except Data Tables."

---

**Tell me your specific Excel question or task** and I'll walk you through it with the exact formulas and steps.

> Cross-reference: For dashboard-specific builds (Power Query + design), use `/build-dashboard`. For financial model architecture, use `/build-model`. For financial statement analysis, use `/analyze-financials`.
