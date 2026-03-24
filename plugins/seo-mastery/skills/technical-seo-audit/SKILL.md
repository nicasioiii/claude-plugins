---
name: "Technical SEO Audit"
description: "Diagnose and fix crawlability, indexation, Core Web Vitals, structured data, and site architecture issues. Comprehensive audit framework, site speed optimization, JavaScript SEO, mobile-first, XML sitemaps, and schema validation. Triggers: technical SEO, site audit, crawl errors, Core Web Vitals, page speed, indexation, schema markup, JavaScript SEO, mobile SEO. Covers: audit workflows, crawlability diagnosis, indexation troubleshooting, Core Web Vitals optimization. Does NOT cover: coding implementation, hosting changes."
Triggers:
  - technical SEO
  - site audit
  - crawl errors
  - Core Web Vitals
  - page speed
  - indexation
  - schema markup
  - JavaScript SEO
  - mobile SEO
---

# Technical SEO Audit & Optimization Mastery

## Core Purpose
Diagnose and fix the technical foundations that prevent sites from ranking. Technical SEO isn't about tricks—it's about removing barriers to crawlability, indexation, and Core Web Vitals performance. A site with perfect content and mediocre technical health will never dominate search.

## Your Goal as a Technical SEO Auditor
You're answering: **"Why isn't this site ranking despite good content and links?"** The answer usually lives in crawlability, indexation, mobile-first readiness, JavaScript rendering issues, or Core Web Vitals bottlenecks.

---

## The Technical SEO Hierarchy (Priority Order)

### Tier 1: Crawlability & Indexation (CRITICAL)
- If Google can't crawl your site → indexation fails → no rankings possible
- **Key metrics**: robots.txt blocks, redirect chains, sitemaps, internal link structure
- **Tools**: Google Search Console Coverage tab, Site Explorer (Ahrefs), GTmetrics

### Tier 2: Mobile-First Indexing (CRITICAL)
- Google crawls mobile version first; if mobile content differs from desktop → ranking issues
- **Key metrics**: Viewport meta tag, responsive design, mobile rendering
- **Tools**: Mobile-Friendly Test, Google PageSpeed Insights, GTmetrics device simulation

### Tier 3: Core Web Vitals (HIGH)
- Largest Contentful Paint (LCP), First Input Delay (FID), Cumulative Layout Shift (CLS)
- Poor CWV = ranking penalty; good CWV = ranking boost
- **Key metrics**: Real-world CrUX data, lab testing with GTmetrics/PageSpeed
- **Tools**: Google PageSpeed Insights, GTmetrics, Core Web Vitals report (GSC)

### Tier 4: Security & HTTPS (CRITICAL)
- Non-HTTPS sites get ranking penalty; SSL certificate is table stakes
- **Key metrics**: HTTPS redirect, mixed content warnings
- **Tools**: Browser console inspection

### Tier 5: Structured Data Validation (MEDIUM)
- Schema markup helps Google understand content type (article, product, FAQ, etc.)
- Rich snippets increase CTR; broken schema gets ignored
- **Key metrics**: Schema syntax, Google Rich Results validation
- **Tools**: Google Rich Results Test, Schema.org validator

### Tier 6: JavaScript SEO (MEDIUM)
- Client-side JavaScript-rendered content may not be indexed
- **Key metrics**: JavaScript execution, content visibility in rendered HTML
- **Tools**: Google's URL Inspection tool (fetch as Google), Screaming Frog JS rendering

---

## Audit Workflow: 5-Step Process

### Step 1: Crawlability Audit (30 min)
1. Check robots.txt (`site.com/robots.txt`) for blocking patterns
2. Review GSC Coverage report for crawl errors
3. Audit internal link structure (broken internal links?)
4. Check robots meta tags on key pages
5. Identify redirect chains (should be max 1)

**Deliverable**: Crawlability audit checklist with findings + fixes ranked by priority

