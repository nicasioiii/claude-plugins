---
name: Build Ecommerce Flows
description: >
  MANDATORY TRIGGERS: email flow, automated flow, welcome series, welcome flow,
  abandon checkout, abandoned cart, abandoned browse, browse abandonment, site abandonment,
  post-purchase, thank you flow, winback, win-back, customer winback, upsell flow,
  cross-sell, replenishment, back-in-stock, sunset flow, VIP flow, date-triggered,
  birthday email, Klaviyo flow, flow architecture, booster email, flow timing,
  flow triggers, flow filters, dynamic segment, offer laddering, smart sending.
  FOR: Designing and configuring automated email flows for ecommerce -- welcome series,
  abandon checkout/cart/browse/site, post-purchase thank you, winback, upsell/cross-sell,
  sunset, VIP, back-in-stock, replenishment, date-triggered, and holiday-specific flows.
  Includes triggers, filters, timing, email counts, content strategy, offer laddering,
  booster mechanics, and conditional splits.
  Do NOT use for: launch sequences for info products (use write-launch-sequence), creator
  welcome sequences (use write-welcome-sequence), campaign strategy (use plan-email-campaigns
  or email-strategy), email copywriting frameworks (use write-email-copy).
---

# Build Ecommerce Flows

## Quick Navigation
- **Welcome, abandon checkout/cart/browse/site, booster** -> ref-acquisition-flows.md
- **Post-purchase, winback, upsell, sunset, VIP, replenishment, back-in-stock** -> ref-retention-flows.md
- **Flow timing and triggers** -> Both reference files
- **Conditional splits and smart sending** -> Both reference files

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| Welcome series, abandon checkout/cart/browse/site, booster emails | ref-acquisition-flows.md |
| How many emails in welcome? What timing? What offers? | ref-acquisition-flows.md |
| Abandon checkout timing by AOV? Offer laddering? | ref-acquisition-flows.md |
| Post-purchase, winback, upsell, sunset, VIP, replenishment | ref-retention-flows.md |
| How long to wait for winback? What delay for upsell? | ref-retention-flows.md |
| Back-in-stock, date-triggered, holiday automations | ref-retention-flows.md |

---

## Cross-References

| Topic | Primary Skill | Go To |
|---|---|---|
| Pop-up forms that trigger welcome flows | list-growth-forms | `skills/list-growth-forms/SKILL.md` |
| Segment definitions for flow filters | segmentation-list-health | `skills/segmentation-list-health/SKILL.md` |
| Email body copy frameworks | write-email-copy | `skills/write-email-copy/SKILL.md` |
| Subject line craft for flow emails | write-subject-lines | `skills/write-subject-lines/SKILL.md` |
| Campaign strategy alongside flows | email-strategy | `skills/email-strategy/SKILL.md` |
| Creator/service welcome sequences | write-welcome-sequence | `skills/write-welcome-sequence/SKILL.md` |

---

## INSTRUCTOR DISAGREEMENT NOTICES

### Disagreement 1: Welcome Series Length

| Position | Advocate | Recommendation |
|---|---|---|
| 3 emails + booster | Boyan (E02) | Concise: intro+offer, story+proof, cross-pollination |
| 3-6 emails (4 standard) | MuteSix (E03) | Standard 4: intro+offer, founder letter, product+proof, last chance |
| 4 emails | Chase Dimond (E01) | Similar to MuteSix structure |

**Resolution:** 3-4 core emails + optional booster for high-AOV stores. Low-AOV impulse brands can use 3. High-AOV considered-purchase brands benefit from 4-6. The booster email is most valuable for high-AOV stores where purchase decisions take longer.

### Disagreement 2: First Abandon Checkout Delay

| Position | Advocate | Recommendation |
|---|---|---|
| 30 min to 4 hours (AOV-based) | Boyan (E02) | Low AOV (<$50): 30 min. Medium ($50-$100): 1-2 hours. High ($100+): 3-4 hours |
| 1-2 hours flat | MuteSix (E03) | Standard delay for all stores |

**Resolution:** Use E02's AOV-based logic for more nuanced timing. Low-AOV stores benefit from faster follow-up (impulse purchases), while high-AOV stores need more time (consulting family/friends).

### Disagreement 3: Smart Sending

| Position | Advocate | When |
|---|---|---|
| OFF for post-purchase | MuteSix (E03) | People expect a thank you after buying |
| ON for campaigns/browse | MuteSix (E03) | Prevents over-sending to active recipients |
| OFF for replenishment | MuteSix (E03) | Personalized, expected messaging |

