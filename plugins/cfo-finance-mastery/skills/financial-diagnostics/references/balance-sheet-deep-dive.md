---
name: "Balance Sheet Deep Dive"
description: "Balance sheet equation and structure, common small-business BS errors, direct/indirect connections between P&L and BS, debits/credits quick reference, asset-liability matching."
when_to_read: "When the user needs to understand balance sheet structure, diagnose BS errors, understand how P&L connects to BS, or needs debit/credit mechanics explained."
---

# Balance Sheet Deep Dive

## Balance Sheet Equation and Structure

```
Assets = Liabilities + Equity
```

This equation must ALWAYS balance. If it does not, something is wrong. But a balanced sheet can still be wrong -- accuracy matters beyond the math.

### Asset Classification (Ordered by Liquidity)

**Current Assets (convert to cash within 12 months):**
| Account | What It Is | Watch For |
|---------|-----------|-----------|
| Cash & Equivalents | Bank balances, petty cash | Low balance relative to monthly expenses |
| Accounts Receivable | Money owed by customers | Aging beyond terms, concentration risk |
| Inventory | Goods held for sale | Slow-moving items, obsolescence |
| Prepaid Expenses | Payments made in advance | Should decline monthly as used |
| Other Current | Short-term notes, deposits | Items that should be reclassified |

**Non-Current Assets:**
| Account | What It Is | Watch For |
|---------|-----------|-----------|
| Property/Equipment | Fixed assets at cost | Missing accumulated depreciation |
| Accumulated Depreciation | Contra asset (negative) | Should increase each period |
| Intangible Assets | Patents, trademarks, goodwill | Proper descriptions and amortization |
| Security Deposits | Landlord/vendor deposits | Often forgotten |

### Liability Classification

**Current Liabilities (due within 12 months):**
- Accounts Payable, Credit card balances, Accrued expenses, Deferred revenue (current portion), Short-term debt, Current portion of long-term debt

**Non-Current Liabilities:**
- Bank loans, Lines of credit, Bonds payable, Lease obligations

### Equity Components
- **Contributed Capital:** Common stock, preferred stock, additional paid-in capital
- **Retained Earnings:** Accumulated profits from all prior periods
- **Current Period Net Income:** Flows from P&L, resets to RE at year-end

**Retained Earnings Cycle (Aharonoff):**
```
Current RE = Prior RE + Prior Year Net Income
```
Net income accumulates monthly as "Profit for the Year." Transfers to Retained Earnings on January 1 each year.

---

## Common Balance Sheet Errors (Leikauf)

### Error 1: AP Listed Under Assets
**Problem:** Accounts payable is a liability, not an asset.
**Impact:** Overstates assets, understates liabilities. Business looks healthier than it is.
**Fix:** Reclassify to current liabilities.

### Error 2: AR Listed as a Liability
**Problem:** Accounts receivable is an asset (money owed TO the business).
**Impact:** Understates assets, overstates liabilities.
**Fix:** Reclassify to current assets.

### Error 3: Equipment Without Accumulated Depreciation
**Problem:** Fixed assets shown at original cost with no depreciation.
**Impact:** Overstates asset value. Missing depreciation expense on P&L.
**Fix:** Calculate and record accumulated depreciation. Add depreciation expense to P&L.

### Error 4: Prepaid Rent Not Split
**Problem:** 12-month prepaid rent shown entirely as current asset.
**Impact:** If prepaid extends beyond 12 months, the non-current portion should be classified separately.

### Error 5: "Loan to Owner" Without Clarification
**Problem:** Owner loans that are really distributions, or vice versa.
**Impact:** Distorts equity and creates tax issues.

### Error 6: Dividends During Net Loss
**Problem:** Paying distributions when the business lost money.
**Impact:** Erodes equity, signals financial distress or poor governance.

### Error 7-9: Missing equity breakdown, undescribed intangibles, RE that does not reconcile
All indicate sloppy bookkeeping that undermines financial statement credibility.

---

## P&L to Balance Sheet Connections (Aharonoff)

### Direct Connections
These flow automatically every period:

1. **Net Income -> Retained Earnings**
```
Current Period RE Change = Current Period Net Income
```

2. **Depreciation Expense -> Accumulated Depreciation**
```
Current Accum Dep = Prior Accum Dep + Current Period Dep Expense
```

3. **Amortization Expense -> Accumulated Amortization**
Same pattern as depreciation.

### Indirect Connections
These happen through business activity:

| P&L Event | BS Impact (first) | BS Impact (second) |
|-----------|-------------------|-------------------|
| Revenue recognized | AR increases | Cash increases when collected |
| COGS recorded | Inventory decreases | (Already on BS) |
| Prepaid expense used | Prepaid asset decreases | Expense on P&L |
| Deferred revenue earned | Deferred rev liability decreases | Revenue on P&L |
| Customer pays in advance | Cash increases, Deferred rev increases | Revenue later |

---

## Debits and Credits Quick Reference (Aharonoff)

| Account Type | Debit (Left) | Credit (Right) |
|-------------|-------------|---------------|
| **Assets** | Increase | Decrease |
| **Liabilities** | Decrease | Increase |
| **Equity** | Decrease | Increase |
| **Revenue** | Decrease | Increase |
| **Expenses** | Increase | Decrease |

Every transaction affects at least two accounts (double-entry bookkeeping).

**Example transactions:**
- Customer pays $1,000 invoice: Debit Cash +$1,000, Credit AR -$1,000
- Purchase equipment for $5,000: Debit Equipment +$5,000, Credit Cash -$5,000
- Record monthly depreciation $500: Debit Dep Expense +$500, Credit Accum Dep +$500

---

## Asset-Liability Matching Principle

**Rule:** Match the term of the financing to the life of the asset.

| Asset | Appropriate Financing | Wrong Financing |
|-------|----------------------|-----------------|
| Equipment (5-year life) | 5-year equipment loan | Credit card |
| Real estate | 15-25 year mortgage | Line of credit |
| Seasonal inventory | Short-term credit line | Long-term loan |
| Working capital gap | Revolving LOC | Owner equity injection |

Mismatching creates cash flow stress: short-term debt for long-term assets means large periodic repayments that drain operations.

---

## Balance Sheet Diagnostic Checklist

1. Does the BS balance? (Assets = L + E)
2. Are all accounts classified correctly? (Current vs non-current)
3. Is accumulated depreciation present for fixed assets?
4. Does retained earnings reconcile with prior periods?
5. Are there unusual or unexplained account balances?
6. Does current ratio suggest adequate liquidity? (-> financial-ratios)
7. Is working capital positive? (Current Assets > Current Liabilities)
8. Are there related-party transactions that need disclosure?

---

## Cross-References

- **Ratio analysis from BS data** -> `financial-ratios/ratio-reference.md`
- **Working capital management** -> `working-capital/ar-ap-inventory.md`
- **BS projection in models** -> `financial-modeling/three-statement-construction.md`
- **Cash flow derived from BS changes** -> `cash-flow-analysis.md` (this skill)
