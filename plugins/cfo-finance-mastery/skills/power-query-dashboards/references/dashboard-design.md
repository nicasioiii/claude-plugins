---
name: Dashboard Design, Formatting & Visual Hierarchy
description: Create professional financial dashboards with effective visual hierarchy, color schemes, and user guidance.
---

# Dashboard Design & Professional Formatting

## Dashboard Sheet Structure

**Create new sheet: "Dashboard"**

**Layout (left to right, top to bottom):**

```
┌─────────────────────────────────────────────────────────┐
│ DASHBOARD TITLE & CONTROLS                              │
│ Period: [Date Range Selector]  [Refresh Button]         │
├─────────────────────────────────────────────────────────┤
│ KEY METRICS ROW (4-6 largest numbers)                   │
│ Revenue: $315K | Margin: 60% | Cash: $75K | DSO: 45    │
├─────────────────────────────────────────────────────────┤
│ INCOME STATEMENT                                         │
│ Revenue      $315,000    100.0%                         │
│ COGS        ($126,000)   (40.0%)                        │
│ Gross Profit $189,000     60.0%                         │
│ OpEx        ($108,000)   (34.3%)                        │
│ Net Income   $ 81,000     25.7%                         │
├─────────────────────────────────────────────────────────┤
│ BALANCE SHEET (Side-by-side)                            │
│ Assets:               │ Liabilities & Equity:           │
│ Cash      $75,000     │ AP         $35,000              │
│ AR        $95,000     │ Debt       $50,000              │
│ Inventory $60,000     │ Equity    $145,000              │
│ Equipment $30,000     │                                 │
│ Total    $260,000     │ Total    $230,000               │
├─────────────────────────────────────────────────────────┤
│ CHARTS (2-4 visuals)                                    │
│ [Revenue Trend]   [Margin %]   [Cash Position]          │
└─────────────────────────────────────────────────────────┘
```

## Color Scheme & Formatting

### Header Row Color

**Use dark color for readability:**

```
Background:  Dark Blue (#1F4E78) or Dark Gray (#333333)
Text:        White (#FFFFFF)
Font:        Bold, Arial, 14pt
Example:
┌────────────────────────────────────┐
│ FINANCIAL DASHBOARD - Q1 2024      │
└────────────────────────────────────┘
```

### Section Headers

**Secondary headers in medium color:**

```
Background:  Light Blue (#D9E1F2) or Light Gray (#EFEFEF)
Text:        Dark Gray (#333333)
Font:        Bold, Arial, 12pt
Example:
┌────────────────────────────────────┐
│ INCOME STATEMENT                   │
└────────────────────────────────────┘
```

### Data Cells

**Clean, simple formatting:**

```
Background:  White (#FFFFFF) for odd rows
             Light Gray (#F2F2F2) for even rows (alternating)
Text:        Dark Gray (#666666)
Font:        Regular, Arial, 11pt
Number Format: #,##0 (no decimal places for whole dollars)
```

### Positive vs. Negative Numbers

```
Positive (Revenue, Income):
  Text Color: Dark Blue (#1F4E78)
  Format: $100,000

Negative (Expenses, Losses):
  Text Color: Red (#C00000)
  Format: ($50,000)  [with parentheses, not minus sign]
```

### Percentage Column

```
Format: 0.0% (one decimal place)
Example:
  Revenue:  100.0%
  COGS:      40.0%
  Margin:    60.0%
```

## Key Metrics (KPI) Box

**Top of dashboard shows 4-6 largest numbers at glance:**

```
┌──────────────────────────────────────────────────────┐
│ KEY METRICS (Period: Jan 1 - Mar 31, 2024)           │
├──────────────────────────────────────────────────────┤
│ Total Revenue  │ Gross Profit  │ Net Income          │
│   $315,000     │   $189,000    │   $81,000           │
│                │               │                     │
│ Gross Margin   │ Operating M.  │ Cash on Hand        │
│    60.0%       │    25.7%      │   $75,000           │
└──────────────────────────────────────────────────────┘
```

**Formatting:**
- Large font (18pt) for numbers
- Bold for emphasis
- Color code: green for profitable metrics, red for concerns
- White background, dark text

## Income Statement Formatting

