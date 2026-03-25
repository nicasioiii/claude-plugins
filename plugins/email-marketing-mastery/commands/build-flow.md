---
name: Build Flow
description: Design a specific automated email flow with triggers, filters, timing, content briefs, and conditional splits. Outputs a complete flow blueprint ready for implementation in Klaviyo or other ESPs. Activates ecom-flows.
---

# Build Flow Wizard

## Step 1: Identify the Flow

Ask the user which flow they want to build:

1. **Welcome Series** -- New subscriber onboarding + first purchase
2. **Abandon Checkout** -- Recover checkout abandoners
3. **Abandon Cart** -- Recover cart abandoners (pre-checkout)
4. **Browse Abandonment** -- Re-engage product viewers
5. **Site Abandonment** -- Re-engage site visitors
6. **Post-Purchase Thank You** -- Build loyalty + collect reviews
7. **Customer Winback** -- Re-engage lapsed buyers
8. **Upsell/Cross-Sell** -- Increase LTV with complementary products
9. **Sunset Unengaged** -- Clean list of non-engagers
10. **VIP** -- Reward best customers
11. **Back-in-Stock** -- Notify interested buyers of restocks
12. **Replenishment** -- Remind for consumable reorders
13. **Date-Triggered** -- Birthday, anniversary, custom dates
14. **Holiday-Specific** -- BFCM capture + welcome

### Additional Context Needed
- **Product type:** What do you sell? Single product or multi-SKU?
- **AOV:** What is your average order value?
- **ESP:** Klaviyo, Mailchimp, or other?
- **Existing offers:** What discounts are you comfortable with?
- **Buying cycle:** How often do customers typically reorder?

---

## Step 2: Load Flow Architecture

**Load skill:** `ecom-flows` SKILL.md for the flow summary table, then the appropriate reference file.

- Pre-purchase flows -> ref-acquisition-flows.md
- Post-purchase flows -> ref-retention-flows.md

---

## Step 3: Generate Flow Blueprint

For each flow, output a complete blueprint in this format:

```
FLOW BLUEPRINT: [Flow Name]
============================

TRIGGER: [Exact trigger event]
FILTERS:
  - [Filter 1] (logic: AND/OR)
  - [Filter 2]
  - [Filter 3]

FLOW STRUCTURE:

Email 1: [Name]
  Delay: [time after trigger]
  Subject Line Direction: [type of subject line]
  Content Brief:
    - Banner: [what to show]
    - Body: [key messaging points]
    - CTA: [button text + destination]
    - Offer: [discount/incentive if any]
  Smart Sending: [ON/OFF]

[Conditional Split if applicable]
  Condition: [what to check]
  YES branch: [action]
  NO branch: [action]

Email 2: [Name]
  Delay: [time after previous]
  ...

[Continue for all emails in flow]

EXIT CONDITIONS:
  - [When subscriber exits flow]

NOTES:
  - [Implementation tips]
  - [Common mistakes to avoid]
```

---

## Step 4: Customize by AOV

If the flow involves timing or offer decisions, customize based on AOV:

| AOV Range | Timing Adjustment | Offer Adjustment |
|---|---|---|
| <$50 (impulse) | Shorter delays, faster follow-up | Smaller discounts, urgency-driven |
| $50-$100 (considered) | Standard delays | Standard offer ladder |
| $100+ (high-consideration) | Longer delays, more touchpoints | Larger discounts later, trust-building first |

---

## Step 5: Next Steps

| Need | Command / Skill |
|---|---|
| Write the actual email copy | `/write-email` command |
| Set up the pop-up that feeds this flow | `/grow-list` command |
| Define segments for flow filters | `segmentation-list-health` skill |
| Audit the full email program | `/audit-email` command |
