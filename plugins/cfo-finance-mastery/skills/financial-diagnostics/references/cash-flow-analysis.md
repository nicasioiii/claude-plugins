---
name: "Cash Flow Analysis"
description: "Cash flow statement three sections, indirect method mechanics, universal cash flow rules, red flags, improvement strategies, cash vs accrual implications, healthy business cash flow pattern."
when_to_read: "When the user needs to understand or diagnose a cash flow statement, build cash flow from balance sheet changes, spot cash flow red flags, or understand indirect method mechanics."
---

# Cash Flow Analysis

## Three Sections of the Cash Flow Statement

### 1. Operating Activities
Cash generated or consumed by core business operations.

**Indirect method (most common):**
```
Net Income
+ Depreciation Expense (add back -- non-cash)
+ Amortization Expense (add back -- non-cash)
+/- Changes in Accounts Receivable
+/- Changes in Prepaid Expenses
+/- Changes in Inventory
+/- Changes in Accounts Payable
+/- Changes in Accrued Expenses
+/- Changes in Deferred Revenue
+/- Changes in Other Working Capital
= Cash from Operating Activities
```

### 2. Investing Activities
Cash used for or received from long-term asset transactions.
```
+/- Changes in Fixed Assets (equipment, property)
+/- Changes in Intangible Assets
+/- Changes in Security Deposits
+/- Changes in Due from Officers
= Cash from Investing Activities
```

### 3. Financing Activities
Cash from debt and equity transactions.
```
+/- Changes in Long-term Debt
+/- Changes in Common/Preferred Stock
+/- Changes in Additional Paid-in Capital
+/- Distributions/Dividends
= Cash from Financing Activities
```

### Total
```
Net Change in Cash = Operating + Investing + Financing
Ending Cash = Beginning Cash + Net Change in Cash
```

---

## Universal Cash Flow Rules (Aharonoff)

These rules derive directly from the balance sheet equation.

| Event | Cash Impact |
|-------|-------------|
| Non-cash asset increases | **Negative** (uses cash) |
| Non-cash asset decreases | **Positive** (releases cash) |
| Liability increases | **Positive** (provides cash) |
| Liability decreases | **Negative** (uses cash) |
| Equity increases | **Positive** (provides cash) |
| Equity decreases | **Negative** (uses cash) |

### Mathematical Foundation
```
If: Assets = Liabilities + Equity
Then: Change_in_Assets = Change_in_Liabilities + Change_in_Equity
```

### Formula for Cash Flow Statement

**For asset accounts (except cash):**
```
Cash Impact = Prior_Period_Balance - Current_Period_Balance
```
(Sign is reversed because asset increases use cash)

**For liability and equity accounts:**
```
Cash Impact = Current_Period_Balance - Prior_Period_Balance
```

### Critical Rule: Exclude Cash from Cash Flow Calculations
Cash balance is DERIVED from the cash flow statement. Including cash as an input creates a circular reference. The cash account row must be removed from operating activities calculations.

---

## Direct vs Indirect Method

| Feature | Direct Method | Indirect Method |
|---------|--------------|-----------------|
| Starting point | Actual cash receipts | Net income |
| Adjustments | None -- shows real cash | Adds back non-cash items, adjusts working capital |
| Ease of preparation | Harder (need cash register data) | Easier (use P&L + BS changes) |
| Ease of understanding | Easier for non-accountants | Requires accounting knowledge |
| Usage | Rare | Most commonly used |
| GAAP/IFRS | Both accepted | Both accepted (indirect preferred) |

---

## Cash Flow Red Flags

### Critical Red Flags
1. **Net income positive, operating cash flow negative:** Earnings quality issue. Business reports profit but consumes cash. Often caused by growing AR or inventory.
2. **Operating cash flow consistently negative:** Business cannot fund itself from operations. Unsustainable without external capital.
3. **Financing activities propping up operations:** Borrowing to cover operating losses. Debt spiral risk.
4. **Large gap between net income and operating cash flow:** Working capital is absorbing cash. Investigate AR, inventory, AP trends.

### Warning Signs
5. **Investing activities consistently zero:** Business not reinvesting. May signal under-investment.
6. **Growing CapEx with flat revenue:** Spending on assets without revenue return.
7. **Distributions exceeding operating cash flow:** Owners extracting more than the business generates.
8. **Misclassified activities:** Operating items in investing (hides operating weakness) or vice versa.

### Healthy Pattern (Aharonoff)
A healthy business generates most cash from operating activities. If most cash comes from financing or investing rather than operations, this is a warning sign. The cash flow statement is the reality check that connects what you earn (P&L) to what you own (balance sheet).

---

## Cash Flow Improvement Strategies (Leikauf)

### Collect Faster (Reduce DSO)
- Tighten AR terms (Net 30 -> Net 15)
- Implement e-invoicing and automated follow-ups
- Bill every 28 days instead of monthly (adds extra billing cycle per year)
- Consider factoring for immediate cash on large receivables
- Use retainer/upfront fee models for service businesses
- Progress billing for large projects (milestone-based)

### Manage Inventory (Reduce DIO)
- ABC analysis: Focus management effort on high-value A items
- JIT methods to reduce on-hand inventory
- Phase bulk purchases into smaller orders
- Consider dropshipping, consignment, or vendor-managed inventory

### Optimize Payables (Extend DPO -- Within Reason)
- Negotiate longer payment terms with vendors
- Automate payments to pay on time but never early
- Skip early-pay discounts unless they exceed ~30% annualized (Leikauf contrarian)

### Time CapEx
- Forecast cash flow before approving capital expenditures
- Coordinate large purchases with high-cash-flow periods
- Consider leasing vs buying for large equipment

---

## Cash vs Accrual Impact on Cash Flow Analysis

| Scenario | Cash Basis P&L | Accrual Basis P&L | Cash Flow Impact |
|----------|---------------|-------------------|-----------------|
| Sell $10K, collect $8K | Revenue: $8K | Revenue: $10K | AR +$2K = Cash drag |
| Prepay $12K rent | Expense: $12K | Expense: $1K/mo | Prepaid +$11K = Cash drag |
| Customer prepays $5K | Revenue: $5K | Revenue: $0 (deferred) | Deferred Rev +$5K = Cash gain |
| Receive inventory $20K, sell $15K | COGS: $15K | COGS: $15K | Inventory +$5K = Cash drag |

**Key insight:** Cash basis P&L already reflects cash flow timing. Accrual basis P&L requires the cash flow statement to reconcile earnings with actual cash movement.

---

## Cash Flow Variance Analysis

When comparing budget vs actuals (Aharonoff):

**[CONTRARIAN] Cash flow variance is more important than P&L variance.** The BvA dashboard may show small P&L variance but large cash variance. This means timing assumptions were wrong even if totals were close. Always investigate cash flow variance independently.

**Common causes of cash flow variance:**
- AR collection timing different from assumptions
- Payment terms not adhered to (customers paying late)
- Inventory purchases front-loaded vs spread
- CapEx timing shifted
- Debt drawdown/repayment timing changed

---

## Cross-References

- **Working capital optimization tactics** -> `working-capital/ar-ap-inventory.md`
- **Cash flow in three-statement models** -> `financial-modeling/three-statement-construction.md`
- **CCC and working capital ratios** -> `financial-ratios/ratio-reference.md`
- **Cash-out dashboard design** -> `dashboards-and-reporting` skill
