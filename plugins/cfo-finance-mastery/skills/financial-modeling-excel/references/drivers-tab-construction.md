---
name: Drivers Tab Construction & SUMIFS Patterns
description: Step-by-step process for building the master control panel, including SUMIFS formulas, historical vs projection logic, and column locking strategies.
---

# Drivers Tab Construction & SUMIFS Patterns

## Overview

The Drivers tab is where all model assumptions live. It has two types of formulas:
- **Historical columns** pull actual data from Source using SUMIFS
- **Projection columns** accept direct input (assumptions you enter)

This reference teaches you to build it.

## Step 1: Export and Clean Source Data

**From your accounting software, export GL in this format:**
```
Account          | Date       | Amount
Revenue          | 2024-01-31 | 100000
COGS             | 2024-01-31 | 40000
Payroll          | 2024-01-31 | 20000
Rent             | 2024-01-31 | 5000
...
Revenue          | 2024-02-28 | 105000
COGS             | 2024-02-28 | 42000
```

**Rules:**
- One row per account per date
- No subtotals (individual accounts only)
- Dates in YYYY-MM-DD format
- Amount column positive (expenses and revenues both positive)

**Create Excel table:**
1. Select all data
2. Ctrl+T (convert to table)
3. Name it "SourceGL"
4. Result: Table that auto-expands as you add rows

## Step 2: Create Drivers Sheet Structure

**New sheet "Drivers"**

**Section 1: Headers (Row 1)**
```
                    | Jan 2024 | Feb 2024 | Mar 2024 | Apr 2024 | Notes
[account names]     |    ...   |   ...    |   ...    |   ...    |
```

**Section 2: Income Statement (Rows 2-20)**
```
                    | Jan 2024 | Feb 2024 | Mar 2024 | Apr 2024 |
Revenue             | [formula]| [formula]| [formula]| [input]  |
COGS                | [formula]| [formula]| [formula]| [formula]|
COGS %              | 40.0%    | 40.0%    | 40.0%    | 40.0%    |
Gross Profit        | [formula]| [formula]| [formula]| [formula]|
...
```

**Section 3: Balance Sheet (Rows 22-40)**
```
Cash                | [formula]| [formula]| [formula]| [formula]|
AR (Days)           | 45       | 45       | 45       | 45       |
AR Balance          | [formula]| [formula]| [formula]| [formula]|
Inventory           | [formula]| [formula]| [formula]| [formula]|
...
```

## Step 3: SUMIFS Formula for Historical Data

**Purpose:** Pull actual amounts from Source tab automatically

**Formula syntax:**
```
=SUMIFS(sum_range, criteria_range, criteria, [criteria_range2, criteria2], ...)
```

**For Drivers tab revenue cell (B2):**

```
=SUMIFS($SourceGL[Amount], $SourceGL[Account], "Revenue", $SourceGL[Date], B$1)
```

**Formula breakdown:**
- `$SourceGL[Amount]`: Column to sum (lock both column and reference)
- `$SourceGL[Account]`: Account criteria column (lock both)
- `"Revenue"`: Which account to match (hardcoded, specific account name)
- `$SourceGL[Date]`: Date criteria column (lock both)
- `B$1`: Date header in Drivers row 1 (lock row only; column floats)

**How to build it:**
1. Click on Drivers!B2 (Revenue, Jan 2024)
2. Type: =SUMIFS($SourceGL[Amount],$SourceGL[Account],"Revenue",$SourceGL[Date],B$1)
3. Press Enter
4. Result shows Jan 2024 revenue (pulled from Source)

**Copy the formula right (across months):**
1. Select B2
2. Ctrl+C (copy)
3. Select B2:E2 (Jan-Apr columns)
4. Ctrl+V (paste)
5. Formula auto-adjusts (B$1→C$1→D$1→E$1)
6. Result: All months show revenue (each pulls from Source for that date)

**Column locking strategy explained:**
```
$SourceGL[Amount]   → Always refers to SourceGL Amount column (locked)
$SourceGL[Account]  → Always refers to SourceGL Account column (locked)
"Revenue"           → Always looks for "Revenue" account (hardcoded)
$SourceGL[Date]     → Always refers to SourceGL Date column (locked)
B$1                 → Row 1 (headers) locked; column B floats (becomes C, D, E as copied right)
```

When copied to C2:
```
=SUMIFS($SourceGL[Amount],$SourceGL[Account],"Revenue",$SourceGL[Date],C$1)
(Column B became C; row 1 stayed row 1)
```

## Step 4: Add Projection Columns

**For Apr 2024 (projection month), change formula logic:**

**Historical months (Jan-Mar): SUMIFS formula**
```
=SUMIFS($SourceGL[Amount],$SourceGL[Account],"Revenue",$SourceGL[Date],B$1)
```

**Projection months (Apr+): Direct input or formula based on assumptions**

**Option A: Direct input (user types forecast)**
```
Cell D2 (Apr 2024 Revenue): Just type 115000 (no formula)
```

**Option B: Formula based on driver assumptions**
```
Cell D2 (Apr 2024 Revenue): =D3*1.05 (prior month * 5% growth)
OR
Cell D2: =B2 * (1 + 5%) (January * annual growth % applied)
```

**Best practice:** Use driver assumptions for projections.

