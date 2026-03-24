---
name: Dynamic Filters, Date Range Selection & Interactive Elements
description: Build interactive dashboards with date pickers, period comparisons, and user-controlled filtering.
---

# Dynamic Filters & Interactive Dashboard Elements

## Date Range Filter (Foundation)

**Every dashboard needs user-controlled date range.**

### Create Filter Controls

**On Dashboard sheet, top-left:**

```
┌──────────────────────────────────────┐
│ PERIOD SELECTION                     │
├──────────────────────────────────────┤
│ Start Date: [1/31/2024    ▼]         │ Cell: E2
│ End Date:   [3/31/2024    ▼]         │ Cell: E3
│                                       │
│ [Refresh Dashboard]                  │ Button
└──────────────────────────────────────┘
```

### Step 1: Set Up Date Cells

**In cell E2 (Start Date):**
```
Value: 1/31/2024 (default month-end date)
Format: Date (mm/dd/yyyy)
```

**In cell E3 (End Date):**
```
Value: 3/31/2024 (default month-end date)
Format: Date (mm/dd/yyyy)
```

### Step 2: Data Validation (Dropdown)

**Select cell E2 → Data → Data Validation**

```
Allow: List
Source: =IncomeStatementData[Date]
(or =UNIQUE(IncomeStatementData[Date]))

Ignore Blank: Unchecked
In-Cell Dropdown: Checked
```

**Result:** User clicks E2, dropdown shows all available dates.

**Repeat for E3.**

### Step 3: Name the Date Ranges

**Formulas → Define Name → "DashboardStartDate"**
```
Refers to: =Dashboard!$E$2
```

**Formulas → Define Name → "DashboardEndDate"**
```
Refers to: =Dashboard!$E$3
```

### Step 4: Update All Formulas to Use Named Ranges

**All SUMPRODUCT formulas reference named ranges:**

```
=SUMPRODUCT(
  (IncomeStatementData[SummaryGroup] = "Revenue")
  * (IncomeStatementData[Date] >= DashboardStartDate)
  * (IncomeStatementData[Date] <= DashboardEndDate)
  * (IncomeStatementData[Amount])
)
```

**When user changes E2 or E3 → all formulas update automatically.**

## Period-over-Period Comparison

**Compare current period to prior year same period.**

### Create Comparison Cells

```
Period 1 Selection:
  Start: [1/31/2024  ▼]  Named range: "P1Start"
  End:   [3/31/2024  ▼]  Named range: "P1End"

Period 2 Selection:
  Start: [1/31/2023  ▼]  Named range: "P2Start"
  End:   [3/31/2023  ▼]  Named range: "P2End"

[Compare]  (Button to trigger refresh)
```

### Build Comparison Table

**Three-column layout:**

```
                    Period 1    Period 2    Change (%)
Revenue             $315,000    $300,000    +5.0%
COGS                $126,000    $120,000    +5.0%
─────────────────────────────────────────────────────
Gross Profit        $189,000    $180,000    +5.0%
Margin %               60.0%       60.0%      —

OpEx                $108,000    $105,000    +2.9%
─────────────────────────────────────────────────────
Net Income          $ 81,000    $ 75,000    +8.0%
Margin %               25.7%       25.0%    +0.7pp
```

### Period 1 Revenue Formula

```
=SUMPRODUCT(
  (IncomeStatementData[SummaryGroup] = "Revenue")
  * (IncomeStatementData[Date] >= P1Start)
  * (IncomeStatementData[Date] <= P1End)
  * (IncomeStatementData[Amount])
)
```

### Period 2 Revenue Formula

```
=SUMPRODUCT(
  (IncomeStatementData[SummaryGroup] = "Revenue")
  * (IncomeStatementData[Date] >= P2Start)
  * (IncomeStatementData[Date] <= P2End)
  * (IncomeStatementData[Amount])
)
```

### Change % Formula

```
=(B2 - C2) / C2
(Period 1 - Period 2) / Period 2
Format as percentage
```

**Interpretation:**
```
+5.0%  = Period 1 is 5% higher (positive growth)
-3.0%  = Period 1 is 3% lower (decline)
0.0%   = Same as prior period (flat)
```

## Visual Slicers (Filter Buttons)

