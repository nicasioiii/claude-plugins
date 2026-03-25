---
name: "Three-Statement Construction"
description: "Building order, P&L-to-BS connections (direct and indirect), cash flow mathematics, connecting statements, closing the loop, success criteria, balance sheet projection framework with key account formulas, waterfall schedule technique."
when_to_read: "When the user is building or connecting the three financial statements, projecting balance sheet accounts, needs cash flow formulas, or is troubleshooting why the model does not balance."
---

# Three-Statement Construction

## Building Order (Aharonoff)

### Step 1: Build Income Statement
Construct P&L with all revenue lines and expense categories. Reference drivers tab for both historical actuals and projected values.

### Step 2: Connect P&L to Balance Sheet
```
Balance Sheet Net Income = P&L Net Income (same period)
Current RE = Prior RE + Prior Year Net Income
Current Accum Dep = Prior Accum Dep + Current Dep Expense
Current Accum Amort = Prior Accum Amort + Current Amort Expense
```

### Step 3: Build Cash Flow Statement
- Copy balance sheet structure
- Replace each account with period-over-period change formula
- Organize into Operating, Investing, Financing sections
- Remove cash row (cash is derived, not input)

### Step 4: Close the Loop
```
Balance Sheet Cash Account = Cash Flow Statement Ending Cash
```

### Step 5: Verify
- Assets = Liabilities + Equity (every period, to the penny)
- Test: change an input and verify it flows through all three statements

---

## Cash Flow Statement Structure (Indirect Method)

### Operating Activities
```
Net Income
+ Depreciation Expense (add back non-cash)
+ Amortization Expense (add back non-cash)
+/- Changes in Accounts Receivable
+/- Changes in Prepaid Expenses
+/- Changes in Inventory
+/- Changes in Accounts Payable
+/- Changes in Accrued Expenses
+/- Changes in Deferred Revenue
+/- Changes in Other Working Capital
= Cash from Operating Activities
```

### Investing Activities
```
+/- Changes in Security Deposits
+/- Changes in Due from Officers
+/- Changes in Fixed Assets (computers, furniture, equipment)
+/- Changes in Intangible Assets
= Cash from Investing Activities
```

### Financing Activities
```
+/- Changes in Long-term Debt
+/- Changes in Common/Preferred Stock
+/- Changes in Additional Paid-in Capital
+/- Distributions
= Cash from Financing Activities
```

### Total Cash Flow
```
Total Cash Flows = Operating + Investing + Financing
Ending Cash = Beginning Cash + Total Cash Flows
```

### Formula Direction Rules
**For non-cash assets:**
```
Cash Impact = Prior_Period_Balance - Current_Period_Balance
```
(Asset increase uses cash, so we reverse the sign)

**For liabilities and equity:**
```
Cash Impact = Current_Period_Balance - Prior_Period_Balance
```
(Liability increase provides cash, so natural direction)

---

## Balance Sheet Projection Framework (Aharonoff)

### Universal Base Formula
Every balance sheet account follows:
```
Ending Balance = Beginning Balance + Additions - Subtractions
```

### Default Strategy
**Start by setting ALL BS accounts equal to their prior period values.** This creates a neutral cash flow impact baseline. Then adjust specific accounts based on business activities.

### [CONTRARIAN] Never Default to Zero
Zero balances create artificial cash impacts. If an account was $10,000 last month and you project zero, the model shows $10,000 of cash impact that does not exist. Always use prior period as the starting point.

### Key Account Formulas

**Accounts Receivable:**
```
Ending AR = Beginning AR + New Invoices (Revenue) - Collections
```
Example with 75/25 split collection:
```
AR Balance = 25% x Monthly_Revenue
```

**Accounts Payable:**
```
Ending AP = Beginning AP + New Purchases - Payments
```
Example with 50/50 payment terms:
```
AP Balance = 50% x (Total_Expenses + COGS)
```

**Deferred Revenue:**
Example with 3-week shipping (75% deferred):
```
Deferred Revenue = 75% x Monthly_Product_Sales
```

**Capital Expenditures:**
```
Ending Fixed Assets = Beginning Fixed Assets + New Purchases
```
Track each asset class separately (computers, furniture, equipment).

**Accumulated Depreciation (rolling):**
```
Current Accum Dep = Prior Accum Dep + Current Month Depreciation Expense
```

**Straight-Line Depreciation:**
```
Monthly Depreciation = Asset_Value / Useful_Life_Years / 12
```
Common schedules: Computers 5 years, Furniture 10 years, Equipment 7 years.

**Retained Earnings:**
```
Current RE = Prior Month RE + Current Month Net Income
```

**Interest Expense (on debt):**
```
Monthly Interest = Outstanding_Principal x Annual_Rate / 12
```

### Accounts That Must Tie to Other Statements
- Accumulated depreciation/amortization -> links to P&L depreciation expense
- Retained earnings and net income -> flows from P&L
- Cash balance -> connects to cash flow statement ending cash

---

## The Waterfall Schedule

For sophisticated projections of accounts that amortize over time:
```
Example: $90,000 initial booking, 3-month amortization
Monthly Recognized = $30,000
```

Works for: deferred revenue recognition, prepaid expense amortization, depreciation, debt amortization. Set up a grid where rows = origination periods and columns = recognition periods.

---

## Troubleshooting: Model Does Not Balance

**If Assets != Liabilities + Equity:**

1. **Check cash link:** Is BS cash = CF ending cash? (Most common issue)
2. **Check retained earnings:** Is current RE = prior RE + prior net income?
3. **Check depreciation:** Is accumulated dep increasing by current period dep expense?
4. **Check cash flow calculation:** Did you include cash row? (Should be excluded)
5. **Check new accounts:** Any new BS accounts not added to cash flow statement?
6. **Check subtotals:** Do all subtotal formulas include every account in the section?
7. **Trace manually:** Pick one period, manually calculate each cash flow item, compare to formula

---

## Success Criteria

Your model is complete when:
1. All three statements balance in every period
2. Changes in one statement properly affect others
3. Cash flow sections accurately reflect business activities
4. Error check tab shows no errors
5. Formatting is consistent and professional
6. Color coding applied correctly
7. Named ranges defined (Company_Name, Latest_Month_of_Actuals, error_check)

---

## Cross-References

- **DADA framework and tab architecture** -> `dada-framework.md` (this skill)
- **Drivers tab construction** -> `drivers-tab.md` (this skill)
- **Actualization and roll-forward** -> `actualization-and-rollforward.md` (this skill)
- **Projection methods for drivers** -> `forecasting-strategy/projection-methods.md`
- **Cash flow diagnostics** -> `financial-diagnostics/references/cash-flow-analysis.md`
