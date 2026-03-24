---
name: Model Error Checking & Validation Techniques
description: Build automated error checks to catch formula bugs, validate balance sheet equality, and spot divergence between statements.
---

# Error Checking & Validation

## Error Check Sheet Structure

**Create new sheet: "ErrorCheck"**

```
MODEL VALIDATION REPORT

1. BALANCE SHEET EQUALITY
Total Assets:                   [from BalanceSheet!B50]
Total Liabilities:              [from BalanceSheet!B75]
Total Equity:                   [from BalanceSheet!B90]
Liabilities + Equity:           [formula: Liab+Equity]
CHECK (should = 0):             [formula: Assets-(Liab+Equity)]

Status:  IF(ABS(CHECK) < 0.01, "PASS", "FAIL - Check Balance Sheet")

---

2. P&L TO BALANCE SHEET RECONCILIATION
Net Income (Jan):               [from IncomeStatement!B11]
Retained Earnings Change (Jan): [from BalanceSheet changes]
CHECK (should match):           [formula: NI - RE_change]

Status:  IF(ABS(CHECK) < 0.01, "PASS", "FAIL - RE doesn't match NI")

---

3. CASH FLOW RECONCILIATION
Operating CF + Investing CF + Financing CF:  [formula: sum of three]
Change in Cash on Balance Sheet:             [formula: Ending-Beginning]
CHECK (should match):                        [formula: CF - BS_change]

Status:  IF(ABS(CHECK) < 0.01, "PASS", "FAIL - CF doesn't reconcile")

---

4. REVENUE CONSISTENCY
Revenue (P&L):                  [from IncomeStatement!B2]
Revenue (Drivers):              [from Drivers!B2]
CHECK (should match):           [formula: P&L - Drivers]

Status:  IF(ABS(CHECK) < 0.01, "PASS", "FAIL - P&L ≠ Drivers")

---

5. INCOME STATEMENT BALANCE
Revenue - COGS - OpEx = Net Income?
Calculated: [formula: Rev - COGS - OpEx]
Reported NI: [from IncomeStatement]
CHECK:       [formula: difference]

Status:  IF(ABS(CHECK) < 0.01, "PASS", "FAIL - P&L math error")
```

## Key Validation Formulas

### Balance Sheet Equality Check

**In ErrorCheck tab, cells B1-B6:**

```
B1: =BalanceSheet!B2  (Total Assets)
B2: =BalanceSheet!B50 (Total Liabilities)
B3: =BalanceSheet!B75 (Total Equity)
B4: =B2+B3 (Liabilities + Equity)
B5: =B1-B4 (Assets - (Liab+Equity) should = 0)
B6: =IF(ABS(B5) < 0.01, "PASS", "FAIL - Balance Sheet doesn't balance")
```

**Interpretation:**
- If B5 = 0 (or very close, <$0.01): Balance sheet balances ✓
- If B5 > 0.01: Assets > Liab+Equity; find missing liability or inflated asset
- If B5 < -0.01: Liab+Equity > Assets; find extra liability or missing asset

### P&L to Retained Earnings Check

**In ErrorCheck tab, cells D1-D5:**

```
D1: =IncomeStatement!B11  (Net Income, Jan)
D2: =BalanceSheet!B90     (Current RE)
D3: =BalanceSheet!A90     (Prior RE from prior month)
D4: =D2 - D3              (Change in RE)
D5: =IF(ABS(D1 - D4) < 0.01, "PASS", "FAIL - RE change ≠ NI")
```

**Interpretation:**
- If D5 = "PASS": Current month's profit correctly updated retained earnings
- If D5 = "FAIL": Either NI calculation is wrong OR RE wasn't updated for NI + distributions

### Cash Flow to Balance Sheet Check

**In ErrorCheck tab, cells F1-F8:**

```
F1: =CashFlow!B7   (Operating CF)
F2: =CashFlow!B12  (Investing CF)
F3: =CashFlow!B17  (Financing CF)
F4: =F1 + F2 + F3  (Net change in CF)
F5: =BalanceSheet!B4  (Ending Cash)
F6: =BalanceSheet!A4  (Beginning Cash)
F7: =F5 - F6       (Change in Cash on BS)
F8: =IF(ABS(F4 - F7) < 0.01, "PASS", "FAIL - CF ≠ Cash change")
```

**Interpretation:**
- If F8 = "PASS": Cash flow statement reconciles to balance sheet ✓
- If F8 = "FAIL": Operating/Investing/Financing CF don't add up to the actual cash change on balance sheet. Find error in CF formulas.

## Common Errors & How to Find Them

### Error 1: Balance Sheet Doesn't Balance

**Possible causes:**
1. Accumulated depreciation is positive (should be negative, reducing assets)
2. Retained earnings not updated for current month net income
3. Asset purchase not matched to corresponding liab/equity reduction
4. Wrong formula in asset or liability cell

