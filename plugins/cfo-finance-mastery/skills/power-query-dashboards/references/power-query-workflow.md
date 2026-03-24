---
name: Power Query Workflow & Unpivoting Guide
description: Step-by-step instructions for converting wide-format financial data into tall tables using Power Query Editor.
---

# Power Query Workflow & Unpivoting

## When to Use Power Query

**Use Power Query when:**
- You have wide-format data (dates as columns)
- Data updates monthly and needs automatic transformation
- You're building a dashboard that requires tall-format tables
- You want to avoid manual column insertions

**Don't use Power Query when:**
- Data is already tall format
- You're doing one-time analysis (just transpose manually)
- Your source system already exports tall format

## The Complete 5-Step Workflow

### Step 1: Prepare Source Data (Wide Format)

Your financial model or GL export arrives in wide format:

```
Account          Jan 2024    Feb 2024    Mar 2024    Apr 2024
Revenue          100,000     105,000     110,000     115,000
COGS              40,000      42,000      44,000      46,000
Payroll           30,000      30,000      30,000      30,000
Marketing          5,000       5,500       6,000       6,500
```

**Step 1 checks:**
- Is there a header row? (Account names in column A)
- Are date columns labeled clearly? (Jan 2024, Feb 2024, etc.)
- Are all numeric values, no text embedded?
- No blank rows or extra spacing?

If passes all checks, proceed to Step 2.

### Step 2: Convert to Excel Table

**Why?** Power Query works best with structured tables, not ranges.

**How:**
1. Select all source data (A1:E4 in example above)
2. Press Ctrl+T (or Data → From Table/Range)
3. Dialog appears: "Format as Table"
4. Confirm: Headers checkbox = ON
5. Click OK
6. Table is created with default name "Table1"

**Rename for clarity:**
1. Right-click table name in ribbon
2. Select "Rename"
3. Name it: "IncomeStatementTable" (or "ExpenseTable", etc.)
4. Press Enter

**Result:** Your data is now a structured table that auto-expands. When you add a row or column, table grows automatically.

### Step 3: Open Power Query Editor

**How:**
1. Select any cell in your table
2. Data menu → Get Data → From Table or Range
3. Power Query Editor opens (new window showing your table)

**Power Query window has two sections:**
- **Left:** Queries (list of transformations)
- **Middle:** Data preview (shows current shape of data)
- **Right:** Query Settings (shows steps applied so far)

### Step 4: Transform (Unpivot)

**Unpivoting:** Converting dates from columns into rows.

**Before unpivoting:**
```
Account    Jan 2024    Feb 2024    Mar 2024
Revenue    100,000     105,000     110,000
COGS        40,000      42,000      44,000
```

**After unpivoting:**
```
Account    Date        Value
Revenue    Jan 2024    100,000
Revenue    Feb 2024    105,000
Revenue    Mar 2024    110,000
COGS       Jan 2024     40,000
COGS       Feb 2024     42,000
COGS       Mar 2024     44,000
```

**Step-by-step unpivot:**

1. **Select the Account column** (first column with account names)
   - Click column header "Account"
   - It highlights blue

2. **Right-click → Unpivot Other Columns**
   - This keeps Account fixed and unpivots all date columns

3. **Result in Power Query preview:**
   ```
   Account    Attribute       Value
   Revenue    Jan 2024        100,000
   Revenue    Feb 2024        105,000
   COGS       Jan 2024         40,000
   ```
   Note: "Attribute" is the new column name (dates)

4. **Rename "Attribute" to "Date"**
   - Right-click "Attribute" column header
   - Select "Rename"
   - Type "Date"
   - Press Enter

5. **Verify Value column is numeric**
   - Click "Value" column header
   - Check "Data Type" shows "Whole Number" or "Decimal"
   - If shows "Text", right-click → Change Type → Whole Number

### Step 5: Add Custom Columns (Optional but Recommended)

**Custom columns add metadata** to make dashboard filtering easier.

**Example: Add financial statement category**

