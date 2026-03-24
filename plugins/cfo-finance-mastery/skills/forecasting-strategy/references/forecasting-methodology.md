---
name: Forecasting Methodology
---

# Forecasting Methodology: Five-Step Process

## Overview
This reference details the complete forecasting process: from analyzing historical data to building executable 12-month projections. The goal is **directionally correct projections that improve with iteration.**

---

## The Five-Step Process

### Step 1: Establish Historical Baseline (1–2 hours)

**Objective:** Understand what actually happened in your business over the past 12–24 months.

**Actions:**
1. Pull P&L for last 24 months (or available history; can work with as little as 6 months)
2. Pull balance sheet (month-end) for last 12 months
3. Pull cash flow statement for last 12 months

**Analysis:**

**Vertical Analysis** — Each line item as % of revenue:
```
Month           Revenue    COGS    COGS %    OpEx    OpEx %    Net Income
January 2025    $100,000   $35,000   35%    $50,000   50%    $15,000
February 2025   $110,000   $38,500   35%    $52,000   47%    $19,500
March 2025      $120,000   $42,000   35%    $55,000   46%    $23,000
```

Look for **deviations:**
- If COGS is normally 35% but spiked to 40% in one month, investigate (supplier cost increase? product mix shift? waste?)
- If OpEx was 50% but dropped to 45%, understand why (hiring delayed? seasonal cost variation?)

**Horizontal Analysis** — Month-over-month and year-over-year growth:
```
Month           Revenue    MoM Growth    YoY Growth
Jan 2025        $100,000   —            15%
Feb 2025        $110,000   +10%         18%
Mar 2025        $120,000   +9%          16%
```

Key insight: MoM growth averaging 9–10% is strong; YoY 15–18% shows consistent growth.

**Month-over-Month Trend Analysis** (if you lack 2 years of history):
```
Trailing 6-Month Growth Rate = (Most Recent Month / First Month) ^ (1/5) - 1
```
Example: If revenue was $80K six months ago and $105K now: ($105K / $80K) ^ (1/5) - 1 = 6.9% monthly growth.

**Identify One-Time Events:**
- Large single customer acquisition/loss?
- Seasonal spike that won't repeat uniformly?
- Marketing campaign with unusual ROI?
- Product launch or discontinuation?

**Exclude one-time events from baseline**, or note them clearly for scenario planning.

---

### Step 2: Identify Seasonal Patterns (30–60 minutes)

**Objective:** Quantify month-to-month and quarter-to-quarter variations.

**Method 1: Simple Seasonal Multipliers**
For each historical month, calculate:
```
Seasonal Multiplier = Actual Month Revenue / Average Monthly Revenue
```

Example:
```
Average Monthly Revenue (12-month avg): $105,000

January 2025        $100,000 / $105,000 = 0.95 (5% below average)
April 2025          $115,000 / $105,000 = 1.10 (10% above average)
December 2024       $160,000 / $105,000 = 1.52 (52% above average)
```

**Apply multipliers to forward months:**
- Project April 2026 revenue = (Base growth assumption) × (April 2025 seasonal multiplier of 1.10)

**Method 2: Quarterly Breakdown** (for less granular data)
```
Q1 (Jan–Mar)    25% of annual revenue
Q2 (Apr–Jun)    24% of annual revenue
Q3 (Jul–Sep)    23% of annual revenue
Q4 (Oct–Dec)    28% of annual revenue
```

Then subdivide quarters by month (Q4 months might be 40% / 35% / 25% of quarterly total if December is biggest).

**Industry Benchmarks if No History:**

If launching a new product/business line with no historical data:

- **Retail:** Q4 = 1.6–2.0X average, Q1 = 0.7–0.8X average
- **Services:** Annual contracts renew in fiscal year (typically Sept/Oct or Jan) → revenue spikes, then declines through year
- **SaaS:** Relatively flat except holiday/back-to-school spikes (Aug, Nov–Dec)
- **Construction:** Spring/summer surge (1.3–1.5X), winter decline (0.6–0.8X)
- **E-commerce:** Black Friday/Cyber Monday (3–5X normal), January post-holiday (0.5–0.7X)

---

### Step 3: Project Revenue Growth & Build Cost Assumptions (2–3 hours)

**Step 3A: Revenue Projection**

**Method 1: Trend Continuation** (most common)
```
Next 12-Month Growth Rate = Current month-over-month growth × 12
OR
Next 12-Month Growth Rate = YoY growth from same period last year
```

Be conservative: If recent growth is 15% YoY, assume 12% forward unless specific drivers justify higher.

**Method 2: Driver-Based** (more sophisticated)
Identify key revenue drivers and project each:

Example (SaaS company):
```
Number of Customers (Month 1): 500
New Customer Acquisition: 25/month
Customer Churn: 5/month
Net Growth: +20/month = 240/year

Months 2-12: 520 + 540 + 560 ... 780 customers
ARPU (Average Revenue Per User): $1,000/month
Revenue growth follows customer growth curve
```

**Method 3: Market Opportunity + Win Rate** (for new markets)
```
Total Addressable Market (TAM): $500M
Market Growth Rate: 8%/year
Your Win Rate: 0.5% (conservative)
Your Potential Revenue: $500M × 0.5% = $2.5M
```

Then project how fast you can capture that share (typically 3–5 year horizon).

