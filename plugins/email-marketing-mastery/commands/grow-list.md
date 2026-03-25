---
name: Grow List
description: Design a list growth strategy including pop-up optimization, paid acquisition funnels, organic growth levers, and recommendation networks. Outputs a growth plan with pop-up specs, funnel architecture, and growth projections. Activates list-growth-forms and segmentation-list-health.
---

# Grow List Wizard

## Step 1: Gather Essential Information

Ask the user these questions before proceeding.

### Required Inputs
1. **Business type:** Ecommerce (DTC), creator/info product, or newsletter/media?
2. **Current list size:** How many subscribers? How many engaged?
3. **Monthly website traffic:** Approximate unique visitors per month?
4. **Current capture method:** Pop-up, footer form, landing page, none?
5. **Current capture rate:** What % of visitors subscribe? (if known)
6. **Growth goal:** Target list size or subscriber growth rate?
7. **Budget for growth:** Any budget for paid acquisition?
8. **ESP:** Klaviyo, Kit, Beehiiv, Mailchimp, or other?

---

## Step 2: Route by Business Type

### Ecommerce Growth Plan
**Load:** `list-growth-forms` -> ref-popup-optimization.md

Focus areas:
1. Pop-up form optimization (offer, behavior, aesthetic)
2. Traffic-source-specific pop-ups
3. Holiday-specific capture
4. Form-to-flow connection

### Newsletter Growth Plan
**Load:** `list-growth-forms` -> ref-newsletter-growth.md

Focus areas:
1. Paid acquisition arbitrage system
2. Organic growth levers
3. Recommendation networks
4. Content-as-growth strategy

### Creator/Service Growth Plan
**Load:** Both reference files

Focus areas:
1. Lead magnet optimization
2. Landing page conversion
3. Quiz funnel for segmentation
4. Organic + paid hybrid strategy

---

## Step 3: Pop-Up Audit (Ecommerce)

If the user has an existing pop-up, audit it:

### Offer Assessment
- What is the current offer? Rate against the conversion ranking:
  1. No offer (lowest)
  2. Info product
  3. Fixed discount ($X off)
  4. Percentage discount (X% off)
  5. Free shipping
  6. Free item
  7. Giveaway (highest but lowest quality)
- **Recommendation:** Move up the ranking if conversion rate is below 5%

### Behavior Assessment
- Mobile: Is there a scroll/time delay? (Never load immediately)
- Desktop: Is exit intent enabled?
- Re-show delay: 5-14 days?
- Excluding existing subscribers?
- Excluding cart/checkout pages?

### Connection Assessment
- Is form connected to correct ESP list?
- Does list trigger the welcome flow?
- Is first-name field included (with fallback)?

---

## Step 4: Generate Growth Plan

```
LIST GROWTH PLAN
================

Business: [name]
Current List: [size]
Target: [goal]
Timeline: [months]

IMMEDIATE ACTIONS (Week 1-2):
1. [Highest-impact change -- usually offer or behavior]
2. [Second change]
3. [Third change]

SHORT-TERM (Month 1-3):
1. [Pop-up optimization / landing page creation]
2. [Form-to-flow connection setup]
3. [Traffic source segmentation]

MEDIUM-TERM (Month 3-6):
1. [Paid acquisition testing (if budget)]
2. [Organic growth levers activation]
3. [Recommendation network setup]

PROJECTED RESULTS:
- Current capture rate: [X%]
- Target capture rate: [Y%]
- Expected monthly new subscribers: [Z]
- Time to goal: [months]
```

---

## Step 5: Paid Acquisition Plan (If Budget Available)

For newsletter/creator businesses with paid acquisition budget:

### The Arbitrage System Blueprint
```
PAID ACQUISITION FUNNEL
========================

Ad Platform: Meta / LinkedIn / [Other]
Target CPA: $[X] per subscriber
Daily Budget: $[X]

FUNNEL:
1. Ad Creative -> [Format: UGC / Static / Text Overlay]
2. Landing Page -> [Headline + CTA + Social Proof]
3. Post-Signup -> [Quiz / Thank You / Direct to Content]
4. Welcome Sequence -> [7 emails, Problem > Solution > Monetize]

MONETIZATION CHECKPOINT:
- Quiz results page revenue: $[X] per subscriber
- Welcome sequence revenue: $[X] per subscriber
- 30-day LTV target: $[X] (must exceed CPA)
```

---

## Step 6: Next Steps

| Need | Command / Skill |
|---|---|
| Build the welcome flow for new subscribers | `/build-flow` command |
| Write welcome sequence copy | `/write-welcome` command |
| Set up segments for new subscribers | `segmentation-list-health` skill |
| Audit full email program | `/audit-email` command |