```
                        Amount      % of Revenue
Revenue                 $315,000    100.0%        ← Bold, dark color
  Prod Sales            $310,000     98.4%
  Service Revenue       $  5,000      1.6%
COGS                   ($126,000)   (40.0%)        ← Parentheses for negative
Gross Profit            $189,000     60.0%        ← Bold, highlight row

Operating Expenses:
  Payroll               ($ 60,000)   (19.0%)
  Marketing             ($ 25,500)    (8.1%)
  Software              ($  9,000)    (2.9%)
  Rent                  ($  9,000)    (2.9%)
  Other                 ($  4,500)    (1.4%)
Total OpEx             ($108,000)   (34.3%)       ← Bold, sum row

Net Income              $ 81,000     25.7%        ← Bold, blue text, highlight
```

**Key formatting:**
- Revenue line bold, dark blue
- Major subtotals (Gross Profit, Total OpEx, Net Income) bold with shading
- % of Revenue aligned right, one decimal
- Negative numbers in parentheses, red text
- Blank rows between sections for visual breathing room

## Balance Sheet Formatting (Side-by-Side)

```
ASSETS                          LIABILITIES & EQUITY
─────────────────────────────   ─────────────────────────────
Cash              $75,000       Accounts Payable    $35,000
AR                $95,000       Accrued Expenses    $12,000
Inventory         $60,000       Short-term Debt    $15,000
Prepaid           $ 5,000       Long-term Debt     $35,000
─────────────────────────────   ─────────────────────────────
Current Assets   $235,000       Total Liabilities   $97,000

Equipment at Cost $100,000      Common Stock        $80,000
Accum Depr        ($40,000)     Retained Earnings  $118,000
Equipment, Net    $ 60,000      ─────────────────────────────
─────────────────────────────   Total Equity       $198,000
TOTAL ASSETS     $295,000
                               TOTAL LIAB + EQ    $295,000
```

**Key formatting:**
- Left column = Assets, Right column = Liabilities + Equity
- Both columns should total the same (balance check)
- Bold subtotals (Current Assets, Total Liabilities, Total Equity)
- Use light gray shading for subtotal rows
- "TOTAL ASSETS" bold, larger font, blue background (stand out)

## Cash Flow Formatting

```
OPERATING ACTIVITIES
Net Income                                $81,000
Adjustments:
  + Depreciation                          $ 1,500
  + Amortization                          $   500
Changes in Working Capital:
  - Increase in AR (120K - 100K)         ($20,000)
  - Increase in Inventory (65K - 50K)    ($15,000)
  + Increase in AP (50K - 40K)           $ 10,000
  ────────────────────────────────────────────────
NET OPERATING CASH FLOW                   $58,000  ← Bold, highlight

INVESTING ACTIVITIES
- Equipment Purchases                    ($15,000)
+ Equipment Sales                        $  2,000
  ────────────────────────────────────────────────
NET INVESTING CASH FLOW                 ($13,000)  ← Bold, red for negative

FINANCING ACTIVITIES
+ Debt Increases                         $ 25,000
- Debt Repayment                        ($ 2,000)
- Owner Draws                           ($ 5,000)
  ────────────────────────────────────────────────
NET FINANCING CASH FLOW                  $18,000   ← Bold

  ════════════════════════════════════════════════
NET CHANGE IN CASH                       $63,000   ← Bold, largest font
Beginning Cash                           $12,000
ENDING CASH                              $75,000   ← Bold, blue
  ════════════════════════════════════════════════
```

## Charts & Visualizations

### Revenue Trend (Line Chart)

```
Title: "Revenue Trend (12 Months)"
X-axis: Month (Jan, Feb, Mar, ...)
Y-axis: Revenue ($)
Line: Blue, 2pt thickness
Data: Point markers at each month
Format: No gridlines (clean look)
```

**When to use:** Show growth trajectory, seasonality patterns, declining/accelerating revenue.

### Margin % Trend (Combination Chart)

```
Title: "Profitability Metrics"
X-axis: Month
Primary Y-axis: Gross Margin % (bar chart, light blue)
Secondary Y-axis: Operating Margin % (line chart, dark blue)
Format: Show target margin line as dashed reference
```

**When to use:** Show margin compression/expansion, operating efficiency trends.

### Balance Sheet Composition (Pie Chart)

```
Title: "Asset Composition"
Segments: Current Assets (70%), Fixed Assets (20%), Other (10%)
Colors: Blue shades (darker = larger segment)
Format: Show value and % for each segment
```

**When to use:** Show where company money is deployed (working capital vs. fixed assets).

### Cash Position (Waterfall Chart)

```
Title: "Cash Flow Waterfall (Jan - Mar 2024)"
Bar 1: Beginning Cash ($12K) - gray
Bar 2: Operating CF ($58K) - green
Bar 3: Investing CF (-$13K) - red
Bar 4: Financing CF ($18K) - blue
Bar 5: Ending Cash ($75K) - dark gray
Connection: Lines showing flows between bars
```

