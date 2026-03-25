---
name: Retention Flows (Post-Purchase, Winback, Upsell, Sunset, VIP, Back-in-Stock)
description: >
  When to Read: User asks about post-purchase flows, winback timing, upsell/cross-sell
  strategy, sunset unengaged, VIP flows, back-in-stock, replenishment reminders,
  date-triggered sequences, or holiday-specific automations.
  Cross-references: ref-acquisition-flows.md for pre-purchase flows,
  segmentation-list-health for unengaged segment definitions used in sunset flows.
---

# Retention Flows

## Post-Purchase Thank You Series

### E02 Architecture (Boyan)

**Trigger:** Placed Order
**Filters:** Cancelled order 0 + Refunded order 0 + Placed order 0 times since starting (all AND)
**Length:** 3 emails + 1 alternative
**Smart Sending:** OFF (people expect a thank you after buying)

| Email | Delay | Content |
|---|---|---|
| Email 1 | 1 day after order | Thank you + set expectations (delivery, FAQs) |
| Email 1.1 (alt) | Same | Different messaging for REPEAT buyers (conditional split) |
| Email 2 | Fulfillment time + 4 days safety | Cross-pollination OR education (product usage) |
| Email 3 | 4 days after Email 2 | Request for review |

### Conditional Split: First-Time vs Repeat (E02 + E03)
- **First-time buyer:** Designed email with brand CTA
- **Repeat buyer:** Plain text email from founder (feels personal, not automated)
- Both E02 and E03 agree: messaging MUST differ between new and repeat customers

### E03 Architecture (MuteSix)

| New Customers | Repeat Customers |
|---|---|
| Email 1: Brand relationship + social follow | Email 1: Brand relationship + social follow |
| Email 2: Nurture + feedback request | Email 2: Nurture + feedback + product catalog for repeat purchase |

### Review Request Timing (E02)
Ask ASAP because:
1. Products break over time
2. Perceived impact diminishes over time (attribution decay)
3. Delay must be long enough for delivery but not too long

### Primary Goal
NOT direct revenue (though it produces some). Goals: build rapport, set expectations, lower cancellation/refund rates, drive repeat purchases, collect reviews.

### Impact
- 54% increase in repeat customers (E03)
- "Sending a thank you often leads to a second purchase within 5-day attribution window" (E03)

---

## Customer Winback Series

### Architecture (E02)

**Trigger:** Placed Order
**Filters:** Placed order 0 times in last 75 days + Cancelled order 0 times (during delay)
**Length:** 2-3 emails

| Email | Content |
|---|---|
| Email 1 | Comeback reminder; "see what you've missed"; dynamic best sellers |
| Email 2 | Core product display + discount offer |
| Email 3 (opt) | Urgency of offer + countdown timer |

### Delay Calculation (E02)
Set to 1.5-2x average buying cycle:

| Brand Type | Buying Cycle | Winback Delay |
|---|---|---|
| Supplements (30-day) | 30 days | 45-60 days |
| Clothing | 60-90 days | 90-120 days |
| Maximum cap | Any | 180 days (beyond = forgotten) |

Never extend to 365 days -- brand is forgotten by then.

### Offer Types for Winback
- Free next-day or free shipping
- Buy X get Y free
- Free product with repurchase
- $X off entire order
- X% off entire order

### Key Principle (E02)
Post-purchase offers are far cheaper than top-of-funnel acquisition. If spending at 4X ROAS on Facebook with 10% discount, email offers to existing customers have near-zero acquisition cost. Giving margin away is vastly cheaper than buying new customers.

---

## Customer Upsell/Cross-Sell Series

### Architecture (E02)

**Trigger:** Fulfilled Order
**Filters:** Fulfilled order 0 + Placed order 0 + Refunded/cancelled 0 (since starting flow)
**Length:** 2 emails

**Delay:** 50% of average buying cycle (NOT a replenishment flow)
- If buying cycle is 60 days, set delay to 30 days

| Email | Content |
|---|---|
| Email 1 | "We know you'll like these" + complementary products + optional 10% discount |
| Email 2 | Urgency of offer + countdown timer; or introduce offer if not in Email 1 |

### E03 Cross-Sell Approach (MuteSix)
- Conditional split based on items purchased
- Customer buys t-shirt -> trigger email offering pants to complete outfit
- Customer buys blue short-sleeve -> offer blue long-sleeve for winter
- Use dynamic tags to pull exact product purchased and recommend complementary products
- Best for: multi-SKU brands

