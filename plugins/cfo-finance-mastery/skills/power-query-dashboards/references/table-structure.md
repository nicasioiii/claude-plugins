---
name: Excel Table Structure & Named Ranges
description: Design data table structure for dashboards, understand table vs. range differences, and implement dynamic references.
---

# Excel Table Structure & Named Ranges

## Table vs. Range: Why Tables Win

### Range (Old Way)

```
A1:E50  "Source Data"
```

**Problems:**
- Add new row → formulas pointing to A1:E50 don't auto-update
- Column reference like "Account" must use INDEX/MATCH
- Refresh Power Query → new data lands outside range → dashboard breaks

### Table (New Way)

```
Data[Account]  "Automatically expands"
```

**Benefits:**
- Add new row → table auto-expands to include it
- Reference by column name: `Data[Amount]` (no row numbers)
- Power Query loads to table → dashboard formulas always include new data
- Sorting/filtering work within table bounds automatically

## Creating an Excel Table

**Step 1: Select your data**
```
A1:E50 (all headers and data)
```

**Step 2: Press Ctrl+T**
- Or: Insert → Table → Format as Table

**Step 3: Confirm headers**
- Dialog appears asking "Does your data have headers?"
- Check the box if row 1 contains column names
- Click OK

**Step 4: Rename the table**
- Table Tools → Design tab
- Field "Table Name" shows "Table1"
- Change to meaningful name: "IncomeStatementData"
- Press Enter

**Result:**
- Table headers have filter dropdowns
- Table auto-expands when new rows added below
- All formulas referencing table update automatically

## Table Naming Conventions

**Use clear, descriptive names:**

```
FINANCIAL DATA TABLES:
- IncomeStatementData (tall format: Account, Date, Amount)
- BalanceSheetData (tall format: Account, Date, Amount)
- CashFlowData (tall format: Account, Date, Amount)

WORKING CAPITAL TABLES:
- ARByCustomer (Customer, Date, Amount)
- InventoryByLocation (Location, Date, Amount)
- APByVendor (Vendor, Date, Amount)

DASHBOARD SUMMARY TABLES:
- RevenueSummary (Month, Revenue, MarginPercent)
- MetricsSummary (MetricName, Value)
```

## Table Column Structure

### Data Table (Tall Format)

**For Power Query output, use this structure:**

```
Column A: Account
  - Values: "Revenue", "COGS", "Payroll", etc.
  - Used for filtering dashboard by account
  - Example: Dashboard shows "Revenue" only

Column B: SummaryGroup
  - Values: "Revenue", "COGS", "OpEx"
  - Higher-level grouping for subtotals
  - Example: Sum all "Revenue" accounts

Column C: FinancialStatement
  - Values: "IncomeStatement", "BalanceSheet", "CashFlow"
  - Separates P&L from balance sheet from CF
  - Example: Dashboard pulls IncomeStatement data only

Column D: Date
  - Values: 1/31/2024, 2/28/2024, 3/31/2024
  - Month-end dates (critical for date range filtering)
  - Must be actual date format, not text
  - Example: =DATE(2024,1,31)

Column E: Amount
  - Values: 100000, 40000, 30000, etc.
  - Numeric values (not text with commas)
  - Used in SUM and SUMPRODUCT formulas
  - Example: 100000 (not "100,000")
```

**Result table:**

```
Account    SummaryGroup  FinancialStatement  Date       Amount
Revenue    Revenue       IncomeStatement     1/31/2024  100,000
Revenue    Revenue       IncomeStatement     2/28/2024  105,000
COGS       COGS          IncomeStatement     1/31/2024   40,000
COGS       COGS          IncomeStatement     2/28/2024   42,000
Payroll    OpEx          IncomeStatement     1/31/2024   30,000
Payroll    OpEx          IncomeStatement     2/28/2024   30,000
```

## Named Ranges for Dashboard Filters

**Create named ranges for date filters** so formulas update when user changes dates.

### Creating a Named Range

**Step 1: Select a cell (e.g., Dashboard!E2 for start date)**

**Step 2: In Ribbon, go to Formulas → Define Name**
- Or: Ctrl+Shift+F3

**Step 3: Name it: "DashboardStartDate"**
- Keep names simple, no spaces
- Prefix with context: "Dashboard"

**Step 4: Formula field shows: =Dashboard!$E$2**
- This is correct (absolute reference to E2)
- Click OK

**Repeat for end date:**
- Select Dashboard!E3
- Define Name: "DashboardEndDate"
- Formula: =Dashboard!$E$3

### Using Named Ranges in Formulas

**Instead of this:**
```
=SUMPRODUCT(
  (IncomeStatementData[Amount])
  * (IncomeStatementData[Date] >= Dashboard!$E$2)
  * (IncomeStatementData[Date] <= Dashboard!$E$3)
)
```

