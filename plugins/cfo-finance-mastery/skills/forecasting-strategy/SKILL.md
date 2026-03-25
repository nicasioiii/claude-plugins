---
name: Forecasting Strategy
description: "MANDATORY TRIGGERS: forecast, 12-month forecast, rolling forecast, scenario planning, scenario modeling, best case, worst case, base case, STEP framework, Porter's Five Forces, headwind, tailwind, projection method, revenue projection, EPN framework, ARSR framework, headcount projection, seasonal adjustment, P&L projection, revenue formula, subscription revenue, unit-based revenue, o shoot fund, reforecasting, three-scenario model. FOR: Anyone who needs to build a 12-month rolling forecast, analyze external factors affecting projections, choose projection methods for P&L accounts, model scenarios, project revenue using EPN/ARSR frameworks, or plan headcount. Do NOT use for: [diagnosing existing financial statements] use financial-diagnostics; [building the actual 3-statement model in Excel] use financial-modeling; [Excel formula help] use excel-for-finance; [dashboard design for forecast output] use dashboards-and-reporting; [ratio analysis] use financial-ratios."
---

# Forecasting Strategy

You are a financial forecasting strategist. Your job is to help users build forward-looking projections grounded in both external analysis and formula-driven methods. Every forecast must be defensible: assumptions documented, scenarios explored, and methods matched to account behavior.

**Instructor synthesis:** Leikauf (CFO Mastery) focuses on external-environment-driven forecasting -- STEP framework, Porter's Five Forces, headwind/tailwind classification. Aharonoff (Financial Modeling) focuses on formula-driven projection mechanics -- nine P&L methods, EPN/ARSR revenue frameworks, headcount projection. These are complementary, not conflicting. The workflow is: (1) use Leikauf's frameworks to set assumptions, (2) use Aharonoff's methods to implement them in the model.

---

## Forecasting Principles

- **12-month rolling forecasts** are the standard. Update monthly with actuals.
- Use **current context over past trends alone** (Leikauf). History informs but does not dictate.
- Build **three scenarios:** Best, Base, and Worst case.
- A forecast is a living document. "One and done" is a myth (Aharonoff).
- The more **collaborative** the forecasting process, the more defensible the projections (Aharonoff).

---

## Phase 1: External Analysis (Leikauf)

Before building any numbers, analyze the environment. This sets the assumptions that drive the forecast.

### STEP Framework

| Factor | What to Analyze |
|--------|----------------|
| **S**ocial | Demographics, attitudes, lifestyle shifts, seasonal demand patterns |
| **T**echnological | R&D, innovation, AI disruption, platform algorithm changes |
| **E**conomic | Interest rates, spending trends, market cycles, inflation |
| **P**olitical | Legislation, taxes, regulations, election impact, trade policy |

For each factor, classify as a **headwind** (barrier to growth) or **tailwind** (growth driver).

### Porter's Five Forces

1. **Rivalry among existing firms** -- More competition = harder to grow and maintain margins
2. **Threat of new entrants** -- Low barriers = risk of new competitors
3. **Supplier power** -- Powerful suppliers can raise costs, pressure margins
4. **Buyer power** -- Easy switching for customers = pricing pressure
5. **Threat of substitutes** -- Alternatives limit pricing power

**Application to forecasting:** Use alongside STEP to adjust revenue and cost assumptions. High rivalry + strong buyer power = conservative revenue growth. Weak supplier power + low substitutes = stable COGS projections.

---

## Phase 2: Scenario Modeling

### Three Scenarios

| Scenario | Description | Assumption Basis |
|----------|-------------|-----------------|
| **Best Case** | Everything works under ideal conditions | Realistic optimism. NOT exaggerated growth. |
| **Base Case** | Most likely outcome | Blend of realism and caution, incorporating headwinds/tailwinds |
| **Worst Case** | A few major setbacks (not catastrophe) | External risks from STEP + Porter's applied |

### Building Scenarios
1. Start with base case as the primary forecast
2. Identify 3-5 key variables that swing outcomes (revenue growth, key cost items, collection speed)
3. For best case: apply optimistic but realistic values to those variables
4. For worst case: apply STEP/Porter-derived risk scenarios
5. Each scenario should represent a plausible future, not a fantasy or nightmare

### "O Shoot Fund" (Leikauf)
Worst-case planning supports building cash reserves. The worst case scenario tells you how much buffer you need. This is more actionable than generic "save 3 months of expenses."

### Decision-Making Across Scenarios
Choose strategies that work in all three scenarios. If an investment only pays off in the best case, it is too risky. If it survives the worst case, it is worth pursuing.

---

## Phase 3: Revenue Projection (Aharonoff)

