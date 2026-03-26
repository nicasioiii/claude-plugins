---
name: Shopify Store Setup
description: >
  MANDATORY TRIGGERS: shopify store, set up shopify, store setup, shopify checklist,
  fulfillment options, FBA shopify, 3PL, revenue per visitor, RPV, upsell funnel,
  post-purchase upsell, bundle strategy, super bundle, subscription sales, zipify,
  free shipping threshold, store optimization, /setup-shopify, maximize RPV,
  increase AOV, average order value shopify, one click upsell, cart upsell.
  FOR: Setting up and optimizing a Shopify DTC store -- 14-step store checklist,
  fulfillment selection (FBA/3PL/self-ship), the 9-step RPV maximization system,
  upsell funnel architecture with Zipify OCU, bundle strategy, super bundle,
  subscription setup, and free shipping threshold calculation.
  Synthesized from Matt Clark (The Omnichannel Machine -- 14-step checklist, RPV
  system, upsell funnels, bundles, subscriptions), ASM14 Off-Amazon program
  (first $1K on Shopify, promotion channel checklist), and Gretta van Riel
  (Start & Scale -- platform selection, free shipping threshold, post-purchase
  upsells).
  Do NOT use for: theme design or development (-> design-mastery), email/SMS
  flow setup (-> email-marketing-mastery), landing page copywriting
  (-> cro-copywriting-mastery), product page copy frameworks like PASTOR
  (-> cro-copywriting-mastery), pricing and margin math (-> pricing-unit-economics).
---

# Shopify Store Setup

## Quick Navigation
- **14-step store checklist, fulfillment options, sales optimization** -> references/shopify-store-setup-ref.md
- **RPV formula, upsell funnel architecture, bundles, subscriptions** -> See frameworks below

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| How do I set up my Shopify store? Step-by-step checklist? | shopify-store-setup-ref.md |
| Which fulfillment option -- FBA, self-ship, or 3PL? | shopify-store-setup-ref.md |
| How do I set up upsells? Zipify? Pre-purchase and post-purchase? | shopify-store-setup-ref.md |
| Bundle strategy? Super bundle? How to create bundles? | shopify-store-setup-ref.md |
| How do I add subscriptions to my store? | shopify-store-setup-ref.md |
| First $1K on Shopify? Promotion channel checklist? | shopify-store-setup-ref.md |

---

## Cross-References

| Situation | Route To |
|---|---|
| Store live, need to validate RPV > CPC before running traffic | pricing-unit-economics |
| Store optimized (RPV maximized), ready to drive traffic | launch-strategy |
| Need landing page copy using PASTOR or similar | cro-copywriting-mastery (external plugin) |
| Need email/SMS flows (abandoned cart, welcome, post-purchase) | email-marketing-mastery (external plugin) |
| Need Shopify theme design or UI/UX work | design-mastery (external plugin) |
| Want to expand to Amazon | amazon-listing-optimization |
| Want to expand to TikTok Shop | tiktok-shop-setup |

---

## Revenue Per Visitor -- The Master Metric (Matt Clark)

**Formula:** RPV = Average Order Value x Conversion Rate

**Benchmarks:**
| AOV | CR | RPV | Verdict |
|---|---|---|---|
| $30 | 2% | $0.60 | Unprofitable for most paid traffic |
| $60 | 2% | $1.20 | Marginal -- depends on CPC |
| $60 | 5% | $3.00 | Strong -- profitable on most channels |

**The Rule:** If RPV > cost per click, you are profitable on paid traffic.

**Case study (Clark):** Member went from $100K/month to $800K/month (8x) by focusing solely on maximizing RPV before scaling ad spend.

[CONTRARIAN -- Clark] **Maximize RPV BEFORE driving traffic.** Most people run ads first. Wrong order. Optimize AOV and conversion first, then turn on traffic.

---

## The 9-Step RPV Maximization System (Clark)

Execute in order. Each step compounds the previous.

1. **Add irresistible guarantee** -- reduce perceived risk (LifeBoost uses 30-day money back). Display on header, footer, product pages, cart page.
2. **Display promo bar** -- free shipping threshold, current offers. Scarcity is the biggest motivator.
3. **Add popup** -- capture email/SMS leads for remarketing (15% off coupon via Klaviyo).
4. **Add abandoned cart flow** -- recover lost sales via email automation.
5. **Add upsells** -- pre-purchase AND post-purchase (see Upsell Funnel Architecture below).
6. **Add bundles** -- buy 2 get X% off, buy 3 get Y% off.
7. **Add super bundle** -- kitchen sink offer combining ALL products.
8. **Execute customer reactivation campaign** -- re-engage past buyers.
9. **Plan one promotion for each of the next 4 weeks** -- maintain momentum.

---

## Upsell Funnel Architecture (Clark)

**Tool:** Zipify OneClickUpsell (OCU)

**Funnel structure per product:**

```
Customer adds to cart
  |-> Pre-purchase upsell (popup): same product at 20% off
      |-> Checkout completes (credit card already entered)
          |-> Post-purchase upsell #1: same product at 25% off
              |-> ACCEPTED -> Post-purchase upsell #2: 2-3 pack or different product
              |-> DECLINED -> Post-purchase downsell: 30% off or different product
```

**Implementation:**
- Funnel 1: Triggered by your main product (highest priority)
- Funnel 2: "Default/catch-all" triggered by ANY product (lower priority)
- Priority/sorting ensures main product funnel fires first, default catches rest
- Result: Every purchase triggers at least 2 additional offers

**LifeBoost case study:** $1M+ in upsell sales alone -- described as "basically free money, super high margin."

---

## Free Shipping Threshold (Clark + Gretta)

**Clark:** Set free shipping threshold to drive higher AOV.

**Gretta:** Free shipping is expected standard. Include in product price. Offer express upgrade for additional charge. Alternative: free shipping over $100+ spend threshold.

[CONTRARIAN -- Gretta] "Customers will always be prepared to pay more for a product if the shipping's free." Build shipping into the price rather than showing it separately.

---

## Subscription Strategy (Clark)

**Goal:** Recurring revenue base (LifeBoost: ~50% of $2.6M/month is subscription).

**Implementation:**
- Add subscription option to products (works best for consumables)
- Non-consumable brands: create subscription via complementary consumable products, refills, or maintenance products
- Promote via autoresponders + store
- Add package inserts directing to subscription signup

---

## /setup-shopify Command Output

When user runs `/setup-shopify`, deliver:
1. **14-step store checklist** (from reference file) tailored to their product
2. **Fulfillment selection guide** comparing FBA vs 3PL vs self-ship for their situation
3. **RPV optimization plan** applying the 9-step system to their specific store
4. **Upsell funnel architecture** with specific pre-purchase and post-purchase offer recommendations
5. **Bundle strategy** with pricing tiers
6. **Subscription recommendation** (if applicable to their product type)
