# E-Commerce Category Strategy

## Category Page Optimization

### Title Tag & H1 Templates
**Title template:** `{Modifier} {Category Name} in {Location} with {Benefit} - {Brand}`
**H1 template:** Same minus brand name.

**Optimization pointers (5 dimensions):**
1. Store characteristics (personalized, custom, wholesale)
2. Category characteristics (bandage for dresses, christmas for gifts)
3. Product characteristics (size, color, type, brand)
4. Target audience (for boys, teens, women)
5. Location (city, state, country)

### Example Transformation
- Before: "Gifts - Brand Name"
- After: "Personalized Gifts for Her in Toronto - Brand Name"

### Implementation Process
1. Create templates first (process approach)
2. Apply templates across all category pages
3. Then customize individual titles based on keyword research
4. Add 100-200 words of unique copy at top of category pages if competition requires it

### Nav vs. H1 Independence
Navigational link anchors and H1 tags must NOT be mutually dependent. Nav can say "Routers" while H1 says "Wifi Routers by Ubiquiti." They serve different functions.

### 657% Growth Case Study (Azarenko)
Results from optimizing category page title tags/H1s + fixing technical SEO: 657% organic traffic growth + 5400% sales growth.

## Creating Specific Categories

### The Specificity Principle
Having only "T-shirts" means you cannot target long-tail transactional searches. Long-tail keywords ("black t-shirts for men") have higher buying intent and conversion rates.

### Case Study: Search Potential Capture
- Starting: 19% of search potential captured
- After 5-10 highest-impact subcategory pages: 29% capture (10% gain in 3 months)
- Full manual implementation: 1-2 years of work

### Category pages are the #1 traffic landing pages for e-commerce (not homepage)

### How to Identify High-Impact Subcategories
1. Export keyword data from Ahrefs/SEMrush for your main category terms
2. Group keywords by modifier type (color, material, use case, audience)
3. Check search volume for each modifier group
4. Prioritize the 5-10 modifier groups with highest combined search volume
5. Create subcategory pages for those groups first
6. Measure traffic impact over 90 days before expanding further

## Faceted Navigation 8-Step Framework

This framework generated $2 million in additional revenue for a single client and saves 1-2 years of manual page creation.

### Step 1: Complete Keyword Research
Understand which filter combinations have search demand. Not all filters deserve indexable pages -- only those with proven search volume.

### Step 2: Analyze Existing Filters
Find which filters become basis for indexable facets. Example filters: Fit (women/men), Color (green t-shirts), Brand (New Balance), Style (long sleeve). Exclude: price, size (often no search demand).

**Filter evaluation criteria:**
- Does the filter term appear as a keyword in Ahrefs/SEMrush? (search demand)
- Is the search volume meaningful (50+ monthly searches)?
- Does the filter currently have enough products to support a landing page?
- Would a dedicated page better serve user intent than the parent page?

### Step 3: Define Indexable Facet Page Rules
- Only for top-level categories
- Only category + ONE filter combination (not multi-filter)
- Decision flowchart: Is it for top-level category? -> Does it use defined filters? -> Is it category + single filter? -> Create facet page
- Multi-filter combinations (e.g., color + size + brand) should remain noindexed -- too many pages, too little unique content

### Step 4: Define Canonicalization Rules -- The 9-Product Threshold
- **9+ products** on facet page -> self-referencing canonical (page has enough content to stand alone)
- **Fewer than 9 products** -> canonical to parent category (thin page, consolidate signals)
- The threshold number (9) is context-dependent -- could be 6 or 12 depending on inventory depth
- **If stock fluctuates, set self-referencing canonical and LEAVE IT** -- never switch back and forth

**Why never switch canonicals back and forth:**
- Google takes weeks to process canonical changes
- Flip-flopping confuses the indexer and can cause both pages to lose rankings
- Set the canonical based on your typical inventory level, not the current moment
- If stock drops temporarily below 9, the self-referencing canonical is still fine

### Step 5: Set Up Internal Linking
Links to new facet pages MUST use href attributes (not JavaScript onclick). Google does not click, it follows href.

**Internal linking structure for faceted pages:**
- Parent category page links to all indexed facet pages
- Facet pages link back to parent category
- Related facet pages cross-link to each other (e.g., "Red Dresses" links to "Blue Dresses")
- Breadcrumbs include the facet hierarchy (Home > Dresses > Red Dresses)

