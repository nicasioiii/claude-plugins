---
name: Google Ads Account Setup
description: Complete Google Ads account setup including Merchant Center configuration, product validation criteria, product feed optimization, conversion tracking with enhanced conversions, and Google Tag Manager implementation. Use when starting Google Ads from scratch, auditing setup, or fixing conversion tracking issues.
---

# Google Ads Account Setup

## CRITICAL FOUNDATION: Conversion Tracking First

**RULE:** Conversion tracking is oxygen for Google Ads. Without it, you cannot:
- Run smart bidding
- Optimize campaigns
- See ROI
- Scale profitably

You are flying blind without conversion tracking. Set this up BEFORE running any campaigns.

---

## PART 1: MERCHANT CENTER SETUP & PRODUCT APPROVAL

### Pre-Approval Strategy: The Bootstrap Approach

Google has no problem with dropshipping—it has a problem with scammers. Your approval strategy:

**Initial Submission (Products for Approval)**
1. Use 5-15 non-branded products from your own home (photograph with your phone)
2. Write ORIGINAL 50-200 word descriptions (not copied from AliExpress/eBay)
3. Take multiple images per product (3-5 minimum for realism)
4. Price each differently—NO uniform 50% markups across catalog
5. Avoid "compare at" prices initially (suspicious to Google)
6. Build professional website with complete policy pages (Privacy, Terms, Shipping, Returns) BEFORE submission
7. Only after approval: Replace with actual dropshipping products

**Product Categories to AVOID for Approval:**
- TVs and electronics
- Books
- Digital products
- Health supplements and beauty creams
- Anything with inhalants
- Anything requiring government licensing

**Collections Must Match Products:**
- Home & Garden products go in Home & Garden collection (not random)
- Google audits collection accuracy as part of approval

### Product Validation Checklist (BEFORE Adding to Feed)

Every product must pass these thresholds. Non-negotiable:

| Criterion | Requirement | Why |
|-----------|------------|-----|
| Monthly searches | 25,000+ minimum | Demand must exist |
| Per-keyword searches | 800+ minimum per keyword | Avoid tail keywords |
| Keyword count | 4+ keywords meeting 800+ threshold | Sufficient search variety |
| Profit margin | $25+ minimum | Economics must work |
| Competitor count | 4-7 dropshippers per keyword | Not too hot, not dead |
| Pricing validation | Competitors selling $20+ | Eliminates scams |
| Seasonal demand | Viable across all 12 months | Year-round viability |

**Tools for Validation:**
- Google Keyword Planner: Verify search volume
- Google Shopping: Check competitor pricing and count
- Search product name: Confirm competitor selling price points

**Red Flag:** All competitors selling suspiciously low prices = likely scam market. Skip it.

### Shopping Campaign Structure

**Campaign Setup:**
- Type: Standard Shopping Campaign (NOT Smart Shopping initially)
- Geographic Target: United States ONLY (one location per campaign)
- Minimum products: 20-25 before launching
- Campaign naming: "[Category - HIGH BID]" and "[Category - LOW BID]"

**Bidding Strategy for New Accounts:**
1. START with Maximize Clicks (not Target ROAS)
2. WHY: Needs $500-$1,000+ historical data before ROAS works properly
3. Manual CPC alternative: $0.30-$0.50 starting bid per product
4. As conversion data builds: Decrease bids for products with ROAS 1.0-2.0
5. A/B testing: Try $0.30 vs $0.50 on similar products to find sweet spot

**Maximize Clicks advantages:**
- Algorithm learns audience faster
- Automatically optimizes bids
- CPC naturally decreases as conversion data builds
- No manual bid adjustment needed

---

## PART 2: PRODUCT FEED ESSENTIALS

### Product Title (SEO Title) - The 50/45/5 Rule

50% of visibility = Title
45% of visibility = Images
5% of visibility = Everything else

**Title Structure (Left-to-Right Keyword Priority):**
1. Highest search volume keyword (LEFTMOST)
2. Variants of high-volume keywords
3. Brand positioning/unique angle
4. Example: "Colorblind Corrective Glasses for Color Blindness | Premium Testing Eyewear"

