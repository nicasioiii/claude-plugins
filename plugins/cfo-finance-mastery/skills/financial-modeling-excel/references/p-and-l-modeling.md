---
name: P&L Modeling Architecture & Revenue-COGS-OpEx Structure
description: Build income statement output that displays Drivers tab data cleanly, with margin calculations and driver examples for every line item.
---

# P&L Modeling: Architecture & Driver Examples

## Income Statement Output Sheet Structure

**Create new sheet: "IncomeStatement"**

**Layout:**
```
                                Jan 2024    Feb 2024    Mar 2024    Apr 2024
REVENUE SECTION
  Product Sales               [formula]   [formula]   [formula]   [formula]
  Service Revenue             [formula]   [formula]   [formula]   [formula]
  Other Revenue               [formula]   [formula]   [formula]   [formula]
Total Revenue                 [formula]   [formula]   [formula]   [formula]

COST OF GOODS SOLD
  Product Costs               [formula]   [formula]   [formula]   [formula]
  Fulfillment/Shipping        [formula]   [formula]   [formula]   [formula]
  Direct Labor                [formula]   [formula]   [formula]   [formula]
Total COGS                    [formula]   [formula]   [formula]   [formula]

Gross Profit                  [formula]   [formula]   [formula]   [formula]
Gross Margin %               [formula]   [formula]   [formula]   [formula]

OPERATING EXPENSES
  Payroll & Benefits          [formula]   [formula]   [formula]   [formula]
  Advertising & Marketing     [formula]   [formula]   [formula]   [formula]
  Software & Subscriptions    [formula]   [formula]   [formula]   [formula]
  Facilities & Rent           [formula]   [formula]   [formula]   [formula]
  Travel & Meals              [formula]   [formula]   [formula]   [formula]
  Professional Services       [formula]   [formula]   [formula]   [formula]
  Other Operating Expenses    [formula]   [formula]   [formula]   [formula]
Total Operating Expenses      [formula]   [formula]   [formula]   [formula]

Operating Income (EBIT)       [formula]   [formula]   [formula]   [formula]
Operating Margin %           [formula]   [formula]   [formula]   [formula]

OTHER INCOME & EXPENSE
  Interest Income             [formula]   [formula]   [formula]   [formula]
  Interest Expense            [formula]   [formula]   [formula]   [formula]
  Gain/Loss on Sale           [formula]   [formula]   [formula]   [formula]
Total Other                   [formula]   [formula]   [formula]   [formula]

NET INCOME (Bottom Line)       [formula]   [formula]   [formula]   [formula]
Net Margin %                  [formula]   [formula]   [formula]   [formula]
```

## Revenue Formulas

**All revenue formulas reference Drivers tab:**

**Product Sales:**
```
=Drivers!B2 (where B2 = Product Sales from Drivers)
```

**Service Revenue:**
```
=Drivers!B5 (where B5 = Service Revenue from Drivers)
```

**Total Revenue:**
```
=SUM(B2:B4) (sum all revenue types)
```

**Copy formulas right across months (Jan-Apr):**
1. Select B2:B7 (all revenue rows, all months)
2. Ctrl+C
3. Copy logic: When pasted to column C, B2→C2 automatically

## COGS Formulas (Two Approaches)

### Approach 1: Direct SUMIFS (Pull from Drivers)
```
Product Costs = =Drivers!B7
Fulfillment = =Drivers!B8
Total COGS = =SUM(B11:B13)
```

### Approach 2: Driver-Based (Calculate from assumption)
```
COGS % (input in Drivers): 40%
Total COGS (formula): =Total Revenue * COGS%

Example:
Revenue: $100K
COGS % assumption: 40%
COGS calculation: =$100K * 40% = $40K
```

**Gross Profit:**
```
=Total Revenue - Total COGS
Example: =$100K - $40K = $60K
```

**Gross Margin %:**
```
=Gross Profit / Revenue
Example: =$60K / $100K = 60%
Format as percentage: 60.0%
```

## Operating Expense Formulas

**Every OpEx line item references Drivers:**

**Payroll:**
```
=Drivers!B16
OR (if calculated in Drivers)
=Drivers!Headcount * Drivers!CostPerPerson
Example: =5 people * $4,000 = $20,000
```

**Advertising & Marketing:**
```
=Drivers!B17
OR (if % of revenue)
=Total Revenue * AdSpend%
Example: =$100K * 8% = $8K
```

**Software & Subscriptions:**
```
=Drivers!B18
(Usually fixed monthly; no variation with revenue)
Example: $2,000/month
```

