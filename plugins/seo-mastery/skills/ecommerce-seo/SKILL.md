---
name: "E-Commerce SEO"
description: >
  MANDATORY TRIGGERS: ecommerce SEO, e-commerce SEO, category page optimization, faceted navigation,
  product schema, product page SEO, seasonal pages, Black Friday SEO, product variations,
  discontinued products, collection pages, online store SEO, product grids, Shopify SEO,
  WooCommerce SEO.
  FOR: Optimizing e-commerce category and product pages for organic rankings. Implementing the
  faceted navigation framework for indexable filter pages. Creating seasonal and promotional page
  strategies. Handling product variations and discontinued product SEO. Implementing product schema
  for organic product grids. Analyzing internal site search for keyword opportunities. E-commerce
  technical SEO (deduplication, pagination, canonical handling).
  Do NOT use for: Local SEO / GBP optimization (use local-seo), general on-page optimization theory
  (use on-page-optimization), directory or programmatic SEO (use directory-programmatic-seo),
  general schema implementation (use schema-entity-optimization), GA4 e-commerce tracking setup
  (use seo-analytics-reporting).
---

# E-Commerce SEO

## Core Philosophy

Category pages are the #1 traffic landing pages for e-commerce (not the homepage). Start optimization there. The philosophy is process-over-individual-fixes: build templates and systems that scale across all pages, then refine individually.

**Contrarian insight (Kristina Azarenko):** Don't fix individual issues. Build processes instead. Templates for title tags/H1s are a process. Manual optimization of each title is a one-off fix. Start with the process.

## Category Page Optimization

### Title Tag & H1 Optimization
Most stores have vague title tags like "Plates" -- massive missed opportunity. Title tag and H1 must be specific to page content.

**Optimization pointers to include:**
1. General store characteristics (personalized, custom, wholesale)
2. Specific category characteristics (bandage for dresses, christmas for gifts)
3. Product characteristics (size, color, type, brand)
4. Target audience (for boys, teens, women)
5. Location (Canada, Toronto, New York)

**Template:** `Personalized {Category Name} in New York with Free Shipping - Brand Name`
H1 follows same template minus brand name. Nav links and H1 must NOT be mutually dependent.

**Case study (Azarenko):** 657% growth in organic traffic + 5400% growth in sales from optimizing category page title tags/H1s + fixing technical SEO.

### Create Specific Categories
Having only "T-shirts" means you cannot target specific long-tail transactional searches. Long-tail keywords ("black t-shirts for men") have buying intent and higher conversion rates.

**Case study:** Client captured only 19% of search potential. Created 5-10 highest-impact subcategory pages. 3 months later, captured 29%.

### Sub-Collection Revenue Multiplier (Cromwell)
Create sub-collections that slice existing categories by attribute. Each sub-collection targets a distinct keyword cluster and captures additional organic traffic.

## Faceted Navigation Framework (8-Step)

This framework generated $2M in additional revenue for a single client and saves 1-2 years of manual implementation.

### The 8 Steps
1. **Complete keyword research** -- understand which opportunities exist
2. **Analyze existing filters** -- find which become indexable facets (Fit, Color, Brand, Style). Exclude filters with no search demand (price, size in some niches)
3. **Define rules for indexable facet pages:** Only top-level categories. Only category + ONE filter (not multi-filter combos)
4. **Define canonicalization rules:** 9+ products = self-referencing canonical. Fewer than 9 = canonical to parent. If stock fluctuates, set self-referencing and leave it (never switch canonicals back and forth)
5. **Set up internal linking** -- links MUST use href attributes (not JavaScript onclick)
6. **Create title/H1 templates:** `{Facet Name} {Category Name} in {Location} - {Brand Name}`
7. **Test everything** -- crawl pages, check canonicals, verify product counts (Screaming Frog + manual)
8. **Improve incrementally** -- refine titles, add descriptions, include synonyms