### Step 6: Create Title/H1 Templates
- Title: `{Facet Name} {Category Name} in {Location} - {Brand Name}`
- H1: Same minus brand name
- Customize in final improvement step

### Step 7: Test Everything
- Crawl pages with Screaming Frog
- Check canonicals, verify products per page
- Manual spot checks alongside automated crawl
- Verify facet pages return 200 status codes
- Confirm facet pages appear in sitemap

### Step 8: Improve Incrementally
- Manually refine titles based on keyword data
- Add descriptions to category pages (100-200 words above products)
- Include keyword synonyms in body copy
- Add FAQ sections to high-value facet pages
- Monitor search performance per facet page monthly

### Framework Applicability
Works for: online stores, dealerships (inventory), marketplaces, aggregator websites, real estate directories. Different categories can have different indexable filter sets.

### Smart Filter Indexing (brightonSEO -- Janczak)
- Traffic light system: search demand + product availability (50+) + conversion value + engagement
- Treat indexed filter pages like category pages (unique H1, title, copy)
- Have filter strategy conversation with dev teams BEFORE website build
- Example: ranked filter pages had MORE and BETTER content than main category pages

### Revenue Impact
$2 million in additional revenue from a single client implementation.

## Seasonal & Promotional Pages

### Evergreen Seasonal Page Rules
- Evergreen URL with no year (/mothers-day, not /mothers-day-2026)
- Update title tag to include current year for relevancy
- Pages available all year (200 status code, no 301s/404s)
- During season: put in main navigation, promo banner
- Off-season: remove from navigation (orphan temporarily OK)
- Always have relevant content -- if products unavailable, say so and offer alternatives

### Seasonal Page Maintenance Process
1. **January:** Update all seasonal page titles with new year
2. **Before each season:** Add page back to navigation, update promo content and product links
3. **During season:** Monitor performance daily, adjust CTA and featured products
4. **After season:** Remove from navigation but do NOT 301, 404, or noindex
5. **Year-round:** Keep at least a skeleton page with content ("Mother's Day is coming soon -- check back for our latest deals")

### Brand Coupon/Discount Pages
- Host on your own site to capture "[brand] + coupons" searches
- "Ridiculously easy to rank" (highest relevancy for branded + coupon)
- Ranks for: [brand + coupon codes], [brand + promo codes], [brand + Black Friday codes]
- Title template: `[Brand] Coupons & Deals: Save Up to {N%} in {Month}`
- Update dynamically with coupon amount and current month
- Link from footer or main navigation
- Make coupon codes case-insensitive for good UX

### Open Graph for Promos
Update homepage OG images before each holiday with promo banners. Clear social caches: Twitter Cards Validator, LinkedIn Inspect, Facebook Sharing Debugger.

### Black Friday / Cyber Monday Process
1. Create dedicated promo page (evergreen URL: /black-friday-deals)
2. Promote + capture emails before prices go live (build anticipation)
3. Make visible on site (banners, pop-ups, hero section)
4. Make internal search redirect "Black Friday" to deals page (not products with "black" color)
5. Update page title: "Black Friday Deals 2026 - Up to 70% Off | Brand"
6. After the event: keep page live, update to "Black Friday 2027 deals coming soon"

## Sub-Collection Revenue Multiplier (Cromwell)

Create sub-collections slicing existing categories by attribute. Each sub-collection targets a distinct keyword cluster. This multiplies organic traffic capture without requiring new product inventory.

### How the Multiplier Works
Example: "Women's Running Shoes" category spawns sub-collections for:
- "Women's Trail Running Shoes"
- "Women's Cushioned Running Shoes"
- "Women's Lightweight Running Shoes"
- "Women's Running Shoes Under $100"

Each sub-collection gets its own landing page with unique title/H1, targeting a different keyword cluster.

### Implementation Steps
1. List all existing category pages
2. For each category, identify 3-5 attribute-based slices with search demand
3. Verify each slice has enough products (9+ threshold)
4. Create sub-collection pages with unique titles, H1s, and 100-200 words of unique copy
5. Link from parent category to all sub-collections
6. Cross-link related sub-collections
7. Add sub-collections to sitemap
8. Monitor traffic growth per sub-collection over 90 days

### Revenue Impact Examples
- One attribute slice = one new keyword cluster = incremental organic traffic
- 5 sub-collections per category x 20 categories = 100 new ranking-eligible pages
- Each page that ranks adds incremental revenue without inventory investment
- Compounds with faceted navigation -- sub-collections and faceted pages can serve different intents
