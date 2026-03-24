# Google Conversion Tracking Implementation Guide

## Core Principles

### Why NOT Google Analytics 4

**The Mistake:**
Many account holders assume GA4 conversions are sufficient for Google Ads. This is incorrect for bidding optimization.

**The Problem:**
- GA4 tracks sessions and user journeys (aggregate data)
- Google Ads needs transaction-level precision for smart bidding
- GA4 reporting lag (6-24 hours) conflicts with real-time bidding
- GA4 definition of "conversion" may not match your business goal
- Import GA4 conversions for comparison reporting only, never as bidding source

**The Solution:**
Set up Google Ads conversion tracking directly on your website. GA4 is complementary, not a replacement.

---

## Google Ads Conversion Tracking Setup

### Step 1: Access Conversions Interface

**Path in Google Ads:**
1. Sign in to ads.google.com
2. Click Tools & Settings (wrench icon, top right)
3. Under "Measurement" section, click "Conversions"
4. New Google Ads: May say "0 conversion actions here"

### Step 2: Create Conversion Action

**Click "+ Conversion" button**

### Step 3: Choose Conversion Type

**Website Options:**
- **Purchase** (recommended primary conversion)
- **Lead** (form submissions, newsletter signup)
- **View Form** (form views for lead quality)
- **Phone Call** (call clicks to phone number)
- **App Download** (mobile app installs)

**Select "Website" for ecommerce**

### Step 4: Fill Conversion Details

**Conversion Name:**
- Primary: "Purchase"
- Alternatives: "Sale", "Order Completed", "Transaction"
- Keep names consistent across account

**Category:**
- Purchase/Sale (for ecommerce)
- Lead (for form submissions)
- Sign Up (for email opt-ins)
- Choose the most accurate match

**Value:**
- Static value: Fixed amount per conversion (e.g., $50)
- Dynamic value: Varies per transaction (use order value)
- **Recommendation: Use dynamic value** (varies by order amount)

**Count Option:**
- "All" (default) — Count every conversion
- "One" — Count only first conversion per session
- **Recommendation: Use "All"** for transaction tracking (captures repeat purchases)

### Step 5: Configure Conversion Settings

**Conversion Window:**
- Default: 30 days (counts conversion if user converts within 30 days of click)
- Options: 1, 7, 15, 30, 60, 90 days
- **Recommendation: 30 days** (standard ecommerce window)
- Why: Accounts for decision-making cycle (research, comparison shopping, purchase)

**Include in 'Conversions':**
- Toggle: ON (default)
- Means: This conversion counts toward campaign metrics and optimization
- Keep ON for primary goal (Purchase)
- Can turn OFF for secondary metrics you want to track but not optimize for

**Attribution Model:**
- Data-driven (recommended for high-volume accounts)
- First-click (give credit to first touchpoint)
- Last-click (give credit to final touchpoint)
- **Recommendation: Data-driven** (requires 15,000 conversions in past 90 days)
- Fallback to Last-click if insufficient data

### Step 6: Choose Tracking Method

**Two Options:**
1. **Website** — Install conversion tag on your website (recommended)
2. **Import** — Import conversion data from third-party sources

**Select "Website"**

### Step 7: Select Installation Method

**For Ecommerce (Recommended):**
1. **Use Google Tag Manager** (easier, no code editing)
2. **Install Global Site Tag** (if no GTM)

**For All Platforms:**
- Get tracking code
- Install on thank-you/purchase confirmation page
- Test before going live

---

## Google Tag Manager Implementation (Recommended)

### GTM Setup Process

**Create GTM Account:**
1. Go to tagmanager.google.com
2. Create new account (or use existing)
3. Choose website as container type
4. Get container code

**Install GTM Container Code:**
- Place container code in website header (before closing </head> tag)
- This loads GTM infrastructure
- Allows tag/trigger management without website edits

### Creating Conversion Event in GTM

**Step 1: Create Tag**
- Tag type: Google Ads Conversion
- Conversion ID: (from Google Ads setup)
- Conversion Label: (from Google Ads setup)
- Trigger: Custom event "purchase"

**Step 2: Create Trigger**
- Type: Custom event
- Event name: "purchase"
- This matches e-commerce event fired by your platform

**Step 3: Test in Preview Mode**
- Enable Preview mode in GTM
- Visit website
- Complete purchase
- Check Preview for tag firing
- Confirm conversion tracking code executes

**Step 4: Publish**
- Click "Submit" in GTM
- Waits 24-48 hours for data to populate in Google Ads

### Verify Installation

**Method 1: Google Ads Conversion Tracking Report**
- After 48 hours, go to Conversions report
- Check "Conversion Tracking Status"
- Should show "Tag is firing" (green check)

