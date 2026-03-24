---
name: Cash Flow Statement & Operating/Investing/Financing Mechanics
description: Build cash flow statement from P&L and balance sheet changes, including working capital adjustments and three-section organization.
---

# Cash Flow Statement & Mechanics

## Cash Flow Output Structure

**Create sheet: "CashFlow"**

```
                                Jan 2024    Feb 2024    Mar 2024    Apr 2024
OPERATING ACTIVITIES
  Net Income                    [P&L]       [P&L]       [P&L]       [P&L]
  Adjustments to Net Income:
    + Depreciation              [formula]   [formula]   [formula]   [formula]
    + Amortization              [formula]   [formula]   [formula]   [formula]
  Changes in Working Capital:
    - Increase in AR            [formula]   [formula]   [formula]   [formula]
    - Increase in Inventory     [formula]   [formula]   [formula]   [formula]
    + Increase in AP            [formula]   [formula]   [formula]   [formula]
    + Increase in Accrued Exp   [formula]   [formula]   [formula]   [formula]
Net Operating Cash Flow         [formula]   [formula]   [formula]   [formula]

INVESTING ACTIVITIES
  - Equipment Purchases         [formula]   [formula]   [formula]   [formula]
  + Equipment Sales             [formula]   [formula]   [formula]   [formula]
Net Investing Cash Flow         [formula]   [formula]   [formula]   [formula]

FINANCING ACTIVITIES
  + Debt Increases              [formula]   [formula]   [formula]   [formula]
  - Debt Repayment              [formula]   [formula]   [formula]   [formula]
  + Equity Contributions        [formula]   [formula]   [formula]   [formula]
  - Owner Draws                 [formula]   [formula]   [formula]   [formula]
Net Financing Cash Flow         [formula]   [formula]   [formula]   [formula]

NET CHANGE IN CASH              [formula]   [formula]   [formula]   [formula]
Beginning Cash                  [formula]   [formula]   [formula]   [formula]
Ending Cash                     [formula]   [formula]   [formula]   [formula]
```

## Operating Activities

**Start with Net Income (from P&L):**
```
=IncomeStatement!B11 (Net Income for that month)
```

**Add back non-cash expenses:**
```
Depreciation: =Drivers!B8 (monthly depreciation)
Amortization: =Drivers!B9 (monthly amortization, if applicable)
Stock-based Comp: =Drivers!B10 (if applicable)

Example:
Net Income: $20,000
+ Depreciation: $1,000
= $21,000 (before working capital adjustments)
```

**Working capital changes (KEY COMPLEXITY):**

**Accounts Receivable increase = cash outflow:**
```
Formula: -(Current AR - Prior AR)
Example: If AR increased from $100K to $120K:
  Change = -($120K - $100K) = -$20,000 (cash outflow; customers owe more)
```

**Accounts Receivable decrease = cash inflow:**
```
Example: If AR decreased from $120K to $100K:
  Change = -($100K - $120K) = +$20,000 (cash inflow; collected from customers)
```

**Inventory increase = cash outflow:**
```
Formula: -(Current Inv - Prior Inv)
Example: If Inventory increased from $50K to $65K:
  Change = -($65K - $50K) = -$15,000 (cash outflow; bought more inventory)
```

**Accounts Payable increase = cash inflow:**
```
Formula: (Current AP - Prior AP)
Example: If AP increased from $40K to $50K:
  Change = ($50K - $40K) = +$10,000 (cash inflow; delayed paying vendors)
```

**Accrued Expenses increase = cash inflow:**
```
Formula: (Current Accrued - Prior Accrued)
Example: If Accrued Expenses increased from $5K to $8K:
  Change = ($8K - $5K) = +$3,000 (cash inflow; owe more, haven't paid)
```

**Deferred Revenue increase = cash inflow:**
```
Example: Customer prepaid $10,000 for future service:
  Deferred Revenue increased by $10,000
  Cash effect: +$10,000 (cash already received)
```

**Complete operating cash flow example:**
```
Net Income                          $20,000
+ Depreciation                      $ 1,000
= Adjusted Net Income              $21,000

Changes in Working Capital:
- Increase in AR (120K-100K)        ($20,000)
- Increase in Inventory (65K-50K)   ($15,000)
+ Increase in AP (50K-40K)          $ 10,000
+ Increase in Accrued (8K-5K)       $  3,000
= Change in Working Capital        ($22,000)

Net Operating Cash Flow            ($1,000)

Result: Despite $20K profit, operating CF is negative due to AR/Inventory growth
and unchanged AP/Accrued relative to expenses. Working capital consumed cash.
```

## Investing Activities

**Equipment Purchases (CapEx):**
```
=Drivers!B12 (monthly equipment budget or actual purchases)
Recorded as negative (cash outflow)
Example: -$5,000 (equipment purchased this month)
```

