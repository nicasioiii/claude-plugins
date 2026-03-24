# Google Merchant Center Complete Guide

## Account Setup & Approval

### Account Types

**New Account from Scratch:**
1. Create Google Merchant Center account (merchantcenter.google.com)
2. Connect to Google Ads account
3. Set primary country (USA for dropshipping)
4. Add website URL
5. Upload product feed (CSV, XML, or Google Sheets)

**Existing Business Account:**
1. Verify website ownership (meta tag or DNS)
2. Set up shipping and return policies
3. Input tax information (if applicable)
4. Connect Ads account
5. Upload product feed

### Merchant Center Data Requirements

**Required Fields for Every Product:**
- `id` — Unique product identifier (SKU or internal ID)
- `title` — Product name (keyword optimized, max 150 characters)
- `description` — Full product description (50-200 words original)
- `availability` — in stock, out of stock, preorder
- `price` — Selling price with currency
- `image_link` — URL to primary product image
- `link` — URL to product page on your website
- `brand` — Brand name (or your store name for non-branded)
- `condition` — new, refurbished, used
- `product_type` — Category path (Home & Garden > Furniture > Chairs)

**Highly Recommended Fields:**
- `additional_image_link` — URLs to 2-4 additional images
- `color` — Color variant if applicable
- `size` — Size variant if applicable
- `material` — Material composition
- `pattern` — Pattern (floral, striped, etc.)
- `shipping` — Shipping cost and time to delivery
- `shipping_label` — Shipping class (standard, oversized, etc.)
- `tax` — Tax rate if applicable
- `mpn` — Manufacturer part number (increases trust)
- `gtin` — UPC/EAN barcode (if available)

### Product Submission Strategy for Approval

**Phase 1: Bootstrap Approval (5-15 Products)**

**Why This Phase:**
- Google audits new accounts heavily for scam indicators
- Real photos + original descriptions = trust signals
- Approval from real products gives account credibility
- After approval, you replace entire catalog with dropshipping products

