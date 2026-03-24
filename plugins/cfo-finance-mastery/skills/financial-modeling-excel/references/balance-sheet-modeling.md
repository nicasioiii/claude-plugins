---
name: Balance Sheet Modeling & Account Drivers
description: Build balance sheet output with asset, liability, and equity sections, including depreciation scheduling and working capital drivers.
---

# Balance Sheet Modeling & Account Drivers

## Balance Sheet Output Structure

**Create sheet: "BalanceSheet"**

```
                                Jan 31      Feb 28      Mar 31      Apr 30
ASSETS
Current Assets
  Cash                          [formula]   [formula]   [formula]   [formula]
  Accounts Receivable           [formula]   [formula]   [formula]   [formula]
  Inventory                     [formula]   [formula]   [formula]   [formula]
  Prepaid Expenses              [formula]   [formula]   [formula]   [formula]
Total Current Assets            [formula]   [formula]   [formula]   [formula]

Fixed Assets
  Equipment at Cost             [formula]   [formula]   [formula]   [formula]
  Accumulated Depreciation      [formula]   [formula]   [formula]   [formula]
  Equipment, Net                [formula]   [formula]   [formula]   [formula]
  Furniture at Cost             [formula]   [formula]   [formula]   [formula]
  Accumulated Depreciation      [formula]   [formula]   [formula]   [formula]
  Furniture, Net                [formula]   [formula]   [formula]   [formula]
Total Fixed Assets, Net         [formula]   [formula]   [formula]   [formula]

Other Assets
  Intangibles/Goodwill          [formula]   [formula]   [formula]   [formula]
Total Assets                    [formula]   [formula]   [formula]   [formula]

LIABILITIES & EQUITY
Current Liabilities
  Accounts Payable              [formula]   [formula]   [formula]   [formula]
  Accrued Expenses              [formula]   [formula]   [formula]   [formula]
  Short-term Debt               [formula]   [formula]   [formula]   [formula]
  Deferred Revenue              [formula]   [formula]   [formula]   [formula]
Total Current Liabilities       [formula]   [formula]   [formula]   [formula]

Long-term Liabilities
  Long-term Debt                [formula]   [formula]   [formula]   [formula]
Total Liabilities               [formula]   [formula]   [formula]   [formula]

Stockholders' Equity
  Common Stock / Paid-in        [formula]   [formula]   [formula]   [formula]
  Retained Earnings             [formula]   [formula]   [formula]   [formula]
Total Equity                    [formula]   [formula]   [formula]   [formula]

Total Liabilities + Equity      [formula]   [formula]   [formula]   [formula]

CHECK (Assets - Liab - Equity)  [formula]   [formula]   [formula]   [formula]
```

## Asset Formulas

**Cash:**
```
=Drivers!B2 (ending cash from Drivers)
OR (calculated from Cash Flow Statement)
=Prior Month Cash + Operating CF + Investing CF + Financing CF
```

**Accounts Receivable (AR):**
```
Approach 1 (Direct): =Drivers!B4
Approach 2 (Calculated from DSO): =Monthly Revenue / 30 * DSO
  Example: If revenue = $100K/month and DSO = 45 days:
  AR = $100K / 30 * 45 = $150,000
```

**Inventory:**
```
Approach 1 (Direct): =Drivers!B5
Approach 2 (Calculated from DIO): =Monthly COGS / 30 * DIO
  Example: If COGS = $40K/month and DIO = 30 days:
  Inventory = $40K / 30 * 30 = $40,000
```

**Equipment:**
```
Equipment Cost = =Drivers!B7 (original purchase price)
Accumulated Depreciation = =Drivers!B8 (running total of depreciation charges)
Equipment Net = =Equipment Cost - Accumulated Depreciation
  Example: Purchased equipment for $100,000 five years ago (5-year life)
  Equipment Cost: $100,000
  Accumulated Depreciation: $100,000 (fully depreciated)
  Equipment Net: $0 (fully expensed)
```

