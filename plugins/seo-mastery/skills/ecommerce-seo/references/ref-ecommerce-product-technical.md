# E-Commerce Product & Technical SEO

## Product Page SEO

### Product Variations Handling
- **Truly unique products** with different search demand -> separate URLs with unique content
- **Minor variations** (color swatches) -> single URL with self-referencing canonical
- Canonical less popular variants to most popular/default variant
- Never let color/size parameters create infinite crawlable URLs
- Use JavaScript-based variant switching (no URL changes) for cosmetic differences
- Use separate URLs only when the variant has independent search demand ("red Nike Air Max" vs "Nike Air Max")

### Discontinued & Sold-Out Products

**Temporarily out-of-stock:**
- Keep page live (200 status)
- Show "out of stock" messaging prominently
- Offer alternatives or email notification for restocking
- Keep structured data (mark as OutOfStock in schema)
- Do NOT remove from sitemap or internal navigation

**Permanently discontinued -- 4 decision options:**
1. **301 redirect to replacement product** -- use when a direct successor exists with the same use case. Preserves link equity and sends existing traffic to the most relevant alternative.
2. **301 redirect to parent category** -- use when no direct replacement exists but the category is relevant. User lands on a browsable page rather than a dead end.
3. **Keep page live with alternatives** -- use when the page has significant traffic/links AND no clear redirect target. Display "This product has been discontinued" with curated alternative product links. This preserves the URL's accumulated authority.
4. **404 the page** -- use when the page has no traffic, no backlinks, and no brand value. Clean removal from the index.

**Never 301 to homepage** -- wastes link equity and creates poor UX. Users who clicked expecting a product and land on a homepage will bounce immediately.

**Decision flowchart:**
- Does the page have 50+ monthly visits OR 5+ referring domains? -> Keep live or 301 to relevant target
- Is there a direct product replacement? -> 301 to replacement
- Is there a relevant parent category? -> 301 to category
- None of the above? -> 404 is fine

## Product Schema for Organic Product Grids

### Three Priority Optimizations (brightonSEO -- Lockwood)

**1. Product Titles**
- Name after product attributes, not internal merch systems
- Formula: [key attribute] + [product type]
- Example: "Waterproof Hiking Boots" not "Style #4782B"
- Include the most-searched attribute first (color, material, use case)
- Match the title in your product feed to the title on the product page exactly

**2. Product Schema (Structured Data)**
- Mandatory base schema: Product type, name, price, availability, image, URL
- Competitive advantage fields: has-varying/product-varying schema for variant-rich products
- **offers** property: include price, priceCurrency, availability, priceValidUntil
- **aggregateRating** property: star rating + review count (if reviews exist)
- **brand** property: brand name for branded search matching
- Feed structured data through Google Merchant Center for product grid eligibility
- Validate schema via Google Rich Results Test before deploying

**3. Feed-to-Page Consistency**
- Mandatory for organic product grid visibility
- Price mismatches cause disapprovals (if feed price lower than on-page, product disapproved)
- Title mismatches cause reduced visibility (feed title must match product page title)
- Availability mismatches cause suspensions (if feed says "in stock" but page says "out of stock")
- Quick check: compare valid items with merchant listings vs product snippets in Search Console
- Run weekly automated checks comparing feed data to on-page data

### Performance Impact
Case study: 74% increase in clicks, 15% increase in revenue to PDPs from three optimizations alone. Product grids drive revenue RIGHT NOW -- changes produce results next month.

### GEO Assessment for E-Commerce
- Lockwood: "GEO for e-commerce is a big nothing burger right now"
- Most optimization advice is just good basic SEO repackaged
- Product grid optimization matters more than GEO for e-commerce today
- Use query fan-out analysis to inform content strategy

### SERP Feature Distribution (brightonSEO Data)
- Informational e-commerce keywords: 66% show AI Overviews
- Commercial browsing keywords: 63% show organic product grids
- Product comparison searches: 83% show discussions/forums pack (AI Overviews rare)

## Technical E-Commerce SEO

### Category Page Deduplication
- Multiple URLs from sort orders, filter combos, pagination + filters dilute value
- Solution: canonical tags pointing duplicate variations to preferred URL
- Consolidate link equity and indexation signals to one canonical version
- Common deduplication problems and fixes:

| Duplicate Type | Example | Fix |
|---------------|---------|-----|
| Sort order parameter | /shoes?sort=price-asc | Canonical to /shoes |
| Filter combination | /shoes?color=red&size=10 | Canonical to /shoes or indexed facet |
| Pagination + filter | /shoes?page=2&color=red | Canonical to /shoes?color=red |
| Trailing slash | /shoes/ vs /shoes | Pick one, canonical the other |
| HTTP vs HTTPS | http://site.com/shoes | 301 to https:// version |
| WWW vs non-WWW | www.site.com/shoes | Pick one, 301 the other |

