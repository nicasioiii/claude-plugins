---
name: "Google Conversion Tracking Implementation"
description: "Native Google Ads conversion code setup, enhanced conversions, conversion windows, GTM configuration, cash vs accrual reporting."
---

# Google Conversion Tracking Implementation

## Why Native Google Ads Code (Not GA4)

Google Ads smart bidding algorithms (Target ROAS, Target CPA, Max Conversions, Max Conversion Value) require the native Google Ads conversion tracking code. They do NOT work properly with GA4 imported conversions.

**GA4 is for:** Comparison, cross-channel analysis, audience building, reporting.
**Google Ads code is for:** Feeding the bidding algorithm, optimization, campaign decisions.

Use both side by side, but always optimize based on Google Ads native data.

---

## Installation Method 1: Direct Platform

### Shopify
1. Google Ads > Goals > Conversions > New Conversion Action > Website
2. Select "Purchase" as conversion category
3. Use "Use a tag" and copy the Global Site Tag and Event Snippet
4. Shopify Admin > Online Store > Themes > Edit Code > theme.liquid > paste Global Site Tag in `<head>`
5. Paste Event Snippet on thank-you page (checkout settings or additional scripts)
6. Alternatively: Use Google & YouTube Shopify app for simplified setup

### WooCommerce
1. Install "Google Listings & Ads" official plugin OR "Conversion Tracking Pro" plugin
2. Enter Google Ads Conversion ID and Conversion Label
3. Plugin automatically fires purchase event on order confirmation page
4. Verify in Google Ads > Tools > Tag Assistant

### BigCommerce
1. Use native Google Ads integration in Channel Manager
2. Enter Conversion ID and Conversion Label
3. BigCommerce handles tag placement automatically

---

## Installation Method 2: Google Tag Manager

### Setup Steps
1. Create GTM account and container for your website
2. Install GTM container code on ALL pages (header + body snippets)
3. In GTM: Create new tag > Google Ads Conversion Tracking
4. Enter Conversion ID, Conversion Label, Conversion Value (dynamic), Currency
5. Create trigger: fires on purchase confirmation page (URL contains "thank_you" or order confirmation)
6. For dynamic values: Set up Data Layer with transaction value variable
7. Test in GTM Preview Mode > verify conversion fires
8. Publish container

### GTM Advantages
- Cleaner code management (one container vs. multiple scripts)
- Easy to add/remove/swap tracking codes
- Built-in debugging with Preview mode
- Version control for all tag changes
- Can manage Google Ads, GA4, Meta Pixel, and more in one place

---

## Enhanced Conversions Setup

### What It Does
- Collects first-party customer data (email, name, address) at conversion
- Hashes data (SHA-256) before sending to Google
- Google matches against logged-in user accounts
- Recovers conversions that browser-only tracking misses

### Setup Steps
1. Google Ads > Goals > Conversions > select your purchase conversion
2. Click "Edit settings"
3. Enable "Enhanced conversions"
4. Choose method: Google Tag (automatic) or GTM (manual)
5. **Automatic:** Google detects form fields and collects data
6. **Manual (GTM):** Add user-provided data variables to your conversion tag
7. Verify: Google Ads > Diagnostics > Enhanced Conversions tab

### Data Parameters (Priority Order)
1. Email address (highest impact)
2. Phone number
3. First name + Last name
4. Street address
5. City, State, Zip code, Country

---

## Conversion Windows by Product Type

| Product Category | Click Window | View-Through | Rationale |
|---|---|---|---|
| Impulse e-commerce (<$50) | 7-14 days | 1 day | Quick purchase decision |
| Standard e-commerce ($50-200) | 30 days | 1 day | Default, covers most buyers |
| High-consideration ($200-1000) | 60 days | 3-7 days | Longer research cycle |
| B2B / High-ticket ($1000+) | 90 days | 7 days | Extended sales cycle |
| Subscription / SaaS | 30-60 days | 3 days | Trial-to-paid conversion |

**View-through definition for YouTube:** Viewer watches 30+ seconds of in-stream ad, then converts within the window. Important for measuring YouTube campaign impact.

---

## Conversion Tracking Maturity Framework

### Level 1: Basic (Minimum Viable)
- Google Ads conversion code installed on purchase page
- Conversion value passed correctly
- One primary conversion action set

### Level 2: Standard (Recommended)
- Enhanced conversions enabled
- Multiple conversion actions tracked (purchase, add-to-cart, lead)
- Conversion windows set appropriately for product type
- GTM managing all tags

### Level 3: Advanced
- Offline conversion tracking (for businesses with phone/in-store sales)
- Store visit tracking (for local businesses with physical locations)
- Consent mode configured for GDPR compliance
- Cross-device conversion tracking optimized
- Profit-based conversion tracking (sending margin data, not revenue)

---

## Troubleshooting Checklist

- [ ] Google Ads Tag Assistant shows tag firing on conversion page
- [ ] Conversion value matches actual order value (not $0 or static number)
- [ ] Currency code is correct (USD, EUR, etc.)
- [ ] Enhanced conversions showing data in diagnostics
- [ ] No duplicate conversion counting (check for multiple tags on same page)
- [ ] Conversion action is set as "Primary" (not "Secondary") for bidding
- [ ] Test purchase shows in Google Ads within 24 hours
- [ ] GA4 and Google Ads numbers are within 15% of each other (if both installed)