**Resolution:** Turn smart sending OFF for: post-purchase, replenishment, back-in-stock (these are expected, personalized). Turn ON for: browse abandonment, campaigns, site abandonment (these are interruptive).

---

## Flow Build Priority Order

Build flows in this sequence (highest revenue impact first):

```
1. Welcome Series          -- 9-15% of email revenue
2. Abandon Checkout        -- 8-12% of email revenue
3. Abandon Cart            -- 4-8% of email revenue
4. Browse Abandonment      -- 2-5% of email revenue
5. Post-Purchase Thank You -- 54% increase in repeat customers
6. Customer Winback        -- Prevents churn, extends LTV
7. Upsell/Cross-Sell       -- Near-zero acquisition cost revenue
8. Site Abandonment        -- Sometimes beats abandon cart
9. Sunset Unengaged        -- Protects deliverability
10. VIP Flow               -- Rewards best customers
11. Back-in-Stock          -- High-intent, product-specific
12. Replenishment          -- Subscription/consumable brands
13. Date-Triggered         -- Birthday, anniversary
14. Holiday-Specific       -- BFCM capture flows
```

---

## Flow Architecture Summary Table

| Flow | Trigger | Emails | First Delay | Key Filter |
|---|---|---|---|---|
| Welcome | Subscribe to list | 3-4 + booster | Immediate | Placed order = 0 since starting |
| Abandon Checkout | Checkout started | 3-4 | 30 min - 4 hrs (by AOV) | Placed order = 0, not in flow last 7 days |
| Abandon Cart | Added to cart | 2-3 | 1-2 hours | Checkout started = 0, placed order = 0 |
| Browse Abandon | Viewed product | 1-2 | 2-4 hours | Cart/checkout/order = 0, not in flow 14 days |
| Site Abandon | Active on site | 1 | 4-6 hours | No product view/cart/checkout/order, not in flow 28-45 days |
| Post-Purchase | Placed order | 3 + split | 1 day | Cancelled/refunded = 0 |
| Winback | Placed order | 2-3 | 1.5-2x buying cycle | Placed order = 0 in last 75+ days |
| Upsell | Fulfilled order | 2 | 50% of buying cycle | No repeat order since flow start |
| Sunset | Joins unengaged segment | 2 | Immediate | Opened/clicked = 0 since start |
| VIP | 4th order (or custom) | 1-2 | 1 day | Custom threshold met |
| Back-in-Stock | Subscribe to restock alert | 1-2 | Automatic on restock | Inventory rules |
| Replenishment | Placed order | 1-2 | Product cycle (e.g., 3-6 months) | No repeat purchase |
| Date-Triggered | Custom date property | 1-3 | Before/on/after date | Date property exists |

---

## Booster Email Mechanics (E02)

The booster email is a powerful tactic for flows and campaigns:

- **What it is:** Same content resent with different subject line to non-openers
- **Conditional split:** "Has opened email [MESSAGE ID] at least once since starting this flow"
- **CRITICAL:** Use MESSAGE ID, not VARIATION ID (common mistake)
- **NO branch = send booster** 24 hours after, then wait another day for next email
- **Best for:** High-AOV stores where customers delay purchasing decisions
- **Less effective for:** Low-AOV impulse-buy stores
- **Test with:** 100-300 booster sends; expected conversion rate 1-3%
- **Real result:** One client generated $18,300 additional revenue from single booster email

---

## Offer Laddering Strategy (E02)

Progressively increase discounts as users move deeper into flows without converting:

- Email 1-3: initial offer (e.g., 10%)
- Email 4+: increased offer (e.g., 15-20%)
- Flow filters ensure purchasers never see the bigger offer
- Total flow recovers 15-25% of abandoned checkouts
- **Exception:** Don't use offer laddering for 8-figure brands where branding matters
- Offers in higher-intent flows (checkout) should always be >= offers in lower-intent flows (browse)

---

## Dynamic Segment Code (Klaviyo -- E02)

For abandon checkout/cart emails with dynamic cart contents:
- Data source: `event.extra.line_items`
- Product name: `{{ item.product.title }}`
- Quantity/price: `Quantity: {{ item.quantity|floatformat:0 }} -- Total: {% currency_format item.line_price|floatformat:2 %}`
- Image: Use variant image with fallback to product image
- Redirect: `{{ organization.url|trim_slash }}/products/{{ item.product.handle }}`
- **Hack:** Save Email 1 as template so you never recreate the dynamic segment
- Abandon cart uses SPLIT BLOCK (not table block like checkout series)
