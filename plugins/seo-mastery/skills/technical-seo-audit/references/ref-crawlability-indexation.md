# Crawlability & Indexation Deep Dive

## Google's Three-Tier Exclusion Engine (Adam Gent, 500K pages/day inspected)

### How Indexing Actually Works
- Both indexed AND non-indexed pages are stored in Google's database
- "Indexed" means eligible to appear in search results, not "stored in database"
- AI mode snippets also require the source page to be indexed

### Tier 1: Technical Errors
- noindex directives
- 404 errors
- robots.txt blocking
- Redirect loops
- Server errors (5xx)
- **Fix:** Identify and remove the technical blocker

### Tier 2: Duplicate/Similar Content
- Canonical conflicts between pages
- Near-duplicate pages (slight variations)
- Thin content that overlaps with other pages
- **Fix:** Set canonical URLs correctly, consolidate or differentiate pages

### Tier 3: Page Quality (Biggest Factor)
Quality is the #1 reason pages are not indexed -- by a huge margin.

Quality signals (from DOJ trial documents):
- **Content** -- vector embeddings mapped to topic (is the content substantive and relevant?)
- **Links** -- PageRank, nearest seed page rank (do authoritative pages link here?)
- **Clicks** -- user engagement/satisfaction (do people actually visit and stay?)

Google measures outcomes not outputs. They don't understand your documents but they measure whether users find them useful.

### Active De-Indexation Patterns
Google actively REMOVES previously indexed pages. Three patterns:

1. **Historic engagement** -- page was popular 2-3 years ago but engagement has declined. Google drops it
2. **Low quality engagement** -- page appears in SERPs occasionally but gets no clicks. Google removes it
3. **No engagement** -- nobody visits, links to, or cares about the page. Google drops it

---

## The 130-Day Indexing Rule

If a page has not been recrawled within 130 days, there is a **99% chance it is not indexed.**

### Crawl Management Timeline
| Days Since Last Crawl | Typical Status |
|---|---|
| 1-130 days | Indexed (healthy) |
| 131-189 days | Crawled, currently not indexed |
| 190+ days | Discovered, currently not indexed |
| 450+ days | URLs unknown to Google (up to 2 years without crawl) |

### Hard Limit / Soft Limit / Quality Threshold System
From Google's "Managing URLs" patent:
- Google has finite capacity for indexing
- When too many pages enter the pipeline, the quality threshold goes UP
- Borderline pages get dropped
- When disk space frees up, threshold goes DOWN and more pages get indexed
- This creates daily fluctuations -- your page might be borderline quality

### Practical Implications
- If GSC shows "crawled currently not indexed," the page likely failed the quality threshold
- Adding more content, internal links, or earning backlinks raises the page above the threshold
- Time matters: fresh content gets a crawl boost; stale content decays in crawl priority

---

## Canonical URL Configuration

### Rules
- Every page should have a self-referencing canonical tag (points to itself)
- Exception: when a page is intentionally a duplicate (like paginated or filtered versions)

### Shopify-Specific Issues
- Shopify generates duplicate URLs via collections: `/collections/sunscreen/products/spf-50` vs `/products/spf-50`
- The canonical should ALWAYS be the `/products/` version
- Fix: remove the `within: collection` Liquid filter in the product thumbnail snippet

### E-Commerce Canonical Rules (Kristina Azarenko)
- 9+ products on a filtered page = self-referencing canonical (enough unique content)
- Fewer than 9 products = canonical to parent category page
- Paginated collection pages: self-referencing canonicals per page, but noindex `?page=2+`

---

## Robots.txt Configuration

### Standard Configuration
- Block admin areas, cart pages, checkout
- Allow all content pages, collection pages, product pages
- Include XML sitemap reference

### Common Mistakes
- Blocking directories that contain API keys needed for JS rendering (hotel chain case study: 33% of content invisible)
- Wildcarding too broadly (blocking `/api/` blocks all API resources)
- Not having a robots.txt at all (Shopify does not auto-create for new stores)

### AI Crawler Considerations
- AI crawlers respect robots.txt
- llms.txt has no measurable impact (confirmed by multiple brightonSEO speakers)
- robots.txt is sufficient for managing AI crawler access

---

## Orphan Pages

### What They Are
Pages that exist on your site but have zero internal links pointing to them. They may be in your XML sitemap but unreachable via site navigation.

### Why They Matter
- Google may crawl them via sitemap but they get minimal authority
- Case study: client had 10K live pages + 40K orphaned pages in XML sitemap
- Orphan pages waste crawl budget and dilute site quality signals

### How to Find
1. Crawl with Screaming Frog
2. Compare crawl URLs with XML sitemap URLs
3. URLs in sitemap but not in crawl = orphans
4. Also check GA for pages getting traffic but not found in crawl

### How to Fix
- Add internal links from relevant pages
- Or remove from sitemap and noindex if no longer needed
- Or 301 redirect to most relevant active page

---

## What to Index vs What to Noindex

### Always Index
- Service pages / product pages with substantive content
- Blog posts and articles
- Category/collection main pages
- Location pages with unique content
- Tool/calculator pages

### Always Noindex
- Paginated URLs (`?page=2`, `?page=3`)
- Tag collection pages (`/collections/tag/brown-shoes`)
- Search results pages
- Cart and checkout pages
- Thank you / confirmation pages
- Author archive pages (unless author pages have substantive content)
- Filtered pages with fewer than 9 products (canonical to parent instead)

### Case-by-Case
- Filtered pages with 9+ products and search demand (may warrant indexing)
- FAQ pages (depends on whether content is also on parent page)
- Landing pages for PPC (usually noindex to avoid cannibalization)
