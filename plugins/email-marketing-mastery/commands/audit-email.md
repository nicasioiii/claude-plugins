---
name: Audit Email Program
description: Comprehensive audit of an existing email marketing program -- flows, campaigns, segmentation, deliverability, KPIs. Outputs scored report with prioritized action items. Activates email-strategy, segmentation-list-health, and fix-deliverability.
---

# Email Program Audit Wizard

## Step 1: Gather Essential Information

Ask the user these questions before proceeding. Do not skip any.

### Required Inputs
1. **Business type:** Ecommerce (DTC), creator/info product, or newsletter/media?
2. **ESP:** Which email service provider? (Klaviyo, Mailchimp, Kit, Beehiiv, etc.)
3. **List size:** Total contacts and approximate engaged contacts?
4. **Monthly email revenue:** What % of total revenue comes from email?
5. **Flow vs campaign split:** What % from automations vs manual campaigns?
6. **Active flows:** Which automated flows are currently live?
7. **Campaign frequency:** How many campaigns per week/month?
8. **Average open rate:** On engaged segments? On full list?
9. **Unsubscribe rate:** Per campaign average?
10. **Spam rate:** Current spam complaint rate?

---

## Step 2: Score Each Category

### Category 1: Revenue Attribution (Load: email-strategy)
- Target: 20-50% of total revenue from email
- Score: 0-10 based on proximity to target
- Check flow vs campaign split (should be roughly even)

### Category 2: Flow Coverage (Load: ecom-flows)
Check which flows are active and score completeness:
- [ ] Welcome series (required)
- [ ] Abandon checkout (required)
- [ ] Abandon cart (required for Shopify)
- [ ] Browse abandonment (recommended)
- [ ] Site abandonment (recommended)
- [ ] Post-purchase (required)
- [ ] Customer winback (required)
- [ ] Upsell/cross-sell (recommended)
- [ ] Sunset unengaged (required)
- [ ] VIP flow (recommended)
- Score: (active flows / 10) x 10

### Category 3: Campaign Strategy (Load: email-strategy)
- Is there a consistent campaign calendar?
- Are all 6 campaign types represented (sales, announcement, holiday, content, product launch, review)?
- Is frequency appropriate (minimum 4/month)?
- Is booster/double-down strategy being used?
- Score: 0-10

### Category 4: Segmentation (Load: segmentation-list-health)
- Is there a defined engaged segment?
- Is there a VIP segment?
- Are recent purchasers excluded from promos?
- Is there a sunset/unengaged segment?
- Are segments using proper logic (OR for engaged, AND for unengaged)?
- Score: 0-10

### Category 5: Deliverability (Load: fix-deliverability)
- Are SPF, DKIM, and DMARC authenticated?
- Is spam rate below 0.2%?
- Is unsubscribe rate below 0.4%?
- Is deliverability rate above 99.5%?
- Are open rates on engaged segments above 25%?
- Score: 0-10

### Category 6: List Growth (Load: list-growth-forms)
- Is there an active pop-up form?
- Is mobile vs desktop optimized separately?
- Is the offer compelling (not just "subscribe to our newsletter")?
- Is form-to-flow connection properly set up?
- Score: 0-10

---

## Step 3: Generate Audit Report

### Report Format

```
EMAIL PROGRAM AUDIT REPORT
==========================

Business: [name]
Date: [date]
Overall Score: [total / 60] ([percentage]%)

CATEGORY SCORES:
1. Revenue Attribution:  [X/10] -- [status emoji]
2. Flow Coverage:        [X/10] -- [status emoji]
3. Campaign Strategy:    [X/10] -- [status emoji]
4. Segmentation:         [X/10] -- [status emoji]
5. Deliverability:       [X/10] -- [status emoji]
6. List Growth:          [X/10] -- [status emoji]

TOP 3 PRIORITIES (in order):
1. [Highest-impact action item]
2. [Second-highest impact]
3. [Third-highest impact]

DETAILED FINDINGS:
[Category-by-category analysis with specific recommendations]
```

---

## Step 4: Prioritized Action Plan

Generate a prioritized action plan following the implementation roadmap:
1. Fix deliverability issues first (if any)
2. Build missing core flows (in revenue-priority order)
3. Improve segmentation
4. Optimize campaign frequency and calendar
5. Improve pop-up/list growth
6. Advanced optimizations (A/B testing, microlists)

For each action item, specify:
- **What:** Specific action to take
- **Why:** Expected impact
- **How:** Step-by-step instructions (reference relevant skill)
- **When:** Priority order (do this first, second, third)

---

## Next Steps

| Need | Command / Skill |
|---|---|
| Build a specific flow | `/build-flow` command |
| Plan campaign calendar | `/plan-campaign` command |
| Optimize pop-up forms | `/grow-list` command |
| Fix deliverability | `/fix-deliverability` command |