**Example:**
```
Row 1:  Growth Assumption = 5% (in separate driver row)
Row 2:  Revenue = =C2 * (1 + Growth_Assumption%)
        Result: Feb revenue * 1.05 = Mar forecast
```

## Step 5: Build Assumption Rows for Key Drivers

**For each major line item, create an "assumption" row:**

**Revenue drivers:**
```
Revenue (actual)    | 100K | 105K | 110K | [formula]
Growth % (input)    | —    | —    | —    | 5%       ← User inputs here
Revenue (forecast)  | —    | —    | —    | =Prior*Growth% ← Calculates
```

**COGS drivers:**
```
COGS (actual)       | 40K  | 42K  | 44K  | [formula]
COGS % (input)      | 40%  | 40%  | 40%  | 42%      ← User inputs here
COGS (forecast)     | —    | —    | —    | =Rev*COGS% ← Calculates
```

**Payroll drivers:**
```
Headcount           | 5    | 5    | 5    | 6        ← User inputs forecast HC
Payroll/Person      | 4K   | 4K   | 4K   | 4.2K     ← User inputs salary
Total Payroll       | 20K  | 20K  | 20K  | 25.2K    ← =HC*Payroll/Person
```

**This structure lets users change growth rate, COGS %, headcount, etc. in one place. Formulas cascade automatically.**

## Step 6: Create Named Range for Last Month of Actuals

**Purpose:** Mark the boundary between historical (actual) and projection (forecast)

**How to create:**
1. Create a reference cell (e.g., Drivers!G1)
2. Enter today's date: 3/31/2024
3. Select cell → Formulas → Define Name
4. Name: "LastMonthOfActuals"
5. Refers to: =Drivers!$G$1

**Use named range in IF logic:**
```
=IF(B$1 <= LastMonthOfActuals, [SUMIFS formula], [assumption input])
```

**Example in cell B2 (Revenue):**
```
=IF(B$1 <= LastMonthOfActuals, SUMIFS($SourceGL[Amount],$SourceGL[Account],"Revenue",$SourceGL[Date],B$1), [input])
```

**Benefit:** When you update G1 to next month's date, historical/projection boundary shifts automatically. No manual column reorganization needed.

## Step 7: Expand to Multiple Periods

**Set up Drivers for three time horizons:**

**Monthly detail (12 months):**
```
                    | Jan 2024 | Feb 2024 | ... | Dec 2024 |
Revenue             | [formula]| [formula]| ... | [formula]|
...
```

**Quarterly summary (4 quarters):**
```
                    | Q1 2024 | Q2 2024 | Q3 2024 | Q4 2024 |
Revenue             | [sum]   | [sum]   | [sum]   | [sum]   |
...
```

**Annual summary (current + prior year):**
```
                    | 2024    | 2023    |
Revenue             | [sum]   | [sum]   |
...
```

**How to set up quarterly formula:**
```
Q1 2024 Revenue = Jan2024 + Feb2024 + Mar2024
Cell: =B2 + C2 + D2 (sums the three months)
```

**Benefit:** Users can work with months, but see quarterly and annual summaries automatically. All reference same base data.

## Step 8: Format and Lock Structure

**Formatting:**
- Headers (row 1): Bold, blue background
- Account names (column A): Bold, left-aligned
- Input assumptions: Light blue cells (signal to user: "change me")
- SUMIFS formulas: Purple cells (signal to user: "don't touch")
- Calculated totals: Green cells (for viewing only)

**Locking columns (optional):**
1. Select columns A:D (accounts + key months)
2. View → Freeze Panes (keeps account names visible when scrolling right)

**Result:** Users can scroll through months but always see account names.

## Step 9: Create SUMIFS for All Line Items

**Revenue (example done above)**

**COGS:**
```
=SUMIFS($SourceGL[Amount],$SourceGL[Account],"COGS",$SourceGL[Date],B$1)
(Copy across all historical months)
(Projections: =B2*COGS% or =Revenue*COGS%)
```

**Payroll:**
```
=SUMIFS($SourceGL[Amount],$SourceGL[Account],"Payroll",$SourceGL[Date],B$1)
(Or calculated: =Headcount*CostPerEmployee)
```

**Other operating expenses (Rent, Ad Spend, Software, etc.):**
```
=SUMIFS($SourceGL[Amount],$SourceGL[Account],"Rent",$SourceGL[Date],B$1)
(Repeats for each account)
```

**Depreciation (special case; not in GL, calculated):**
```
=DepreciationSchedule!Amount (pulled from separate depreciation table)
OR
=FixedAssetCost * DepreciationRate / 12 (monthly allocation)
```

**Rule:** One SUMIFS formula per account. Copy across all months. Instant data pull from Source.

## Step 10: Validation

**Check:** Do the SUMIFS formulas pull the right numbers?

1. Manually add up Jan 2024 revenue from Source (should be sum of all "Revenue" rows with that date)
2. Compare to Drivers!B2 (SUMIFS result)
3. If they match: SUMIFS is correct
4. If they don't: Check account name spelling, date format

**Common SUMIFS mistakes:**
- Account name has space or typo ("Revenue " vs "Revenue")
- Date format mismatch (1/31/2024 vs 2024-01-31)
- Criteria range is wrong (using wrong column)
- Sum range includes subtotal row (which double-counts)

**Test data:** Use a small GL export first (10 transactions). Verify SUMIFS pulls correct subset. Then expand to full GL.