**Depreciation Calculation:**
```
Monthly Depreciation = Equipment Cost / Useful Life / 12
  Example: $100,000 / 5 years / 12 months = $1,667/month

Accumulated Depreciation = Prior Month Accumulated + Current Month Depreciation
  Example: Month 1 = $0 + $1,667 = $1,667
  Month 2 = $1,667 + $1,667 = $3,333
  ... continues for 60 months until fully depreciated
```

## Liability Formulas

**Accounts Payable (AP):**
```
Approach 1 (Direct): =Drivers!B12
Approach 2 (Calculated from DPO): =Monthly COGS / 30 * DPO
  Example: If COGS = $40K/month and DPO = 30 days:
  AP = $40K / 30 * 30 = $40,000
```

**Accrued Expenses:**
```
=Drivers!B13
(Includes accrued payroll, accrued taxes, accrued interest)
Typical: One month of expenses not yet paid
```

**Short-term Debt (current portion of long-term loan):**
```
=Drivers!B14
(Principal payment due within 12 months)
Example: $100,000 loan, 5-year term = $20,000/year = $1,667/month short-term
```

**Long-term Debt:**
```
=Drivers!B15
(Principal payment due beyond 12 months)
Example: $100,000 loan, year 1 payment = $20,000, so $80,000 goes to long-term
```

## Equity Formulas

**Common Stock / Paid-in Capital:**
```
=Drivers!B18
(Historical contribution; doesn't change unless new capital injection)
Example: Owner contributed $50,000 cash at start = $50,000 stock/paid-in
```

**Retained Earnings Bridge (Critical Link to P&L)**

Current Retained Earnings = Prior Retained Earnings + Net Income - Owner Draws/Dividends

Formula in model:
=Prior_Period_RE + P&L_Net_Income - Draws_This_Period

This is THE link between your P&L and balance sheet. If this formula is wrong, your balance sheet won't balance and your model is broken.

Error check: Total Assets must equal Total Liabilities + Total Equity. If not balanced, the retained earnings bridge is usually the culprit.

**Example:**
  Prior month RE: $100,000
  Current month NI: $10,000
  Owner draw: $5,000
  Current month RE: $100,000 + $10,000 - $5,000 = $105,000

**Formula in spreadsheet:**
```
=Prior Month Equity Cell + IncomeStatement!Current Month NI - Distributions
Example: =A25 + IncomeStatement!B11 - Drivers!B20
```

## Working Capital Management (Optimized)

**Three-part optimization:**

**1. Accounts Receivable (DSO optimization):**
```
Current: DSO = 45 days
Target: DSO = 30 days
Current AR: $150,000 (assumes $100K/month revenue)
Target AR: $100,000
CASH FREED: $50,000

Implementation: Improve collections process, call overdue accounts
```

**2. Accounts Payable (DPO optimization):**
```
Current: DPO = 30 days
Target: DPO = 45 days (negotiate with vendors)
Current AP: $40,000 (assumes $40K/month COGS)
Target AP: $60,000
CASH FREED: $20,000

Implementation: Negotiate Net 45 terms with suppliers
```

**3. Inventory (DIO optimization):**
```
Current: DIO = 40 days
Target: DIO = 25 days (better forecasting)
Current Inventory: $50,000 (assumes $30K/month COGS)
Target Inventory: $31,250
CASH FREED: $18,750

Implementation: Improve demand forecasting, reduce overstock
```

**Total working capital freed: $88,750 (=$50K + $20K + $18.75K)**

**In Drivers, model these optimizations:**
```
                    Jan     Feb     Mar     Apr
DSO (current)       45      45      45      30 (improvement target)
DSO (gradual)       45      42      36      30 (phased improvement)
AR Balance          150K    147K    135K    100K (declines as DSO improves)
```

## Depreciation Schedule Tab (Optional but Recommended)

**Create separate "DepreciationSchedule" tab for equipment tracking:**

```
Asset               | Cost     | Life  | Start  | End    | Annual  | Month
Computer            | $5,000   | 3yr   | 1/2024 | 12/2026| $1,667  | $139
Furniture           | $10,000  | 5yr   | 1/2024 | 12/2028| $2,000  | $167
Equipment           | $50,000  | 7yr   | 1/2024 | 12/2030| $7,143  | $595
---
Total Monthly Depreciation:                                              $901
```

**This schedule makes it easy to add assets over time and track depreciation automatically.**

