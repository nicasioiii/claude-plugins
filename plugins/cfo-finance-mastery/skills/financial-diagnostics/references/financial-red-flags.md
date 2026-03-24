---
name: Financial Red Flags & Error Detection Checklist
description: Spot accounting errors, ratio interpretation traps, and common statement distortions before they become problems.
---

# Financial Red Flags & Error Detection Checklist

## The Five-Minute Red Flag Scan

Before any deep analysis, run these five checks. Most problems surface here.

### Check 1: Balance Sheet Balances

**The rule:** Assets = Liabilities + Equity (always, no exceptions)

**If it doesn't balance:**
- Bookkeeping error (most common)
- Misclassified account (asset recorded as liability or vice versa)
- Missing transaction
- Rounding error (rare in software, common in manual entries)

**How to find the error:**
1. Difference between left and right = missing amount
2. Check recent transactions for that amount
3. Verify account classifications (undeposited funds shouldn't be a liability; it's an asset)

### Check 2: Net Income Matches Retained Earnings Change

**The rule:** Prior Year Retained Earnings + Current Year Net Income - Distributions = Current Year Retained Earnings

**Example:**
```
Dec 31, Year 1 Retained Earnings: $100,000
Year 2 Net Income:               $ 50,000
Owner distributions (dividends): $ 20,000
Dec 31, Year 2 Retained Earnings: Should be $130,000 ($100K + $50K - $20K)

If actual is $125,000, $5,000 is missing. Find it.
```

**Common errors:**
- Owner draw not recorded as distribution
- Prior year adjustment posted to current year (distorts comparison)
- Net income calculated differently for P&L vs equity section

### Check 3: Revenue Reconciliation

**Compare three sources:**
1. P&L revenue (top line)
2. Accounts receivable increase + cash collections (balance sheet + cash flow)
3. GL account total for revenue

**They should match (or be explainable by timing).**

**Example of timing issue:**
```
P&L revenue (accrual): $100,000
AR increased (customers owe): $30,000
Cash collected: $70,000
Total cash received this month matches P&L revenue (good)
```

**Red flag:**
```
P&L revenue: $100,000
AR increased: $50,000
Cash collected: $40,000
Total doesn't add up ($90K vs $100K revenue)
Missing $10,000. Find it.
```

### Check 4: COGS Makes Sense

**Rule:** If inventory is present, COGS should be roughly 40-80% of revenue (varies by industry).

