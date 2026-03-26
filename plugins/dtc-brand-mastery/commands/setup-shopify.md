---
name: Setup Shopify Store
description: Shopify store setup wizard. Walks through the 14-step build process, platform configuration, PASTOR framework for product pages, conversion optimization checklist, and upsell/bundle setup. Uses shopify-dtc-setup skill.
---

# /setup-shopify -- Shopify Store Setup Wizard

## INTAKE QUESTIONS (Ask All Before Guiding)

### Question 1: Current Status
**Where are you in the store setup process?**

| Choice | Starting Point |
|--------|---------------|
| A) Haven't started yet | Begin at Step 1 of 14-step build |
| B) Store exists but not optimized | Skip to conversion optimization |
| C) Store is live, want to improve AOV/revenue | Skip to upsell/bundle setup |
| D) Need a landing page for ads | Skip to landing page builder |

### Question 2: Product Status
**What's your product situation?**
- How many products do you plan to sell? (Start with 1 hero product)
- Do you have product photography ready?
- Do you have product copy written?

### Question 3: Channel Strategy
**Where else do you sell (or plan to sell)?**

| Choice | Fulfillment Recommendation |
|--------|--------------------------|
| A) Shopify only | Self-ship or 3PL |
| B) Shopify + Amazon | Amazon FBA with MCF for Shopify orders |
| C) Shopify + Amazon + TikTok Shop | Amazon FBA with MCF for all channels |
| D) Not sure yet | Start with self-ship, plan for FBA |

---

## WIZARD FLOW

### Phase 1: Store Build (Steps 1-14)
Walk through each step from `skills/shopify-dtc-setup/SKILL.md` -> "14-Step Store Build Process":
1. Create Shopify store
2. Add first product
3. Choose theme (recommend free theme)
4. Update company info
5. Activate Shopify Payments + PayPal
6. Create legal pages
7. Create shipping/returns page
8. Create contact page
9. Create navigation menu
10. Add custom domain
11. Add remaining products
12. Set up fulfillment
13. Configure sales tax
14. Go live

**At each step, ask if completed or needs help.**

### Phase 2: Conversion Optimization
Apply the conversion optimization checklist from SKILL.md:
- Apply PASTOR framework to hero product page
- Add trust signals, guarantee, promo bar, popup
- Install Judge.me for reviews
- Set up abandoned cart flow (Klaviyo)
- Do live test purchase

### Phase 3: Revenue Maximization
Guide through upsell/bundle setup:
- Install Zipify OneClick Upsell (reference ref-dtc-apps-stack.md)
- Set up pre-purchase and post-purchase upsell funnels
- Create product bundles
- Set up free shipping threshold

### Phase 4: Pre-Launch Checklist
- [ ] PASTOR framework applied to product page(s)
- [ ] Promo bar active with offer
- [ ] Email popup active (10% off for signup)
- [ ] Abandoned cart flow configured
- [ ] Upsells installed and tested
- [ ] Live test purchase completed (verify entire flow)
- [ ] Tracking installed (Shopify pixel, Facebook pixel, Google Analytics, UTM parameters)
- [ ] All legal pages live (privacy, terms, refund, shipping)

---

## OUTPUT FORMAT

Deliver a personalized setup plan based on intake answers:
1. **Immediate next steps** (3-5 actions)
2. **Timeline** (based on current status)
3. **App installation list** (from ref-dtc-apps-stack.md)
4. **PASTOR framework draft** for their hero product (if they provide product details)
5. **Conversion optimization priority list** (ordered by impact)

---

## SKILLS ACTIVATED
- Primary: `shopify-dtc-setup`
- Supporting: `shipping-fulfillment` (for fulfillment setup guidance)
- Reference: `ref-dtc-apps-stack.md` (for app recommendations)