**Facilities & Rent:**
```
=Drivers!B19
(Fixed monthly cost)
Example: $5,000/month
```

**Professional Services (pro-rata annual costs):**
```
=Drivers!B20
Example: $12,000 annual accounting fee / 12 = $1,000/month
```

**Other OpEx:**
```
=Drivers!B21
(Catch-all for miscellaneous)
```

**Total Operating Expenses:**
```
=SUM(B16:B21) (sum all OpEx categories)
```

## Margin & Income Formulas

**Operating Income (EBIT):**
```
=Gross Profit - Total Operating Expenses
Example: =$60K - $38K = $22K
```

**Operating Margin %:**
```
=Operating Income / Revenue
Example: =$22K / $100K = 22%
Format: 22.0%
```

**Interest Expense (if debt):**
```
=Drivers!B25
Example: Monthly debt payment * interest rate
For $100K debt at 5% annual = $5K / 12 = $417/month
```

**Net Income:**
```
=Operating Income + Other Income - Other Expense - Interest Expense - Taxes
(Simplified; may include more line items)
Example: =$22K - $417 (interest) - $4,288 (taxes at 25%) = $17,295
```

**Net Margin %:**
```
=Net Income / Revenue
Example: =$17,295 / $100K = 17.3%
```

## Real Example: E-Commerce P&L

```
                                Jan 2024    Feb 2024    Mar 2024    Apr 2024
REVENUE
  Product Sales               $100,000    $105,000    $110,250    $115,763
  Other Revenue               $    500    $    525    $    551    $    579
Total Revenue                 $100,500    $105,525    $110,801    $116,342

COST OF GOODS SOLD
  Product COGS (40%)          $ 40,000    $ 42,000    $ 44,100    $ 46,305
  Fulfillment (5%)            $  5,000    $  5,250    $  5,513    $  5,788
  Refunds/Chargebacks (2%)    $  2,000    $  2,100    $  2,215    $  2,327
Total COGS                    $ 47,000    $ 49,350    $ 51,828    $ 54,420
Gross Profit                  $ 53,500    $ 56,175    $ 58,973    $ 61,922
Gross Margin %                   53.2%       53.2%       53.2%       53.2%

OPERATING EXPENSES
  Payroll & Benefits (15%)    $ 15,075    $ 15,829    $ 16,620    $ 17,451
  Advertising & Marketing     $  8,000    $  8,500    $  9,000    $  9,500
  Software & Subscriptions    $  3,000    $  3,000    $  3,000    $  3,000
  Facilities                  $  3,000    $  3,000    $  3,000    $  3,000
  Professional Services       $    833    $    833    $    833    $    833
  Other                       $  1,000    $  1,000    $  1,000    $  1,000
Total Operating Expenses      $ 30,908    $ 32,162    $ 33,453    $ 34,784
Operating Income              $ 22,592    $ 24,013    $ 25,520    $ 27,138
Operating Margin %               22.5%       22.7%       23.0%       23.3%

OTHER
  Interest Expense            $   (417)   $   (417)   $   (417)   $   (417)
Net Income (pre-tax)          $ 22,175    $ 23,596    $ 25,103    $ 26,721
Income Tax (25%)              $  5,544    $  5,899    $  6,276    $  6,680
NET INCOME                    $ 16,631    $ 17,697    $ 18,827    $ 20,041
Net Margin %                      16.5%       16.8%       17.0%       17.2%
```

## Key Modeling Rules

1. **All revenue/expense formulas reference Drivers** (never hardcoded amounts)
2. **Totals use SUM formulas** (not SUMIFS; SUMIFS only in Drivers)
3. **Percentages calculated from P&L rows** (not directly from Drivers)
4. **Consistent column locking:** =Drivers!B2 copies to =Drivers!C2 (column float, row locked)
5. **Margins = category / revenue** (margin % = profitability of that category)
6. **Total OpEx = SUM of categories** (not a SUMIFS; sum the line items)
7. **Copy formulas right:** Select one column, copy, paste to adjacent columns
8. **Format margins as percentage:** Right-click → Format → Percentage → 0.0%

## Testing & Validation

**Before considering P&L "complete":**

1. **Manually calculate one month's Net Income** (add it up yourself)
2. **Compare to P&L formula result** (should match)
3. **Change one Drivers assumption** (increase revenue by $10K)
4. **Verify P&L updates automatically** (if COGS is % of revenue, COGS and Net Income should both increase)
5. **Check margin percentages:** (Gross margin should stay constant if COGS % is assumption-driven)

**If anything doesn't update or margins are wrong, formula is hardcoded or broken. Find and fix before using model.**