**Title Rules:**
- DO keyword optimize but MUST read naturally in English
- DO NOT keyword stuff or repeat same keyword multiple times
- DO NOT use filler words ("for people", "for you", "bestseller")
- DO NOT include competitor brand names
- Max keyword count: 3-5 primary keywords
- Test: "Would I click this if I saw it on Google Shopping?"

### Product Images - Lifestyle > Studio Shots

**Image Reality:**
- Real-use-case images (lifestyle) outperform generic white-background shots
- Case study: Same product with lifestyle image = $150 price vs white background = $100 price

**Image Requirements:**
- 3-5 images minimum per product
- All products must have similar professional quality
- Consistency across entire catalog essential
- Competitor analysis: Look at top 3-5 ranking products, replicate quality/style (not copy)

**Image Selection Strategy:**
- Lead with lifestyle shot (person using/wearing product)
- Include detail/close-up shots
- Include scale shot (item next to common object for size reference)
- Include packaging/unboxing shot (if applicable)

### Product Descriptions (50-200 Words Original)

- Original descriptions = higher approval chances
- Google detects copied/spun text
- Must be appropriate to collection category
- Include use cases and benefits (not just features)
- Avoid exaggerated claims without backup

### Product Pricing Strategy

**Price Point Validation:**
- Product must have competitors selling at your price point
- Example: $350 cost product + $30 profit = $380 selling price (must compete on image quality, not price alone)
- If all competitors selling suspiciously low = red flag product
- Validation: Search product on Google Shopping, check 3-5 top sellers' prices

**Price Variation Rule:**
- Do NOT set same discount (e.g., 50% off) across entire catalog
- Vary markup across products based on market position
- Avoid "compare at" prices initially (suspicious during approval)

---

## PART 3: CONVERSION TRACKING SETUP

### Why NOT Google Analytics 4 for Bidding

**The Trap:**
- GA4 and Google Ads sync beautifully (both Google properties)
- TRAP: Do NOT import GA4 conversions into Google Ads for bidding

**Why:**
- GA4 tracks sessions and user journeys (not transaction-level events)
- Google Ads needs precise transaction-level data for smart bidding
- GA4 reporting lag conflicts with real-time bidding optimization
- Use GA4 as reporting comparison side-by-side, not as bidding source

**RULE:** Set up Google Ads conversion tracking directly on your website. Not GA4. Not imported. Direct.

### Conversion Tracking Setup Steps

**Step 1: Access Conversions Menu**
- Sign in to Google Ads (ads.google.com)
- Click Tools & Settings (wrench icon, top right)
- Select "Conversions" under Measurement section

**Step 2: Create New Conversion Action**
- Click "+" button to create conversion
- Choose conversion type: Website
- Name: "Purchase" (primary) or specific action name
- Category: Choose best match (e.g., Purchase for ecommerce)

**Step 3: Configure Conversion Settings**
- Count option: "All" (counts every conversion)
- Conversion window: 30 days default (reasonable for most ecommerce)
- Value: Assign order value (enables value-based optimization)
- Include in Conversions: YES

**Step 4: Choose Tracking Method**
- Method: Website (not Import)
- Install conversion tag on your thank-you/purchase confirmation page

### Enhanced Conversions Implementation (Post-Purchase Data)

**What It Is:**
- Server-side conversion verification (more reliable attribution)
- Send purchase data (email, phone, name, address) to Google for matching
- Increases conversion accuracy and attribution reliability
- Works with first-party data (your customer data)

**Enhanced Conversions Setup:**
1. Create custom conversion with Enhanced Conversions enabled
2. Send customer data (hashed) to Google Conversion API
3. Google matches data to user profile
4. More accurate attribution window (helps with iOS tracking loss)

**Data Elements to Send (Hashed):**
- Email address
- Phone number
- First/last name
- Street address
- City/state/zip
- Country

**Privacy Compliance:**
- Hash all PII before sending to Google
- Obtain customer consent for data sharing
- Comply with GDPR/CCPA requirements

---

## PART 4: TAG MANAGER & EVENTS IMPLEMENTATION