1. In Power Query, go to Add Column tab
2. Click "Custom Column"
3. Dialog appears: "Custom Column"
4. **Name:** FinancialStatement
5. **Formula:** ="IncomeStatement"
6. Click OK

**Result:** New column added with "IncomeStatement" for every row.

**Another example: Add line item category**

```
Custom Column Name: SummaryGroup
Formula:
= if [Account] = "Revenue" then "Revenue"
  else if [Account] = "COGS" then "COGS"
  else "OpEx"
```

**Result:**
```
Account    Date        Value       FinancialStatement   SummaryGroup
Revenue    Jan 2024    100,000     IncomeStatement      Revenue
COGS       Jan 2024     40,000     IncomeStatement      COGS
Payroll    Jan 2024     30,000     IncomeStatement      OpEx
```

### Step 6: Load to Excel

**How:**
1. In Power Query Editor, click "Close & Load"
2. Dialog: "Load To"
3. Select "Table" radio button (loads as structured table)
4. Choose sheet name (e.g., "DataTable")
5. Click OK

**Result:** Power Query closes, Excel shows new sheet "DataTable" with tall-format table.

**Important:** The table is now LINKED to Power Query. When source data updates:
1. Update IncomeStatementTable in original sheet
2. Right-click DataTable → Refresh
3. Dashboard data updates automatically

## Handling Common Data Issues

### Issue 1: Dates Are Text ("Jan 2024") Not Actual Dates

**Problem:** Formulas can't do date comparisons.

**Solution in Power Query:**
1. Right-click "Date" column
2. Select "Change Type" → Date
3. If Excel can't parse, use custom column: `=Date.FromText([Date])`
4. Specify format if needed: `=Date.FromText([Date], "MMM YYYY")`

**Result:** Dates become actual date values, not text.

### Issue 2: Numeric Values Are Text ("100,000" with comma)

**Problem:** SUM formulas treat as text.

**Solution in Power Query:**
1. Right-click "Value" column
2. Select "Change Type" → Whole Number or Decimal

### Issue 3: Extra Blank Rows in Source

**Problem:** Unpivoting includes blanks as rows.

**Solution in Power Query:**
1. Right-click "Value" column
2. Select "Remove Errors" or "Remove Blanks"
3. Filter to keep only non-null values

## Real Example: Multi-Statement Unpivot

**Source data (three statements pasted together):**

```
Account           Jan 2024    Feb 2024
INCOME STATEMENT
Revenue            100,000     105,000
COGS                40,000      42,000
───────────────────────────────────────
BALANCE SHEET
Cash                50,000      75,000
AR                  30,000      35,000
AP                  20,000      22,000
```

**Issue:** Mix of P&L and BS in one table.

**Solution:**
1. In Excel, separate into two tables: IncomeStatementTable and BalanceSheetTable
2. Create Power Query for each
3. Add custom column in first: FinancialStatement = "IncomeStatement"
4. Add custom column in second: FinancialStatement = "BalanceSheet"
5. Append (combine) both queries in Power Query
6. Result: One tall table with FinancialStatement column distinguishing P&L from BS

**Append formula in Power Query:**
1. Right-click IncomeStatementQuery
2. Select "Append Queries"
3. Choose BalanceSheetQuery
4. Click OK
5. Result: Two tables combined into one

## Power Query Maintenance

**Monthly refresh process:**

```
Month 1: Build query (one-time setup)
Months 2+: Repeat these steps
  1. Update IncomeStatementTable with new month data (wide format)
  2. Right-click DataTable in Excel
  3. Select "Refresh" (or Refresh All)
  4. Power Query automatically unpivots new data
  5. Dashboard pulls from DataTable, so charts update automatically

Time required: 30 seconds
Manual work: 0
```

## Key Principles

1. **Source stays wide format.** Your financial model or GL export is wide. Don't change it.
2. **Power Query handles transformation.** It unpivots automatically.
3. **Tall table is the output.** Dashboard reads from tall table, not source.
4. **Refresh is automatic.** If you've set up Power Query correctly, monthly updates require no formula rewriting.
5. **One query per statement.** Separate Income Statement, Balance Sheet, and Cash Flow into different queries.

