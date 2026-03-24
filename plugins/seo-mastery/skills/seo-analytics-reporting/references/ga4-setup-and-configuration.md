# GA4 Setup & Configuration: Complete SEO Implementation Guide

**Length:** ~350 lines

## Part 1: Account Structure

**Best practice:** Single GA4 property per domain

```
Google Account
└── GA4 Property: yourdomain.com
    ├── Data Stream 1: yourdomain.com (web)
    ├── Data Stream 2: staging.yourdomain.com (testing)
    └── Admin settings (filters, consent, referrer exclusion)
```

## Part 2: Data Stream Setup

### Create Web Data Stream

1. **GA4 Property** → **Data Streams** → **Create**
2. **Select platform:** Web
3. **Enter website URL:** yourdomain.com
4. **Stream name:** "yourdomain.com Production"
5. Copy **Measurement ID** (starts with G-)

### Install Google Tag Manager (Recommended)

Instead of direct gtag.js installation, use GTM:

1. **Create GTM account:** tagmanager.google.com
2. **Create GTM container** for web
3. **Install GTM container code** on all pages (one code snippet)
4. **Inside GTM**, add GA4 configuration tag
   - Tag type: Google Analytics: GA4 Configuration
   - Measurement ID: [Paste G- ID from GA4]
   - Trigger: Initialization - All Pages

**Benefits:**
- Manage tags without code changes
- Add Facebook Pixel, LinkedIn Pixel, custom tags easily
- A/B test tag changes before deployment

## Part 3: Critical GA4 Settings

### Enable Enhanced Measurement

GA4 → Admin → Data Streams → [Stream] → Enhanced Measurement

Enable:
- Page views ✅
- Scroll tracking ✅
- Outbound link clicks ✅
- Site search ✅
- File downloads ✅
- Video engagement ✅

### Configure Data Retention

GA4 → Admin → Data Settings → User data retention

**Recommendation:** 14 months (balances privacy + historical data)

### Set Up Internal Traffic Filter

GA4 → Admin → Data Filters → Create new filter

```
Filter name: "Internal Traffic"
Status: Active
Filter type: Custom
Condition: Traffic type > contains > organic
[This example filters internal organic only - adjust as needed]
```

**Alternative:** Filter by office IP range:
```
Condition: IP address > matches regex > ^192\.168\.1\..*
[Adjust for your office IP range]
```

### Referrer Exclusion

GA4 → Admin → Data Streams → [Stream] → View Settings → Referral exclusion list

Add:
- yourdomain.com (avoid self-referrals)
- payment-gateway.com (if using Stripe, WooCommerce, etc.)
- email-platform.com (if Mailchimp, ActiveCampaign, etc.)

**Purpose:** Prevents artificial referral traffic from inflating metrics.

## Part 4: Custom Events Setup

### Pre-built Recommended Events

GA4 recognizes these without custom setup:

```
purchase               // Ecommerce transaction
add_to_cart            // Product added to cart
view_item              // Product page viewed
begin_checkout         // Started checkout
login                  // User logged in
sign_up                // New user signup
search                 // Site search performed
```

### Custom Events (SEO-Specific)

Create custom events for SEO-relevant actions:

**Event: contact_form_submitted**
```json
Event name: "contact_form_submitted"
Event parameters:
  - form_location: "blog-sidebar" | "contact-page" | "footer"
  - form_type: "demo" | "inquiry" | "newsletter"
```

**Event: guide_downloaded**
```json
Event name: "guide_download"
Event parameters:
  - guide_name: "[name of guide]"
  - guide_category: "[category]"
```

**Event: pricing_page_viewed**
```json
Event name: "pricing_page_view"
Event parameters:
  - pricing_tier: "starter" | "pro" | "enterprise"
```

**Implementation (via GTM):**

1. GTM → Tags → New Tag
2. Tag type: Custom HTML
3. Paste:
```javascript
gtag('event', 'contact_form_submitted', {
  'form_location': 'blog-sidebar',
  'form_type': 'demo'
});
```
4. Create trigger: "Form Submission"
5. Publish

## Part 5: Custom Dimensions & Metrics

### Create Custom Dimensions

GA4 → Admin → Custom definitions → Create custom dimension

