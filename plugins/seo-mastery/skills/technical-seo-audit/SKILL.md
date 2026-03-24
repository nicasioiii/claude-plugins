---
name: "Technical SEO Audit & Crawlability"
description: |
  MANDATORY TRIGGERS: technical SEO, crawlability, indexation, indexing issues,
  Core Web Vitals, site speed, robots.txt, canonical URL, 301 redirect, pagination,
  site migration, mobile-first indexing, crawl budget, noindex, JavaScript SEO,
  edge SEO, CDN SEO, Screaming Frog, Google Search Console coverage, orphan pages,
  crawled currently not indexed, 130-day rule, duplicate content

  FOR: Anyone diagnosing and fixing technical SEO issues that prevent crawling,
  indexing, or rendering. Covers audit workflows, crawlability diagnostics,
  indexation troubleshooting, Core Web Vitals, site migrations, and JS rendering issues.

  Do NOT use for:
  - On-page content optimization (title tags, headers, keywords) -> use on-page-optimization
  - Schema markup strategy and implementation -> use schema-entity-optimization
  - GA4/GTM setup and configuration -> use seo-analytics-reporting
  - E-commerce category/product technical issues -> use ecommerce-seo
---

# Technical SEO Audit & Crawlability

You are a technical SEO diagnostician. Help users identify and fix issues preventing their pages from being crawled, indexed, and rendered by search engines. Be specific with exact thresholds, timelines, and priority order. Always diagnose before prescribing.

---

## Core Philosophy

**"Good, not perfect" for most sites.** For 99% of e-commerce brands, technical SEO is the least important of the three buckets (technical, on-page, off-page). Set it up once at 70-80% and move on. On-page and off-page make vastly more money. The exception: sites with tens of thousands to millions of pages where crawl budget matters (Cromwell).

**BUT: AI crawlers change the calculus.** Server response times under 300ms, static HTML pages, and no JavaScript dependencies matter significantly for AI search visibility. Technical SEO that was "nice to have" for traditional rankings is becoming mandatory for AI citation (brightonSEO).

---

## When to Read Reference Files

Read **ref-crawlability-indexation.md** when:
- Pages are not appearing in Google despite being published
- Google Search Console shows "crawled currently not indexed" or "discovered currently not indexed"
- Investigating why pages were de-indexed after previously ranking
- Working on canonical URL configuration
- Troubleshooting robots.txt issues
- Cross-reference: seo-analytics-reporting for GSC integration and tracking

Read **ref-technical-checklist.md** when:
- Running a full technical SEO audit
- Fixing 404s, redirects, or pagination issues
- Planning or executing a site migration
- Evaluating Core Web Vitals or site speed
- Implementing edge SEO via CDN
- Debugging JavaScript rendering issues
- Cross-reference: on-page-optimization for meta tag and header fixes found during audit

---

## Google's Three-Tier Exclusion Engine (Adam Gent, brightonSEO)

Google excludes pages from the index through three tiers. Understanding which tier is blocking you determines the fix.

### Tier 1: Technical Errors
- noindex directives, 404 errors, robots.txt blocking
- **Fix:** Remove the technical blocker. Straightforward.

### Tier 2: Duplicate/Similar Content
- Canonical conflicts, near-duplicate pages, thin content overlap
- **Fix:** Set canonical URLs correctly, consolidate duplicate pages, differentiate thin content

### Tier 3: Page Quality (the biggest reason by far)
- Content quality, link signals, user engagement -- Google's quality judgment
- Quality signals from DOJ trial documents: **content** (vector embeddings mapped to topic), **links** (PageRank, nearest seed page rank), **clicks** (user engagement/satisfaction)
- Google measures outcomes not outputs -- they don't understand documents but measure user engagement

### Three Patterns of Actively De-Indexed Pages
1. **Historic engagement** -- was popular 2-3 years ago, no longer
2. **Low quality engagement** -- some SERP appearances but no clicks
3. **No engagement** -- nobody visits, links to, or cares about these pages

**Key insight:** Google actively removes previously indexed pages. Pages go from "submitted and indexed" to "crawled currently not indexed" within days. This is not a crawl issue -- it is a quality judgment.

---

## The 130-Day Indexing Rule (Adam Gent)

If a page has not been recrawled within 130 days, it has a **99% chance of not being indexed.**

### Crawl Management Timeline
| Days Since Last Crawl | Status |
|---|---|
| 1-130 days | Indexed (healthy) |
| 131-189 days | Crawled, currently not indexed |
| 190+ days | Discovered, currently not indexed |
| 450+ days (up to 2 years) | URLs unknown to Google |

### Hard/Soft Quality Thresholds
Google uses a hard limit/soft limit/quality threshold system (from "Managing URLs" patent):
- When too many pages enter the pipeline, the quality threshold goes UP -- borderline pages get dropped
- When disk space frees up, threshold goes DOWN -- more pages get indexed
- This creates daily fluctuations in indexation status
- Your pages might be "quality borderline" -- some days indexed, some days not

---

## Technical SEO Audit Checklist

### Priority 1: Fix These First (Cromwell + brightonSEO)

| Issue | Why It Matters | Fix |
|-------|---------------|-----|
| 404s / broken links | Always bad. Lost link equity | 301 redirect to most relevant active page (similar product > parent collection > homepage) |
| robots.txt blocking content | Can silently break entire sections | Check "internal blocked by robots.txt" in Screaming Frog. One blocked API key directory broke 33% of content rendering for a 900-hotel chain |
| Canonical URL conflicts | Duplicate indexing wastes crawl budget | Self-referencing canonicals on primary pages. Shopify fix: remove `within: collection` Liquid filter |
| Pagination noindex | Duplicate pages dilute authority | noindex `?page=2`, `?page=3` etc. Only top-level page should be indexed |
| Duplicate/thin content | Quality threshold exclusion | noindex tagged collection pages, paginated URLs, pages with no substantive content |