### Key Insight
Revenue from upsell customers has near-zero acquisition cost. Include discounts generously to extend LTV.

---

## Sunset Unengaged Series

### Architecture (E02)

**Trigger:** Joins Unengaged Segment
**Filters:** Opened OR clicked email 0 times since starting flow
**Length:** 2 emails only (more is redundant -- they're not opening)

| Email | Content |
|---|---|
| Email 1 | Goodbye email + offer incentive (plain text OR designed) |
| Email 2 | Offer urgency + unsubscribe option; "parting gift" with substantial discount |
| Action | Mark as unengaged if no open/click on either email |

### Unengaged Segment Definition (E02)
- Opened 0 emails in last 90 days (sweet spot: 90-120 days; never less than 60)
- Clicked 0 emails in last 90 days
- Received at least 15 emails (adjust based on send frequency)
- NOT already suppressed
- Active on site 0 times in last 45 days
- All logic gates: AND

### Sunset Offer Strategy
Give a substantial offer -- retaining a churning customer is extremely valuable. This is their last chance. Don't hold back on the discount.

---

## VIP Flow

### Architecture (E03 -- MuteSix)

**Trigger:** Place Order for the 4th time (or custom threshold)
**Length:** 1-2 emails

### Key Tactics
- Similar to post-purchase but with "extra special" coupon code
- Very personalized: thank them for continuous purchase and support
- Give generous offer -- "these people are your most qualified customers"
- Also ask for: reviews, refer-a-friend, early access to new products
- Set up separate VIP flows vs normal customer flows for different messaging

---

## Back-in-Stock Flow

### Architecture (E03 -- MuteSix)

**Trigger:** Subscribe to Back-in-Stock alert (Shopify + Klaviyo integration)
**Length:** 1-2 emails

### Setup
- Add code snippet to Shopify theme: shows CTA when item is sold out
- Customer enters email to subscribe to restock alert
- When product restocked, flow triggers automatically

### Key Tactics
- Set up separate flows for VIPs and normal customers
- Pull in exact product dynamically
- **Pro tip:** Set minimum inventory rules -- don't send if inventory only covers 100 of 500 subscribers for that product

---

## Replenishment / Restock Reminder

### Architecture (E03)

**Trigger:** Place Order + wait X days (based on product replenishment cycle)
**Smart Sending:** OFF (personalized, expected messaging)

### Examples
- Water filter purchased -> send reminder at 3-6 months for replacement
- Supplements purchased -> send reminder at 25-28 days for reorder

### Key Tactics
- Dynamically pull in items from their last order
- Include product recommendations ("Want to try something new?")
- If subscription available, encourage subscription conversion
- Time the delay to just BEFORE they run out (not after)

---

## Date-Triggered Sequences

### Architecture (E03)

**Trigger:** Custom date property (birthday, first purchase date, subscription anniversary, wedding date)

### Key Tactics
- Use dynamic time delays: emails leading up to, during, and after the event
- Collect date data through popups, surveys, or profile enrichment
- Birthday emails with discount are high-converting, low-effort
- Anniversary emails celebrate the customer relationship

---

## Holiday-Specific Automations (E03)

### Architecture

**Trigger:** Holiday-specific pop-up subscribe (e.g., Black Friday pop-up)

### Key Tactic
- During BFCM, set up separate pop-up with holiday discount
- When someone enters email via BFCM popup, trigger holiday-specific welcome email
- Captures NEW visitors during peak traffic who would otherwise miss campaign emails
- Fills gaps between campaign sends (e.g., between 6 AM send and Cyber Monday)

---

## Flow Optimization Rules (E02)

### Priority
- Optimize from top down (Email 1 first, not last emails)
- Deeper in flow = naturally lower conversion (this is normal)
- Only extend a flow if final email still converts 3-5%+ of recipients
- Generally don't need flows longer than 3-4 emails with proper full-spectrum funnel

### Flow Split Testing (Klaviyo)
- Add variation to any flow email; equalize weights
- Test subject lines first (higher opens = higher clicks = higher conversions)
- Only test single variables at a time
- Sample size: 100-500 emails per variation before declaring winner
- Optimize flows in order of revenue (dashboard performance ranking)
