---
name: "SEO Audit"
description: |
  Full technical + on-page SEO audit for any website. Activates technical-seo-audit,
  on-page-optimization, and schema-entity-optimization skills. Outputs priority-ranked
  issue list with fix instructions.
---

# /seo-audit -- Comprehensive SEO Audit Workflow

## Skills Activated
- **technical-seo-audit** (primary) -- crawlability, indexation, Core Web Vitals, JS SEO
- **on-page-optimization** (secondary) -- meta tags, headers, keyword placement
- **schema-entity-optimization** (tertiary) -- structured data assessment

## Invocation
```
/seo-audit [domain.com]
```

## Required Input
Ask the user for:
1. **Domain** -- the website to audit
2. **Business type** -- e-commerce, content site, local service, SaaS, directory
3. **Primary goal** -- more traffic, fix indexing issues, prepare for AI search, site migration
4. **Available tools** -- Google Search Console access, Ahrefs/SEMrush, Screaming Frog
5. **Page count** -- approximate number of pages on the site

---

## Audit Section 1: Crawlability Assessment

### Check These First
1. **robots.txt review** -- is anything critical blocked? Check for wildcards blocking API/JS resources
2. **XML sitemap** -- does it exist? Does it include only indexable pages? Any orphans?
3. **Google Search Console coverage** -- what is the indexed vs submitted ratio?
4. **Internal link structure** -- are there orphan pages with zero internal links?
5. **Redirect chains** -- any chains (A > B > C) that need collapsing?

### Diagnostic Questions
- Are pages appearing as "crawled currently not indexed" in GSC? (likely quality issue -- Tier 3)
- Are pages "discovered currently not indexed"? (likely not being crawled at all -- check internal links)
- Has any page not been crawled in 130+ days? (99% chance of not being indexed)
- Is robots.txt blocking CSS/JS files needed for rendering?

### Output Format
```
CRAWLABILITY SCORE: X/100

Critical Issues:
- [Issue]: [Pages affected] | [Fix instruction]

Warnings:
- [Issue]: [Pages affected] | [Fix instruction]

Healthy:
- [What is working correctly]
```

---

## Audit Section 2: Indexation Diagnosis

### Apply the Three-Tier Exclusion Framework
For each non-indexed page, diagnose which tier is causing exclusion:

**Tier 1 (Technical):** noindex tag, 404 error, robots.txt block, redirect loop
- Fix: remove the technical blocker

**Tier 2 (Duplicate/Similar):** canonical conflicts, near-duplicate content, thin overlap
- Fix: set canonicals, consolidate, differentiate

**Tier 3 (Quality):** insufficient content, no links, no engagement
- Fix: improve content quality, add internal links, earn backlinks

### Output Format
```
INDEXATION STATUS:
- Total pages submitted: [X]
- Total pages indexed: [Y]
- Index ratio: [Y/X]%

Non-Indexed Pages by Tier:
- Tier 1 (Technical): [count] pages -- [top issues]
- Tier 2 (Duplicate): [count] pages -- [top issues]
- Tier 3 (Quality): [count] pages -- [recommendations]
```

---

## Audit Section 3: On-Page Optimization Assessment

### Sample 5-10 Key Pages
For the site's most important pages (homepage, top service/product pages, top blog posts):

| Page | Meta Title | H1 | Keywords in Intro | Internal Links | Schema |
|------|-----------|-----|-------------------|----------------|--------|
| [URL] | [OK/Fix] | [OK/Fix] | [OK/Fix] | [Count] | [Type or Missing] |

### Common Issues to Flag
- Meta titles not front-loading keywords
- H1 not matching meta title (Google rewrite risk)
- Missing keywords in first/last 100 words
- No internal links or poor anchor text
- Missing schema markup
- Images without alt text

---

## Audit Section 4: Technical Health

### Core Web Vitals
| Metric | Current | Target | Status |
|--------|---------|--------|--------|
| LCP | [X]s | <2.5s | [Pass/Fail] |
| CLS | [X] | <0.1 | [Pass/Fail] |
| INP | [X]ms | <200ms | [Pass/Fail] |
| Server Response (TTFB) | [X]ms | <300ms (for AI crawlers) | [Pass/Fail] |

### Mobile-First Check
- Does the site render correctly on mobile?
- Are tap targets adequate?
- Is text readable without zoom?

### JavaScript Rendering
- Is critical content rendered only via JavaScript?
- Are any JS/CSS resources blocked by robots.txt?
- Compare source HTML vs rendered version for key pages

### SSL/HTTPS
- Is HTTPS enforced?
- Any mixed content warnings?

---

## Audit Section 5: Schema Assessment

### Current Schema
- What schema types are currently implemented?
- Are they valid (schema.org validator)?
- Do they pass Google Rich Results Test?

### Missing Schema Opportunities
| Page Type | Recommended Schema | Priority |
|-----------|-------------------|----------|
| Homepage | Organization + LocalBusiness | High |
| Service pages | Service or specific type | High |
| Blog posts | Article with author | Medium |
| FAQ sections | FAQPage | Medium |
| Products | Product with offers | High (e-commerce) |

---

## Audit Section 6: AI Search Readiness

### Technical Requirements for AI Crawlers
- [ ] Server response under 300ms
- [ ] Critical content in static HTML (not JS-dependent)
- [ ] Schema markup implemented (orchestrator layer reads schema)
- [ ] Semantic URLs (5-7 word natural-language slugs)
- [ ] Meta descriptions spoil content (answer in description)

### Content Requirements for AI Citation
- [ ] Fact-dense pages (self-contained claim statements)
- [ ] FAQ sections mirroring key facts
- [ ] Question-style H2s with 40-60 word answer blocks
- [ ] Real author bios (not AI personas)
- [ ] Year in titles/H1s for recency signal

---

## Priority Fix Roadmap

### Tier 1: Critical (Fix This Week)
Issues that actively prevent crawling, indexing, or rendering.
```
1. [Issue] -- [X pages affected] -- [Fix instruction] -- [Time estimate]
2. [Issue] -- [X pages affected] -- [Fix instruction] -- [Time estimate]
```

### Tier 2: Important (Fix This Month)
Issues that reduce ranking potential but are not blocking.
```
1. [Issue] -- [Impact estimate] -- [Fix instruction] -- [Time estimate]
```

### Tier 3: Optimization (Ongoing)
Improvements that enhance performance but are not urgent.
```
1. [Issue] -- [Impact estimate] -- [Fix instruction] -- [Time estimate]
```

---

## Tool Recommendations

### Free Tools
- Google Search Console (indexation, performance, coverage)
- Google Rich Results Test (schema validation)
- PageSpeed Insights (Core Web Vitals)
- Screaming Frog (free up to 500 URLs)
- schema.org validator

### Paid Tools
- Ahrefs or SEMrush (backlink analysis, keyword tracking, site audit)
- Screaming Frog (paid for unlimited URLs)
- Sitebulb (visual crawl analysis)
- ContentKing (real-time SEO monitoring)

---

## Post-Audit Monitoring
- Re-check GSC coverage weekly for first month after fixes
- Track keyword rankings for affected pages
- Monitor Core Web Vitals monthly
- Re-audit quarterly for ongoing maintenance
- For 10K+ page sites, consider continuous monitoring tools
