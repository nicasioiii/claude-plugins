---
name: SEO Audit
description: "Generate a complete technical SEO audit for any website with priority-ranked issues and actionable fixes."
---

# /seo-audit — Comprehensive Technical SEO Audit Workflow

## Command Purpose
Generate a complete technical SEO audit for any website. Outputs priority-ranked issues with actionable fixes.

## Invocation
```
/seo-audit [domain.com]
```

## What You Get
1. **5-Page Audit Report** with executive summary
2. **Crawlability Score** (0-100)
3. **Indexation Status** breakdown
4. **Mobile-First Assessment** with fixes
5. **Core Web Vitals Analysis** (LCP, CLS, INP)
6. **Prioritized Fix Roadmap** (quick wins → long-term)
7. **Tool Recommendations** (free + paid)

---

## Audit Sections

### 1. Executive Summary (1 page)
- Overall health score: X/100
- Top 3 critical issues
- Estimated traffic loss from each issue
- Recommended quick wins (can implement in <1 day)

### 2. Crawlability Audit (1 page)
- robots.txt analysis
- Google Search Console coverage report summary
- Internal link structure health
- Broken internal links count
- Redirect chain issues
- Verdict: "Crawlable ✓" or "Issues Found ✗"

### 3. Indexation Diagnosis (½ page)
- Total indexed pages (from GSC)
- Coverage status breakdown (valid, warning, excluded)
- Any noindex issues
- Duplicate content signals
- Action items

### 4. Mobile-First Health (½ page)
- Mobile-Friendly Test result
- Viewport meta tag present? ✓/✗
- Responsive design: ✓/✗
- Content parity (mobile vs desktop): Match/Mismatch
- Mobile performance score

### 5. Core Web Vitals Analysis (1 page)
- PageSpeed mobile score
- LCP, CLS, INP breakdown
- Real-world CrUX data (if available)
- Bottleneck identification
- Optimization roadmap (by impact)

### 6. Schema & Technical Validation (½ page)
- Schema types found on key pages
- Validation errors count
- Missing schemas on important pages
- Security (HTTPS) check

### 7. Fix Roadmap (1 page)

**Quick Wins (Day 1)**:
- Issue 1: What to do → Expected impact
- Issue 2: What to do → Expected impact
- Issue 3: What to do → Expected impact

**Medium-Term (1-2 weeks)**:
- Issue A: Effort required → Impact

**Long-Term (1-3 months)**:
- Issue X: Effort required → Impact

---

## How the Audit Works

### Step 1: Crawlability Check (10 min)
- robots.txt inspection
- GSC Coverage report analysis
- URL Inspection fetch tests (5 key pages)
- Internal link structure crawl

### Step 2: Indexation Analysis (10 min)
- GSC indexation status
- noindex tag audit
- Duplicate content detection
- Soft 404 identification

### Step 3: Mobile Assessment (5 min)
- Mobile-Friendly Test
- Viewport tag check
- Responsive design verification
- Content parity comparison

### Step 4: Performance Analysis (10 min)
- PageSpeed Insights (mobile + desktop)
- GTmetrics waterfall analysis
- Core Web Vitals real-world data (CrUX)
- Bottleneck identification

### Step 5: Technical Validation (5 min)
- Schema.org validation
- HTTPS/security check
- JavaScript rendering test
- XML sitemap verification

### Step 6: Compile Recommendations (10 min)
- Consolidate findings
- Rank by impact
- Estimate effort per fix
- Create prioritized roadmap

**Total Time**: ~50 minutes per audit

---

## Output Format

### Report Template