### EPN Framework
Breaks revenue sources into three categories:

**E -- Existing Customers:** Active contracts, regular purchase patterns, renewable agreements. Most predictable revenue source.

**P -- Pipeline Customers:** Tracked in CRM with defined close probabilities and timelines. Apply probability weighting to expected revenue.

**N -- New Customers:** Future customers not yet engaged. Use the ARSR framework (below) to project.

### ARSR Framework (for New Customer Revenue)

**A -- Acquire:** How will you get new customers? What marketing channels, sales processes, growth strategies?

**R -- Retain:** What are retention patterns? Monthly contracts, annual agreements, one-time purchases?

**S -- Sell:** Define pricing strategy. Fixed product pricing, tiered models, customer segmentation, average transaction values.

**R -- Record:** How revenue impacts other statements. COGS implications, inventory needs, deferred revenue treatment, sales commissions.

### Revenue Formula Patterns

**Unit-based:**
```
Monthly Revenue = (Base Units + Monthly_Increase x Month_Number) x Price_Per_Unit
```
Example: 600 units at $100, growing 20 units/month:
```
= (600 + 20 * month_number) * 100
```

**Subscription:**
```
Monthly Revenue = (Base_Users + New_Monthly_Users x Month_Number) x Monthly_Fee
```
Example: 25 users at $500/month, adding 3 new users/month:
```
= (25 + 3 * month_number) * 500
```

---

## Phase 4: P&L Projection Methods (Aharonoff)

Nine methods for projecting P&L line items. Different accounts deserve different methods.

| # | Method | Best For |
|---|--------|----------|
| 1 | **6-Month Average + Buffer** | Stable, recurring expenses |
| 2 | **Prior Period Reference** | Seasonal/annual recurring items |
| 3 | **Revenue Percentage** | Variable costs that scale with sales |
| 4 | **Per-Hire Calculations** | Recruiting, onboarding costs |
| 5 | **Fixed Assumptions** | Contracted costs, rent, subscriptions |
| 6 | **YoY Growth** | Gradually growing expenses |
| 7 | **Annual / 12** | Annual contracts, professional fees |
| 8 | **Departmental Intake** | Costs best estimated by department heads |
| 9 | **Dormant Accounts** | Inactive GL accounts (project as zero) |

**Method selection principle:** There is no single correct method. Different accounts need different approaches. The goal is accuracy and practicality, not consistency of method (Aharonoff contrarian).

---

## Phase 5: Headcount Projection (Aharonoff)

### Detailed Method
Import current team: title, start date, salary, department. Split FTE vs contractors.

**Total cost per FTE:**
```
Base Salary (prorated for start/end dates)
+ Payroll Taxes (~8%)
+ Health Benefits (~10%)
+ Payroll Admin Fees
+ Other Employee-Specific Costs
= Total Cost (~120% of base salary)
```

Contractors: base cost only (no burden).

### Summarized Method
Two inputs per department: planned hires and average cost per hire.
```
Projected Payroll = Planned_Hires x Avg_Cost_Per_Hire
```

### Hybrid Approach (Recommended)
- Detailed method for near-term (6-12 months) with specific hiring plans
- Summarized method for longer-term where exact details are uncertain
- Prorate salaries for mid-month starts (do NOT just divide annual by 12)

---

## Forecast Template Structure (Leikauf)

```
Revenue Section:
  Seasonal/Event Impact (% adjustment per month)
  Normal Growth (% per month)
  Gross Revenue -> Discounts -> Refunds -> Net Revenue

COGS Section:
  COGS (as % of Net Revenue)
  Shipping, Transaction Fees, Fulfillment (each as %)
  => Total COGS -> COGS Margin %

Gross Profit + Gross Margin %

Operating Expenses:
  Personnel by department
  Advertising, Technology, Professional Services
  => Total OPEX

EBITDA / Operating Income + Operating Margin
  - D&A, Interest
  => Profit Before Tax
  - Income Tax
  => Profit After Tax
```

---

## Seasonal Adjustment

Build seasonal patterns from prior-year data:
1. Calculate each month as % of annual total (prior year)
2. Apply percentage pattern to projected annual total
3. Overlay STEP-driven adjustments (events, campaigns, policy changes)
4. Document rationale using cell comments (Shift+F2)

---

## Cross-References

- **Diagnostic findings feed forecast assumptions** -> `financial-diagnostics`
- **Ratios help set growth targets** -> `financial-ratios`
- **Forecast feeds the three-statement model** -> `financial-modeling` (drivers tab, projection formulas)
- **Profit lever assumptions in forecast** -> `profit-optimization`
- **Presenting forecast to stakeholders** -> `advisory-communication`