### Step 2: Indexation Diagnosis (30 min)
1. Run `site:domain.com` search; compare to GSC indexed pages
2. Check for canonical tag conflicts (self-referencing canonicals?)
3. Review noindex tags (accidentally blocking pages?)
4. Audit URL parameters causing duplicate indexation
5. Check Search Console coverage report for "not indexed" pages

**Deliverable**: Indexation audit with fix recommendations

### Step 3: Mobile-First Health Check (20 min)
1. Use Mobile-Friendly Test on 3-5 key pages
2. Check viewport meta tag presence
3. Test responsive design on iPhone/Android devices
4. Check for mobile blocking (app redirects, excessive overlays)
5. Compare mobile vs. desktop content (should be identical)

**Deliverable**: Mobile-first checklist + priority fixes

### Step 4: Core Web Vitals Analysis (30 min)
1. Run Google PageSpeed Insights (mobile + desktop)
2. Check CrUX real-world data in GSC
3. Document LCP, FID/INP, CLS scores
4. Identify top bottlenecks (images, JavaScript, rendering)
5. Check GTmetrics for waterfall analysis

**Deliverable**: CWV optimization roadmap (quick wins first)

### Step 5: Schema & Security Validation (20 min)
1. Validate all schema markup with Google Rich Results Test
2. Check HTTPS coverage (non-HTTPS pages?)
3. Review mixed content warnings
4. Audit JavaScript rendering (is critical content client-side?)
5. Test nofollow/sponsored link attributes

**Deliverable**: Schema fixes + security audit results

---

## Common Technical SEO Issues & Solutions

### Issue 1: Crawl Budget Waste
**Symptom**: GSC shows "Crawled - not indexed" or "Crawl errors" spike
**Root causes**:
- Paginated URL parameters (?page=1, ?sort=price)
- Session IDs in URLs (changing on each visit)
- Infinite crawl traps (auto-paginating archives)
- Excessive internal linking to non-essential pages

**Fix Priority**:
1. Use URL parameters in GSC Settings to control crawl
2. Add `rel="next" rel="prev"` for pagination
3. Robots.txt block low-value parameter combinations
4. Clean up internal linking (remove links to filters, sorts)

### Issue 2: Mobile Content Mismatch
**Symptom**: Mobile version shows different content than desktop
**Root causes**:
- JavaScript not rendering on mobile
- Mobile viewport blocking essential content
- Lazy loading breaking mobile crawl

**Fix**: Ensure GSC "Fetch as Mobile" shows same content as desktop fetch

### Issue 3: Core Web Vitals Failure
**Symptom**: PageSpeed score <50 on mobile; CrUX data shows poor LCP/CLS
**Root causes** (in order of prevalence):
1. Unoptimized images (largest single factor)
2. Render-blocking CSS/JavaScript
3. Slow third-party scripts (ads, analytics, chat)
4. Poor hosting performance
5. Cumulative Layout Shift from ads/embeds

**Fix Roadmap**:
1. Image optimization (WebP format, lazy loading, sizing)
2. Remove unused CSS/JS
3. Defer third-party scripts
4. Optimize server response time (TTFB)

### Issue 4: Indexation Drops
**Symptom**: Sudden drop in indexed pages; no obvious deletions
**Root causes**:
- Accidental noindex tag on important pages
- Robots meta tag changes
- Canonical chain issues
- Duplicate content from new features/templates

**Debug**: Check GSC Coverage → "Excluded" → "Noindexed by user"

### Issue 5: Schema Markup Not Triggering Rich Results
**Symptom**: Schema validates but no rich snippets appear in SERP
**Root causes**:
- Schema syntax valid but Google doesn't recognize content type
- Missing required fields (Google requires more than schema.org spec)
- Content doesn't meet Google's eligibility (e.g., Product needs image + price)
- Wrong schema type for content

**Fix**: Test with Google Rich Results Test; check eligibility guidelines per type

---

## Tools You'll Use

