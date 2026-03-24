# Technical SEO Checklist & Implementation Guide

## Priority Technical Fixes

### Critical (Fix Immediately)

**404s / Broken Links**
- Always bad. Every broken link is lost link equity
- Set up 301 redirects: similar product > parent collection > homepage
- Check with Screaming Frog or Ahrefs broken link report
- Monitor weekly in Google Search Console

**robots.txt Blocking Content Rendering**
- Check "internal blocked by robots.txt" in Screaming Frog
- Case study: US hotel chain -- previous agency crawled 18 months, found "no issues." 33% of content was invisible because robots.txt wildcarded a directory containing an API key needed for rendering
- The answer was already in Screaming Frog's report -- the agency never looked
- Always verify your robots.txt is not blocking CSS, JS, or API resources

**Canonical URL Conflicts**
- Deduplicate URLs pointing to the same content
- Self-referencing canonicals on primary pages
- Shopify fix: remove `within: collection` Liquid filter
- Check with: `site:yourdomain.com "page title"` -- multiple results = canonical issue

**Pagination Noindex**
- Noindex all `?page=2`, `?page=3` etc.
- Only top-level page should be indexed
- But keep pagination crawlable (do not block in robots.txt) so Google can discover products on later pages

### Important (Fix This Week)

**Duplicate / Thin Content**
- Noindex tagged collection pages (e.g., `/collections/tag/brown-shoes`)
- Noindex any page with no substantive content
- Merge thin pages covering the same topic (keep-kill-merge-refresh framework)

**Schema Markup**
- Product schema (star ratings, pricing in SERP)
- FAQ schema where appropriate
- Not a direct ranking factor but increases CTR and AI orchestrator readability
- See schema-entity-optimization skill for full implementation guide

**SSL / HTTPS**
- Mandatory since 2018. Use Cloudflare for free SSL + CDN
- Mixed content warnings (HTTP resources on HTTPS pages) hurt trust signals

**XML Sitemap Hygiene**
- Include only indexable pages
- Remove orphan URLs, noindexed pages, redirected URLs
- Case study: 10K live pages + 40K orphaned pages in sitemap -- clean it up
- Submit via Google Search Console

---

## Mobile-First Indexing Checklist

- Google indexes the mobile version of your site exclusively
- Over 50% of internet traffic is mobile
- Check every page on mobile before publishing

### Mobile Audit Steps
1. Open Chrome DevTools > Toggle Device Toolbar
2. Check all pages render correctly on mobile
3. Verify text is readable without zooming
4. Confirm buttons/links have adequate tap targets
5. Test forms function properly on mobile
6. Verify no horizontal scrolling
7. Check images scale properly

---

## Core Web Vitals

### The Three Metrics
| Metric | What It Measures | Good Threshold |
|--------|-----------------|----------------|
| LCP (Largest Contentful Paint) | Loading speed | Under 2.5 seconds |
| CLS (Cumulative Layout Shift) | Visual stability | Under 0.1 |
| INP (Interaction to Next Paint) | Interactivity | Under 200ms |

### Pragmatic Approach (Cromwell)
- Under 3 seconds total load = fine
- Under 4 seconds = acceptable for e-commerce
- Only fix if exceeding 5-6+ seconds
- Page speed improvements = ~0.5% impact vs content + links at 90%

### AI Crawler Requirements (brightonSEO)
- Server response time under 300ms (this is TTFB, not full page load)
- No JavaScript runtime required
- Static HTML pages preferred
- These are more stringent than traditional CWV thresholds

### Quick Wins for Speed
1. Compress images (WebP format)
2. Enable browser caching
3. Minify CSS/JS
4. Use CDN (Cloudflare free tier)
5. Lazy load below-fold images
6. Remove unused plugins/scripts

---

## 301 Redirect Strategy

### When to Use 301s
- Page permanently moved to new URL
- Old content consolidated into new page
- Domain migration
- Fixing URL structure changes