**Step 3B: Cost Assumptions**

**COGS/Cost of Revenue:**
- Express as % of revenue if relatively variable
- Example: E-commerce with COGS of 35% → assume 35% forward unless supplier contracts changing
- If COGS varies by product (high-margin vs. low-margin mix), use weighted average

**Operating Expenses:**
- **Personnel (typically 30–50% of OpEx):**
  - Current headcount × expected salary + benefits (use 1.35X salary as all-in cost)
  - Add planned hires with ramp-up period (assume 60% productivity Month 1, 100% by Month 4)

- **Marketing & Sales:**
  - If volume-driven, express as % of revenue (e.g., "we spend 8% of revenue on ads")
  - If fixed, project quarterly spend

- **Rent, Utilities, Insurance:** Typically fixed or slowly increasing (typically +2–5%/year)

- **Software/Subscriptions:** Fixed monthly + growth-based (add CRM seat at 50 employees, upgrade analytics tool at $2M revenue, etc.)

- **Professional Services (accounting, legal, consulting):** Fixed unless growth-driven (e.g., audit fees scale with revenue)

**Example Cost Structure:**
```
Revenue                        $1,200,000    100%
COGS                            $420,000     35%
Gross Profit                    $780,000     65%

OpEx:
  Payroll (6 people)            $300,000     25%
  Marketing                     $96,000      8%
  Rent/Utilities                $36,000      3%
  Software                      $24,000      2%
  Professional Services         $18,000      1.5%
Total OpEx                      $474,000     39.5%

Net Operating Income           $306,000      25.5%
```

---

### Step 4: Apply Strategic Growth Modifiers (STEP & Porter's)

See **step-framework.md** and **porters-forces.md** for detailed breakdowns.

**Simplified Approach:**
1. List 3–5 external factors likely to impact your business next 12 months
2. Estimate impact (% change to revenue, COGS, or OpEx)
3. Assign probability (High/Medium/Low or 70%/50%/20%)

Example:
```
Factor                          Impact              Probability    Adjusted Growth
Base Growth (trend continuation) +12%               100%           +12%
New competitor enters market     -3% share loss      60%            -1.8%
AI productivity tools improve    +2% efficiency      70%            +1.4%
Interest rates stay elevated     -1% customer demand 50%            -0.5%

Adjusted Forecast              +12% - 1.8% + 1.4% - 0.5% =        +11.1%
```

---

### Step 5: Stress-Test Assumptions & Build Scenarios

See **stress-testing.md** for detailed framework.

**Quick Stress-Test:**
For each major assumption, ask:
1. What's the worst-case outcome if this assumption is wrong?
2. What's the best-case outcome?
3. What early warning signs would tell us to change the forecast?

Example:
```
Assumption: "Marketing CAC will stay at $50/customer"

Worst case: CAC rises to $70 (algorithm change, market saturation)
→ Impact: If we acquire 100 customers/month at $70 CAC vs. $50, extra $2K/month cost
→ Warning signs: CAC trending up over 2 months, ROAS declining

Best case: CAC drops to $35 (viral effect, algorithm favor)
→ Impact: If CAC drops $15, marketing ROI improves significantly, can scale budget
→ Warning signs: ROAS improving, organic traffic spiking

Decision: Build base forecast at $50 CAC; have contingency if exceeds $60 two months running.
```

---

## Working Backward from Goals (If You Have a Target)

Sometimes you start with a goal (e.g., "We need $2M revenue by end of next year").

**Reverse-engineer the forecast:**
```
Goal: $2M annual revenue
Current revenue: $1.4M
Required growth: 42.9%
Months available: 12
Required monthly growth rate: 42.9% ^ (1/12) - 1 = 3.0%

Is 3.0% monthly growth achievable?
- Current trend: 1.5%/month
- Need acceleration of 1.5X

How? (Pick 2–3):
- Increase marketing budget +30% → should drive +0.5% incremental growth
- Launch new product line → should drive +0.7% incremental growth
- Improve retention (churn -2%) → keeps customers longer, compounds growth
- Total: +1.5% + 0.2% (churn) = achievable, though stretched

Conclusion: Goal is achievable with specific actions; forecast should show those actions explicitly.
```

---

## Red Flags: When to Question Your Forecast

1. **Revenue grows but expenses stay flat** → Unrealistic. Scaling requires hiring and infrastructure.
2. **Margin expands without explanation** → Be specific: "Volume discounts negotiate better supplier terms" beats "operational leverage."
3. **Major expense category is missing** → Did you account for payroll taxes, benefits? Sales commission? Software costs?
4. **One customer is >30% of revenue** → Flag concentration risk in assumptions.
5. **Growth rate is identical every month** → Unlikely unless highly predictable subscription business. Add seasonality.
6. **No downside scenario** → Lazy forecasting. Build pessimistic case to stress-test robustness.

---

## From Forecast to Action

Once forecast is built:

1. **Publish it in writing** with all assumptions documented
2. **Share with team** so everyone operates from same baseline
3. **Set reforecasting calendar** — Update monthly actuals, reforecast quarterly
4. **Use for planning** — Budget hiring, inventory, marketing spend based on forecast
5. **Track vs. actual** — If variance exceeds 15%, investigate and adjust forward months

The forecast is **not a prediction.** It's a **planning tool** that keeps the business aligned on priorities and resource allocation.
