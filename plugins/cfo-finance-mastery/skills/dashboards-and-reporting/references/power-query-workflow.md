---
name: Power Query Workflow for Financial Dashboards
description: Complete ETL process for transforming financial statements into dashboard-ready data using Power Query, including unpivoting, date parsing, aggregation mapping, and refresh workflow.
---

# Power Query Workflow for Financial Dashboards

## Why Power Query

Power Query is Excel's built-in Extract-Transform-Load (ETL) tool. It records every transformation step, so next month you click Refresh All and the entire pipeline re-runs. No manual data manipulation.

**The three phases:**
1. **Extract:** Pull from Excel tables, files, folders, databases, or web sources
2. **Transform:** Unpivot, merge, filter, add columns, parse dates in the Power Query Editor
3. **Load:** Send results to worksheet as table, pivot table, or connection-only

---

## The Six-Step Dashboard ETL Process

### Step 1: Add Summary Grouping Column

Add a "Summary Grouping" column to each financial statement that maps individual accounts to summary categories.

**Income Statement groupings:**
- Revenue, COGS, Advertising & Marketing, Other G&A, Software & Tech, Professional Fees, Headcount, Travel Meals & Entertainment, Other Income, Other Expense

**Balance Sheet groupings:**
- Cash, Accounts Receivable, Other Current Assets, Fixed Assets, Accounts Payable, Other Current Liabilities, Deferred Revenue, Debt, Contributed Capital, Retained Earnings

**Cash Flow groupings:**
- Cash from Operating Activities, Cash from Investing Activities, Cash from Financing Activities

**Critical rule:** Never include total rows in summary groupings. Totals get a blank grouping intentionally -- they are calculated in the dashboard layer. Including them causes double-counting.

### Step 2: Create Aggregation Mapping Table

Create a "Mappings" sheet with three columns: Account, Aggregation, Financial Statement.

**Two aggregation methods:**

| Method | Logic | Applies To |
|--------|-------|-----------|
| **Sum** | Add values between Start Date and End Date | Income Statement accounts, Cash Flow activities, Cash Burn |
| **Index** | Take value at End Date only | Balance Sheet accounts, Beginning Cash, Ending Cash |

**Special cases:**
- Cash Burn = Sum (operating + investing, excludes financing)
- Beginning Cash = Index (point-in-time value)
- Ending Cash = Index

The Financial Statement column prevents duplicate account names across statements from causing merge conflicts (e.g., "Other" might appear in both IS and BS).

### Step 3: Convert to Excel Tables

Select all data including headers for each statement, press Ctrl+T.

**Table naming convention:**
- `IncomeStatement`, `BalanceSheet`, `CashFlows`, `AggregationMapping`
- Names cannot start with numbers or contain spaces

Tables auto-expand when data is added. References never break. Table headers become named variables in formulas.

### Step 4: Load into Power Query

For each financial statement table:

1. Data tab > From Table/Range
2. In Power Query Editor, select non-date columns (Summary Grouping, Account) -- hold Ctrl to multi-select
3. Right-click > **Unpivot Other Columns** -- converts wide (dates as columns) to narrow (one row per account per date)
4. Add Column > Custom Column named "Financial Statement" with value `"Income Statement"` (in quotes for text literal)
5. File > Close & Load To > **Only Create Connection** (do NOT load to worksheet yet)

Repeat for Balance Sheet and Cash Flows tables. Load Mappings table as connection only too.

### Step 5: Append Queries

1. Open Power Query Editor
2. Append Queries > Append as New > Three or more tables
3. Stack: Income Statement + Balance Sheet + Cash Flows
4. Result: single unified data table with columns: Summary Grouping, Account, Attribute (date text), Value, Financial Statement

### Step 6: Parse Dates and Merge Mapping

**Date parsing (critical -- do not skip):**

Column headers like "Jan 21" need conversion to proper dates. Do NOT use Transform > Parse directly (misinterprets "Jan 21" as January 21st of current year).

**Correct approach:**
1. Add Custom Column with formula: `Text.Start([Attribute], 3) & "20" & Text.End([Attribute], 2)`
2. Transform > Date > Parse on the new column
3. Transform > Date > End of Month (standardize to month-end)
4. Delete original Attribute column, rename new column to "Date"

**Merge aggregation mapping:**
1. In the combined query: Merge Queries
2. Match on BOTH Account AND Financial Statement columns (Ctrl-click to multi-select)
3. Map to AggregationMapping table
4. Expand to pull in Aggregation column
5. Close & Load (this final query loads to worksheet as an actual table)

---

## Power Query Refresh Workflow