### Smart Filter Indexing (brightonSEO -- Janczak)
Stop automatically de-indexing all filters. Traffic light system for decisions based on search demand, product availability (50+ products minimum), conversion value, and engagement signals. Treat indexed filter pages like category pages with unique H1, title tag, and copy.

> See `ref-ecommerce-category-strategy.md` for complete faceted navigation and seasonal page details.

## Seasonal & Promotional Pages

### Evergreen Seasonal Pages
- Evergreen URL with no year (/mothers-day)
- Update title tag with current year for relevancy
- Pages available all year (200 status, no 301s/404s)
- During season: main navigation, promo banner. Off-season: remove from navigation (orphan OK temporarily)

### Brand Coupon/Discount Pages
Host dedicated coupon page to capture "[brand] + coupons" searches. "Ridiculously easy to rank" -- highest relevancy for branded + coupon queries.

### Black Friday Process
1. Create dedicated promo page
2. Promote + capture emails before prices go live
3. Make visible on site (banners, pop-ups)
4. Make internal search work: "Black Friday" should redirect to deals page, not products with "black" color

## Product Page SEO

### Variations Handling
- Truly unique products with different search demand -> separate URLs with unique content
- Minor variations (color swatches) -> single URL with self-referencing canonical
- Canonical less popular variants to most popular/default

### Discontinued & Sold-Out Products
- **Temporarily out-of-stock:** Keep page live (200), show "out of stock," offer alternatives, mark OutOfStock in schema
- **Permanently discontinued:** If significant traffic/links -> 301 to most relevant replacement or parent category. If no traffic/links -> 404. Never 301 to homepage.

## Product Schema for Organic Product Grids (brightonSEO -- Lockwood)

### Three Priority Optimizations
1. **Product titles:** Name after product attributes, not internal merch systems. Formula: [key attribute] + [product type]
2. **Product schema:** Mandatory base schema plus competitive advantage fields (has-varying/product-varying)
3. **Feed-to-page consistency:** Mandatory. Price mismatches cause disapprovals

**Case study:** 74% increase in clicks, 15% increase in revenue from three optimizations alone.

### INSTRUCTOR DISAGREEMENT: GEO for E-Commerce

**Lockwood (brightonSEO):** GEO for e-commerce is "a big nothing burger" right now. Most advice is just basic SEO repackaged.

**Leliukh (Surfer):** 22% of new customers from LLMs. Conversion rates equal to organic.

**Resolution:** Product grid optimization matters more than GEO for e-commerce today. GEO matters more for content-heavy sites.

## Technical E-Commerce SEO

### Category Deduplication
Multiple URLs for same content (sort orders, filter combos, pagination + filters) dilute value. Solution: canonical tags to preferred URL.

### Pagination
- Make pagination crawlable -- Google must follow paginated links
- Do NOT noindex paginated pages
- Do NOT canonical all paginated pages to page 1
- Self-referencing canonicals on each paginated page

### Site Search Analysis
Mine internal search data for keyword opportunities. If customers search for terms with poor results, create pages for those terms. Internal site search data is often more valuable than external keyword tools because it shows what YOUR customers want.

### E-Commerce Header Structure (Cromwell)
Collection description split strategy: place some content above products and some below. Keyword density is less important than natural placement and semantic relevance.

## Cross-References

- For local SEO / GBP optimization -> `local-seo`
- For general on-page optimization theory -> `on-page-optimization`
- For product schema implementation details -> `schema-entity-optimization`
- For technical crawlability and indexation -> `technical-seo-audit`
- For content creation for e-commerce blogs -> `content-production`
- For AI search optimization for product content -> `geo-ai-search-optimization`

## Reference Files

- `ref-ecommerce-category-strategy.md` -- Category optimization, faceted navigation 8-step, seasonal pages, brand coupons, sub-collection multiplier
- `ref-ecommerce-product-technical.md` -- Product page SEO, product schema, discontinued products, deduplication, pagination, site search analysis, header structure