**Equipment Sales:**
```
=Drivers!B13 (sale of old equipment)
Recorded as positive (cash inflow)
Example: +$2,000 (sold old furniture)
```

**Formula for Investing CF:**
```
=Equipment Purchases (negative) + Equipment Sales (positive)
Example: (-$5,000) + $2,000 = -$3,000
```

**Interpretation:**
- Negative: Company investing in growth (buying assets)
- Positive: Company harvesting (selling assets, not reinvesting)
- Zero: Maintenance mode (replacing equipment only)

## Financing Activities

**Debt Increases:**
```
=Drivers!B14 (new borrowing)
Recorded as positive (cash inflow)
Example: +$25,000 (new business line of credit)
```

**Debt Repayment (Principal only; not interest):**
```
=Drivers!B15 (loan payments)
Recorded as negative (cash outflow)
Example: -$2,000 (monthly loan repayment)
```

**Equity Contributions:**
```
=Drivers!B16 (owner or investor capital injection)
Recorded as positive (cash inflow)
Example: +$50,000 (owner injects capital)
```

**Owner Draws/Dividends:**
```
=Drivers!B17 (owner extraction of profit)
Recorded as negative (cash outflow)
Example: -$5,000 (owner draws salary above W-2)
```

**Formula for Financing CF:**
```
=Debt Increases - Debt Repayment + Equity Contributions - Owner Draws
Example: $25,000 - $2,000 + $0 - $5,000 = $18,000
```

## Net Change & Ending Cash

**Net Change in Cash:**
```
=Operating CF + Investing CF + Financing CF
Example: ($1,000) + ($3,000) + $18,000 = $14,000
```

**Cash Balance Reconciliation:**
```
Beginning Cash (prior month)       $40,000
+ Operating CF                     ($1,000)
+ Investing CF                     ($3,000)
+ Financing CF                     $18,000
= Ending Cash (this month)         $54,000
```

**Validation:**
```
Ending Cash from CF statement = Ending Cash on Balance Sheet
If they don't match, formula error in CF. Find it.
```

## Real Example: 3-Month Cash Flow

```
                            Jan 2024    Feb 2024    Mar 2024
OPERATING
Net Income                  $15,000     $18,000     $21,000
+ Depreciation              $ 1,000     $ 1,000     $ 1,000
- Change in AR (100→110)    ($10,000)   0           0
- Change in Inv (50→55)     ($ 5,000)   0           0
+ Change in AP (40→42)      $ 2,000     0           0
Op CF                       $ 3,000     $19,000     $22,000

INVESTING
- CapEx                     ($ 5,000)   0           ($ 3,000)
Inv CF                      ($ 5,000)   0           ($ 3,000)

FINANCING
- Debt Repay                ($ 2,000)   ($ 2,000)   ($ 2,000)
- Owner Draw                ($ 5,000)   0           0
Fin CF                      ($ 7,000)   ($ 2,000)   ($ 2,000)

Net Change                  ($ 9,000)   $17,000     $17,000
Beginning Cash              $50,000     $41,000     $58,000
Ending Cash                 $41,000     $58,000     $75,000
```

**Interpretation:**
- January: Cash declined despite positive net income (working capital consumed $15K; CapEx $5K; debt repay+draw $7K)
- February: Cash grew strongly (operating CF $19K exceeded debt/draw $2K)
- March: Continued growth (operating CF $22K exceeded CapEx+debt $5K)

## Cash Conversion Cycle Visualization in Cash Flow

**The working capital cycle shows in Operating CF section:**

```
Inventory Increase (Jan):    ($5,000)  ← Cash outflow: inventory purchased
AR Increase (Jan):           ($10,000) ← Cash outflow: revenue on credit, not yet collected
AP Increase (Jan):           $ 2,000   ← Cash inflow: delayed paying vendors
Net WC drain:                ($13,000) ← Despite $15K net income, CF is only $3K

February (stable):
No major WC changes
Operating CF = Net Income (approximately)

Result: Short-term cash tight (January) despite profitability.
Solution: Either extend AP terms, accelerate AR collections, or reduce inventory.
```

## Key Rules

1. **Operating CF formula**: NI +/- WC changes
2. **Investing CF**: CapEx (negative) ± Asset sales (positive)
3. **Financing CF**: Debt changes ± Equity changes - Owner draws
4. **WC changes**: If balance sheet account increases, it's cash outflow (AR, Inv). If liability increases, it's cash inflow (AP, Accrued).
5. **Validation**: Ending CF Cash = Ending BS Cash (MUST match)
6. **Negative Operating CF despite profit**: Working capital problem (AR growing faster than revenue, inventory building, etc.)