**Product Selection Rules:**
1. Use products from your own home/property
2. Photograph with your phone (real images, not pro studio)
3. Select variety: furniture, décor, kitchen items, etc.
4. Avoid restricted categories (electronics, supplements, etc.)
5. Price variation: $20-$200+ range (mix of high/low)
6. Collections match product category (don't mix home goods with fashion)

**Description Writing Process:**
1. Write 50-200 words about each product
2. Include actual use case (where it goes, how it's used)
3. Describe materials and dimensions
4. Be honest about condition (new, vintage, etc.)
5. Do NOT copy from anywhere (AliExpress, eBay, competitors)
6. Use natural English, not keyword-stuffed

**Image Checklist:**
- 3-5 images per product minimum
- Mix of angles: front, side, detail, lifestyle use
- Include scale reference (item next to common object)
- If furniture: show it in room context
- No watermarks or stock photo indicators
- Consistent lighting across all images
- All images must be original (not from internet)

**Website Quality Before Submission:**
- Professional header/footer with logo
- Complete About page (who are you, why do you sell this)
- Visible contact information (email, phone if possible)
- Privacy Policy page (required)
- Terms of Service page (required)
- Shipping Policy page (required)
- Return/Refund Policy page (required)
- Product pages well-formatted with descriptions
- Mobile-responsive design
- 20-25 products live before campaign launch

**Submission Checklist:**
- [ ] Website looks professional and complete
- [ ] All policy pages written and live
- [ ] 5-15 products with original photos
- [ ] Product descriptions written in your own words
- [ ] Pricing varied (not uniform markups)
- [ ] Collections assigned correctly
- [ ] Feed uploaded to Merchant Center
- [ ] Google review starts (1-3 business days typical)

**What Google Looks For During Approval:**
- Do images look real? (Not stock photos)
- Does description match image quality? (Professional = trustworthy)
- Is pricing reasonable? (Not suspiciously low)
- Do policies exist and are complete? (Trust signal)
- Is account history clean? (No prior violations)
- Do products match collections? (Attention to detail)

### Phase 2: Full Catalog Deployment (After Approval)

**Timeline:**
- Get approval notification from Google (email + Merchant Center alert)
- Usually 1-3 business days from submission
- Can happen instantly if account is clean and products look good

**Post-Approval Actions:**
1. Delete or unpublish initial bootstrap products
2. Upload full dropshipping product catalog (via feed)
3. Monitor for disapprovals (usually none if first batch approved)
4. Start shopping campaigns with Merchant Center account

**Catalog Upload Methods:**

**CSV Upload (Recommended for startups):**
- Create spreadsheet with all required fields
- Export as CSV
- Upload to Merchant Center
- Google validates and processes
- Typically 24 hours for full processing

**Feed URL (Recommended for scale):**
- Create XML or CSV feed that updates automatically
- Host on your server or feed management service
- Provide feed URL to Merchant Center
- Google fetches feed every 24 hours
- Automatic updates to inventory, pricing, etc.

**Spreadsheet Link (Limited):**
- Create Google Sheet with products
- Link to Merchant Center
- Limited to 5,000 products
- Good for testing before CSV/XML

### Troubleshooting Disapprovals

**Common Disapproval Reasons:**

| Reason | Cause | Fix |
|--------|-------|-----|
| "Unacceptable Business Practice" | Price too low compared to image quality | Increase price or improve product quality |
| "Prohibited Item" | Product in restricted category | Remove product, choose from allowed categories |
| "Misrepresentation" | Image doesn't match description | Update image or description to match |
| "Suspicious Activity" | Account flagged as test/scam | Provide business verification, wait 30 days |
| "Policy Violation" | Violates Google/legal policy | Review product against Google's merchant policies |

**Recovery Process:**
1. Identify disapproved products (Merchant Center > Status > Issues)
2. Read specific violation (usually detailed)
3. Fix product (image, description, pricing, or removal)
4. Resubmit for review
5. Monitor for approval (24-48 hours)
6. If denied again: appeal with explanation or remove product

**Appeal Process:**
- Click "Appeal" on disapproved product
- Provide detailed explanation of why product is compliant
- Include evidence (receipt, supplier documentation, etc.)
- Google reviews within 2-5 business days
- Usually approved if evidence supports your case

---

## Feed Management & Optimization

### Feed Quality Signals

**Google Prioritizes Products With:**
- Accurate, detailed descriptions (50+ words)
- 3+ high-quality images
- Matching collection category
- Original product photos (not generic stock)
- Reasonable pricing with competitor validation
- In-stock status (not "preorder" or "out of stock")
- Complete data (no missing fields)
- Fast shipping time (< 5 days to delivery)

**Products That Underperform:**
- Generic one-line descriptions
- Single blurry image
- Wrong collection (home goods in fashion)
- Suspiciously low prices (75% off everything)
- Preorder or "coming soon" status
- Missing shipping information
- Incomplete product data

### Feed Update Frequency

**Daily Updates Recommended For:**
- Inventory status (in stock vs out of stock)
- Price changes (competitor pricing adjustments)
- High-velocity items (seasonal products, trending)
- Sales/discounts (limited-time offers)

**Weekly Updates Acceptable For:**
- Product descriptions (content rarely changes)
- Images (unless rotating new photos)
- Shipping information (usually static)
- Collections/categories (organizational rarely changes)

**Update Method:**
- Automated feed URL: Google fetches daily, auto-updates
- Manual CSV upload: Upload new file to override previous
- Google Sheets: Link persists, updates as you edit
- E-commerce platform (Shopify/WooCommerce): Auto-syncs if connected

### Feed Optimization Rules

**Titles (Max 150 characters):**
- Left-to-right keyword priority
- Highest search volume keyword first
- Natural English (read it aloud test)
- No duplicate keywords
- Include color/size if variants exist in same listing
- Example: "Vintage Oak Dining Chair | Mid-Century Modern Seating"

**Descriptions (50-200 words):**
- First sentence: What is it? What does it do?
- Middle: Materials, dimensions, use cases
- End: Benefits or unique features
- Use natural paragraphs (not walls of text)
- Include care instructions if relevant
- Avoid price in description (price field separate)

**Images (3-5 minimum):**
- Image 1: Primary product shot (clean background ok)
- Image 2: Alternative angle or lifestyle use
- Image 3: Detail shot (fabric texture, stitching, etc.)
- Image 4: Scale reference (with hand or common object)
- Image 5: Packaging or unboxing (if applicable)
- All images must be original to your store
- All images minimum 800×800 pixels
- Use JPG format (faster loading)

**Pricing Strategy in Feed:**
- Include actual selling price (what customer pays)
- Include cost (for Google's competitive analysis)
- If discount: Include original price in "compare at" field
- All prices in same currency
- Update prices within 24 hours of any change
- Competitive pricing: Check 5 competitors before setting price

**Availability Status Values:**
- `in stock` — Ready to ship (default)
- `out of stock` — Temporarily unavailable
- `preorder` — Available for advance purchase
- `backorder` — Restocking, will ship later
- Google prioritizes "in stock" products in results

**Product Collections (Critical for Approval):**
- Match collection to actual product
- Example collections:
  - Home & Garden > Furniture > Chairs
  - Home & Garden > Kitchen & Dining > Cookware
  - Fashion > Women's > Clothing > Tops
- Mismatched collection = potential disapproval
- Check product against category rules before assignment

---

## Merchant Center Account Management

### Store Info Configuration

**Required Information:**
- Store name (your business name)
- Contact email (monitored daily)
- Phone number (Google may call for verification)
- Store URL (must match Ads account domain)
- Country of operation (primary market)

**Shipping Configuration:**
- Shipping methods (Standard, Express, Overnight)
- Shipping cost calculation (flat, percentage, by weight)
- Delivery timeframe (1-3 business days, 4-7 days, etc.)
- Regions (US only vs international)
- Free shipping threshold (if applicable)

**Tax Configuration (if required):**
- Tax rate by region (state level for US)
- Tax-exempt categories (if applicable)
- Applied to shipping (yes/no)
- Sales tax nexus requirements

**Returns/Refund Policy:**
- Return window (30 days, 60 days, etc.)
- Who pays return shipping (you or customer)
- Refund timeline (immediate, 5-10 days post-receipt)
- Non-returnable categories (final sale items)

### Data Quality Dashboard

Monitor these metrics in Merchant Center:

| Metric | Target | Action if Below |
|--------|--------|-----------------|
| Feed quality score | 95%+ | Fix disapproved products |
| Product approval rate | 100% | Investigate disapprovals |
| Crawlability score | 95%+ | Fix website issues |
| Mobile-friendliness | 95%+ | Responsive design update |
| Click-through rate | 2%+ | Improve product images/titles |
| Conversion rate | 1%+ | Improve product descriptions/pricing |

### Performance Monitoring

**Key Metrics to Track:**
- Impressions (how many times products shown)
- Clicks (how many times clicked)
- CTR (click-through rate = clicks ÷ impressions)
- Conversions (purchases)
- Conversion rate (conversions ÷ clicks)
- Average order value (revenue ÷ orders)
- ROAS (revenue ÷ ad spend)

**Product Performance:**
- Rank products by impressions (which sell best)
- Analyze low-impression products (title/image issue?)
- Monitor conversion rate by product (high vs low performers)
- Identify seasonal trends (higher volume certain months)
- Test price adjustments on underperforming products

---

## Common Best Practices

1. **Original Content Always:** Never copy descriptions from competitors
2. **Consistent Image Quality:** All products should look professionally photographed
3. **Price Validation:** Always check 3-5 competitors before setting final price
4. **Regular Feed Updates:** Keep inventory and pricing current (at least weekly)
5. **Policy Pages:** Complete, clear, customer-friendly policies reduce returns
6. **Category Precision:** Match products to exact categories (not "other")
7. **Monitor Disapprovals:** Fix issues immediately (don't ignore alerts)
8. **Test Before Scale:** Approve 5-15 products before submitting 100+ product catalog
