---
name: "Meta Pixel & CAPI Implementation"
description: "Pixel installation methods, CAPI setup, enhanced conversions, event match quality scoring, tracking hierarchy technical details."
---

# Meta Pixel & CAPI Implementation Reference

## Tracking Hierarchy -- Technical Details

### Level 1: Browser Pixel Only (~50% Data Recovery)
- Standard JavaScript pixel fires on page load events
- Blocked by: iOS 14.5+ App Tracking Transparency, ad blockers, browser privacy settings
- Misses: All iOS opt-out users, Safari ITP users, Firefox ETP users
- **Verdict:** Minimum viable tracking -- never run ads with only this

### Level 2: Browser Pixel + Shopify CAPI (~80% Data Recovery)
- Shopify's native CAPI integration sends server-side events
- Events fire from Shopify's servers, bypassing browser-level blocking
- Setup: Shopify Admin > Settings > Customer Events > Meta Pixel (enable server-side)
- Also available via: WooCommerce plugins (PixelYourSite Pro), BigCommerce native
- **Verdict:** Standard for most advertisers. Get here immediately.

### Level 3: Advanced Server-Side Tracking (~100% Data Recovery)
- Dedicated server gateway (Stape.io, Analyzify, Google Cloud) processes ALL events
- Events sent to Meta via server, never touching browser
- Deduplication required: browser + server events must not double-count
- Setup complexity: Medium-High (requires DNS configuration, server provisioning)
- **Verdict:** Required for $5K+/day spend or highly competitive verticals

---

## Pixel Installation Methods

### Method 1: Direct Platform Installation
**Best for:** Shopify, WooCommerce, BigCommerce users
- Shopify: Settings > Customer Events > Add Meta Pixel > Enter Pixel ID
- WooCommerce: PixelYourSite Pro plugin or Facebook for WooCommerce plugin
- BigCommerce: Native Meta integration in Channel Manager

### Method 2: Google Tag Manager
**Best for:** Custom sites, WordPress (non-WooCommerce), multi-pixel setups
- Create Meta Pixel tag in GTM
- Fire on All Pages trigger for PageView event
- Create additional tags for Purchase, AddToCart, ViewContent events
- Publish container after testing in Preview mode

### Method 3: Manual Code Installation
**Best for:** Custom-built sites without CMS
- Place base pixel code in `<head>` section of every page
- Add event-specific code on relevant pages (purchase confirmation, cart, product pages)
- Test with Meta Pixel Helper Chrome extension

---

## CAPI Setup Methods

### Shopify Native CAPI
1. Go to Shopify Admin > Settings > Customer Events
2. Ensure Meta Pixel is added with your Pixel ID
3. Enable "Server-side tracking" toggle
4. Verify in Events Manager: events should show "Browser and Server" source

### Third-Party CAPI Solutions
- **Stape.io:** Server-side GTM hosting, $20-100/month depending on events
- **Analyzify:** Shopify-specific, handles deduplication automatically
- **Elevar:** Premium server-side tracking with data layer management
- **Custom API:** Use Meta Marketing API directly (developer required)

### Deduplication Rules
- Every event MUST have an `event_id` parameter
- Browser event and server event for the same action share the same `event_id`
- Meta automatically deduplicates events with matching `event_id` within 48 hours
- Without deduplication: conversions count double, bidding becomes inaccurate

---

## Event Match Quality (EMQ) Scoring

### What EMQ Measures
EMQ scores how well your customer parameters match Meta's user database. Higher score = more conversions attributed = better optimization.

### Score Interpretation
| Score | Meaning | Action |
|-------|---------|--------|
| 0-3 | Poor | Urgent fix needed -- you are losing most conversion data |
| 4-5 | Below average | Add more customer parameters |
| 6-7 | Good | Acceptable but room for improvement |
| 8-10 | Great | Optimal matching -- maintain this |

### Parameters by Impact (Highest to Lowest)
1. **Email address** (em) -- Most impactful. Pass hashed email on every event.
2. **Phone number** (ph) -- Second most impactful. Include country code.
3. **First name** (fn) -- Moderate impact. Lowercase, no special characters.
4. **Last name** (ln) -- Moderate impact. Lowercase, no special characters.
5. **City** (ct) -- Lower impact but helps with geo-matching.
6. **State** (st) -- Lower impact. Two-letter abbreviation.
7. **Zip code** (zp) -- Lower impact. Five-digit format.
8. **Country** (country) -- Lower impact. Two-letter ISO code.
9. **Date of birth** (db) -- Minimal impact for most advertisers.
10. **Gender** (ge) -- Minimal impact for most advertisers.

### Advanced Matching Setup
**Automatic Advanced Matching:**
- Events Manager > Settings > Automatic Advanced Matching > Toggle ON
- Meta automatically detects and hashes customer data from form fields
- Easiest method but less reliable than manual

**Manual Advanced Matching:**
- Pass parameters explicitly in pixel code or CAPI payload
- More reliable but requires development work
- Always hash (SHA-256) PII before sending

---

## Essential Events to Configure

### Standard Events (Priority Order)
1. **Purchase** -- Non-negotiable. Include value, currency, content_ids
2. **AddToCart** -- Track cart additions with product details
3. **InitiateCheckout** -- Track checkout starts
4. **ViewContent** -- Track product page views with content_id
5. **PageView** -- Base event, auto-fires with pixel installation

### Custom Events (If Applicable)
- **Lead** -- For lead generation forms
- **CompleteRegistration** -- For account creation
- **Subscribe** -- For subscription sign-ups
- **AddPaymentInfo** -- For payment method entry

### Value Parameters (Critical for Value Optimization)
- Always pass `value` and `currency` with Purchase events
- Pass `content_ids` matching your product catalog IDs
- Pass `content_type` as "product" for e-commerce
- Accurate value data enables value-based optimization and ROAS bidding

---

## Attribution Settings Guide

| Window | Best For | Notes |
|--------|----------|-------|
| 7-day click (default) | Most products | Standard post-iOS setting |
| 1-day click | Impulsive/low-price products (<$50) | Reduces over-attribution |
| 7-day click + 1-day view | Standard e-commerce | Default and recommended |
| 1-day click + 1-day view | Strict attribution needed | Most conservative |

**View-through attribution caution:** Advantage Shopping campaigns can over-report by 30%+ with view-through enabled. If view conversions exceed 50% of click conversions, you likely have an over-attribution problem.

---

## Troubleshooting Checklist

- [ ] Pixel Helper shows green icon on all key pages
- [ ] Events Manager shows events firing in real-time
- [ ] Events show "Browser and Server" source (not just "Browser")
- [ ] Event Match Quality score is 6+ (target 8+)
- [ ] Purchase events include value and currency parameters
- [ ] No duplicate events (check for double-firing in Events Manager)
- [ ] Deduplication event_id is present on both browser and server events
- [ ] Test purchase shows correctly in Events Manager within 5 minutes