```
TECHNICAL SEO AUDIT REPORT
Domain: [domain.com]
Date: [Date]
Auditor: [Your Name]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

EXECUTIVE SUMMARY

Overall Health Score: 72/100
Status: Good (but improvements available)

Top 3 Critical Issues:
1. Core Web Vitals failing on mobile (LCP 4.2s, target <2.5s)
   → Estimated traffic loss: 15-20% from mobile users
   → Fix: Image optimization + defer JavaScript

2. Mobile content showing different text than desktop (lazy loading)
   → Estimated impact: Indexation issues on 10-20 pages
   → Fix: Ensure images load before JavaScript

3. 5 noindex tags on active service pages
   → Estimated traffic loss: 5-10% from organic
   → Fix: Remove noindex tags; request indexing in GSC

Quick Wins (Implement First):
✓ Convert images to WebP (30-40% page speed boost)
✓ Defer JavaScript (20-30% boost)
✓ Remove noindex from service pages (5-10% traffic recovery)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. CRAWLABILITY AUDIT

Robots.txt Status: ✓ CLEAN
- No over-blocking patterns
- Search functionality not blocked
- Sitemap declared correctly

GSC Coverage: ⚠ WARNINGS
- 95% indexed (Good)
- 5 pages with redirect errors (Action: Fix redirects)
- 0 pages blocked by robots.txt (Good)

Internal Links: ✓ HEALTHY
- 3 broken internal links (Low: <5 acceptable)
- All key pages reachable within 3 clicks
- Breadcrumb navigation present

Verdict: CRAWLABLE ✓
Action: Fix 3 broken internal links

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

2. INDEXATION STATUS

Total Indexed Pages: 245 (from GSC)
Coverage Breakdown:
- Valid: 240 (98%)
- Excluded (Noindex): 8 (includes 5 service pages with accidental noindex)
- Excluded (Duplicate): 3
- Errors: 2

Issues Found:
⚠ 5 service pages have noindex tag (REMOVE IMMEDIATELY)
⚠ 2 pages with redirect chains (consolidate)

Verdict: NEEDS ATTENTION ✗
Priority Fix: Remove 5 noindex tags from service pages

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

3. MOBILE-FIRST HEALTH

Mobile-Friendly Test: ✓ PASS
Viewport Tag: ✓ Present & correct
Responsive Design: ✓ Working
Content Parity: ✗ MISMATCH FOUND
- Desktop: Shows full article text
- Mobile: Shows only headline (lazy loading issue)
- Action: Ensure images load before JavaScript executes

Mobile Performance Score: 45/100 (POOR)
- LCP: 4.2s (Target <2.5s) ✗
- CLS: 0.08 (Target <0.1) ✓
- INP: 120ms (Target <200ms) ✓

Verdict: NEEDS FIXING ✗
Priority: Fix lazy loading + Core Web Vitals

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

4. CORE WEB VITALS ANALYSIS

Real-World Data (CrUX):
- 40% of mobile traffic: LCP >2.5s (Poor)
- 10% of mobile traffic: CLS >0.1 (Poor)
- Desktop: Mostly good (LCP <2.5s)

Root Causes (Priority Order):
1. Unoptimized images (48KB average, should be <30KB)
   → Impact: 1-1.5s LCP improvement possible

2. Render-blocking CSS (critical.css not inlined)
   → Impact: 0.5-1s improvement

3. JavaScript execution slow on mobile
   → Impact: 0.3-0.5s improvement

Optimization Roadmap:
Week 1: Convert images to WebP + compress with TinyPNG
Week 2: Inline critical CSS + defer non-critical JS
Week 3: Monitor impact; adjust as needed

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

5. SCHEMA & SECURITY

Schema Validation:
✓ Article schema on blog posts (correct)
✓ Organization schema on homepage (correct)
✗ Product schema missing on 12 product pages (MEDIUM PRIORITY)

Security:
✓ HTTPS enabled (all pages)
✓ No mixed content warnings

Sitemap:
✓ sitemap.xml present and valid
✓ Declared in robots.txt

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

6. PRIORITIZED FIX ROADMAP

QUICK WINS (Day 1 - 2 hours):
□ Remove noindex from 5 service pages
□ Fix 3 broken internal links
□ Request indexing in GSC for re-indexed pages

Expected Impact: +5-10% organic traffic

MEDIUM-TERM (Week 1-2 - 10 hours):
□ Convert images to WebP
□ Compress with TinyPNG
□ Implement lazy loading
□ Inline critical CSS

Expected Impact: 30-40% PageSpeed improvement

LONG-TERM (Week 3-4 - 20 hours):
□ Defer JavaScript
□ Implement CDN
□ Remove unused CSS
□ Consider hosting upgrade (TTFB currently 1.2s)

Expected Impact: 50%+ PageSpeed improvement

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

TOOLS NEEDED

Free:
- Google PageSpeed Insights
- Google Search Console
- Screaming Frog (free tier)
- GTmetrics
- Google Mobile-Friendly Test

Paid (Recommended):
- Ahrefs ($99/month) - Site audit
- WP Rocket ($39/month) - Caching if WordPress

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

NEXT STEPS

1. Implement quick wins immediately
2. Track metrics weekly (PageSpeed, GSC coverage)
3. Implement medium-term fixes over next 2 weeks
4. Monitor rankings for improvement signals
5. Re-run full audit in 30 days

Contact: [Your contact info]
```

---

## When to Use This Command

✓ **New client onboarding** — Baseline assessment
✓ **Rankings dropping unexpectedly** — Diagnose technical issues
✓ **Before launching major redesign** — Audit current state first
✓ **Quarterly health check** — Stay on top of technical SEO
✓ **After core update** — Check for technical issues

---

## Limitations & Notes

- Assumes site is publicly accessible
- Requires access to Google Search Console
- May take 50+ minutes for comprehensive audit
- Best for sites <10,000 pages (crawl limitations)
- Does not guarantee ranking improvement (assumes content + links are solid)

---

## Integration with Other Skills

**After audit, hand off to**:
- **technical-seo-audit skill** — For detailed reference docs on fixes
- **on-page-optimization** — If schema/metadata issues found
- **content-cluster-strategy** — If content gaps discovered
- **link-authority-building** — If authority signals weak