### Google Tag Manager Setup Basics

**Purpose:**
- Centralized tag management (no code edits needed)
- Track multiple events without touching website code
- Easy A/B testing and event modifications

**Installation:**
1. Create Google Tag Manager account
2. Install GTM container code in website header
3. Add Google Ads conversion tag in GTM
4. Create event triggers for purchase/lead/view actions
5. Test using Preview mode before publishing

### Event Implementation Priority (Ecommerce)

**Tier 1 (CRITICAL):**
- Purchase: Must send order value, product IDs, category

**Tier 2 (HIGH VALUE):**
- Add to Cart: Intent signal for remarketing
- View Item: Funnel tracking
- Initiate Checkout: Drop-off analysis

**Tier 3 (OPTIONAL):**
- View Category: Broad interest signals
- Search: Query understanding

### Purchase Event Data Requirements

**MUST Include:**
- Conversion value (order total including tax/shipping)
- Transaction ID (unique per order, prevents double-counting)
- Currency (USD, EUR, etc.)
- Product IDs (if multi-product order)

**Example Event:**
```
gtag('event', 'purchase', {
  'transaction_id': '12345_6789',
  'value': 149.99,
  'currency': 'USD',
  'items': [
    {
      'id': 'SKU_12345',
      'quantity': 1
    }
  ]
});
```

---

## PART 5: ACCOUNT STRUCTURE BASICS

### When to Segment Campaigns

**Segment by Geography:**
- Different countries = different campaign (different currencies, languages, shipping)
- US-only vs multi-country should be separate
- Regional testing (different ad angles for regions) = separate campaigns

**Segment by Product Category:**
- Different product types = different audience intent
- Electronics vs home goods = different searcher behavior
- Allows category-specific bid strategies

**Segment by Bidding Strategy:**
- High-bid test campaigns separate from low-bid
- Different optimization events separate (Purchase vs Lead)
- Prevents algorithm confusion

**DON'T Over-Segment:**
- Too many small campaigns = poor data, slow learning
- Minimum: 20-25 products per campaign for data sufficiency
- Consolidate unless you have specific testing need

### Account Health Checklist

- [ ] Conversion tracking live and firing on purchase confirmation page
- [ ] Google Ads conversion pixel installed (NOT GA4 import)
- [ ] Enhanced Conversions enabled for high-value conversions
- [ ] Tag Manager events tested in Preview mode
- [ ] All products validated for demand (25k+ searches minimum)
- [ ] All products have profit margin $25+ minimum
- [ ] All product titles optimized (keywords left-to-right)
- [ ] All products have 3-5+ images (lifestyle preferred)
- [ ] Merchant Center account clean (no disapprovals pending)
- [ ] Shopping campaign structure labeled clearly (HIGH BID / LOW BID)
- [ ] Bidding strategy set to Maximize Clicks (not ROAS on new accounts)

---

## QUICK REFERENCE: Common Mistakes

| Mistake | Impact | Fix |
|---------|--------|-----|
| Using GA4 conversions for bidding | Poor attribution, wasted spend | Set up Google Ads conversion tracking directly |
| Launching without conversion tracking | Flying blind, no ROI visibility | Pause campaigns, install conversion tags first |
| Adding products under $25 profit | Unprofitable at scale | Remove immediately, focus on $25+ margin products |
| Launching with <20 products | Insufficient data for algorithm | Add minimum 20-25 products to campaign |
| Using Target ROAS on new accounts | Algorithm breaks, overspend | Use Maximize Clicks until you have $500-$1,000 spend history |
| Identical product prices across catalog | Google flags as scam | Vary markups based on market position |
| Product images with white background only | Lower CTR and lower prices | Use lifestyle images, 3-5 varied shots per product |
| Skipping original product descriptions | Higher disapproval risk | Write 50-200 word original descriptions |

---

## Reference Files

See detailed implementation in:
- `/references/google-merchant-center.md` — Complete Merchant Center approval workflows
- `/references/google-conversion-tracking.md` — Event implementation, attribution models, UTM strategy
- `/references/google-product-feed.md` — Product title construction, image optimization, pricing validation process
