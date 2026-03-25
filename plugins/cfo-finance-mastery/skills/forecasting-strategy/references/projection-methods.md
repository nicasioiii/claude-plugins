---
name: "Projection Methods"
description: "Nine P&L projection methods with formulas and use cases, EPN and ARSR revenue frameworks, headcount projection (detailed/summarized/hybrid), revenue formula patterns, seasonal adjustment techniques."
when_to_read: "When the user needs to choose a projection method for a specific account, build revenue projections, plan headcount, apply seasonal adjustments, or needs the specific formula for any projection method."
---

# Projection Methods -- Complete Reference

## Nine P&L Projection Methods (Aharonoff)

### Method 1: Six-Month Average + Buffer
**Formula:**
```
= AVERAGE(last 6 months) * 1.05
```
**Best for:** Relatively stable, recurring expenses (utilities, software subscriptions, insurance).
**When to use:** When the expense has been consistent with minor variations.
**Warning:** Do not use for seasonal or rapidly changing accounts.

### Method 2: Prior Period Reference
**Formula:**
```
= Same_Month_Prior_Year
```
**Best for:** Seasonal businesses with predictable annual patterns. One-time annual events (annual audit, insurance renewal, annual conference).
**When to use:** When seasonality is the dominant driver.

### Method 3: Revenue Percentage
**Formula:**
```
= Revenue x Percentage
```
**Best for:** Sales commissions, credit card processing fees, variable shipping costs, merchant fees -- any cost that scales directly with revenue.
**When to use:** When historical analysis shows a stable ratio to revenue.
**Validation:** Always check the historical % and verify it is stable. If it varies significantly, investigate why before projecting.

### Method 4: Per-Hire Calculations
**Formula:**
```
= New_Hire_Salary x Recruiting_Fee_Percentage
```
**Best for:** Recruiting fees, onboarding costs, equipment for new hires, training expenses.
**When to use:** When costs are triggered by hiring events.

### Method 5: Fixed Assumptions
**Formula:**
```
= Specific_Dollar_Amount (constant across periods)
```
**Best for:** Contracted costs with known amounts (rent, equipment leases, retainer fees).
**When to use:** When there is a signed contract or well-understood fixed cost.
**Note:** Step-fixed costs should be modeled with breakpoints (e.g., rent doubles when second location opens in Month 8).

### Method 6: Year-Over-Year Growth
**Formula:**
```
= Prior_Year_Same_Month x (1 + Growth_Rate)
```
**Best for:** Accounts that grow gradually (general office expenses, minor subscriptions, insurance premiums).
**When to use:** When the account has a clear growth trajectory.

### Method 7: Annual Inputs / 12
**Formula:**
```
= Annual_Contract_Amount / 12
```
**Best for:** Professional service fees billed annually, annual software contracts, memberships.
**When to use:** When the total annual cost is known but the timing within the year is even.
**Warning:** If timing is uneven (e.g., large payment in Q1), use fixed assumption or prior period reference instead.

### Method 8: Departmental Intake
**Formula:** No formula -- gather specific input from department heads via structured forms.
**Best for:** Costs where department managers have the clearest visibility (travel, training, project-specific expenses).
**When to use:** One of the most valuable approaches. Department heads know what is coming in their area better than finance does.

### Method 9: Dormant Accounts
**Formula:**
```
= 0
```
**Best for:** Inactive GL accounts with no expected activity.
**When to use:** Perfectly valid for accounts that have been zero for months with no planned activity.

### Method Selection Guide
| Account Characteristic | Recommended Method |
|-----------------------|-------------------|
| Stable, recurring | Method 1 (6-month avg) |
| Annual/seasonal | Method 2 (prior period) |
| Scales with revenue | Method 3 (revenue %) |
| Tied to hiring | Method 4 (per-hire) |
| Contracted/fixed | Method 5 (fixed) |
| Gradual growth trend | Method 6 (YoY growth) |
| Known annual total | Method 7 (annual/12) |
| Department-specific | Method 8 (intake) |
| No activity expected | Method 9 (dormant) |

