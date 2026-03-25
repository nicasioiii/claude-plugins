---
name: Optimize Funnel
description: Run a CRO diagnostic process on an existing funnel. Asks for current metrics by funnel stage, identifies the bottleneck, and produces a prioritized test backlog with expected impact using the 5D system and Position/Price/Switch framework.
---

# /optimize-funnel -- Funnel CRO Diagnostic & Test Planner

## INTAKE QUESTIONS (Ask All Before Diagnosing)

### Question 1: Funnel Type & Structure
**What does your funnel look like?**
- What pages are in your funnel? (sales page, checkout, upsell 1, upsell 2, etc.)
- What is the front-end product and price?
- What upsells/bumps do you have? (products and prices)
- What platform are you using? (ThriveCart, SamCart, ClickFunnels, Shopify, etc.)

### Question 2: Current Metrics by Stage
**What are your current conversion numbers?**

| Metric | Their Number |
|--------|-------------|
| Traffic volume (visitors/week or month) | |
| Sales page conversion rate | |
| Bump take rate | |
| Upsell 1 take rate | |
| Upsell 2 take rate (if applicable) | |
| Upsell 3+ take rates (if applicable) | |
| Overall AOV | |
| CPA (cost to acquire a customer) | |
| Cart abandonment rate (if known) | |

### Question 3: Traffic Source
**Where is your traffic coming from?**

| Source | Implications |
|--------|-------------|
| A) Meta (Facebook/Instagram) ads | Check platform congruency, test platform-specific pages |
| B) Google ads | Check search intent match, landing page relevance |
| C) YouTube ads | Check video-to-page congruency |
| D) Organic (content, SEO, social) | Typically warmer traffic, conversion should be higher |
| E) Email list | Warmest traffic, highest expected conversion |
| F) Multiple sources | Need to segment data by source |

### Question 4: Data Volume
**How many customers have gone through this funnel?**
- Under 30: Too early to diagnose reliably. Focus on getting more traffic.
- 30-100: Can make initial assessments. Flag urgent issues (AOV under $70).
- 100+: Reliable data. Full diagnostic and test planning possible.

### Question 5: What Have You Already Tested?
**Have you made any changes or run any tests?**
- List any recent changes (copy rewrites, price changes, product swaps)
- Any A/B tests run and their results
- How long has the current version been running?

---

## DIAGNOSTIC PROCESS

### Step 1: Load CRO Framework
Load `funnel-cro` for:
- Diagnostic signals table
- Position/Price/Switch framework
- 9 conversion levers
- Compound testing methodology
- Benchmark data

### Step 2: Compare Against Benchmarks
Compare each metric against industry benchmarks:

| Metric | Benchmark | Source |
|--------|-----------|--------|
| Sales page conversion (cold) | 1-3% | Georgi, Katie |
| Sales page conversion (warm) | 3-7% | Gusten |
| Bump take rate | 25-40% (target 40%+) | Katie |
| Upsell 1 take rate | 10-20% | Katie |
| Upsell 2 take rate ($197) | 10-15% | Katie |
| Upsell 3+ take rate | 5-12% | Katie |
| Overall AOV minimum | $70 | Katie |
| Cart abandonment recovery | 15% target | Georgi |

### Step 3: Identify the Bottleneck
Use the diagnostic signals table to determine what is underperforming and why:

**If sales page conversion is low:** Copy, offer, or traffic mismatch. Load `sales-page-copy` or `vsl-sales-copy`.
**If bump is low:** Copy or alignment issue. Apply 4-Part bump copy structure from `upsell-downsell-strategy`.
**If upsells are low:** Apply Position/Price/Switch framework from `funnel-cro`.
**If AOV is under $70:** Urgent -- fix using Position/Price/Switch. May need to raise upsell prices.
**If checkout abandonment is high:** Load `checkout-optimization` for trust elements, payment plans, form simplification.

### Step 4: Load Relevant Bottleneck Skill
Based on the identified bottleneck, load the appropriate skill for detailed guidance:
- Copy bottleneck -> `sales-page-copy` or `vsl-sales-copy`
- Offer bottleneck -> `offer-stack-design` or `upsell-downsell-strategy`
- Checkout bottleneck -> `checkout-optimization`
- Traffic quality bottleneck -> defer to paid-ads-mastery plugin

---

## OUTPUT FORMAT

Deliver the optimization plan as:

1. **Funnel Health Scorecard** -- Each metric rated as Healthy / Needs Work / Critical with comparison to benchmarks

2. **Primary Bottleneck Identification** -- The single biggest leverage point (where fixing one thing has the largest revenue impact)

3. **Prioritized Test Backlog** -- Ordered list of tests to run:
   - Test name
   - What to test (variant A vs. variant B)
   - Which conversion lever it pulls
   - Expected impact (% improvement estimate)
   - Data required to declare a winner
   - Priority (1 = run first, 2 = run next, etc.)

4. **Revenue Projection** -- If the top 3 tests win at expected rates, calculate the compound improvement on monthly revenue

5. **Quick Wins** -- Any changes that do not require testing (e.g., adding missing trust badges, fixing broken mobile layout, adding "no subscription" text)

6. **Next Review Date** -- When to re-assess (typically after 30 customers or 2 weeks of data on the first test, whichever comes first)