**Method 2: Google Tag Assistant Browser Extension**
- Install Google Tag Assistant extension
- Visit website
- Complete test purchase
- Extension shows conversion tag executing in real-time

**Method 3: Google Ads Conversion Helper**
- In Google Ads, click "Test conversion" next to conversion
- Shows if conversion can be detected
- Useful for troubleshooting

---

## Ecommerce Event Data Implementation

### Google Analytics 4 Event Syntax

**Most Platforms (Shopify, WooCommerce, BigCommerce):**
Connect GA4 to GTM, which auto-fires purchase events.

**Custom Implementation:**

### Purchase Event (Primary Conversion)

```javascript
gtag('event', 'purchase', {
  'transaction_id': '12345_abc',          // Unique order ID
  'affiliation': 'Google Store',           // Store/channel name
  'value': 149.99,                         // Total order value (required)
  'currency': 'USD',                       // Currency code (required)
  'tax': 19.99,                            // Tax amount
  'shipping': 14.99,                       // Shipping cost
  'items': [
    {
      'item_id': 'SKU123',                // Product ID
      'item_name': 'Colorblind Glasses',  // Product name
      'affiliation': 'Seller',             // Seller name
      'item_category': 'Accessories',      // Product category
      'price': 129.99,                     // Unit price
      'quantity': 1                        // Quantity purchased
    }
  ]
});
```

**CRITICAL FIELDS:**
- `transaction_id`: Unique per order (prevents duplicate counting)
- `value`: Total order amount (enables value optimization)
- `currency`: Currency code (USD, EUR, GBP, etc.)
- `items`: Product details (if multi-product order, add multiple items)

### AddToCart Event

```javascript
gtag('event', 'add_to_cart', {
  'value': 129.99,
  'currency': 'USD',
  'items': [
    {
      'item_id': 'SKU123',
      'item_name': 'Colorblind Glasses',
      'price': 129.99,
      'quantity': 1
    }
  ]
});
```

**Purpose:** Track purchase intent (signals product interest without conversion)

### ViewContent Event

```javascript
gtag('event', 'view_item', {
  'items': [
    {
      'item_id': 'SKU123',
      'item_name': 'Colorblind Glasses',
      'item_category': 'Accessories',
      'price': 129.99
    }
  ]
});
```

**Purpose:** Track product page visits (funnel awareness)

### InitiateCheckout Event

```javascript
gtag('event', 'begin_checkout', {
  'value': 129.99,
  'currency': 'USD',
  'items': [
    {
      'item_id': 'SKU123',
      'item_name': 'Colorblind Glasses',
      'price': 129.99,
      'quantity': 1
    }
  ]
});
```

**Purpose:** Track checkout abandonment (helps identify cart issues)

---

## Troubleshooting Conversion Tracking

### Common Issues & Fixes

| Issue | Cause | Fix |
|-------|-------|-----|
| "No recent conversions" | Code not firing | Verify tag placement on thank-you page |
| "Tag is NOT firing" | Page not loading tag | Check GTM preview, ensure page has tag |
| "Conversions showing but ROAS is wrong" | Value not included | Add order value to purchase event |
| "Duplicate conversions" | Same order counted twice | Add `transaction_id` to prevent duplicates |
| "Data not in Google Ads after 48h" | Waiting period | GA4 sync can take 48-72 hours |

### Testing Process

**Manual Test (Before Going Live):**
1. Copy thank-you page URL
2. Add `?debug=true` to URL
3. Visit conversion page
4. Open browser developer console (F12)
5. Search for "gtagSendEvent" or "Purchase"
6. Verify event fires with correct data
7. Remove debug parameter before launch

**QA Testing:**
1. Create test purchases through your system
2. Use GTM Preview mode
3. Watch for tag firing in real-time
4. Verify data in GTM Preview panel
5. Confirm purchases appear in Google Ads Conversions report (next day)

**Production Verification:**
- Go live with tracking code
- Monitor for 24-48 hours
- Check Google Ads "Conversions" report
- Status should show green "Tag is firing"

---

## Attribution Models & Settings

### Multi-Touch Attribution

**Data-Driven Attribution (Recommended):**
- Gives credit to each touchpoint based on actual impact
- Requires: 15,000 conversions in past 90 days
- Most accurate for complex customer journeys
- **If you have sufficient volume: Use this**

**Last-Click Attribution (Default):**
- Gives 100% credit to final touchpoint (last ad clicked)
- Simple, easy to understand
- Slightly undervalues early awareness ads
- **Use if: <15,000 conversions per 90 days**

**First-Click Attribution:**
- Gives 100% credit to first touchpoint
- Useful for awareness campaigns
- Undervalues conversion-stage ads
- **Rarely recommended for primary optimization**