---

## Common Mistakes

1. **Using GA4 as primary conversion source** -- Smart bidding will underperform
2. **Static conversion values** -- Passing $1 or $0 instead of actual order value breaks ROAS bidding
3. **Multiple primary conversions** -- Having both "Purchase" and "Add to Cart" as primary confuses bidding
4. **Not testing after setup** -- Always place a test order and verify within 24 hours
5. **Ignoring enhanced conversions** -- Leaving 20-30% of conversion data on the table

---

## Enhanced Conversions Deep Dive

### Why Enhanced Conversions Matter
- Browser-based tracking misses conversions due to: cookie blocking, cross-device journeys, Safari ITP, ad blockers
- Enhanced conversions recover 20-30% of these missed conversions
- More conversion data = better smart bidding = lower CPA/higher ROAS
- Free to enable -- there is no reason not to set this up

### Implementation Priority
1. Email address (highest match rate -- most Google users are logged in via email)
2. Phone number (strong secondary signal)
3. Name (first + last) combined with address improves match when email unavailable
4. Full address (city, state, zip, country) -- lowest priority but additive

### Verification Process
1. After enabling, wait 48-72 hours for data to populate
2. Go to Google Ads > Goals > Conversions > select your purchase action
3. Check the "Diagnostics" tab for enhanced conversions status
4. Look for: match rate percentage, data freshness, and any error flags
5. Healthy match rate: 60%+ of conversions should show enhanced data
6. If match rate is below 40%: check implementation -- likely a tag configuration issue

### Consent Mode (GDPR Compliance)
- Required for EU/EEA audiences
- Google Consent Mode v2 sends anonymized pings even when consent is denied
- These pings help model conversions without collecting personal data
- Implementation: Add consent parameters to your Google tags
- Two modes: "Granted" (full tracking) and "Denied" (anonymized modeling)
- Google uses conversion modeling to estimate missing conversions

---

## Measurement Maturity Framework (Expanded)

### Level 1: Basic (Minimum Viable)
- [ ] Google Ads conversion code installed on purchase page
- [ ] Conversion value passed correctly (dynamic, matches order total)
- [ ] One primary conversion action set (Purchase)
- [ ] Currency code correct
- **Time to implement:** 1-2 hours
- **Impact:** Smart bidding can function at basic level

### Level 2: Standard (Recommended)
- [ ] Enhanced conversions enabled and verified
- [ ] Multiple conversion actions tracked: Purchase (primary), Add-to-Cart (secondary), Lead Form (secondary)
- [ ] Conversion windows set appropriately for product type
- [ ] GTM managing all tags (cleaner, version-controlled)
- [ ] GA4 running side-by-side for comparison reporting
- **Time to implement:** 2-4 hours
- **Impact:** Smart bidding operates with good data quality

### Level 3: Advanced
- [ ] Offline conversion tracking (for phone/in-store sales)
- [ ] Store visit tracking (for businesses with physical locations)
- [ ] Consent mode configured for GDPR compliance
- [ ] Cross-device conversion tracking optimized
- [ ] Profit-based conversion tracking (sending margin data, not revenue)
- [ ] Custom parameters for audience segmentation
- **Time to implement:** 4-8 hours + ongoing maintenance
- **Impact:** Maximum bidding intelligence, true profitability optimization

### Level 4: Expert (High-Spend Accounts)
- [ ] Offline conversion imports from CRM (Salesforce, HubSpot)
- [ ] Enhanced conversions for leads (passing lead quality data back to Google)
- [ ] Lifetime value import for LTV-based bidding
- [ ] Cart data tracking for Shopping campaigns
- [ ] Attribution model customization (data-driven, position-based)
- **Time to implement:** 8-20 hours + developer resources
- **Impact:** Precision bidding based on actual business outcomes

---

## Cash vs. Accrual Reporting (Expanded)

### Why Numbers Never Match Between Platforms
- **Google Ads (accrual):** Credits the conversion to the date of the CLICK (not the purchase date)
- **GA4 / Shopify (cash):** Credits the conversion to the date of the PURCHASE
- **Example:** User clicks ad on March 1, purchases on March 15. Google Ads counts it in March 1 data. Shopify counts it in March 15 data.

### Practical Impact
- March 1 report in Google Ads may show 0 conversions, but by March 31, that same day could show 5 conversions (from delayed purchases)
- Always wait 7-14 days before evaluating a specific day's performance in Google Ads
- Weekly and monthly totals are more reliable than daily figures
- Acceptable discrepancy between Google Ads and Shopify: within 15-20%

### Reconciliation Process
1. Compare 30-day totals (not daily) between Google Ads and Shopify/GA4
2. Calculate the ratio: Google Ads Revenue / Actual Revenue
3. If ratio is consistent (e.g., Google Ads always reports 85% of actual), use this as your adjustment factor
4. Set Google Ads ROAS targets based on the adjusted ratio
5. Example: If real ROAS is 4x when Google Ads shows 3.2x, target 3.2x in Google Ads to achieve 4x real ROAS
