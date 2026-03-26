---
name: Setup TikTok Shop
description: Step-by-step TikTok Shop setup wizard covering registration, geo-locking, account linking, shipping/fulfillment, customer support, creator outreach, and the 22-step launch sequence. Uses tiktok-shop-setup skill.
---

# /setup-tiktok-shop -- TikTok Shop Setup Checklist

## INTAKE QUESTIONS (Ask All Before Guiding)

### Question 1: Current Status
**Where are you in the TikTok Shop setup?**

| Choice | Starting Point |
|--------|---------------|
| A) Haven't started | Begin at Step 1 (business registration) |
| B) Registered but not set up | Skip to account linking and configuration |
| C) Shop is live but no sales | Skip to creator outreach and advertising |
| D) Shop is live, want to optimize | Skip to GMV Max optimization |

### Question 2: Existing Platforms
**Where do you currently sell?**

| Choice | Fulfillment Recommendation |
|--------|--------------------------|
| A) Amazon only | Use Amazon MCF via Aftership or WebBee |
| B) Amazon + Shopify | Use TikTok for Shopify Channel (free) |
| C) Shopify only (no Amazon) | Self-ship or 3PL; consider adding FBA |
| D) Not selling anywhere yet | Set up Amazon FBA first, then MCF for TikTok |

### Question 3: Product Readiness
- Does your product meet 3/5 TikTokability criteria? (Demonstrability, Unique Attributes, Serves a Niche, Solves a Problem, Impulse Buy Pricing <$50)
- Is the product on the prohibited/restricted products list?
- Do you have content/video assets?

### Question 4: Team
- Do you have team members (VAs) available?
- If VAs are outside the US: do they have US VPN access?

---

## WIZARD FLOW -- 22-Step Launch Sequence

Walk the user through each step, checking completion and providing guidance:

### Phase 1: Registration & Accounts (Steps 1-7)
- [ ] **Step 1:** Validate 3/5 TikTokability criteria
- [ ] **Step 2:** Review prohibited/restricted products list
- [ ] **Step 3:** Complete business registration (SS4 letter in JPG format)
- [ ] **Step 4:** Create US-based TikTok social account (US device or US VPN)
  - **CRITICAL:** Warn about geo-locking rules
  - Birthday must match real ID
  - Complete identity verification within 24 hours
- [ ] **Step 5:** Verify identity on social account
- [ ] **Step 6:** Link social account to TikTok Shop (QR code scan process)
- [ ] **Step 7:** Connect ad account (new or existing)

### Phase 2: Operations Setup (Steps 8-14)
- [ ] **Step 8:** Set up customer support
  - FAQ card in chat greeting
  - Saved replies in brand voice
  - AI chatbot activated all day
  - Customer Service Agent and Order Fulfillment Specialist roles assigned
- [ ] **Step 9:** Set up warehouse (pickup + return addresses)
- [ ] **Step 10:** Create shipping template ($5-$8 flat rate, exclude HI/AK)
- [ ] **Step 11:** Choose shipping method (TikTok Shipping or Seller Shipping)
- [ ] **Step 12:** Install fulfillment integration
  - **If Amazon + Shopify:** TikTok for Shopify Channel (free)
  - **If Amazon only:** Aftership ($11/mo) or WebBee
  - Match product SKUs between platforms
- [ ] **Step 13:** Configure sync settings
  - Sync inventory only (NOT product details, NOT price)
  - 1-hour order sync delay
  - Expedited shipping selected
  - Auto-restock on cancellation
  - No category mapping
- [ ] **Step 14:** Run test order (verify full pipeline before any marketing)

### Phase 3: Content & Social Proof (Steps 15-16)
- [ ] **Step 15:** Import reviews (if Amazon reviews exist)
  - Export from Amazon via Helium 10 Review Insights
  - Import to Shopify via Yotpo (paid plan required)
  - Import from Shopify to TikTok via Yotpo
  - Match SKUs between Shopify and TikTok
  - Cancel Yotpo after import
- [ ] **Step 16:** Add team members with role-specific access
  - Use Gmail +1/+2 workaround for VA emails
  - Ensure all VAs use US VPN

### Phase 4: Growth & Optimization (Steps 17-22)
- [ ] **Step 17:** Begin creator outreach (30-50 daily via Target Collaborations)
  - Load ref-tiktok-workflows.md for detailed workflow
- [ ] **Step 18:** Set up 3 simultaneous promotions
  - Free shipping + product discount + coupon
- [ ] **Step 19:** Launch Video Shopping Ads (if limited content)
- [ ] **Step 20:** Graduate to GMV Max (once converting content exists)
  - One product per campaign
  - Start with TikTok's suggested ROI target
  - Auto-select videos
- [ ] **Step 21:** Set up weekly customer marketing campaigns
  - Recent customers + potential customers
  - Up to 4 products per campaign
- [ ] **Step 22:** Optimize GMV Max (adjust ROI target, review creatives, collect spark codes)

---

## CRITICAL WARNINGS TO SURFACE

At the appropriate step, explicitly warn about:
1. **Geo-locking** (Step 4) -- account locks to country of creation/access
2. **SS4 letter** (Step 3) -- digital EIN copy will be rejected
3. **Test order** (Step 14) -- do NOT skip; do NOT launch marketing without it
4. **Sync settings** (Step 13) -- only sync inventory; DO NOT sync product details or price
5. **1-hour delay** (Step 13) -- prevents fulfilling canceled orders
6. **Customer support** (Step 8) -- unread messages directly impact account health

---

## OUTPUT FORMAT

Based on intake answers, deliver:
1. **Personalized checklist** starting from their current step
2. **Estimated timeline** to complete remaining steps
3. **Fulfillment integration recommendation** based on existing platforms
4. **Team assignment recommendations** (who handles what)
5. **First-week action plan** after launch

---

## SKILLS ACTIVATED
- Primary: `tiktok-shop-setup`
- Supporting: `shipping-fulfillment` (for MCF configuration details)
- Reference: `ref-tiktok-workflows.md` (for creator outreach and review importing)