### Attribution Window Explained

**What It Means:**
- 30-day window: If user clicks ad on Day 1, purchases on Day 25 = counts as conversion
- If user purchases on Day 31 = does NOT count

**Why It Matters:**
- Longer window = more conversions counted (inflates ROI)
- Shorter window = fewer conversions counted (deflates ROI)
- Should match your customer decision cycle

**Recommendation by Business Type:**

| Business | Window | Why |
|----------|--------|-----|
| Impulse products (<$30) | 7 days | Quick purchase decision |
| Standard ecommerce ($30-500) | 30 days | Customer research cycle |
| High-ticket items (>$1,000) | 60-90 days | Extended decision-making |
| B2B/Enterprise | 90 days | Long sales cycles |

---

## Enhanced Conversions Setup

### Purpose & Benefits

**What It Does:**
- Matches purchase data to user Google accounts
- Increases conversion attribution accuracy
- Helps track iOS users (where app tracking is limited)
- Improves customer journey understanding
- Enables more accurate Smart Bidding

**Requirements:**
- Customer email, phone, name, address
- Hash function (SHA-256 or MD5)
- First-party data consent (GDPR/CCPA compliant)
- Google customer match capability

### Implementation Steps

**Step 1: Enable Enhanced Conversions**
- In Google Ads, go to Conversions settings
- Click conversion action
- Enable "Enhanced Conversions"
- Choose data collection method (automatic or manual)

**Step 2: Collect Customer Data (Manual Method)**
```
Collect on thank-you page:
- Email address
- Phone number (full international format)
- First name
- Last name
- City
- State/Province
- Postal code
- Country
```

**Step 3: Hash PII Data**
- Use SHA-256 hash function
- Hash email: Remove spaces, convert to lowercase, hash
- Hash phone: Remove spaces/dashes, hash
- Never send unhashed PII to Google

**Step 4: Send to Google Conversion API**
```javascript
// Example with hashed data
gtag('event', 'purchase', {
  'transaction_id': '12345_abc',
  'value': 149.99,
  'currency': 'USD',
  'user_data': {
    'email_address': 'sha256_hash_of_email',
    'phone_number': 'sha256_hash_of_phone',
    'first_name': 'sha256_hash_of_first_name',
    'last_name': 'sha256_hash_of_last_name',
    'city': 'sha256_hash_of_city',
    'state': 'sha256_hash_of_state',
    'postal_code': 'sha256_hash_of_zip',
    'country': 'sha256_hash_of_country'
  }
});
```

**Step 5: Privacy Compliance**
- Obtain explicit consent for data sharing (checkbox on checkout)
- Include in Privacy Policy
- Comply with GDPR (EU) and CCPA (California)
- Document consent timestamp

### Privacy & Compliance

**GDPR Compliance:**
- Obtain explicit opt-in consent before data collection
- Include specific language about Google data sharing
- Allow users to opt-out
- Document consent for 3+ years
- Implement data deletion requests

**CCPA Compliance:**
- Disclose data collection in Privacy Policy
- Allow users to "Do Not Sell My Personal Information"
- Provide data deletion mechanism
- Track opt-out compliance

**General Privacy Best Practices:**
- Only collect minimum required data
- Hash before transmission to Google
- Use secure HTTPS connections
- Never expose hashed values in logs
- Implement data retention policies

---

## Reporting & Analysis

### Key Metrics to Monitor

| Metric | Formula | Target |
|--------|---------|--------|
| Conversion rate | Conversions ÷ Clicks | 1-3% |
| Cost per conversion | Total spend ÷ Conversions | < 3x profit margin |
| ROAS | Revenue ÷ Ad spend | > 3.0 |
| Conversion value | Revenue from conversions | Growing |
| Conversion rate by product | Product conversions ÷ product clicks | > 1% |

### Monthly Review Checklist

- [ ] Conversion tracking firing properly (check status = green)
- [ ] Conversion value accurate (spot-check sample orders)
- [ ] No unusual spikes in conversion count
- [ ] Conversion rate stable (month-to-month)
- [ ] Top converting products identified
- [ ] ROAS by campaign documented
- [ ] UTM parameters consistent in URLs
- [ ] Enhanced conversions matching rate checked (if enabled)

### Quarterly Deep Dive

1. **Attribution Model Review:** Is current model still accurate?
2. **Conversion Window Analysis:** Is 30 days still right?
3. **Product Performance:** Which products converted most?
4. **Traffic Source Analysis:** Which channels drive best conversions?
5. **Seasonal Patterns:** Any time-of-year trends?
6. **Algorithm Performance:** Has Smart Bidding improved?