## Equity Transactions to Model

- Owner investments (increases equity)
- Owner draws/distributions (decreases equity)
- Stock issuance (if applicable)
- Retained earnings (auto-calculated from P&L)

In drivers tab, create input rows for: monthly draws, planned investments

## Balance Sheet Validation

**Critical check: Assets = Liabilities + Equity**

**In your ErrorCheck tab, create:**
```
Total Assets                    [from BalanceSheet]
Total Liabilities               [from BalanceSheet]
Total Equity                    [from BalanceSheet]
Check (Assets - Liab - Equity): Should = 0

If not zero, balance sheet doesn't balance. Find the error.
```

**Common errors:**
- Accumulated depreciation positive instead of negative (should reduce assets)
- Retained earnings not updated for current month net income
- Asset purchase not matched to corresponding liability or equity reduction

---

## Working Capital Mechanics: Detailed Deep Dive

Working capital is the engine of business cash flow. Understanding the mechanics is critical for forecasting and optimization.

### The Working Capital Triangle

Three interconnected accounts drive working capital:

**1. Accounts Receivable (AR) — How fast you collect cash from customers**

**Days Sales Outstanding (DSO):**
```
Formula: AR / (Daily Revenue) = Days to collect

Example:
- Monthly revenue: $100,000
- Daily revenue: $100,000 / 30 = $3,333/day
- Current AR: $150,000
- Current DSO: $150,000 / $3,333 = 45 days

Interpretation: Customers owe you 45 days of sales on average.
Takes 45 days to collect typical invoice.
```

**DSO Improvement Impact (Concrete Example):**
```
Current State:
  Monthly revenue: $100,000
  DSO: 45 days
  AR: $150,000

Target: Reduce DSO to 30 days
  AR target: ($100,000 / 30) × 30 = $100,000
  Cash freed: $150,000 - $100,000 = $50,000

Implementation: Better collections process, invoice on time, follow up on overdue accounts
```

**2. Accounts Payable (AP) — How long you take to pay suppliers**

**Days Payable Outstanding (DPO):**
```
Formula: AP / (Daily COGS) = Days to pay suppliers

Example:
- Monthly COGS: $40,000
- Daily COGS: $40,000 / 30 = $1,333/day
- Current AP: $40,000
- Current DPO: $40,000 / $1,333 = 30 days

Interpretation: You typically owe suppliers 30 days of COGS.
```

**DPO Improvement Impact:**
```
Current State:
  Monthly COGS: $40,000
  DPO: 30 days
  AP: $40,000

Target: Negotiate Net 45 terms (vs. Net 30)
  AP target: ($40,000 / 30) × 45 = $60,000
  Cash retained: $60,000 - $40,000 = $20,000

Implementation: Contact top 5 suppliers, negotiate terms, offer volume commitments
```

**3. Inventory (DIO) — How long inventory sits before being sold**

**Days Inventory Outstanding (DIO):**
```
Formula: Inventory / (Daily COGS) = Days inventory sits

Example:
- Monthly COGS: $40,000
- Daily COGS: $40,000 / 30 = $1,333/day
- Current Inventory: $50,000
- Current DIO: $50,000 / $1,333 = 37.5 days

Interpretation: Average product sits 37.5 days before selling.
```

**DIO Improvement Impact:**
```
Current State:
  Monthly COGS: $40,000
  DIO: 37.5 days
  Inventory: $50,000

Target: Improve demand forecasting, reduce to 25 days
  Inventory target: ($40,000 / 30) × 25 = $33,333
  Cash freed: $50,000 - $33,333 = $16,667

Implementation: Better demand planning, reduce safety stock, faster turnover
```

### Cash Conversion Cycle: The Integration

**Formula:**
```
CCC = DSO + DIO - DPO

Example:
- DSO: 45 days (collecting from customers)
- DIO: 37.5 days (inventory sitting)
- DPO: 30 days (paying suppliers)
- CCC: 45 + 37.5 - 30 = 52.5 days

Interpretation: Need 52.5 days of working capital to fund operations.
Every $1 in revenue ties up capital for 52.5 days.
```

