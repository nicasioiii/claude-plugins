---
name: Build Forecast
description: Build a 12-month rolling forecast with external analysis, scenario modeling, and method selection for each P&L account. Activates forecasting-strategy skill with cross-references to financial-diagnostics for historical context.
---

# /build-forecast -- 12-Month Rolling Forecast Builder

## Step 1: Gather Context

Ask the user:

1. **Historical data:** How many months/years of actual data available?
2. **Business type:** Industry, revenue model (product, service, subscription, hybrid)?
3. **Revenue streams:** How many distinct revenue sources?
4. **Team size:** Current headcount and hiring plans?
5. **Known changes:** Any planned events (expansion, new product, price changes)?
6. **Seasonality:** Does the business have seasonal patterns?

## Step 2: External Analysis (STEP Framework)

Walk through each STEP factor with the user:

### Social
- What demographic or lifestyle trends affect demand?
- Are there seasonal patterns or events?

### Technological
- Any platform changes affecting marketing or operations?
- New tech that could reduce costs or create opportunities?

### Economic
- Interest rate environment? Consumer spending trends?
- Inflation impact on costs?

### Political
- Regulatory changes? Tax policy? Trade policy?
- Election or policy uncertainty?

**Classify each factor as headwind or tailwind.** Quantify the estimated impact where possible.

## Step 3: Scenario Framework

Build three scenarios based on STEP analysis:

1. **Base Case:** Most likely outcome with headwinds/tailwinds balanced
2. **Best Case:** Tailwinds materialize, headwinds partially mitigated
3. **Worst Case:** Headwinds materialize, tailwinds do not

Identify 3-5 swing variables and their range across scenarios.

## Step 4: Revenue Projection

Use the EPN framework:
- **Existing:** Known/contracted revenue
- **Pipeline:** CRM-based with probability weighting
- **New:** ARSR framework (Acquire, Retain, Sell, Record)

Select the appropriate revenue formula pattern (unit-based, subscription, service, ROAS-driven).

## Step 5: Expense Projection

For each P&L line item, select the appropriate method from the nine options:

| Account Type | Recommended Method |
|-------------|-------------------|
| Stable recurring | Method 1: 6-month average + buffer |
| Seasonal/annual | Method 2: Prior period reference |
| Variable with revenue | Method 3: Revenue percentage |
| Hiring-related | Method 4: Per-hire calculation |
| Contracted/fixed | Method 5: Fixed assumption |
| Gradually growing | Method 6: YoY growth |
| Annual contracts | Method 7: Annual / 12 |
| Department-specific | Method 8: Departmental intake |
| Inactive accounts | Method 9: Dormant |

Document the method and rationale for each account.

## Step 6: Headcount Plan (if applicable)

- Near-term (1-6 months): Detailed method (specific hires, salaries, start dates)
- Longer-term (7-12 months): Summarized method (department targets)
- Include full cost loading for FTEs (~120% of base salary)

## Step 7: Seasonal Adjustment

- Apply prior-year monthly weights to annual projections
- Overlay STEP-driven adjustments for known events
- Document every adjustment

## Step 8: Output and Next Steps

Deliver:
1. Base case P&L forecast (monthly for 12 months)
2. Scenario summary (best/base/worst for key metrics)
3. Key assumptions documented with methods
4. "O Shoot Fund" calculation from worst case

Suggest follow-up:
- `/forecast-to-model` to build the full three-statement model
- `/analyze-financials` to validate historical data quality first
