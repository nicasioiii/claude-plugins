---
name: "Drivers Tab Construction"
description: "Core concept of drivers tab as command center, structure (P&L + BS sections), SUMIFS for historicals, INDEX for BS, three time views, mapping column, driver description column, P&L vs BS formula difference."
when_to_read: "When the user is building or modifying a drivers tab, needs SUMIFS or INDEX pull formulas, wants to set up mapping columns, or needs to understand the drivers tab structure."
---

# Drivers Tab Construction

## Core Concept (Aharonoff)

The drivers tab is the single central place where you adjust assumptions and they flow through the entire model. Think of it as the control room.

### [CONTRARIAN] The Drivers Tab Is the ONLY Place Where Historical and Projection Formulas Differ
- **Historical data:** SUMIFS formulas pulling from source tabs
- **Projections:** Forward-looking assumption formulas (from forecasting-strategy's nine methods)
- **Every other tab** in the model uses the SAME formula structure for both historical and projected periods
- This means your income statement, balance sheet, and cash flow tabs maintain formula consistency throughout

---

## Structure

The drivers tab contains two major sections:

### 1. Income Statement Section
All P&L line items with data pulled from source.

**Build process:**
1. Copy line items from income statement source (account names only)
2. Remove all subtotal rows (rebuild with proper formulas later)
3. Create buffer spaces between sections for readability
4. Add SUMIFS formulas to pull historical data
5. Lock column references with $ for copying across periods
6. Build calculated rows: Gross Profit, Net Operating Income, Net Other Income, Net Income
7. Copy across all time periods

### 2. Balance Sheet Section
All BS line items with data pulled from source.

**Build process:**
- Same approach as P&L, but remember: BS shows point-in-time positions, not period flows
- For quarterly/annual views, use INDEX formula (not SUMIFS)
- Maintain Assets = Liabilities + Equity check at all times

---

## Pull Formulas

### SUMIFS -- For Income Statement (Flow Data)
Sums activity over a period:
```
=SUMIFS([source_data_range], [account_name_column], [target_account_name])
```

**With date filtering:**
```
=SUMIFS([amount_range], [account_column], [account_name], [date_column], ">=" & [period_start], [date_column], "<=" & [period_end])
```

**Critical:** Lock the source range column references with $ so formulas copy correctly across periods:
```
=SUMIFS($B:$B, $A:$A, $A5, C$1:C$1, ">=" & C$2)
```

### INDEX -- For Balance Sheet (Stock Data)
Grabs the exact balance at a point in time:
```
=INDEX([values_row], 0, MATCH([period_end_date], [date_range], 0))
```

### Why Two Different Formulas
- **Income Statement (SUMIFS):** Revenue and expenses accumulate over time. You need the SUM of all transactions within a period.
- **Balance Sheet (INDEX):** Asset and liability balances are snapshots. You need the EXACT balance at period end, not a sum.

**Common mistake:** Using SUMIFS for BS data -- this gives you the change during the period, not the ending balance.

---

## Three Time Views

Every drivers tab should display data in three views:

### 1. Annual View
- High-level year totals
- P&L: Sum of all monthly amounts
- BS: December (or fiscal year-end) ending balance

### 2. Quarterly View
- Q1, Q2, Q3, Q4 breakdowns
- P&L: Sum of 3 months
- BS: Quarter-end balance (use INDEX to grab March, June, September, December)

### 3. Monthly View
- Full monthly detail
- Primary working view for model building
- Most formulas built here first, then aggregated up

---

## Mapping Column

Add a "Mapping" column to the drivers tab. This bridges detailed accounts to summary categories.

### Purpose
Summary financials tab uses SUMIFS referencing the mapping column:
```
=SUMIFS([driver_values], [mapping_column], "Revenue")
```

### Two Approaches
1. **Section-level mapping:** All revenue accounts map to "Revenue" as one category
2. **Account-level mapping:** Individual revenue streams map to specific summary lines (e.g., "Product Revenue", "Service Revenue")

Choose based on how detailed the summary financials need to be for your audience.

---

## Driver Description Column

Document the assumption behind each projected line item directly in the drivers tab.

### Examples
| Account | Driver Description |
|---------|-------------------|
| Revenue - Product | "$100/unit x projected units" |
| Shipping Cost | "3.5% of product revenue" |
| Rent | "$8,500/month fixed through December" |
| Sales Salaries | "3 reps x $75K + 2 new hires starting June" |
| Software | "6-month average + 5% buffer" |
| Office Supplies | "Prior year same month" |

This documentation makes the model self-explaining and defensible during board review.

---

## Building Subtotals

After copying line items, rebuild subtotals with formulas:

```
Gross Profit = Revenue - COGS
Net Operating Income = Gross Profit - Operating Expenses
Net Other Income = Other Income - Other Expenses
Net Income = Net Operating Income + Net Other Income
```

**Margin calculations (with error handling):**
```
Gross Margin = IF(ISERROR(Gross_Profit / Revenue), 0, Gross_Profit / Revenue)
```

Always wrap division in IF(ISERROR()) to handle periods where revenue is zero.

---

## Cross-References

- **DADA framework and tab design** -> `dada-framework.md` (this skill)
- **Connecting drivers to financial statements** -> `three-statement-construction.md` (this skill)
- **Projection methods for the projection columns** -> `forecasting-strategy/projection-methods.md`
- **SUMIFS and INDEX formula details** -> `excel-for-finance`
- **Summary financials using mapping** -> `dashboards-and-reporting`
