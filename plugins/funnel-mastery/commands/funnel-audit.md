---
name: Funnel Audit
description: Diagnose an existing funnel's performance. Evaluates economics, identifies bottlenecks, and outputs a prioritized action plan with specific fixes.
---

# /funnel-audit -- Funnel Performance Diagnosis

## INTAKE QUESTIONS (Ask All Before Diagnosing)

### Question 1: Funnel Type
**What type of funnel are you running?**
- A) Low-ticket digital product ($7-$100 front-end)
- B) SLO / Self-Liquidating Offer
- C) VSL / Webinar funnel
- D) Application funnel (high-ticket)
- E) DTC / Physical product
- F) SaaS
- G) Other (describe)

### Question 2: Current Metrics
**Share your current numbers (as many as you have):**
- Monthly traffic to funnel entry point
- Cost per click / CPM
- Opt-in or landing page conversion rate
- Purchase conversion rate
- Average Order Value (AOV)
- Customer Acquisition Cost (CPA/CAC)
- Order bump take rate
- Upsell 1 take rate + price
- Upsell 2 take rate + price (if applicable)
- Monthly revenue from funnel
- Backend email revenue (if applicable)

### Question 3: Traffic Source
**Where does your traffic come from?**
- A) Meta (Facebook/Instagram) ads
- B) Google ads
- C) YouTube ads
- D) Native ads (Taboola/Outbrain)
- E) Organic content
- F) Email list
- G) Multiple sources (list them)

### Question 4: History
**How long has this funnel been running, and what have you already tested?**

---

## DIAGNOSIS PROCESS

### Step 1: Economics Check (Load funnel-economics)
- Calculate LTGP:CAC ratio
- Assess CFA level (1, 2, or 3)
- Compare AOV against $70 minimum (low-ticket) or appropriate benchmark
- Identify if the funnel is profitable, break-even, or losing money

### Step 2: Bottleneck Identification (Load funnel-cro)
- Compare each metric against benchmarks in economics-benchmarks.md
- Identify which stage has the biggest gap between actual and benchmark
- Apply diagnostic signals table to determine if issue is copy, price, or product

### Step 3: Prioritized Action Plan
- Rank fixes by impact (Georgi's optimization lever priority: CPA > AOV > LTV > COGS)
- For each fix, specify which skill to load for detailed guidance
- Include expected impact range for each fix

### Step 4: Output
Deliver a structured diagnosis:
1. **Economics Summary** -- Current state, CFA level, key ratios
2. **Primary Bottleneck** -- Where the biggest leak is
3. **Secondary Issues** -- Other areas below benchmark
4. **Prioritized Action Items** -- Specific fixes in order of impact
5. **Expected Impact** -- What improved metrics would mean for revenue
