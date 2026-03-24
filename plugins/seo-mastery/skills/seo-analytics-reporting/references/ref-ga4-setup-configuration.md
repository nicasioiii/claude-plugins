# GA4 Setup & Configuration Reference

Reference file for the `seo-analytics-reporting` skill. Covers the complete GA4 architecture, event system, setup methods, consent mode v2, data privacy, multi-domain decisions, tracking concept creation, cross-device tracking, e-commerce events, and UTM parameters.

---

## GA4 Architecture: Account > Property > Data Stream

### Account Level
- Top-level organizational unit
- Max 100 accounts per Google account
- Contains one or more properties

### Property Level
- The data repository where analytics data lives
- Max 2,000 properties per account
- Collects from one or more data streams
- All reporting happens at the property level

### Data Stream Level
- Tells GA4 where data comes from: Web, Android app, iOS app
- Each stream has a unique **measurement ID** (format: G-XXXXXXX for web)
- Max 20 data streams per property
- Google recommends as few streams as possible (multiple streams hurt report performance)

### Multi-Domain Architecture Decision

**Use ONE property + ONE data stream when:**
- Sites share content (language versions with identical URLs)
- Sites are closely interlinked (website + blog on different domains)
- User paths cross domains (website to store checkout)
- Sites are advertised together

**Use SEPARATE properties when:**
- Data is viewed independently by different teams
- Agency managing separate client projects (separate accounts for easy handover)

**Critical rule:** If multiple domains point to the same content, set up 301 redirects to one primary domain. Otherwise you get duplicate user counts and cookie problems.

You CAN include multiple Google tags for different properties on one site to count users in both a main property and a sub-property simultaneously.

---

## Events: The Foundation of Everything

GA4 is entirely event-based. Every user action is an event. The page_view event replaces pageviews. The purchase event replaces e-commerce transactions.

### Four Types of Events

**1. Automatically Recorded Events**
Collected without any configuration:
- `page_view` -- fires on every page load
- `session_start` -- fires when a new session begins
- `first_visit` -- fires on first-ever visit
- `user_engagement` -- fires when user is actively engaged

**2. Enhanced Measurement Events**
Toggle ON in data stream settings (Admin > Data Streams > select stream > Enhanced measurement):
- Scroll (90% page scroll)
- Outbound clicks
- Site search (when user searches on your site)
- Video engagement (YouTube embeds: start, progress, complete)
- File downloads
- Form interactions

**3. Recommended Events**
Google-suggested event names for specific industries. Use these names exactly for automatic reporting features:
- `add_to_cart` -- user adds product to shopping cart
- `purchase` -- transaction completes
- `sign_up` -- user registers an account
- `generate_lead` -- lead form submitted
- `begin_checkout` -- checkout process started

**4. Custom Events**
Define for any tracking need unique to your business. Name them descriptively with snake_case format.

### Key Events (Formerly "Conversions")

GA4 renamed conversions to **key events**. Any event can be marked as a key event in Admin > Key events. Key events are the primary success metrics for your business.

---

## Three GA4 Setup Methods

### Method 1: CMS/Store Plugin
- WordPress: Google Site Kit plugin
- Shopify: Native Google Analytics integration
- Enter measurement ID in plugin settings
- Verify that plugin respects consent mode
- Simplest setup but limited customization

### Method 2: Google Tag (gtag) Directly in Source Code
- JavaScript snippet placed in `<head>` of every page
- More control than plugins
- Requires developer access for changes
- No tag management layer

### Method 3: Google Tag Manager (Recommended)
- GTM loads the Google tag
- More complex initial setup
- Superior management for multiple tracking codes
- No code deploys needed per tag change
- Supports consent mode integration
- Enables tag testing before publishing

**Recommendation:** Use GTM for any site beyond a simple blog. The initial setup cost is repaid many times over in management efficiency.

---

## Consent Mode v2 (Mandatory for EU)

### Why It's Mandatory
EU's Digital Markets Act (2024) requires consent mode v2 for all Google tags. This applies to any site that may have EU visitors.

### How It Works
1. Consent mode transmits user's consent status with each GA4 measurement call
2. Consent signals include: analytics_storage, ad_storage, ad_user_data, ad_personalization
3. Without consent, GA4 uses **modeling** to extrapolate missing data from measured users
4. Modeling requires minimum data thresholds to be statistically valid

### Implementation Requirements
1. Deploy a **consent management platform (CMP)**: Usercentrics, OneTrust, Cookiebot, etc.
2. CMP displays cookie consent banner to users
3. CMP communicates consent state to GTM/gtag
4. Actual tracking prevention must be implemented in GTM or code (CMP alone is not enough)
5. Tags must be configured to respect consent state

### Server-Side Tagging
The future building block for privacy-compliant tracking:
- You operate your own tracking server
- Server accepts data from client-side tags
- Server forwards to marketing services (GA4, Google Ads, etc.)
- Reduces client-side tag burden
- Provides more control over what data leaves your infrastructure

---

## Data Privacy Configuration Checklist

Complete this checklist for every GA4 property:

1. **Consent obtained** -- CMP deployed and functioning before any tracking tags fire
2. **Opt-out enabled** -- consent box allows users to withdraw consent
3. **Privacy policy updated** -- lists all analytics services, data collected, retention periods
4. **IP anonymization** -- automatic in GA4 (shortened to city-level); no action needed
5. **Data retention** -- set to 14 months (Admin > Data Settings > Data Retention); no regulation mandates 2 months
6. **Reset on activity** -- enable "Reset user data on new activity" to extend retention with each return visit
7. **Data processing agreement** -- accepted during account creation; verify in Admin
8. **Contacts appointed** -- primary contact and data protection officer listed in account settings
9. **Pre-setup data** -- delete any non-compliant data collected before proper consent setup

---

## Account Data Sharing Settings

Recommended: **deactivate all four** with no noticeable restrictions:

| Setting | Recommendation | Reason |
|---------|---------------|--------|
| Google products & services | OFF | Not needed; separate from Google Ads linking |
| Benchmarking | OFF | Data too general; not yet available for GA4 |
| Technical support | Optional | Activate only when filing support request |
| Account manager | OFF | Allows Google sales staff to access your data |

Deactivating all four is better for data privacy audits and poses no functional limitations.

---

## Property Configuration

### Time Zone
- Determines how all access is logged
- User access from other time zones is converted to your property's time zone
- Choose the time zone of your primary business location

### Currency
- Default for e-commerce and campaign cost data
- Can be overridden per transaction in tracking code
- Choose the currency you report revenue in

### Naming Trick
For large accounts with many properties: prefix with numbers ("1 Website.com", "2 Store") for alphabetical sorting. Use emojis via UTF-8 for visual identification.

---

## Tracking Concept Creation

Before installing GA4, answer two questions:
1. **What CAN users do** on the website? (List all action items)
2. **What SHOULD users do?** (Define conversions)

For each action item, document:
- What exactly happens (form submit -> thank you page? overlay? redirect?)
- What data is generated (form field values, link names, product data)
- Whether GA4 already records it or needs custom tracking

### Macro vs Micro Conversions

**Macro conversions** -- the big final actions:
- Purchase
- Lead form submission
- Booking/appointment

**Micro conversions** -- smaller steps leading to macro:
- Watching product video
- Adding to cart
- Newsletter signup
- Downloading resource
- Clicking phone number

Track BOTH from the start. Micro conversions provide insights into the full customer journey and help diagnose conversion funnel issues.

---

## Cross-Device / Cross-Platform Tracking

GA4 can combine data from websites and apps in one property (cross-platform). To recognize users across devices:

1. Pass a **unique user ID** to GA4 in tracking requests
2. User ID must be the same on all devices (customer number, hashed email after login)
3. Without user ID, GA4 falls back to cookie-based identification (limited to single device/browser)

---

## E-Commerce Tracking Events

### Standard Event Flow

```
view_item -> add_to_cart -> begin_checkout -> purchase
```

### Item-Level Parameters

Each e-commerce event carries item parameters:
- `item_id` -- product SKU or unique identifier
- `item_name` -- product name
- `item_category` -- product category (supports up to 5 levels)
- `price` -- unit price
- `quantity` -- number of items

### Extended Tracking

- Shopping cart additions AND abandonments
- Wish list additions
- Individual checkout steps
- Voucher/coupon usage and redemption rates
- Registration/login events
- Repeat buyer identification
- User lifetime value calculations

### Data Import

GA4's data import feature allows uploading product catalog data for enrichment. This adds dimensions (brand, margin, supplier) to e-commerce reports without modifying tracking code.

---

## UTM Parameters for Campaign Tracking

### Required Parameters

| Parameter | Purpose | Example Values |
|-----------|---------|---------------|
| utm_source | The referrer platform | newsletter, facebook, google, linkedin |
| utm_medium | Marketing medium type | email, cpc, social, referral, organic |
| utm_campaign | Specific campaign name | spring-sale-2026, product-launch |

### Optional Parameters

| Parameter | Purpose | Example Values |
|-----------|---------|---------------|
| utm_term | Paid search keyword | best-crm-software |
| utm_content | Ad/link variation | banner-v2, sidebar-link |

### Rules

- GA4 uses source/medium/campaign to classify traffic into channels
- Use consistent naming conventions across all campaigns
- Document UTM naming conventions in a shared spreadsheet
- Never use UTM parameters on internal links (breaks session attribution)
- UTM parameters are case-sensitive; standardize on lowercase

---

## AI Capabilities in GA4

### 1. Anomaly Detection
- Compares actual data against AI-generated forecasts
- Configurable sensitivity and training period
- Surfaces unexpected changes automatically
- Useful for detecting algorithm update impact

### 2. Predictive Audiences
- Segments based on predicted future behavior
- Purchase probability: likelihood of purchasing in next 7 days
- Churn probability: likelihood of not returning in next 7 days
- Requires sufficient data volume to generate predictions

### 3. Traffic and Conversion Modeling
- Reconstructs data from users who declined tracking consent
- Uses behavior of consenting users as statistical basis
- Requires minimum data thresholds for accuracy

### 4. External AI Analysis
- Export GA4 data as CSV
- Upload to ChatGPT for ad-hoc analysis and chart generation
- **Privacy caveat:** deactivate training data usage in ChatGPT settings before uploading analytics data