### Pagination Rules
- **Make pagination crawlable** -- Google must follow paginated links
- Use standard anchor links for next/previous
- Do NOT noindex paginated pages (they help Google discover deep products)
- Do NOT canonical all paginated pages to page 1 (each has unique products)
- Self-referencing canonicals on each paginated page
- Include page number in title tag: "Running Shoes - Page 2 | Brand"
- Ensure paginated pages load quickly (lazy-load images below the fold)

### Page Speed for E-Commerce
- Critical: slow pages lose sales directly (1-second delay = 7% conversion loss)
- Key improvements: image compression, lazy loading, minimize CSS/JS, CDN, server response time
- One of the "10 huge SEO wins" for any online store (Azarenko)
- Target: under 2.5 seconds LCP (Largest Contentful Paint)
- Product images are usually the biggest speed bottleneck -- use WebP with JPEG fallback

### Site Search Analysis (Keyword Mining Gold)
- Mine internal site search data for keyword opportunities in GA4
- If customers search for terms with poor results, create pages for those terms
- Internal site search data is often more valuable than external tools -- shows what YOUR customers want, filtered by purchase intent
- GA4 integration: track site search queries as events (Enhanced Measurement > Site Search toggle)

**Site search mining process:**
1. Enable site search tracking in GA4 (Enhanced Measurement settings)
2. Export 90 days of site search queries
3. Group queries by theme (product type, brand, attribute)
4. Identify queries with high volume but no matching category page
5. Create new category/subcategory pages for the top unserved queries
6. Monitor conversion rate on new pages vs existing pages

### Collection Description Split Strategy (Cromwell)
- Place descriptive content both above and below products on category pages
- Above-the-fold content: brief, keyword-rich introduction (50-100 words)
- Below-products content: more detailed description, FAQ, internal links (200-400 words)
- Avoids pushing products below the fold while still providing crawlable content
- SEO benefit without harming UX or conversion rate

### E-Commerce Header Structure
- H1 on every category page (specific to the category, not the store)
- H2s for sections within the page (featured products, brand sections, FAQ)
- Keyword density is less important than natural placement and semantic relevance
- Nav links and H1 must NOT be mutually dependent (nav says "Routers", H1 says "Wifi Routers by Ubiquiti")

### Process-Over-Fixes Philosophy (Azarenko)
- Don't fix individual issues -- build processes that scale
- Templates for title tags/H1s are a process
- Manual optimization of each title is a one-off fix
- Start with the process, refine individually after
- Every store needs 3-5 of the core SEO wins applied -- rarely all 10

## User Intent for E-Commerce Content

### Four Intent Types
1. **Informational:** "How to clean a leather bag" -> blog posts, guides
2. **Navigational:** "[Brand name] leather bags" -> brand/category pages
3. **Transactional:** "Buy leather crossbody bag" -> product/category pages
4. **Commercial investigation:** "Best leather bags for travel" -> comparison pages, buying guides

Create content for ALL intent types. Informational content builds topical authority and feeds the purchase funnel.

## Key E-Commerce SEO Wins (Azarenko's Priority List)
1. Category page title tag and H1 optimization
2. Create specific subcategories for long-tail keywords
3. Faceted navigation framework
4. Product variation handling
5. Discontinued product management
6. Seasonal page strategy
7. Internal search analysis
8. Pagination fixes
9. Page speed optimization
10. Schema implementation

## E-Commerce Internal Linking Strategy

### Product-to-Category Links
- Every product page should link back to its parent category
- Breadcrumbs provide automatic parent-category linking
- "Related Products" sections create cross-links between products in the same category
- "Customers Also Bought" sections create cross-category product links

### Category-to-Category Cross-Links
- Related categories should link to each other ("Men's Running Shoes" links to "Men's Trail Shoes")
- Footer navigation should include top-level categories
- Seasonal landing pages should link to relevant product categories
- Blog posts should deep-link to specific category and product pages

### Blog-to-Commerce Linking
- Every informational blog post should link to at least one relevant product or category page
- Use contextual anchor text matching the target keyword of the linked page
- "Buying guide" posts should link to every product mentioned
- Comparison articles should link to individual product pages for each compared item

## E-Commerce URL Structure Best Practices

### Recommended Patterns
- Category: `/category-name/`
- Subcategory: `/category-name/subcategory-name/`
- Product: `/product-name/` (flat) or `/category/product-name/` (nested)
- Facet page: `/category-name/filter-value/`

### Rules
- Use hyphens between words, never underscores
- Keep URLs under 100 characters when possible
- Include the primary keyword in the URL slug
- Avoid session IDs, tracking parameters, or filter parameters in indexable URLs
- Use consistent trailing slash convention (either always or never)