**Dimension 1: Content Type**
```
Dimension name: "content_type"
Scope: Page
Description: "Type of page (blog, product, service)"
Event parameter: content_type
```

**Dimension 2: Traffic Intent**
```
Dimension name: "traffic_intent"
Scope: Session
Description: "Intent of organic traffic (informational, commercial, transactional)"
Event parameter: traffic_intent
```

### Create Custom Metrics

GA4 → Admin → Custom definitions → Create custom metric

**Metric 1: Engagement Rate**
```
Metric name: "engagement_rate"
Description: "% of sessions with meaningful engagement"
Calculation: engaged_sessions / sessions
Unit: Percentage
```

## Part 6: Key Events Configuration

Mark important conversion events as "Key Events" so GA4 optimizes reporting around them.

GA4 → Admin → Conversions

1. Click "New conversion event"
2. Select event: contact_form_submitted
3. Enable "Mark as key event"
4. Click "Create"

Repeat for:
- purchase (if ecommerce)
- contact_form_submitted
- guide_download
- demo_scheduled

**Why it matters:** GA4 uses key events for:
- Insights & anomaly detection
- Attribution modeling
- Conversion rate optimization suggestions

## Part 7: Audience Creation

GA4 → Data & Privacy → Audiences

### Create Audience: High-Value Organic Traffic

```
Audience name: "Organic - High Engagement"
Conditions:
- traffic_source = "google"
- traffic_medium = "organic"
- engagement_rate > 50%
```

### Create Audience: Organic Converters

```
Audience name: "Organic - Converted"
Conditions:
- traffic_source = "google"
- traffic_medium = "organic"
- completed_purchase = true
```

### Create Audience: Blog Readers

```
Audience name: "Blog Readers"
Conditions:
- page_path contains "/blog/"
- session_duration > 60 seconds
```

## Part 8: Conversion Tracking Verification

### Real-Time Report

GA4 → Reports → Real-time

1. On your site, complete a conversion action (submit form, make purchase)
2. Refresh GA4 real-time view
3. Verify event appears within 30 seconds
4. Check event parameters are captured correctly

**If not appearing:**
- Check GTM: Verify tag is firing (GTM Preview mode)
- Check measurement ID is correct
- Wait 24 hours for initial data (GA4 can be slow)

### Conversion Validation Report

GA4 → Admin → Conversion events

Verify:
- Event count > 0 (conversions are recording)
- Event parameters complete (no null values)
- No suspicious spikes (indicates measurement error)

## Part 9: Integration with Google Search Console

Link GA4 to GSC for keyword data:

GA4 → Admin → Product Links → Google Search Console

1. Click "Link"
2. Select GSC property
3. GA4 will import keyword data
4. Reports → Acquisition → Google Organic Search → Queries

Now you can see:
- Which keywords drive conversions
- Conversion rate by keyword
- Revenue by keyword

## Part 10: Consent Mode Configuration

If you use cookie banner (OneTrust, Cookiebot, etc.):

GA4 → Admin → Data Settings → Consent settings

Set default consent state:
```
Analytics cookies: Denied (until user accepts)
Advertising cookies: Denied (until user accepts)
```

Update GTM container to respect consent:
- Only fire GA4 tag if user accepts analytics
- Only fire ads pixels if user accepts marketing

## Part 11: Regular Maintenance

### Weekly
- [ ] Check real-time report for anomalies
- [ ] Verify key events are recording

### Monthly
- [ ] Review custom events (any events firing unexpectedly?)
- [ ] Check data quality (nulls, errors)
- [ ] Create backup report (export current data)

### Quarterly
- [ ] Review data retention settings
- [ ] Update custom dimensions (new content types, etc.)
- [ ] Audit internal traffic filter effectiveness

## Checklist: Before Declaring GA4 Complete

- [ ] Measurement ID installed on all pages
- [ ] Enhanced measurement enabled
- [ ] At least 3 key events configured
- [ ] Internal traffic filtered
- [ ] Custom dimensions created (content_type, intent)
- [ ] Real-time report shows conversions
- [ ] Data arriving for 7+ days
- [ ] GSC linked (for keyword integration)
- [ ] Consent mode configured (if applicable)