**[CONTRARIAN] Different methods for different accounts is expected and correct (Aharonoff).** There is no single correct projection method. The goal is accuracy and practicality, not consistency of method. Mix and match based on each account's behavior.

---

## Revenue Projection Frameworks (Aharonoff)

### EPN Framework

**E -- Existing Customers**
- Active contracts with known revenue
- Regular purchase patterns (calculate average order value x frequency)
- Renewable agreements (apply historical renewal rate)
- Most predictable source -- start here

**P -- Pipeline Customers**
- Tracked in CRM (Salesforce, HubSpot)
- Apply close probability weighting:
```
Expected Revenue = Deal_Value x Close_Probability
```
- Time based on expected closing timeline
- Review pipeline quality with sales team

**N -- New Customers**
- Use ARSR framework (below) to estimate
- Least predictable -- build conservative base case
- This is where scenario modeling adds the most value

### ARSR Framework (for New Customer Revenue)

**A -- Acquire:** Marketing channels, conversion rates, cost per acquisition
```
New_Customers = Marketing_Spend / CPA
```

**R -- Retain:** Retention rates by cohort, churn assumptions
```
Active_Customers_Month_N = Prior_Customers x (1 - Monthly_Churn)
```

**S -- Sell:** Average deal size, pricing tiers, upsell rates
```
Revenue_Per_Customer = Avg_Order_Value x Purchase_Frequency
```

**R -- Record:** COGS per customer, deferred revenue treatment, commission structure

### Revenue Formula Examples

**Unit-based product business:**
```
= (Base_Units + Monthly_Growth x Month_Number) x Price_Per_Unit
```

**Subscription business:**
```
= (Base_Subscribers + Net_New_Monthly x Month_Number) x Monthly_Fee
```

**Service business:**
```
= Number_of_Clients x Avg_Monthly_Retainer
```

**E-commerce with ROAS:**
```
= Ad_Spend x ROAS_Target
```

---

## Headcount Projection (Aharonoff)

### Detailed Method
For near-term projections where specific hires are planned.

**Data needed per employee:**
- Title, department, start date
- Base salary (annual)
- FTE vs contractor status

**Cost buildup for FTEs:**
```
Base Salary (prorated by start date)
+ Payroll Taxes: 8% of salary
+ Health Benefits: 10% of salary
+ Payroll Admin Fees: fixed per employee
+ Other (equipment, training)
= Total Cost (~120% of base)
```

**Proration for mid-month starts:**
```
Monthly Cost = (Annual Salary / 12) x (Working Days Remaining / Total Working Days in Month)
```
Do NOT simply divide annual salary by 12 for partial months.

### Summarized Method
For longer-term projections where specific hires are unknown.

**Two inputs per department:**
1. Number of planned hires per period
2. Average cost per hire (fully loaded)

```
= Planned_Hires x Avg_Loaded_Cost
```

### Hybrid Approach (Recommended)
- **Months 1-6:** Detailed method (specific people, specific costs)
- **Months 7-12:** Summarized method (headcount targets by department)

---

## Seasonal Adjustment Technique

1. Pull prior year monthly revenue (or any seasonal account)
2. Calculate each month as % of annual total:
```
Month_Weight = Month_Revenue / Annual_Revenue
```
3. Apply weights to new year's projected annual total:
```
Projected_Month = Annual_Projection x Month_Weight
```
4. Overlay STEP adjustments (e.g., "October -15% due to algorithm change")
5. Document every adjustment with cell comments

---

## Cross-References

- **External factors driving assumptions** -> `external-analysis.md` (this skill)
- **Scenario modeling for projections** -> `scenario-modeling.md` (this skill)
- **Building projections into the model** -> `financial-modeling/drivers-tab.md`
- **Revenue formula patterns in Excel** -> `excel-for-finance`