**When to use:** Show how cash balance changed month-to-month, clearly showing which activities added/drained cash.

## Date Range Selector

**Place at top of dashboard for user filtering:**

```
Period: [Select Start Date ▼]  to  [Select End Date ▼]
        ┌─────────────────────────────────┐
        │ 1/31/2024                       │
        │ 2/29/2024                       │
        │ 3/31/2024  ← User clicks        │
        │ 4/30/2024                       │
        └─────────────────────────────────┘
```

**Implementation:**
- Cell E2: "Start Date" label, E3: dropdown (Data Validation)
- Cell F2: "End Date" label, F3: dropdown
- Both dropdowns reference IncomeStatementData[Date] column
- All formulas use named ranges (DashboardStartDate, DashboardEndDate)

## Professional Formatting Checklist

Before considering dashboard complete:

- [ ] **Colors consistent** (one color scheme, not rainbow)
- [ ] **Fonts consistent** (Arial or Calibri throughout, not mixed)
- [ ] **Numbers right-aligned** (easier to scan vertically)
- [ ] **Negative numbers in parentheses** (not minus sign)
- [ ] **Percentages one decimal** (60.0%, not 60.00% or 0.60)
- [ ] **Thousands with commas** ($100,000 not 100000)
- [ ] **No cents on whole dollars** ($100,000 not $100,000.00)
- [ ] **Column widths adjusted** (no "###" overflow; text fits)
- [ ] **Row heights consistent** (data rows same height)
- [ ] **Alternating row colors** (gray/white for readability)
- [ ] **Section headers bold** (clear visual breaks)
- [ ] **White space used** (blank rows between sections)
- [ ] **Subtotals bold and shaded** (stand out from detail)
- [ ] **Charts have clear titles** (user knows what they're looking at)
- [ ] **Axis labels readable** (not rotated 90°, not overlapping)

## Real Dashboard Example

```
╔════════════════════════════════════════════════════════╗
║           MANAGEMENT DASHBOARD - Q1 2024               ║
║  Period: Jan 1 - Mar 31   [Refresh: Last updated 3/31] ║
╚════════════════════════════════════════════════════════╝

┌──────────────────────────────────────────────────────┐
│ QUARTERLY HIGHLIGHTS                                 │
├────────────┬──────────┬──────────┬──────────────────┤
│ Revenue    │ Margin   │ Cash     │ Days Sales Out   │
│ $315K      │ 60.0%    │ $75K     │ 45 days          │
└────────────┴──────────┴──────────┴──────────────────┘

┌──────────────────────────────────────────────────────┐
│ INCOME STATEMENT (Jan 1 - Mar 31, 2024)              │
├──────────────────────────────────┬──────┬────────────┤
│ Revenue                          │$315K │   100.0%   │
│   Product Sales    $310K         │      │    98.4%   │
│   Service Revenue  $  5K         │      │     1.6%   │
├──────────────────────────────────┼──────┼────────────┤
│ COGS                            │$126K │    40.0%   │
├──────────────────────────────────┼──────┼────────────┤
│ GROSS PROFIT                    │$189K │    60.0%   │
├──────────────────────────────────┼──────┼────────────┤
│ Operating Expenses               │$108K │    34.3%   │
│   Payroll         $60K           │      │    19.0%   │
│   Marketing       $25.5K         │      │     8.1%   │
│   Software        $ 9K           │      │     2.9%   │
│   Rent            $ 9K           │      │     2.9%   │
│   Other           $ 4.5K         │      │     1.4%   │
├──────────────────────────────────┼──────┼────────────┤
│ OPERATING INCOME                │$ 81K │    25.7%   │
├──────────────────────────────────┼──────┼────────────┤
│ NET INCOME                       │$ 81K │    25.7%   │
└──────────────────────────────────┴──────┴────────────┘

┌─────────────────────────────────────────────────────┐
│ TRENDS & METRICS                                    │
│ [Revenue Growth]    [Margin %]    [Cash Forecast]   │
│ (3 line charts showing Jan-Feb-Mar trends)          │
└─────────────────────────────────────────────────────┘
```

## Key Principles

1. **Hierarchy first.** Largest numbers at top, details below.
2. **Color with purpose.** Not decorative; highlights key insights.
3. **White space matters.** Breathing room makes dashboards readable.
4. **Consistent formatting.** Same treatment for same data types.
5. **User-focused.** CFO gets what they need in 10 seconds.

