---
name: Acquisition Flows (Welcome, Abandon Checkout/Cart/Browse/Site)
description: >
  When to Read: User asks about welcome series architecture, abandon checkout/cart/browse/site
  flows, booster email setup, flow timing, offer laddering, dynamic segments, or
  pre-purchase automated sequences.
  Cross-references: ref-retention-flows.md for post-purchase flows,
  list-growth-forms for pop-up to flow connection.
---

# Acquisition Flows

## Welcome Series

### E02 Architecture (Boyan -- 3 emails + booster)

**Trigger:** Subscribes to [MAIN_LIST]
**Filter:** Placed order 0 times since starting flow
**Length:** 3 emails + 1 booster

| Email | Content | Purpose |
|---|---|---|
| Email 1 | Brand intro + offer (banner + offer + CTA) | Convert first-time buyers; highest revenue email in flow |
| Booster | Same content as Email 1, different subject line | Sent to non-openers of Email 1; conditional split on open |
| Email 2 | Brand story/values/benefits + social proof + offer | Build trust; authority hijacking, testimonials, influencer reviews |
| Email 3 | Cross-pollination + offer with urgency | Drive traffic to strongest social channel; ONE CTA only |

### E03 Architecture (MuteSix -- 3-6 emails, standard 4)

**Trigger:** Subscribe to list (via welcome pop-up)
**Filter:** Place Order = 0 times since starting this flow
**Length:** 3-6 emails (4 standard), spread over 3-7 days

| Email | Wait | Content | Discount |
|---|---|---|---|
| 1 | Immediate | Brand intro, mission, values, reiterate pop-up offer | Initial discount (e.g., 10%) |
| 2 | 1 day | Company story, founder letter (personalized, plain text) | Same discount |
| 3 | 2 days | Product-specific uses, customer reviews, social proof | Same discount |
| 4 | 2-3 days | Last chance / urgency -- "discount expires in 48 hours" | Same or stacked (higher) |

### Welcome Series Key Tactics (Synthesized)
- Use expiring discount codes (Klaviyo feature) so urgency is real
- Discount stacking: if no conversion after 3 emails at 10%, bump to 15% in email 4
- Email 2 personalized letter from CEO/founder has high conversion rates (E03)
- Always show same discount code from pop-up in welcome email 1
- Use first name personalization with fallback (e.g., "friend" if empty)
- Embed discount code into button/link for auto-apply at checkout
- Cross-pollination: redirect to strongest social channel; algorithms love third-party traffic

### Welcome Benchmarks
- Email 1: 48-65% open rate (E03)
- Emails 2-4: 23-25% open rate (normal drop-off)
- Welcome series: 9-15% of total email revenue

---

## Abandon Checkout Series

### E02 Architecture (Boyan -- AOV-based timing)

**Trigger:** Checkout Started
**Filters:** Placed order 0 times since starting + not in flow last 7 days
**Length:** 3-4 emails

| Email | Delay | Content |
|---|---|---|
| Email 1 | 30 min - 4 hrs (by AOV) | Header + dynamic cart items + CTA; pure retargeting |
| Email 2 | 24 hrs minus Email 1 delay | Social proof + trust factors; handles trust objections |
| Email 3 | 1 day after Email 2 | Comeback reminder + offer (optional); handles price/value |
| Email 4 (opt) | 2 days after Email 3 | Bigger discount (offer laddering) + urgency/scarcity |

### Timing Logic by AOV (E02)
- **Low AOV (<$50):** 30-minute delay (impulse-driven)
- **Medium AOV ($50-$100):** 1-2 hour delay
- **High AOV ($100+):** 3-4 hour delay (bigger decision, consulting family)

### Critical Delay Formula (E02)
First delay + second delay = 24 hours total. Email 2 arrives at approximately the same time of day the person was shopping.

### E03 Architecture (MuteSix)

**Trigger:** Checkout Started
**Filter:** Place Order = 0, not in flow last 15-30 days
**Length:** 3-5 emails, first email 1-2 hours after