**Monthly update process:**
1. Update source data in the Excel tables (paste new month's trial balance)
2. Click Data > Refresh All
3. All queries cascade-refresh automatically
4. Dashboards update because they reference the output table

**Validation after refresh:**
- Filter the Aggregation column for blanks -- should only show total rows you intentionally excluded
- If new accounts appear with blank aggregation, add them to the Mappings table and refresh again

---

## Power Query for AP Consolidation

**Use case:** Multiple monthly AP aging files from different periods plus exchange rates for multi-currency.

**Workflow:**
1. Load each monthly AP file into Power Query
2. Apply consistent transformations (column rename, type conversion)
3. Merge with exchange rates table for currency conversion
4. Append all months into single consolidated AP aging report
5. Power Query records every step -- next month, add the new file and refresh

---

## The Data Model and DAX Introduction

**What it unlocks:** Relationships between multiple tables, pivot tables pulling from multiple sources simultaneously.

**How to access:** Right-click any table or Power Query connection > Load To > check "Add to Data Model."

**Key features:**
- Diagram view shows table relationships visually
- DAX measures auto-calculate based on active filters/slicers
- Format cells within the model for pre-formatted pivot output
- DAX is similar to Excel formulas but is also the language of Power BI

**Finance application:** Build a one-click dashboard where slicer buttons for Department, Date, and Account all filter a single pivot table pulling from actuals, budgets, and mapping tables simultaneously.

---

## Unpivoting Financial Data -- The Most Important Skill

### Why Unpivot

Financial statements are cross-tab format (accounts as rows, dates as columns). This is readable for humans but terrible for formulas, pivot tables, and analysis. You cannot use SUMIFS on cross-tab data. You cannot build dynamic date-filtered charts on cross-tab data.

**Before unpivot (wide):**
```
Account        | Jan 24 | Feb 24 | Mar 24
Revenue        | 50,000 | 55,000 | 60,000
COGS           | 20,000 | 22,000 | 24,000
```

**After unpivot (tall/narrow):**
```
Account  | Date   | Value
Revenue  | Jan 24 | 50,000
Revenue  | Feb 24 | 55,000
Revenue  | Mar 24 | 60,000
COGS     | Jan 24 | 20,000
COGS     | Feb 24 | 22,000
COGS     | Mar 24 | 24,000
```

### The Unpivot Process in Power Query

1. Select non-date columns (Account, Summary Grouping) -- hold Ctrl to multi-select
2. Right-click > **Unpivot Other Columns**
3. Result: two new columns ("Attribute" = date text, "Value" = the number)
4. Rename columns as needed

Every time source data changes (new month added as a column), Power Query automatically includes it in the unpivot. No formula updates needed.

---

## Summary Grouping Best Practices

### Income Statement Groupings

| Summary Grouping | Typical Accounts |
|-----------------|------------------|
| Revenue | Product Revenue, Service Revenue, Recurring Revenue |
| COGS | Materials, Direct Labor, Fulfillment, Shipping |
| Advertising & Marketing | Ad Spend, Marketing Tools, Events |
| Headcount | Salaries, Benefits, Payroll Taxes, Contractors |
| Software & Tech | SaaS Subscriptions, Hosting, Dev Tools |
| Professional Fees | Legal, Accounting, Consulting |
| Other G&A | Rent, Insurance, Office Supplies, Travel |
| Other Income | Interest Income, Gains |
| Other Expense | Interest Expense, Losses |

### Balance Sheet Groupings

| Summary Grouping | Typical Accounts |
|-----------------|------------------|
| Cash | Operating Account, Savings, Petty Cash |
| Accounts Receivable | Trade AR, Unbilled Revenue |
| Other Current Assets | Prepaid Expenses, Inventory, Deposits |
| Fixed Assets | Equipment, Furniture, Leasehold Improvements |
| Accounts Payable | Trade AP, Accrued Expenses |
| Other Current Liabilities | Payroll Liabilities, Sales Tax Payable |
| Deferred Revenue | Unearned Revenue, Customer Deposits |
| Debt | Lines of Credit, Term Loans, Notes Payable |
| Contributed Capital | Common Stock, Additional Paid-in Capital |
| Retained Earnings | Retained Earnings, Net Income |

**Rule:** Total rows (Gross Profit, Total Assets, etc.) get a BLANK summary grouping. They are calculated in the dashboard layer, not in source data. Including them causes double-counting.

---

## Common Power Query Issues

| Problem | Cause | Fix |
|---------|-------|-----|
| Blank aggregation on non-total rows | Account missing from Mappings table | Add to Mappings, Refresh All |
| Date parsed as wrong year | "Jan 21" interpreted as Jan 21st | Use custom Text.Start + Text.End formula |
| Merge returns nulls | Account name mismatch between statement and mapping | Check for trailing spaces, different capitalization |
| #SPILL error on dashboard | Cell blocking a spill range | Clear the blocking cell |
| Query won't refresh | Source table renamed or deleted | Open Power Query, update source reference |
| New accounts show blank aggregation | New COA entries not in Mappings | Add to Mappings table, Refresh All |
| Double-counting in totals | Total row included in summary grouping | Leave grouping blank for total rows |
| Slow refresh | Large dataset with many transformations | Reduce steps, filter early in query |

> Cross-reference: For the SUMPRODUCT formula that consumes this data, see the parent SKILL.md. For Excel table best practices, see `excel-for-finance > excel-productivity.md`. For financial statement structure and account classification, see `financial-diagnostics`.