**Red flags:**
- COGS < 10% of revenue (possible for pure service biz, unlikely for product)
- COGS > 85% of revenue (unsustainable; negative margins coming)
- COGS flat while revenue grows 20% (inventory depletion; not sustainable)
- COGS negative (data error; COGS can't be negative)

**What to check:**
- GL account: Is revenue recorded gross or net of returns?
- Is COGS inventory-based or direct labor-based?
- Are all COGS items included (freight, taxes, commissions)?
- Is depreciation included in COGS (manufacturing) or OpEx (services)?

### Check 5: Cash Balance is Reasonable

**Rule of thumb:** Cash should be 1-3 months of operating expenses (not including COGS).

**Example:**
```
Monthly operating expenses (excluding COGS): $50,000
Healthy cash range: $50K-$150K

If cash is $10K: Dangerously low (no cushion for emergencies)
If cash is $500K: Excessive (capital not deployed; opportunity cost)
```

**Red flag:**
- Cash declining month-to-month with positive P&L (working capital eating cash)
- Cash negative (impossible; company is not operating)
- Cash balance doesn't match bank statement (reconciliation error)

---

## Common P&L Distortions

### 1. Revenue Timing Errors

**Issue: Revenue in wrong month**

**Accrual basis rule:** Record revenue when earned, not when cash received or invoice sent.

**Example of error:**
```
Service delivered: January 15
Invoice sent: February 1
Cash received: March 1

Correct: Record revenue in January (when earned)
Wrong: Record revenue in February (invoice) or March (cash)

If recorded in wrong month, January looks weak, March looks strong.
Trend analysis is misleading.
```

**How to spot:**
- Compare revenue month-to-month against service delivery dates (not invoice dates)
- Large revenue spikes with no explanation
- Revenue consistently lagging behind cash collections (late invoice period)

**How to fix:**
- Use service delivery date, not invoice or payment date
- Reconcile GL to customer contracts (when delivery occurred)

### 2. Revenue Recognition for Multi-Month Contracts

**Issue: Annual contract recorded in month 1, not pro-rated**

**Example:**
```
Contract: $12,000/year (customer paid in January)
Wrong: Recognize $12,000 revenue in January
Right: Recognize $1,000/month for 12 months

Wrong P&L:
Jan: $12,000 revenue (spike)
Feb-Dec: $0 revenue (each month looks weak)

Right P&L:
Jan-Dec: $1,000/month revenue (consistent)
```

**How to spot:**
- Revenue lumpy (some months $50K, others $5K)
- No correlation with actual service delivery
- Revenue and cash collections widely mismatched

**How to fix:**
- Use deferred revenue account (liability)
- Record upfront payment as deferred revenue
- Recognize revenue monthly as service is delivered

### 3. COGS Below Cost-of-Inventory

**Issue: COGS recorded as less than actual product cost**

**Example:**
```
Inventory purchased: $100,000
Inventory sold: 80% of purchase
COGS should be: $80,000 (80% of $100,000)

If recorded as: $60,000
Gross margin overstated by $20,000
Profit inflated
```

**Red flags:**
- Gross margin rising while revenue flat or declining (inventory depletion)
- Inventory declining without corresponding COGS increase (stock being given away?)

**How to fix:**
- Reconcile COGS to inventory movements (GL)
- Use inventory formula: Beginning Inv + Purchases - Ending Inv = COGS
- Monthly inventory counts (quarterly minimum)

### 4. Non-Recurring Expenses Distorting Profitability

**Issue: One-time charges treated as recurring**

**Examples:**
- Legal settlement ($50,000 one-time charge)
- Equipment sale (gain or loss)
- Severance package (one-time for laid-off employee)
- Goodwill impairment (one-time accounting charge)

**How to spot:**
- Unusual items in P&L with no explanation
- Operating income suddenly drops, rebounds next month

**How to fix:**
- Separate "Adjusted Net Income" excluding one-time items
- Report both GAAP net income (including one-time) and adjusted net income (recurring only)

**Example:**
```
GAAP Net Income: $50,000
Less: Legal settlement (one-time): $40,000
Add back: Tax benefit of settlement: $10,000
Adjusted Net Income: $20,000 (recurring profitability)

Interpretation: Business is $20K profitable on recurring basis.
The $50K GAAP number is inflated by one-time charge.
```

### 5. Depreciation Timing

**Issue: Annual depreciation recorded in December only, not monthly**

**Impact:**
```
Equipment purchased: January ($120,000, 5-year life = $2,000/month)

Monthly depreciation approach:
Jan-Dec: $2,000/month expense
Consistent profitability across months

Annual depreciation approach:
Jan-Nov: $0 expense (artificially inflated profit)
Dec: $24,000 expense (artificially depressed profit)

Result: November looks 2x more profitable than December (misleading)
```

**How to fix:**
- Record depreciation monthly or quarterly (proportional to time)
- Even if tax return uses annual-only, GAAP accounting requires periodic allocation

---

## Common Balance Sheet Distortions

### 1. Negative Accounts Payable (Impossible)

**Issue: Accounts Payable showing negative balance**

**Possible causes:**
1. **Prepaid expenses miscategorized as AP** (should be asset, not liability)
   ```
   Prepaid ad spend: $50,000 (recorded as AP instead of prepaid expense)
   Shows negative AP; actually positive prepaid asset
   ```

2. **Credit from vendor recorded as negative AP** (unusual, but possible)
   ```
   Vendor issued $10,000 credit (returned goods)
   Recorded as AP = -$10,000 instead of reducing AP by $10,000
   ```

3. **Bookkeeping error** (debit/credit reversal)

**How to fix:**
- GL audit of AP account
- Reconcile to actual vendor invoices
- Reclassify to correct account

### 2. Undeposited Funds in Liability Section

**Issue: "Undeposited Funds" listed as liability instead of asset**

**Problem:**
```
Undeposited Funds is cash you've collected but not deposited.
It's an ASSET (your cash), not a LIABILITY (what you owe).

Misclassification makes:
- Current assets look too low
- Current liabilities look too high
- Current ratio looks worse than it is
```

**How to fix:**
- Move to Current Assets section (or merge into Cash)
- Reconcile to actual deposits

### 3. Accounts Receivable Overstated

**Issue: AR includes uncollectible invoices (no allowance for doubtful accounts)**

**Example:**
```
Total AR: $100,000 (reported)
Actually collectable: $85,000
Uncollectible (bad customers): $15,000

If no reserve recorded, AR is overstated by $15,000
True AR: $85,000
Net income overstated (no bad debt expense)
```

**How to spot:**
- AR growing faster than revenue (customers not paying)
- DSO >90 days (customers taking 3+ months)
- Large AR balances from customers with payment issues

**How to fix:**
- Allowance for doubtful accounts (reserve)
- Record bad debt expense equal to estimated uncollectible amount
- P&L impact: Bad debt expense reduces net income
- Balance sheet impact: AR reduced by allowance

### 4. Inventory Overstated

**Issue: Inventory includes obsolete or damaged goods at original cost**

**Example:**
```
Inventory cost: $200,000 (original purchase price)
Obsolete/damaged goods: $40,000 (can't sell for full price)
Net realizable value: $160,000

If not written down, inventory is overstated by $40,000
```

**How to fix:**
- Inventory reserve for obsolescence
- Write obsolete inventory to lower of cost or market value
- P&L impact: Inventory write-down (expense)
- Inventory decreases on balance sheet

### 5. Equipment Not Depreciated Annually

**Issue: Equipment listed at cost; no accumulated depreciation recorded**

**Example:**
```
Equipment purchased 2020: $100,000
Current accumulated depreciation: $0
Book value: $100,000

If 5-year life, should have $20,000/year depreciation:
After 3 years: Accumulated depreciation should be $60,000
Book value should be: $40,000

Error: Equipment overstated by $60,000
Profit overstated: $60,000 in depreciation not recorded
```

**How to fix:**
- Calculate accumulated depreciation for each asset
- Record annually (or catch up if missing)
- Monthly or quarterly depreciation most accurate

### 6. Goodwill from Acquisition Not Impaired

**Issue: Acquired business; paid $500K for company worth $300K; $200K goodwill**

**Problem:**
- Goodwill sits on balance sheet at $200K
- If business underperforms, goodwill may be impaired (worthless)
- Goodwill impairment is large one-time charge reducing profitability

**How to fix:**
- Periodic impairment tests (annually minimum)
- If acquisition underperforms, write down goodwill
- Record impairment expense on P&L

---

## Common Ratio Interpretation Traps

### 1. Current Ratio Trap

**Metric:** Current Ratio = Current Assets / Current Liabilities

**Trap:**
```
Company A: Current ratio = 2.0 (looks healthy: $200K assets, $100K liabilities)
Company B: Current ratio = 1.5 (looks weaker: $150K assets, $100K liabilities)

Interpretation trap: Company A is healthier.

Reality: If all $100K current liabilities are due tomorrow,
Company A can pay ($200K assets available)
Company B can pay with some effort ($150K assets, slightly tight)

BUT if current assets are:
Company A: $150K inventory (slow-moving) + $50K cash
Company B: $140K cash + $10K inventory

Company B is healthier (mostly liquid).
Company A has ratio cushion but liquidity problem.

Better metric: Quick Ratio (excludes inventory) = 1.4 vs 1.4 (tie)
```

**Fix:** Always look at quick ratio (excludes inventory), not just current ratio.

### 2. DSO Benchmarking Trap

**Metric:** Days Sales Outstanding = (AR / Revenue) × 30

**Trap:**
```
Company A: DSO = 45 days (vs industry average 30)
Interpretation: "Collection problem, we're slow"

Reality: Company A offers Net 60 payment terms (financing strategy)
Company B offers Net 30 (industry standard)

Expected DSO differences:
- Company offering Net 30: DSO ≈ 30 days (on terms)
- Company offering Net 60: DSO ≈ 60 days (on terms)

A "high" DSO is only bad if above YOUR stated terms.
If you offer Net 60, DSO 60 is healthy.
If you offer Net 30, DSO 60 is a problem.
```

**Fix:** Compare to your terms, not industry average. If industry is Net 30 and you offer Net 60, your "high" DSO is intentional (pricing strategy).

### 3. Margin Ratio Trap

**Metric:** Net Margin = Net Income / Revenue

**Trap:**
```
Company A: 10% net margin, $1M revenue = $100K profit
Company B: 20% net margin, $200K revenue = $40K profit

Interpretation trap: Company A is better (higher margin %).

Reality: Company A makes more total profit dollars ($100K vs $40K)
even though margin % is lower.

Which is better depends on goals:
- Revenue/profit dollars: Company A wins
- Efficiency: Company B wins
- Cash flow: Company A (higher dollars)
```

**Fix:** Compare total dollars (more important), not just %.

### 4. Debt-to-Equity Trap

**Metric:** Debt-to-Equity = Total Debt / Total Equity

**Trap:**
```
Company A: Debt-to-Equity = 1.0 (50% debt, 50% equity; looks balanced)
Company B: Debt-to-Equity = 5.0 (83% debt, 17% equity; looks overleveraged)

Interpretation trap: Company B is risky, Company A is safe.

Reality: If debt is at 4% interest and equity investors expect 15% return,
Company B's high debt is cheaper capital.
Company A's high equity is expensive capital.

But risk: If business hits downturn,
Company A still pays 50% to equity (profit-dependent)
Company B must pay 83% debt (mandatory regardless of profit)

Better metric: Interest coverage = EBITDA / Interest Expense
- Company A: High (low debt, can cover easily)
- Company B: Low (high debt, barely can cover)
```

**Fix:** Look at interest coverage (ability to pay), not just debt %, for risk assessment.

### 5. ROE Trap

**Metric:** Return on Equity (ROE) = Net Income / Equity

**Trap:**
```
Company A: ROE = 20% ($100K profit, $500K equity)
Company B: ROE = 100% ($50K profit, $50K equity)

Interpretation trap: Company B is wildly more efficient.

Reality: Company B has minimal equity (high leverage).
One bad year, equity is wiped out.
Company A has cushion; can absorb losses.

ROE is inflated for highly leveraged businesses (not a good thing).
```

**Fix:** Look at ROA (Return on Assets) instead for true operational efficiency, not leverage effects.

---

## Financial Statement Red Flag Checklist

Before analyzing, verify:

- [ ] **Balance sheet balances** (Assets = Liabilities + Equity)
- [ ] **Net income reconciles to retained earnings change**
- [ ] **Revenue reconciles across P&L, AR, and cash flow**
- [ ] **COGS is reasonable** (40-80% of revenue for product biz)
- [ ] **Cash balance is reasonable** (1-3 months operating expenses)
- [ ] **Depreciation is recorded monthly** (not annual-only)
- [ ] **Negative accounts impossible** (no negative AP or AR unless special reason)
- [ ] **One-time charges separated** from recurring items
- [ ] **Undeposited funds categorized as asset** (not liability)
- [ ] **AR aging reviewed** (DSO matches terms)
- [ ] **Inventory is current** (not obsolete)
- [ ] **Equipment accumulated depreciation tracked**
- [ ] **Deferred revenue separated** from earned revenue
- [ ] **Prior year adjustments documented**
- [ ] **Significant transactions explained**

If any check fails, investigate before doing financial analysis.

