---
name: Building Summarized P&L, Balance Sheet & Cash Flow
description: Create dashboard views of financial statements using SUMPRODUCT aggregation and intelligent summarization.
---

# Summarized Financial Statements

## Three Statement Summarization Strategy

**Dashboard shows summaries, not raw data. Build three aggregation layers:**

```
Layer 1: Raw Data (from Power Query)
  - IncomeStatementData table (one row per account per date)
  - Granular, un-aggregated

Layer 2: Summarization Formulas (SUMPRODUCT)
  - Create totals by SummaryGroup (Revenue, COGS, OpEx)
  - Respect date range filters

Layer 3: Display (Dashboard Sheet)
  - Shows summaries in financial statement format
  - Uses Layer 2 formulas, not raw data
  - Professional formatting
```

## Income Statement Summarization

### Create Summarization Sheet

**In worksheet, create "P&L_Summary" tab**

**Structure:**
```
                    Jan 2024    Feb 2024    Mar 2024
REVENUE
  Total Revenue     [formula]   [formula]   [formula]

COST OF GOODS SOLD
  COGS              [formula]   [formula]   [formula]
─────────────────────────────────────────────────────
Gross Profit        [formula]   [formula]   [formula]
Gross Margin %      [formula]   [formula]   [formula]

OPERATING EXPENSES
  Payroll           [formula]   [formula]   [formula]
  Marketing         [formula]   [formula]   [formula]
  Rent              [formula]   [formula]   [formula]
  Software          [formula]   [formula]   [formula]
  Other             [formula]   [formula]   [formula]
─────────────────────────────────────────────────────
Total OpEx          [formula]   [formula]   [formula]

OPERATING INCOME    [formula]   [formula]   [formula]
Operating Margin %  [formula]   [formula]   [formula]

Other Income/Exp    [formula]   [formula]   [formula]
─────────────────────────────────────────────────────
NET INCOME          [formula]   [formula]   [formula]
Net Margin %        [formula]   [formula]   [formula]
```

### Revenue Summarization Formula

**In cell B2 (Jan 2024 Revenue):**

```
=SUMPRODUCT(
  (IncomeStatementData[SummaryGroup] = "Revenue")
  * (IncomeStatementData[Date] = $B$1)
  * (IncomeStatementData[Amount])
)
```

**Explanation:**
- Look at IncomeStatementData table
- Find rows where SummaryGroup = "Revenue"
- AND Date matches column header (B1 = 1/31/2024)
- Sum the Amount values

**Result:** $100,000 (sum of all Revenue accounts for Jan)

**Copy right (Jan → Feb → Mar):** Formula auto-adjusts column reference

### COGS Summarization

**Same pattern, different SummaryGroup:**

```
=SUMPRODUCT(
  (IncomeStatementData[SummaryGroup] = "COGS")
  * (IncomeStatementData[Date] = $B$1)
  * (IncomeStatementData[Amount])
)
```

### Gross Profit Formula

**Gross Profit = Revenue - COGS (reference cells above)**

```
=B2 - B5
(where B2 = Revenue, B5 = COGS)
```

**Copy right:** Automatically calculates for Feb, Mar

### Gross Margin % Formula

**Gross Margin % = Gross Profit / Revenue**

```
=B7 / B2
(where B7 = Gross Profit, B2 = Revenue)

Format as percentage: Right-click → Format Cells → Percentage
```

**Result:** 60% (if Gross Profit $60K, Revenue $100K)

### Operating Expenses (Detailed Lines)

**For each expense account, separate formula:**

**Payroll:**
```
=SUMPRODUCT(
  (IncomeStatementData[Account] = "Payroll")
  * (IncomeStatementData[Date] = $B$1)
  * (IncomeStatementData[Amount])
)
```

**Marketing:**
```
=SUMPRODUCT(
  (IncomeStatementData[Account] = "Marketing")
  * (IncomeStatementData[Date] = $B$1)
  * (IncomeStatementData[Amount])
)
```

**Rent:**
```
=SUMPRODUCT(
  (IncomeStatementData[Account] = "Rent")
  * (IncomeStatementData[Date] = $B$1)
  * (IncomeStatementData[Amount])
)
```

**Repeat for Software, Other, etc.**

**Total OpEx (sum line):**
```
=SUM(B11:B16)
(where B11:B16 are individual OpEx line items)
```

### Operating Income & Margin

**Operating Income = Gross Profit - Total OpEx**

```
=B7 - B18
(where B7 = Gross Profit, B18 = Total OpEx)
```

**Operating Margin % = Operating Income / Revenue**

```
=B20 / B2
(format as percentage)
```

### Net Income (Bottom Line)

**Net Income = Operating Income + Other Income/Expense**

```
=B20 + B22
(where B20 = Operating Income, B22 = Other Exp)
```

**Net Margin % = Net Income / Revenue**

```
=B24 / B2
(format as percentage)
```

## Balance Sheet Summarization

### Create BS Summary Sheet

**In worksheet, create "BS_Summary" tab**