### Rules
- Always redirect to the most relevant replacement page
- Avoid redirect chains (A -> B -> C should be A -> C)
- Never redirect to homepage as default (relevance matters)
- Keep redirects in place for at least 1 year (ideally permanently)

### Redirect Priority for Deleted Products (E-Commerce)
1. Similar/replacement product page (best)
2. Parent category page (good)
3. Homepage (last resort)

---

## Site Migration Checklist (Daphne Monro)

### Pre-Migration (4-6 weeks before)
1. Export complete keyword portfolio from GSC
2. Export all backlink data from Ahrefs/SEMrush
3. Screenshot Core Web Vitals (cannot retroactively test old site)
4. Map every URL to its destination URL
5. Identify pages to consolidate (no standalone keyword = consolidate)
6. Find primary keywords per page: GSC > filter by PAGE > enter URL > see engagement
7. Plan new site architecture (parent-child hierarchy to stop cannibalization)

### During Migration
- Implement all 301 redirects before DNS switch
- Verify redirect map covers 100% of indexed URLs
- Test redirects with Screaming Frog before going live
- Set up new Google Search Console property

### Post-Migration (Ongoing)
- Monitor new GSC property daily for first 2 weeks
- Continue monitoring OLD GSC property indefinitely
- Check for 404 spikes in new property
- Track keyword rankings daily for first month
- Verify all redirects are working
- Submit new XML sitemap

### Brand Transition (if applicable)
- HTML banner explaining the change on new site
- Old brand mentioned in footer and about page
- Full brand story available (also helps LLM citations)
- Pre-migration 302 redirect can generate community buzz and early links

---

## Edge SEO via CDN (Eben Aguilar, brightonSEO)

### What You Can Implement at the Edge
Without touching origin server or CMS:
- Redirects (301, 302)
- Canonical tags
- Hreflang tags
- Meta robots directives
- Schema injection (JSON-LD)
- HTTP header modifications
- Content injection (add text, scripts)

### Platforms
- Cloudflare Workers
- Akamai EdgeWorkers
- AWS Lambda@Edge
- Fastly VCL

### Best Use Cases
- CMS cannot implement required changes
- Dev queue is months long
- Code freeze period (pre-Black Friday)
- Test-and-learn approach: deploy at edge, measure impact, then decide whether to implement permanently in codebase

---

## JavaScript SEO Diagnostics

### The Problem
- AI crawlers do NOT execute JavaScript
- Google's crawler can render JS but it is resource-intensive and delayed
- Content rendered only via JS is at risk of not being indexed

### Diagnostic Process
1. Crawl with Screaming Frog in both source HTML and JS-rendered modes
2. Compare: content only in rendered mode = at risk
3. Check "internal blocked by robots.txt" report
4. Use Google URL Inspection Tool to see rendered version
5. View source (Ctrl+U) vs inspect element -- if content only in inspect, it is JS-rendered

### Fixes
- Server-side rendering (SSR) for critical content
- HTML fallbacks for JS components
- Static HTML tables to duplicate JS visualizations
- Ensure robots.txt does not block JS/CSS resources needed for rendering
- For AI crawler optimization: provide static versions of all critical content

---

## Crawl Audit First-Pass Protocol (Charles Meaden)

### Before Full Crawl (2-3 Minutes)
Run a quick first-pass crawl to catch:
- Query string parameters inflating page count
- Tracking URLs creating duplicates
- Print-friendly page versions
- Calendar widgets generating infinite URLs

### During Full Crawl
- Compare source HTML vs JS-rendered output
- Check "internal blocked by robots.txt" report
- Identify orphan pages (in sitemap but not crawled via links)
- Flag redirect chains

### Post-Crawl Analysis
- Combine crawl data with business metrics (GA sessions, revenue, stock levels)
- Prioritize by business impact: high-traffic page with broken image > low-traffic page with missing alt text
- Create prioritized action score: issue severity x page business value
