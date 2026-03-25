---
name: Forecast to Model
description: Convert forecast assumptions into a three-statement financial model. Guides through DADA framework, tab architecture, drivers tab construction, BS projection, CF connection, error checks, and model audit. Activates financial-modeling skill with cross-references to forecasting-strategy for assumptions.
---

# /forecast-to-model -- Three-Statement Model Builder

## Step 1: Assess Readiness

Ask the user:

1. **Forecast complete?** Have they built P&L projections? (If not, suggest `/build-forecast` first)
2. **Historical data:** Do they have historical financials to include as actuals?
3. **Chart of accounts:** Do they have a COA or GL export?
4. **Balance sheet data:** Do they have opening BS balances?
5. **Model purpose:** M&A, board reporting, or business insights?
6. **Audience:** Who will use this model? (Determines detail level and DADA priorities)

## Step 2: Model Architecture (DADA Framework)

Guide the user through the tab architecture:

### Visible Tabs (in order)
1. **Instructions** -- Color legend, tab descriptions, navigation links, flow diagram
2. **Summary Financials** -- Dashboard view of all three statements
3. **Drivers** -- Central assumption control panel
4. **Income Statement** -- Detailed P&L
5. **Balance Sheet** -- Detailed BS
6. **Cash Flow Statement** -- Derived from BS changes
7. **Error Checks** -- Comprehensive validation

### Hidden Tabs
- **Source tabs** -- Accounting exports (P&L data, BS data)
- **Template tab** -- Blueprint for new sections

### Named Ranges to Create
- `Company_Name` -- single cell referenced everywhere
- `Latest_Month_of_Actuals` -- date cell controlling actuals/projection boundary
- `error_check` -- comprehensive error result displayed on every tab

## Step 3: Drivers Tab Construction

Guide through building the drivers tab:

1. **P&L Section:** Copy account names from COA, remove subtotals, add SUMIFS for historicals
2. **BS Section:** Same approach, using INDEX for point-in-time balances
3. **Mapping Column:** Bridge detailed accounts to summary categories
4. **Driver Description Column:** Document the projection method for each account
5. **Three time views:** Monthly (primary), quarterly, annual

**Key distinction:** Drivers tab is the ONLY place where historical and projection formulas differ.

## Step 4: Build Income Statement

- Reference drivers tab for all line items
- Build calculated rows (gross profit, operating income, net income)
- Add margin calculations with IF(ISERROR()) wrappers
- Apply consistent formatting and color coding

## Step 5: Build Balance Sheet

- Reference drivers tab for all accounts
- Default all projections to prior period values first (never zero)
- Apply key account formulas:
  - AR: Beginning + Revenue - Collections
  - AP: Beginning + Purchases - Payments
  - Accumulated Dep: Prior + Current Dep Expense
  - Retained Earnings: Prior RE + Current Net Income
- Verify: Assets = Liabilities + Equity (every period)

## Step 6: Build Cash Flow Statement

- Copy BS structure
- Replace values with change formulas (Prior - Current for assets, Current - Prior for liabilities)
- Organize into Operating, Investing, Financing
- Remove cash row (derived, not input)
- Calculate ending cash: Beginning + Operating + Investing + Financing

## Step 7: Close the Loop

- Link BS cash account to CF ending cash
- Verify BS balances in every period
- Test: change one input, verify flow-through to all three statements

## Step 8: Error Checks

Build error check tab monitoring:
- Balance sheet equation (every period)
- Revenue match (drivers vs P&L vs summary)
- Cash alignment (drivers vs CF ending cash)
- Net income consistency (P&L vs BS)
- Source-to-destination matches

## Step 9: Color Coding and Polish

- Blue: all editable inputs
- Black: all formulas and historicals
- Purple: cross-tab references
- Red: error check rows
- Apply using Go To Special > Constants method

## Step 10: Model Audit

Run through the complete audit checklist from actualization-and-rollforward.md:
- Pre-delivery checks (25+ items)
- Deliberately introduce and catch an error
- Verify instructions tab is complete
- Confirm tab order and hidden tabs

## Step 11: Actualization Setup (if including actuals)

- Set up source tabs for accounting exports
- Create `Latest_Month_of_Actuals` named range
- Build COUNTIF account detection formulas for future roll-forwards
- Document the monthly roll-forward procedure for the user

Suggest follow-up:
- `/build-dashboard` to create a BvA dashboard from the model
- `/explain-to-stakeholder` to present the model to the board