**Use this:**
```
=SUMPRODUCT(
  (IncomeStatementData[Amount])
  * (IncomeStatementData[Date] >= DashboardStartDate)
  * (IncomeStatementData[Date] <= DashboardEndDate)
)
```

**Benefits:**
- Formula is more readable
- If date cells move, named range updates automatically
- Multiple formulas can share same date range

## Table Slicers (Visual Filters)

**Slicers are visual filters that users click** to filter the table.

### Creating a Slicer

**Step 1: Select data table (e.g., IncomeStatementData)**

**Step 2: Insert → Slicer**
- Dialog appears: "Insert Slicers"
- Check "SummaryGroup" and "Date" columns
- Click OK

**Step 3: Slicers appear as floating boxes**
```
SummaryGroup Slicer:
  [Revenue] [COGS] [OpEx]

Date Slicer:
  [1/31/2024] [2/28/2024] [3/31/2024]
```

**Step 4: User clicks to filter**
- Click "Revenue" → table shows Revenue only
- Click "Revenue" + "1/31/2024" → shows Revenue on 1/31 only
- Click "Clear Filter" → shows all data

### Connecting Slicer to Dashboard Formulas

**Slicers automatically filter the source table,** so any formula reading the table sees filtered data.

**Example:**
```
Dashboard SUMPRODUCT formula:
=SUMPRODUCT(IncomeStatementData[Amount])

User clicks "Revenue" slicer → formula sees only Revenue rows → result = Revenue total
User clicks "OpEx" slicer → formula sees only OpEx rows → result = OpEx total
```

**Result:** No change to formula needed. Slicer does the filtering.

## Linked Table Relationships

### One-to-Many Example

**Main table: IncomeStatementData** (one row per account per date)
**Related table: AccountDetail** (drilling into account details)

```
IncomeStatementData:
Account    Date        Amount
Revenue    1/31/2024   100,000
Revenue    2/28/2024   105,000

AccountDetail:
Account    SubAccount  Date        Amount
Revenue    Product     1/31/2024    95,000
Revenue    Service     1/31/2024     5,000
Revenue    Product     2/28/2024   100,000
Revenue    Service     2/28/2024     5,000
```

**In dashboard, SUMPRODUCT can drill into detail:**

```
=SUMPRODUCT(
  (AccountDetail[SubAccount] = "Service")
  * (AccountDetail[Amount])
  * (AccountDetail[Date] >= DashboardStartDate)
)
Result: Sum of service revenue only
```

## Table Auto-Expansion (Power Query Integration)

**When Power Query loads data to a table, it auto-expands:**

**Month 1:**
```
IncomeStatementData has 36 rows (12 months × 3 accounts)
Range: A1:E36
```

**Month 2: New month data added**
```
Power Query refresh adds 3 new rows
IncomeStatementData now has 39 rows
Range: A1:E39 (automatically updated)
```

**No manual intervention needed.** Formulas reading `IncomeStatementData[Amount]` automatically include new rows.

## Table Structure Best Practices

**1. One table per statement**
```
- IncomeStatementData (not all three combined)
- BalanceSheetData
- CashFlowData
```
Reason: Makes filtering by FinancialStatement column easier.

**2. Date column is always month-end**
```
1/31/2024 (not 1/1/2024 or 1/15/2024)
2/28/2024 (not 2/1/2024)
```
Reason: Aligns with financial reporting periods.

**3. Amount column is numeric, no currency formatting**
```
100000 (not $100,000 or 100000.00)
40000 (not 40K or 40,000)
```
Reason: Numeric values work in formulas; formatting is applied in dashboard, not source.

**4. Account and SummaryGroup use exact spelling**
```
"Revenue" (not "revenue" or "REVENUE")
"OpEx" (not "Operating Expense")
```
Reason: SUMPRODUCT comparisons are case-sensitive; inconsistent naming breaks aggregation.

**5. No blank rows or columns within table**
```
Good:  Data → Data → Data → (blank below)
Bad:   Data → (blank row) → Data
```
Reason: Blank rows confuse Power Query unpivoting.

## Troubleshooting Table Issues

**Problem: Dashboard formula shows wrong total**
- Check: Does table include all data rows? (Scroll to bottom)
- Check: Are Account names spelled correctly? ("Revenue" vs "revenue")
- Check: Is amount column numeric? (Left-aligned = text; right-aligned = numeric)

**Problem: Power Query refresh adds rows but dashboard doesn't update**
- Check: Are formulas referencing the table name? (Good: `IncomeStatementData[Amount]`) (Bad: `A2:E100`)
- Check: Did you use absolute range (A2:E100) instead of table reference?

**Problem: Slicer won't filter dashboard**
- Check: Is slicer connected to correct table? (Right-click slicer → Report Connections)
- Check: Are formulas reading filtered table or hard-coded range?