**How to find:**
1. Check accumulated depreciation (should be negative/reduction)
2. Check retained earnings = prior RE + current NI - distributions
3. Check if major asset purchase (CapEx) was funded by debt or equity
4. Manually calculate Total Assets, Total Liab, Total Equity on paper; compare to sheet

### Error 2: P&L and Balance Sheet Diverge

**Example:** P&L says NI = $10K, but Retained Earnings didn't increase by $10K

**Possible causes:**
1. Distributions/owner draws were recorded in equity but not subtracted from RE
2. NI was calculated one way in P&L, different way in equity
3. Prior month's RE wasn't included in current month's calculation

**How to find:**
1. Check Retained Earnings formula: =Prior RE + Current NI - Distributions
2. Confirm NI cell reference in RE formula points to IncomeStatement!NI
3. Verify distributions are subtracted from RE

### Error 3: Cash Flow Doesn't Reconcile

**Example:** CF says Cash increased $20K, but Balance Sheet cash only increased $5K

**Possible causes:**
1. AR/AP/Inventory changes incorrect in Operating CF
2. CapEx or financing activity missed
3. Beginning cash balance is wrong

**How to find:**
1. Manually calculate: Beginning Cash + Net CF = Ending Cash
2. Check if actual bank statement matches ending cash (BS number or CF ending number?)
3. Verify AR/AP changes are calculated correctly: Current - Prior (not Prior - Current)

### Error 4: Revenue Differs Between P&L and Drivers

**Example:** Income Statement shows $100K revenue, Drivers shows $105K

**Possible causes:**
1. P&L references wrong cell in Drivers
2. Drivers tab has SUMIFS formula pulling from wrong account name (typo)
3. P&L has hardcoded number instead of formula

**How to find:**
1. Click P&L revenue cell; check formula. Should be =Drivers!B2 (or similar)
2. Click Drivers revenue cell; check it's SUMIFS pulling from SourceGL
3. Verify account names match exactly ("Revenue" ≠ "revenue "; no extra spaces)

## Testing Procedure (Before Model is "Final")

**Step 1: Manual validation of one month**

Take January 2024 data and manually calculate:
```
Revenue (from source data):    $100,000
COGS (from source):            $ 40,000
OpEx (from source):            $ 35,000
Expected Net Income:           $ 25,000

Check Income Statement cell = $25,000? If no, formula error.
```

**Step 2: Run all error checks**

```
Balance sheet equality:        PASS?
P&L to RE:                     PASS?
CF to cash change:             PASS?
Revenue consistency:           PASS?
```

If all PASS: Model is valid.
If any FAIL: Stop. Find and fix the error.

**Step 3: Change one assumption, verify cascade**

Example: Increase revenue forecast from $100K to $110K.
- Does P&L revenue update? ✓
- Does AR update proportionally? ✓
- Does cash flow operating section update? ✓
- Does ending cash update? ✓
- Do error checks still show PASS? ✓

If anything doesn't update, formula is broken.

**Step 4: Extreme case testing**

Set revenue to $0 for one month. Does model still balance?
Set COGS % to 100% (no margin). Does model still balance?

If model breaks with extreme inputs, there's a formula error or division-by-zero problem.

## Red Flags That Model Has Errors

- Numbers with many decimals (more than 2) that seem suspicious
- Balance sheet doesn't balance
- P&L and balance sheet show different net income
- Cash flow ending ≠ Balance sheet cash
- Revenue changed but net income didn't change proportionally
- Percentages >100% (margin %, percentages of revenue)
- Circular reference error message appears
- One month's numbers look wildly different from adjacent months (and seasonality doesn't explain it)

## Error Check Dashboard (Visual)

**Create a simple visual on ErrorCheck sheet:**

```
┌─────────────────────────────────────────┐
│ MODEL STATUS                            │
├─────────────────────────────────────────┤
│ Balance Sheet Equality:    ✓ PASS       │
│ P&L to RE Reconciliation:  ✓ PASS       │
│ Cash Flow Reconciliation:  ✓ PASS       │
│ Revenue Consistency:       ✓ PASS       │
│ P&L Math Check:            ✓ PASS       │
├─────────────────────────────────────────┤
│ OVERALL:                   ✓ MODEL OK   │
└─────────────────────────────────────────┘
```

Use conditional formatting (IF statements with color):
- Green = PASS
- Red = FAIL

At a glance, user knows if model is valid.

## Key Principles

1. **Automate everything.** Don't manually check; use formulas with IF conditions.
2. **Absolute tolerance.** <$0.01 difference is due to rounding, not an error.
3. **Check after every change.** Monthly updates require re-validation.
4. **Error checks document assumptions.** They show what the model expects to be true.
5. **Reconciliation is non-negotiable.** If statements don't tie, something is wrong.