| Email | Wait | Content |
|---|---|---|
| 1 | 1-2 hours | Reminder -- dynamic cart contents, product images |
| 2 | 1 day | Urgency -- "Your cart is about to expire" |
| 3 | 1-2 days | Discount offer with expiring unique coupon (48-hr expiry) |
| 4 (opt) | 2-3 days | Higher discount or personal message |

### Advanced: Cart Value Split (E03)
- Trigger split by cart value: higher discount for high-AOV carts
- Example: Cart > $75 = bigger offer; Cart < $75 = standard messaging
- Result: 9.2% place order rate on high-AOV branch vs 1.2% standard

### Abandon Checkout Key Tactics
- Total flow recovers 15-25% of abandoned checkouts (E02)
- Abandon cart email 1 should target 35%+ open rate (E03)
- When offering promo: A/B test placement in subject line vs pre-header (E03)
- Add filter: "not in flow last 15-30 days" to prevent re-entry fatigue
- Alternative: clone flow with different creative for repeat abandoners

---

## Abandon Cart Series

### Architecture (E02 -- Separate from Checkout)

**Trigger:** Added To Cart (custom metric, NOT default in Klaviyo)
**Filters:** Checkout started 0 times + Placed order 0 times + Not in flow last 7 days (all AND)
**Length:** 2-3 emails

| Email | Content |
|---|---|
| Email 1 | Header + dynamic segment (SPLIT BLOCK, not table) + CTA |
| Email 2 | Benefits of product + educational content + optional offer |
| Email 3 (opt) | Urgency about stock levels; countdown timer if offer included |

### Key Distinction from Checkout
- Cart uses SPLIT BLOCK for dynamic segment (not table block)
- Import Klaviyo's "abandon cart reminder (added to cart trigger)" template -- look for cog wheel icon
- Email 2 copy: focus on how products benefit consumer (transformation) not brand features

---

## Browse Abandonment Series

### E02 Architecture

**Trigger:** Viewed Product
**Filters:** Checkout started 0 times last 14 days + Placed order 0 + Added to cart 0 + Not in flow last 14 days (all AND)
**Length:** 1-2 emails

### Key Differences from Cart/Checkout
- 14-day "not been in flow" window (less aggressive -- lower buyer intent)
- Exclude all later-stage funnel actions to prevent flow clashing
- For single-product brands: no dynamic segment needed, use banner
- For high-AOV stores: encourage contact with sales team
- Third highest revenue-producing flow typically
- Offer in browse Email 2 should NEVER exceed offers in checkout/cart flows

### E03 Architecture (MuteSix)

**Trigger:** Viewed Product (but did not add to cart)
**Filter:** Not in flow last 30 days
**Length:** 2-3 emails

- Conditional split: viewed product X times
  - 3+ views = higher intent, offer discount
  - Fewer views = no discount, reminder with value props
- Pull in exact product dynamically
- Keep total flow under 5-8 days (not 8+)
- Requires proper tracking (Klaviyo snippet on website)

---

## Site Abandonment Series

### Architecture (E02)

**Trigger:** Active on Site
**Filters:** Placed order 0 + Viewed product 0 + Added to cart 0 + Checkout started 0 + Not in flow last 28-45 days (all AND)
**Length:** 1 email only

### Key Details
- Longest cycle: 28-45 day "not been in flow" window
- Approach like a retail shop assistant: "Hey, can I help you with anything?"
- Do NOT be too direct about tracking their browsing (can feel invasive)
- Multi-SKU stores: include dynamic display of best sellers collection
- High-AOV stores: encourage contact with customer service
- NOT a default Klaviyo flow template -- must build manually
- Sometimes beats abandoned cart series in revenue

---

## Smart Sending Rules Summary

| Flow | Smart Sending | Rationale |
|---|---|---|
| Welcome Series | ON | Prevent overlap with campaigns |
| Abandon Checkout | ON (E03 recommendation) | Prevents sending if they got a recent campaign |
| Abandon Cart | ON | Same as checkout |
| Browse Abandon | ON | Lower intent, more interruptive |
| Site Abandon | ON | Lowest intent |
| Post-Purchase | OFF | Expected messaging post-purchase |
| Replenishment | OFF | Personalized, expected |
| Back-in-Stock | OFF | High intent, they opted in |