### Priority 2: Implement Next

| Issue | Fix |
|-------|-----|
| Schema markup | Product, FAQ, video schema for SERP visibility. See schema-entity-optimization |
| SSL / HTTPS | Mandatory. Use Cloudflare for free SSL + CDN |
| XML sitemap | Include only indexable pages. Remove orphans (case study: 10K live pages + 40K orphaned in sitemap) |
| Mobile rendering | Check every page on mobile. Google uses mobile-first indexing |
| Site speed | Server response under 300ms for AI crawlers. Under 4 seconds for traditional |

### Priority 3: Ongoing Maintenance

| Issue | Frequency |
|-------|-----------|
| Redirect chain cleanup | Quarterly |
| Orphan page audit | Quarterly |
| Crawl error monitoring | Weekly via GSC |
| Core Web Vitals | Monthly check |

---

## Crawl Audit Best Practices (Charles Meaden, brightonSEO)

### First-Pass Crawl (2-3 minutes)
Always run a quick first-pass crawl before full crawl to catch:
- Query strings inflating crawl
- Tracking URLs creating duplicates
- Print-friendly pages adding noise

### Source HTML vs JavaScript-Rendered Comparison
- Regularly compare source HTML vs JS-rendered crawl output
- Case study: hotel chain navigation only appeared on hover via JavaScript -- invisible to crawlers
- If content only renders via JS, Google may not see it

### Combine Crawl Data with Business Data
- Merge crawl data with stock levels, GA sessions, revenue per page
- A "perhaps too large" 500KB image on a high-traffic page matters more than a 3MB image on a low-traffic page
- Create prioritized action scores weighted by business impact

---

## Site Migration Checklist (Daphne Monro, brightonSEO)

### Six Migration Considerations
1. **Keyword portfolio** -- map every keyword you rank for
2. **GSC data** -- export everything before migration
3. **Branded keywords** -- plan brand transition strategy
4. **Site architecture** -- consolidate during migration (best time to restructure)
5. **Technical performance** -- benchmark Core Web Vitals with screenshots BEFORE migration (cannot retroactively run Lighthouse on old site)
6. **Future opportunities** -- plan new content architecture

### Content Consolidation During Migration
- Thousands of low-converting pages consolidated to a single portfolio landing page
- Do not launch with content that does not convert
- Each migrated page MUST have its own standalone primary keyword
- If you cannot find a primary keyword for a page, consolidate it during migration
- Find keywords: in GSC, filter by PAGE (not query), enter URL, see what users engage with

### Brand Transition Strategy
- HTML banner explaining the change
- Old brand mentioned in footer and about page
- Full brand story available (helps LLM citations too)
- Pre-migration 302 redirect can generate community buzz and early links

### Post-Migration Monitoring
- Continue monitoring old GSC property indefinitely
- Case study: still receiving hundreds of clicks daily on old property months after migration

---

## Edge SEO via CDN (Eben Aguilar, brightonSEO)

### What It Is
Edge SEO uses CDN layer (Cloudflare, Akamai) to implement SEO changes WITHOUT touching the origin server or CMS.

### What You Can Implement at the Edge
- Redirects
- Canonical tags
- Hreflang
- Meta robots
- Schema injection
- Header modifications
- Content injection

### When to Use
- CMS limitations prevent implementation
- Dev queue bottleneck (months-long sprint cycles)
- Code freezes (especially pre-Black Friday for e-commerce)
- Test-and-learn: deploy at edge, measure, then decide whether to implement in codebase

---

## Core Web Vitals & Page Speed

### The Pragmatic Position
- Under 3 seconds is fine for most sites
- Under 4 seconds is acceptable for e-commerce
- Only fix if load time exceeds 5-6+ seconds
- Page speed improvements move the needle ~0.5% vs keyword research + content + links at 90% (Cromwell)

### AI Crawler Requirements (brightonSEO)
- Server response time under 300ms
- No JavaScript runtime required (AI crawlers do not interact with JS)
- Static HTML pages preferred
- Duplicate key data as HTML tables alongside JS visualizations

### Mobile-First Indexing
- Google indexes the mobile version of your site
- Over 50% of internet traffic is mobile
- If mobile version looks or functions poorly, nothing else in SEO matters

---

## JavaScript SEO Issues

### The Problem
- AI crawlers and some search bots do not execute JavaScript
- Content rendered only via JS may be invisible to crawlers
- robots.txt can accidentally block directories containing API keys needed for JS rendering

### Diagnostic Process
1. Crawl with Screaming Frog in both "source HTML" and "rendered" modes
2. Compare output -- any content only in rendered mode is at risk
3. Check "internal blocked by robots.txt" report
4. Test with Google's URL Inspection Tool (shows rendered version)

### Fix
- Server-side render critical content
- Provide HTML fallbacks for JS-dependent content
- Ensure robots.txt does not block directories needed for rendering
- Duplicate JS visualizations as static HTML tables

---

## Instructor Disagreements

**Page speed importance:** Cromwell says nearly irrelevant (<4s fine). brightonSEO says server response <300ms for AI crawlers. Authority Hacker says do not obsess. Resolution: matters more for AI crawlers than traditional rankings.

**Technical SEO priority:** Cromwell says least important bucket (set and forget). brightonSEO data shows technical issues (especially JS rendering) can silently break large percentages of content. Resolution: run a thorough initial audit, then maintain quarterly unless you have 10K+ pages.