### Free Tools (Start Here)
- **Google Search Console**: Crawl errors, indexation, mobile usability, Core Web Vitals
- **Google PageSpeed Insights**: CWV analysis, optimization suggestions
- **Mobile-Friendly Test**: Quick mobile check
- **Google Rich Results Test**: Schema validation + rich snippet preview
- **Screaming Frog (free tier)**: Crawl audit (up to 500 URLs)

### Paid Tools (ROI Tools)
- **Ahrefs Site Audit**: Site-wide technical analysis, crawl errors, backlink health
- **GTmetrics**: Waterfall analysis, performance metrics, device simulation
- **Semrush Technical SEO Audit**: Covers crawlability, mobile, Core Web Vitals

### Chrome DevTools & Manual Testing
- Network tab (identify render-blocking resources)
- Lighthouse (accessibility + performance audit)
- Console (JavaScript errors)
- Performance tab (identify slow operations)

---

## Reference Files to Use
- **crawlability-audit-workflow.md** — Step-by-step crawlability diagnosis with GSC navigation
- **indexation-troubleshooting.md** — Fixing noindex, canonicals, duplicate content
- **mobile-first-implementation.md** — Mobile-friendly checklist + responsive design audit
- **core-web-vitals-optimization.md** — LCP/CLS/INP fixes with priority order
- **site-speed-optimization.md** — Image optimization, caching, third-party script deferral
- **schema-validation-checklist.md** — Schema types, validation tools, common failures
- **javascript-seo-guide.md** — Client-side rendering, fetch-as-Google testing
- **xml-sitemap-generation.md** — Sitemap structure, best practices, submission

---

## Quick Diagnosis Questions

Answer these before diving into audit:

1. **Is the site crawlable?**
   - Run `site:domain.com`; does Google see any pages?
   - Check robots.txt for blocking

2. **Is mobile blocking content?**
   - Test on Mobile-Friendly Test
   - Compare GSC "Fetch as Mobile" vs. "Fetch as Desktop"

3. **Are Core Web Vitals passing?**
   - Check Google PageSpeed Insights
   - Mobile or desktop failing? (Usually mobile)

4. **Is the issue indexation or ranking?**
   - Use GSC Coverage report
   - If not indexed → fix crawlability/indexation first
   - If indexed but not ranking → add content/links or schema

5. **Is there a penalty history?**
   - Check GSC Manual Actions report
   - Any unresolved manual actions = fix first

---

## Actionable Deliverables

Each audit produces:
1. **Technical Audit Report** (7-page max)
   - Executive summary (top 5 issues)
   - Crawlability findings + fixes
   - Indexation status + recommendations
   - Mobile-first assessment + checklist
   - Core Web Vitals analysis + prioritized fixes
   - Schema validation results

2. **Fix Implementation Roadmap**
   - Quick wins (can implement in <1 day)
   - Medium-term fixes (1-2 weeks)
   - Long-term optimization (1-3 months)
   - Estimated traffic impact per fix

3. **Monitoring Dashboard Setup**
   - Core Web Vitals tracking
   - Crawl health metrics
   - Indexation trend monitoring

---

## When to Hand Off to Other Skills

- **Content gaps discovered?** → Hand off to content-cluster-strategy
- **On-page optimization needed (meta tags, headers)?** → Hand off to on-page-optimization
- **Link profile weak?** → Hand off to link-authority-building
- **Need structured data strategy for competitive advantage?** → Combine with on-page-optimization

---

## Key Principles to Remember

1. **Crawlability > Indexation > Rankings**: Fix the foundation first
2. **Mobile-first isn't optional**: Google indexes mobile version; desktop is secondary
3. **Core Web Vitals matter**: Poor CWV = ranking penalty, no exceptions
4. **Schema helps Google understand, not rank**: Valid schema ≠ automatic rankings
5. **Iteration > Perfection**: Start with GSC + PageSpeed; refine based on data
6. **Test with data, not intuition**: Browser caching makes sites feel faster than they are