**Structure:**
```
                    Jan 31      Feb 28      Mar 31
CURRENT ASSETS
  Cash              [formula]   [formula]   [formula]
  Accounts Recv     [formula]   [formula]   [formula]
  Inventory         [formula]   [formula]   [formula]
─────────────────────────────────────────────────
Total Current      [formula]   [formula]   [formula]

FIXED ASSETS
  Equipment, Net    [formula]   [formula]   [formula]
─────────────────────────────────────────────────
TOTAL ASSETS       [formula]   [formula]   [formula]

CURRENT LIAB
  Accounts Pay      [formula]   [formula]   [formula]
  Accrued Exp       [formula]   [formula]   [formula]
  Short-term Debt   [formula]   [formula]   [formula]
─────────────────────────────────────────────────
Total Current L    [formula]   [formula]   [formula]

LONG-TERM LIAB
  Long-term Debt    [formula]   [formula]   [formula]
─────────────────────────────────────────────────
TOTAL LIAB         [formula]   [formula]   [formula]

EQUITY
  Common Stock      [formula]   [formula]   [formula]
  Retained Earn     [formula]   [formula]   [formula]
─────────────────────────────────────────────────
TOTAL EQUITY       [formula]   [formula]   [formula]

TOTAL LIAB + EQ    [formula]   [formula]   [formula]

CHECK (should = 0) [formula]   [formula]   [formula]
```

### Balance Sheet Formulas

**Balance Sheet dates are "as of" (not period, but specific date).**

**Cash (most recent month-end):**

```
=SUMPRODUCT(
  (BalanceSheetData[Account] = "Cash")
  * (BalanceSheetData[Date] = $B$1)
  * (BalanceSheetData[Amount])
)
```

**Accounts Receivable:**

```
=SUMPRODUCT(
  (BalanceSheetData[Account] = "AR")
  * (BalanceSheetData[Date] = $B$1)
  * (BalanceSheetData[Amount])
)
```

**Equipment, Net:**

```
=SUMPRODUCT(
  (BalanceSheetData[Account] = "Equipment-Net")
  * (BalanceSheetData[Date] = $B$1)
  * (BalanceSheetData[Amount])
)
```

**Total Assets:**

```
=SUM(B2:B4) + B8
(Current assets + Fixed assets)
```

**Total Current Liabilities:**

```
=SUM(B14:B16)
(Accounts Payable + Accrued + Short-term debt)
```

**Total Equity:**

```
=SUM(B26:B27)
(Common Stock + Retained Earnings)
```

**Balance Check:**

```
=B20 - (B24 + B28)
(Assets - (Liabilities + Equity); should = 0)
```

## Cash Flow Summarization

### Create CF Summary Sheet

**In worksheet, create "CF_Summary" tab**

**Structure:**
```
                        Jan         Feb         Mar
OPERATING ACTIVITIES
  Operating CF          [formula]   [formula]   [formula]
  Depr/Amort            [formula]   [formula]   [formula]
  WC Changes            [formula]   [formula]   [formula]
─────────────────────────────────────────────────
Total Operating CF      [formula]   [formula]   [formula]

INVESTING ACTIVITIES
  CapEx                 [formula]   [formula]   [formula]
─────────────────────────────────────────────────
Total Investing CF      [formula]   [formula]   [formula]

FINANCING ACTIVITIES
  Debt Increases        [formula]   [formula]   [formula]
  Debt Repay            [formula]   [formula]   [formula]
  Owner Draw            [formula]   [formula]   [formula]
─────────────────────────────────────────────────
Total Financing CF      [formula]   [formula]   [formula]

NET CHANGE IN CASH      [formula]   [formula]   [formula]
Beginning Cash          [formula]   [formula]   [formula]
ENDING CASH             [formula]   [formula]   [formula]
```

### Cash Flow Formulas

**Operating Cash Flow (pulled from prior analysis):**

```
=SUMPRODUCT(
  (CashFlowData[Section] = "Operating")
  * (CashFlowData[Date] = $B$1)
  * (CashFlowData[Amount])
)
```

**CapEx (Investing activity):**

```
=SUMPRODUCT(
  (CashFlowData[Section] = "Investing")
  * (CashFlowData[Date] = $B$1)
  * (CashFlowData[Amount])
)
```

**Total Operating CF:**

```
=B2 + B3 + B4
(Operating CF + Depr/Amort + WC Changes)
```

**Net Change in Cash:**

```
=B11 + B17 + B23
(Operating + Investing + Financing)
```

**Ending Cash:**

```
=B25 + B26
(Beginning Cash + Net Change)
```

**Validation (should match BS):**

```
=B27 - BalanceSheetData[Cash]
(Should = 0)
```

## Real Example: 3-Month P&L Summary

```
                        Jan 2024    Feb 2024    Mar 2024
REVENUE                 100,000     105,000     110,000

COGS                     40,000      42,000      44,000
─────────────────────────────────────────────────────
Gross Profit             60,000      63,000      66,000
Gross Margin %              60.0%       60.0%       60.0%

OPERATING EXPENSES
  Payroll                30,000      30,000      30,000
  Marketing               5,000       5,500       6,000
  Rent                    5,000       5,000       5,000
  Software                2,000       2,000       2,000
  Other                   1,000       1,000       1,000
─────────────────────────────────────────────────────
Total OpEx               43,000      43,500      44,000

OPERATING INCOME         17,000      19,500      22,000
Operating Margin %          17.0%       18.6%       20.0%

Other Exp                   (500)       (500)       (500)
─────────────────────────────────────────────────────
NET INCOME               16,500      19,000      21,500
Net Margin %                16.5%       18.1%       19.5%
```

**All numbers pulled from Power Query data using SUMPRODUCT. Change date filter → all recalculate.**

## Key Principles

1. **Summarize by SummaryGroup, not Account.** Income statement shows Revenue, not detailed revenue accounts.
2. **Use SUMPRODUCT for flexibility.** Easy to add filters (date range, account type, etc.).
3. **Formulas cascade properly.** Change one SUMPRODUCT → all dependent calculations update.
4. **Balance checks built-in.** BS always checks Assets = Liab + Equity; CF ending = BS cash.
5. **Margin percentages calculated dynamically.** Change revenue → margins recalculate automatically.