**Slicers are visual drop-down boxes on dashboard for easy filtering.**

### Creating a Slicer

**Select data table → Insert → Slicer**

```
Available columns:
  ☑ SummaryGroup (Revenue, COGS, OpEx)
  ☑ Account (Revenue, COGS, Payroll, Marketing, ...)
  ☑ Date (1/31/2024, 2/28/2024, 3/31/2024, ...)

Click OK
```

**Result: Three floating slicer boxes appear on dashboard**

```
┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│ SummaryGroup │  │   Account    │  │    Date      │
├──────────────┤  ├──────────────┤  ├──────────────┤
│ Revenue  ☐   │  │ Revenue  ☐   │  │ 1/31/2024 ☐  │
│ COGS     ☐   │  │ COGS     ☐   │  │ 2/28/2024 ☐  │
│ OpEx     ☐   │  │ Payroll  ☐   │  │ 3/31/2024 ☐  │
└──────────────┘  │ Marketing☐   │  └──────────────┘
                  │ Rent     ☐   │
                  └──────────────┘
```

### Using Slicers

**User clicks filter options:**

```
Click "Revenue" checkbox → Table shows Revenue rows only
Click "Revenue" + "1/31/2024" → Table shows Revenue on 1/31 only
Click "Clear Filter" → Table shows all data

Any formula reading the table automatically sees filtered data.
```

**Result:** SUMPRODUCT formulas automatically see filtered table. No formula changes needed.

### Positioning Slicers

**Move slicers to top-right of dashboard:**
- Right-click slicer
- Drag to desired position
- Resize by corner handles

**Arrange side-by-side** for clean look.

## Multi-Select Dropdown (Advanced)

**If slicers not available, use data validation multi-select.**

### Create Multi-Select Cell

**In cell F5 (Account filter):**

**Data → Data Validation**

```
Allow: List
Source: =IncomeStatementData[Account]
Separated by: Comma (or semicolon based on locale)
In-cell dropdown: Checked
```

**Result:** User can type "Revenue, COGS" (comma-separated) to filter to multiple accounts.

### Formula Adjustment

**SUMPRODUCT formula must handle comma-separated list:**

```
=SUMPRODUCT(
  (ISNUMBER(SEARCH(IncomeStatementData[Account], F5)))
  * (IncomeStatementData[Date] >= DashboardStartDate)
  * (IncomeStatementData[Date] <= DashboardEndDate)
  * (IncomeStatementData[Amount])
)
```

**Explanation:** SEARCH looks for account name in F5 string; if found, includes in sum.

## Refresh Button (Macro)

**Optional: Create button to refresh Power Query and recalculate all formulas.**

### Step 1: Create Button

**Insert → Button**
- Draw rectangle on dashboard
- Label: "Refresh Data"

### Step 2: Assign Macro

**Right-click button → Assign Macro**

**Create new macro:**

```vba
Sub RefreshDashboard()
  ' Refresh all Power Query connections
  ActiveWorkbook.Connections("IncomeStatementData_Connection").Refresh
  ActiveWorkbook.Connections("BalanceSheetData_Connection").Refresh
  ActiveWorkbook.Connections("CashFlowData_Connection").Refresh

  ' Force recalculation
  Application.Calculate

  MsgBox "Dashboard updated: " & Now()
End Sub
```

### Step 3: User Clicks Button

**Dashboard → Refresh Data button → All data updates → Success message shows timestamp.**

## Scenario Analysis (What-If)

**Build alternative forecasts by changing single assumptions.**

### Create Scenario Selector

```
Scenario Analysis:
  Base Case      (default, using actual data)
  Optimistic     (revenue +10%, expenses flat)
  Conservative   (revenue -5%, expenses +10%)

  [Select Scenario ▼]  Default: "Base Case"
```

### Build Scenario Logic

**In Drivers tab, create three forecast sets:**

```
                    Base        Optimistic   Conservative
Revenue Forecast    $100,000    $110,000     $95,000
COGS %              40%         40%          42%
OpEx               $35,000     $35,000      $38,500
```

### Scenario Selector Formula

**In dashboard, use IF to pick which forecast:**