**Cash Impact (Real Dollar Calculation):**
```
Daily revenue: $100,000 / 30 = $3,333/day
Capital tied up: 52.5 days × $3,333/day = $175,000

If CCC improves to 30 days:
  New capital tied up: 30 × $3,333 = $100,000
  Freed cash: $175,000 - $100,000 = $75,000

This $75,000 can be used for debt reduction, growth, or distributions.
```

### Working Capital Bridge in the Balance Sheet

**Example: Month-to-Month Transition**

```
                        Jan 31          Feb 28          Change
Accounts Receivable     $150,000        $140,000        ($10,000)
Inventory              $50,000         $48,000         ($2,000)
Accounts Payable       $40,000         $42,000         $2,000

Net Working Capital Change:
AR decrease:           $10,000 (cash inflow)
Inventory decrease:    $2,000 (cash inflow)
AP increase:           $2,000 (cash inflow)
Total WC inflow:       $14,000 ← appears as positive CF in Operating Activities
```

**Cash Flow Statement Impact:**
```
Cash Flow from Operating Activities:
  Beginning Cash: $80,000
  + Operating Income: $25,000
  + Depreciation (non-cash): $2,000
  + Decrease in AR (cash collected): $10,000
  + Decrease in Inventory (cash freed): $2,000
  + Increase in AP (delayed payment): $2,000
  = Total Operating CF: $41,000
  Ending Cash: $80,000 + $41,000 = $121,000
```

---

## Retained Earnings Bridge: The P&L to Balance Sheet Link

This formula is THE critical link between your income statement and balance sheet. If wrong, your balance sheet won't balance.

### The Formula (In Plain English)

```
Current Retained Earnings = Prior Retained Earnings + Current Period Net Income - Owner Distributions
```

### The Formula (In Excel)

```
=Prior_Period_RE_Cell + P&L!CurrentMonth_NetIncome - Drivers!CurrentMonth_Draws

Example formula (for February):
=A25 + IncomeStatement!B11 - Drivers!B20
```

### Why This Matters

**Without correct retained earnings bridge:**
```
P&L shows: Net Income = $10,000
BS shows: Equity increased by $5,000
Imbalance of $5,000 (where did it go?)
User loses confidence in model.
```

**With correct bridge:**
```
P&L shows: Net Income = $10,000
Owner draws = $5,000
Retained Earnings increases by $5,000 ($10K - $5K)
BS equity increases by $5,000 (exactly matches)
Model balances perfectly.
```

### Real Example: Multi-Month Bridge

```
                        Jan         Feb         Mar         Total
Beginning RE           $100,000    $100,000    $105,000    $100,000
+ Net Income           $10,000     $15,000     $12,000     $37,000
- Owner Draws          $10,000     $10,000     $10,000     $30,000
= Ending RE            $100,000    $105,000    $107,000    $107,000

Validation:
  P&L Total NI (Jan-Mar): $37,000
  Total Draws (Jan-Mar):  $30,000
  RE increase:           $7,000 ($107K - $100K) ✓ Correct!
```

### Common Errors in RE Bridge

**Error 1: Not including owner draws**
```
Formula: =Prior_RE + NI (missing the draws)
Result: RE overstated by distribution amount
Balance sheet won't balance
```

**Error 2: Referencing wrong cell for NI**
```
Formula: =Prior_RE + BS!Revenue (oops, should be P&L!NI)
Result: RE drastically overstated
Balance sheet way off
```

**Error 3: Negative accumulated depreciation**
```
Formula: =Accum_Depr + Monthly_Depr (should be subtraction)
Result: Depreciation adds to assets instead of reducing them
Assets inflated, model fails
```

**Error 4: Annual reset (treating RE like profit-first)**
```
Formula: =0 (reset annually) + NI (this year only)
Result: Prior year profits lost; equity understated
Only shows current year profit, not accumulated wealth
```

### Testing the Retained Earnings Bridge

**Quick validation check:**
```
1. Note the RE balance at end of Period 1: $100,000
2. Note the RE balance at end of Period 2: $105,000
3. Calculate: $105,000 - $100,000 = $5,000 (the change)

4. From P&L: NI in Period 2 = $15,000
5. From Drivers: Draws in Period 2 = $10,000
6. Calculate: $15,000 - $10,000 = $5,000 (expected change)

7. Compare: $5,000 (actual change) = $5,000 (expected change) ✓
```

