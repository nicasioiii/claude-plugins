---
name: Forecast to Model
description: "Convert your strategic forecast into a detailed financial model in Excel. Link revenue assumptions to P&L, balance sheet, and cash flow automatically."
---

# /forecast-to-model

Let's convert your forecast into a working financial model. I'll ask about your forecast assumptions, then build a model you can use for scenario planning and monthly updates.

**1. Do you have a forecast already?**
- Yes, I have a forecast (paste or share key assumptions)
- No, I need to build it first (we'll do /build-forecast first)
- Partial (some pieces, need to fill gaps)

**2. What's your forecast time horizon?**
- 12 months (monthly detail)?
- 3 years (annual + monthly detail for year 1)?
- 5 years (annual detail)?

**3. What revenue assumptions do you want to model?**
- Single revenue stream (product sales, services, subscriptions)?
- Multiple streams with different growth rates?
- Share assumptions (units, price, growth rate)?

**4. What cost structure applies?**
- Percent of revenue (COGS 40%, OpEx 35%)?
- Mixed (some fixed, some variable)?
- Detailed line-item breakdowns?

**5. Are you planning headcount changes?**
- Hiring additional team (when, how many, cost)?
- Contractor additions?
- Salary increases?
- Share your planned headcount timeline?

**6. Do you have other drivers to model?**
- Capex / equipment purchases?
- Loan payments or debt schedules?
- Inventory changes?
- Seasonal multipliers?

**7. What scenarios do you want to test?**
- Just base case (most likely)?
- Base + optimistic + pessimistic?
- Multiple sensitivities (what if revenue grows 10% slower)?

---

## Once You Answer, Here's What I'll Build:

**Model Architecture**
- Drivers tab (single control panel for all assumptions)
- P&L section (revenue, COGS, OpEx, net income)
- Balance sheet section (assets, liabilities, equity)
- Cash flow calculation (from P&L changes and balance sheet timing)
- Error checking (balance sheet validation)

**Drivers Tab Setup**
- Revenue drivers (units × price, growth multipliers)
- Cost drivers (% of revenue, fixed amounts)
- Headcount timeline (hiring dates, salary, benefits)
- Seasonal adjustments and one-time items

**Three Linked Statements**
- Income Statement (what's the profit?)
- Balance Sheet (what are assets/liabilities?)
- Cash Flow (when does cash actually arrive/leave?)

**Rolling Forecast Mechanism**
- Historicals pull from source data automatically (SUMIFS formulas)
- Projections overwrite with assumptions
- Named range for "last month of actuals" (easy monthly rollover)

**Scenario Tabs**
- Base case (standard forecast)
- Optimistic case (best reasonable outcome)
- Pessimistic case (worst case to stress-test)
- Sensitivity analysis (what happens if X changes?)

**Dashboard / Summary View**
- Annual and quarterly summaries
- Budget vs forecast comparison
- KPI tracking (margins, cash position, etc.)

**Monthly Update Workflow**
- Step-by-step process to add actuals and roll forecast forward
- Takes 10 minutes per month once setup

**Share your answers and forecast assumptions above** and I'll build your model.