```
=IF(
  ScenarioSelector = "Base Case", BaseRevenue,
  IF(
    ScenarioSelector = "Optimistic", OptimisticRevenue,
    ConservativeRevenue
  )
)
```

**Result:** User picks scenario → all dashboard numbers shift accordingly. Easy "what-if" without changing model.

## Dashboard Guidance (User Instructions)

**Add a help section to dashboard:**

```
┌──────────────────────────────────────────┐
│ HOW TO USE THIS DASHBOARD                │
├──────────────────────────────────────────┤
│ 1. Select date range (top-left)          │
│    Dashboard auto-updates                │
│                                          │
│ 2. Use slicers to filter by account      │
│    All charts and metrics respond        │
│                                          │
│ 3. Click "Refresh Data" if source        │
│    changed (GL imported new month)       │
│                                          │
│ 4. Compare periods using P&P comparison  │
│    See YoY growth and trends             │
│                                          │
│ For questions, contact: CFO@company.com  │
└──────────────────────────────────────────┘
```

## Filter Validation Rules

**Make filters foolproof:**

### Rule 1: Start Date ≤ End Date

**Add validation formula:**

```
If Start Date > End Date:
  Show warning: "Start date must be ≤ End date"
  Use IF logic: =IF(E2 > E3, "⚠ Invalid range", "OK")
```

### Rule 2: Both Dates Must Exist in Data

**Validate against available dates:**

```
If Start Date not in IncomeStatementData[Date]:
  Show error: "No data for that start date"
  Use COUNTIF: =COUNTIF(IncomeStatementData[Date], E2)
```

### Rule 3: Clear Previous Filters When Changing Periods

**If user selects new date range, auto-clear slicer filters:**

```
When E2 changes:
  Clear all slicer selections
  Show: "Slicer filters reset for new period"
```

## Interactive Dashboard Checklist

Before considering dashboard truly interactive:

- [ ] Date range selector works (start ≤ end)
- [ ] All formulas use named ranges (not hard-coded dates)
- [ ] Formulas recalculate when dates change
- [ ] Slicers connected to data table
- [ ] Slicer filtering works (click option → data updates)
- [ ] Charts respond to date filter
- [ ] Period-over-period comparison built
- [ ] Refresh button available and works
- [ ] Help/instructions visible to user
- [ ] No errors (#VALUE!, #NAME?) appear
- [ ] Dashboard updates within 2 seconds of user input

## Real Example: Complete Interactive Dashboard

```
╔════════════════════════════════════════════════════╗
║   INTERACTIVE FINANCIAL DASHBOARD - 2024           ║
╚════════════════════════════════════════════════════╝

Period Selection:
  Start: [1/31/2024 ▼]   End: [3/31/2024 ▼]   [Refresh]

Filters:
┌──────────────┐  ┌──────────────┐
│ SummaryGroup │  │   Account    │
├──────────────┤  ├──────────────┤
│ ☑ Revenue    │  │ ☑ Revenue    │
│ ☑ COGS       │  │ ☑ COGS       │
│ ☑ OpEx       │  │ ☑ Payroll    │
└──────────────┘  │ ☑ Marketing  │
                  │ ☑ Rent       │
                  │ ☑ Software   │
                  └──────────────┘

Key Metrics:
│ Revenue: $315K │ Margin: 60% │ Cash: $75K │

Income Statement (responds to all filters above):
Revenue                 $315,000    100.0%
COGS                   ($126,000)   (40.0%)
Gross Profit            $189,000     60.0%
OpEx                   ($108,000)   (34.3%)
NET INCOME              $ 81,000     25.7%

Charts (interactive):
[Revenue Trend]    [Margin %]    [Cash Flow]

Period-over-Period Comparison:
                    Q1 2024    Q1 2023    Change
Revenue             $315K      $300K      +5.0%
Net Income          $ 81K      $ 75K      +8.0%

[How to Use This Dashboard] ↓
```

## Key Principles

1. **One date range controls all.** User changes start/end, everything updates.
2. **Slicers are optional filters.** Main dashboard works without them.
3. **Validation prevents errors.** Dates must be valid, ranges must be logical.
4. **Speed matters.** Dashboard should update in <2 seconds.
5. **Help text essential.** Users need to know what filters do.

