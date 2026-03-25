---
name: "Actualization & Roll-Forward"
description: "Including actual data in models, model structure enhancement, data sources, Latest_Month_of_Actuals named range, 8-step roll-forward procedure, account change detection formulas, model audit checklist, common myths."
when_to_read: "When the user needs to update a model with actual data, perform monthly roll-forward, detect new accounts in exports, run a model audit, or understand the actualization workflow."
---

# Actualization & Roll-Forward

## Why Include Actuals (Aharonoff)

- Validates projections against reality
- Provides starting points for forecasts
- Creates clear transition between historical and projected data
- Enables budget vs actuals analysis
- Makes the model a living document, not a one-time artifact

## Enhanced Model Structure

**Traditional (projections only):**
```
Drivers Tab -> Summary Financials -> P&L, BS, CF
```

**Enhanced (with actuals):**
```
Source Tabs (P&L Data, BS Data, Accounting Integration)
  -> Drivers Tab (actuals + projections side by side)
  -> Financial Statements
  -> Budget vs Actuals Dashboard
```

## Data Sources for Actuals
1. **Accounting Software** -- Monthly financials, matching account structures
2. **HR Systems** -- Current team, salary data, headcount changes
3. **CRM** -- Customer information, renewal tracking, pipeline status

---

## The "Latest Month of Actuals" Named Range

This is the cornerstone of actualization.

**Setup:**
1. Open Name Manager (Ctrl+F3)
2. Create named range: `Latest_Month_of_Actuals`
3. Point to a date cell representing the last month with real data
4. Reference throughout model to control the actuals/projection boundary

**How it works:**
- Formulas reference this named range to determine whether to pull actual data (SUMIFS from source) or use projection formulas
- Conditional formatting uses it to visually distinguish actual vs projected columns
- Update this ONE cell each month, and the entire model adjusts

---

## Roll-Forward Procedure (8 Steps)

### Step 1: Preserve Original Projections
Save a copy of current model with naming convention:
```
Company_Financial_Model_[Month][Year]_Actuals.xlsx
```
Example: `Acme_Financial_Model_Dec24_Actuals.xlsx`

This becomes the baseline for budget vs actual comparison.

### Step 2: Export Fresh Data
Pull income statement and balance sheet from accounting software.

**Critical:** Get the FULL date range from model start through current month. Not just the new month. This catches inactive accounts that may have disappeared from recent exports.

### Step 3: Update Source Tabs
Paste new exports into source tabs. Attention to detail is critical here -- column alignment, date formatting, account name consistency.

### Step 4: Check for New Accounts
Use COUNTIF to identify accounts in the new export that do not exist in the model:
```
=COUNTIF([existing_model_accounts], [new_export_account_name])
```
Result of 0 = new account that needs to be added.

Also verify account alignment:
```
=([new_export_cell] = [existing_model_cell])
```
Should return TRUE for all accounts. FALSE indicates a mismatch (even small differences like trailing spaces).

### Step 5: Add New Accounts (if needed)
When a new account appears, add it to ALL necessary locations:
1. Drivers tab (correct section, proper formatting, blue input cells)
2. Financial statement tab (income statement or balance sheet)
3. Cash flow statement (if balance sheet account)
4. Update all subtotal and total formulas to include new row
5. Verify error checks still pass

### Step 6: Roll Forward the Actuals Column
In drivers tab:
1. Locate the last column of actuals
2. Copy the entire column to the right
3. This extends the SUMIFS formulas into the new period
4. Historical months now pull actual data; future months use projection formulas

### Step 7: Update Name Manager
- Open Name Manager (Ctrl+F3)
- Find `Latest_Month_of_Actuals`
- Edit to point to the new month's date
- This automatically shifts the actuals/projection boundary throughout the model

### Step 8: Verify Everything
- All accounts aligned (TRUE/FALSE checks)
- Totals reconciled
- Formulas intact
- Cross-statement flows verified
- Error check tab shows no errors
- BS balances in every period

---

## Common Issues During Roll-Forward

| Issue | Cause | Fix |
|-------|-------|-----|
| Mismatched account names | Small differences (spaces, case) | Exact string match check |
| Broken formulas | Row insertion shifted references | Check all formulas in affected area |
| New accounts missing from subtotals | Inserted row outside SUM range | Extend SUM formula to include new row |
| Source data incomplete | Partial export | Re-export full date range |
| BS does not balance after update | New account not in CF statement | Add account to appropriate CF section |

---

## Model Audit Checklist (Aharonoff)

### Pre-Delivery Checks
- [ ] All error check indicators show green / "No errors"
- [ ] Balance sheet balances in every period (Assets = L + E)
- [ ] Net income matches across P&L, BS, and CF
- [ ] Cash balance matches between BS and CF ending cash
- [ ] All source-to-destination data matches verified
- [ ] No circular references (unless intentional and documented)
- [ ] Run "Go To Special > Constants" for unauthorized hard-coded values
- [ ] Use Ctrl+/ to find formula inconsistencies
- [ ] Color coding applied consistently across all tabs
- [ ] All blue inputs actually editable and affect outputs
- [ ] All black cells contain formulas (no manual overrides)
- [ ] Instructions tab complete with color legend, tab descriptions, navigation
- [ ] Named ranges properly defined
- [ ] Test: Change input, verify flows through all three statements
- [ ] Test: Introduce error, verify error check catches it
- [ ] Formatting consistent across all tabs
- [ ] Source tabs hidden, template tab hidden
- [ ] Tab order logical
- [ ] Date formatting consistent (MMM-YY recommended)
- [ ] Number formatting consistent (accounting format)
- [ ] No #REF, #N/A, or #DIV/0 errors visible
- [ ] Quarterly and annual aggregation verified
- [ ] Margin calculations wrapped in IF(ISERROR())
- [ ] Projection drivers documented in description column

### Monthly Actualization Checks
- [ ] New export covers full date range from model start
- [ ] COUNTIF check for new accounts
- [ ] TRUE/FALSE alignment check for all accounts
- [ ] New accounts added to: drivers, financial statement, cash flow, subtotals
- [ ] Name Manager updated for latest month of actuals
- [ ] Error check tab confirmed clean after update

---

## Common Myths Debunked (Aharonoff)

1. **"All models need three statements"** -- For small businesses, yes. Larger orgs may separate revenue forecasting and headcount into standalone models.
2. **"Models are one and done"** -- Building the model is when the work BEGINS.
3. **"You don't need accounting knowledge"** -- You don't need a CPA, but understanding how accounts connect is essential.
4. **"Models should be built solo"** -- Best models are collaborative.
5. **"Models are only about projections"** -- Historical data is equally important.

---

## Cross-References

- **DADA framework and design** -> `dada-framework.md` (this skill)
- **Three-statement construction** -> `three-statement-construction.md` (this skill)
- **Drivers tab structure** -> `drivers-tab.md` (this skill)
- **BvA dashboard design** -> `dashboards-and-reporting`
- **Excel techniques for roll-forward** -> `excel-for-finance`