---

## Balance Sheet Relationship Examples

### Scenario 1: Revenue Growth (Everything Connected)

**Starting position (Month 1):**
```
P&L: Revenue $100K, COGS 40%, GP $60K, Opex $50K, NI $10K
BS: Cash $50K, AR $50K (DSO=15), Inv $30K (DIO=22), AP $20K (DPO=15)
    CCC = 15 + 22 - 15 = 22 days
    WC = $50K + $30K - $20K = $60K
```

**Scenario: Revenue grows to $150K (no other changes)**
```
Updated (Month 2):
P&L: Revenue $150K, COGS $60K, GP $90K, Opex $50K, NI $40K
BS should change:
  AR: ($150K / 30) × 15 = $75K (up from $50K) → $25K cash tied up
  Inventory: ($60K / 30) × 22 = $44K (up from $30K) → $14K cash tied up
  AP: ($60K / 30) × 15 = $30K (up from $20K) → $10K extra credit
  Net WC increase: $25K + $14K - $10K = $29K

Cash impact:
  Operating CF: +$40K (NI)
  WC increase: -$29K (tie up more capital)
  Net CF: +$11K

Equation:
  Begin Cash: $50K
  Operating CF: $11K
  End Cash: $61K

BS validates:
  Total Assets: $61K (cash) + $75K (AR) + $44K (Inv) = $180K
  AP: $30K
  Equity: $100K + $40K (NI) = $140K
  Check: $180K (assets) = $30K (AP) + $140K (equity) ✓ Balances!
```

### Scenario 2: Debt Repayment (Liability → Cash)

**Starting position:**
```
BS: Cash $100K, Debt $50K (liability), Equity $100K
CF: Operating CF +$30K (no distributions yet)
```

**Scenario: Repay $20K of debt**
```
Updated:
BS: Cash $100K + $30K - $20K = $110K
    Debt: $50K - $20K = $30K
    Equity: $100K + $30K (NI) = $130K
    Check: $110K = $30K + $130K ✓

CF statement:
  Operating: +$30K
  Financing (debt repayment): -$20K
  Net: +$10K
  Ending Cash: $100K + $10K = $110K ✓ Matches!
```

### Scenario 3: Asset Purchase (Cash → Fixed Asset)

**Starting position:**
```
BS: Cash $50K, Equipment $100K (net), Equity $150K
```

**Scenario: Purchase equipment for $30K cash**
```
Updated:
BS: Cash: $50K - $30K = $20K
    Equipment: $100K + $30K = $130K (gross value increases)
    Equity: Still $150K (no P&L impact from purchase)
    Check: $150K ($20K + $130K) = $150K ✓

CF statement:
  Investing CF: -$30K (equipment purchase)
  This reduces cash directly (no P&L impact)
```

---

## Depreciation Schedule Best Practices

When your model spans multiple years, track depreciation carefully:

### Full Depreciation Schedule Tab

```
Asset          | Acquisition | Cost      | Life  | Annual  | Month   | Year 1 Dep | Year 2 Dep | Accumulated (Year 2)
               | Date         |           |       | Depr    | Depr    |            |            |
Computers      | 1/1/2024     | $10,000   | 3yr   | $3,333  | $278    | $3,333     | $3,333     | $6,666
Furniture      | 1/1/2024     | $15,000   | 5yr   | $3,000  | $250    | $3,000     | $3,000     | $6,000
Equipment      | 7/1/2024     | $50,000   | 7yr   | $7,143  | $595    | $3,571     | $7,143     | $10,714
              |              |            |       |         | Total   | $10,004    | $13,476    | $23,380
```

**Usage in model:**
```
Balance Sheet line:
  Accumulated Depreciation: =DepreciationSchedule!CumulativeDepreciation(current month)

P&L line:
  Depreciation Expense: =DepreciationSchedule!MonthlyDepreciation(current month)

Cash Flow (add back):
  +Depreciation: =DepreciationSchedule!MonthlyDepreciation(current month)
```

