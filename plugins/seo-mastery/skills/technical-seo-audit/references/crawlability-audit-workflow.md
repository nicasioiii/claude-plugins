# Crawlability Audit Workflow: Complete Diagnosis

## Why Crawlability Matters First
If Google can't crawl your site, you have zero ranking potential. Crawlability is the foundation—no exceptions. A site with perfect content and poor crawlability is invisible.

---

## Part 1: robots.txt Analysis (10 minutes)

### Step 1: Access & Inspect robots.txt
Navigate to `yoursite.com/robots.txt` and examine the entire file.

**What to Look For**:

```
User-agent: *
Disallow: /admin/
Disallow: /wp-admin/
Disallow: /wp-includes/
Disallow: /?s=
Disallow: /*?*
Allow: /*?utm_source=
Sitemap: https://yoursite.com/sitemap.xml
```

### Step 2: Check for Over-Blocking Patterns

**Common Mistakes**:
1. **`Disallow: /` (entire site blocked)** — Verify intentional (should only be on maintenance sites)
2. **`Disallow: /?*` (all URLs with parameters)** — Blocks pagination, filters, UTM parameters
   - Fix: Use `Allow: /*?utm_source=` instead to allow UTM params
3. **`Disallow: /admin/ /includes/ /temp/`** — OK to block admin paths
4. **`Disallow: /search` or `/search?`** — Common mistake if site has internal search
   - Impact: Filters, sorts, facets not crawlable
   - Fix: Remove unless you specifically don't want these indexed

### Step 3: Sitemap Declaration
Check if robots.txt includes:
```
Sitemap: https://yoursite.com/sitemap.xml
```

**If Missing**: Add this line. Google will still find sitemap through Search Console, but explicit declaration is recommended.

### Step 4: User-Agent Specificity
Check if rules target all bots or specific ones:
- `User-agent: *` = applies to all crawlers (Google, Bing, etc.)
- `User-agent: Googlebot` = applies only to Google

**Best Practice**: Use `User-agent: *` for broad rules; specific user-agents only if testing/debugging.

### Crawlability Audit Checklist
- [ ] No overly broad `Disallow: /` or `Disallow: /?*`
- [ ] Search functionality not blocked (remove if `/search` appears)
- [ ] Parameter blocking intentional (document why)
- [ ] Sitemap URL declared
- [ ] No blocking of mobile-friendly resources (CSS, JavaScript)

---

## Part 2: Google Search Console Coverage Analysis (15 minutes)

### Step 1: Access GSC Coverage Report
1. Open Google Search Console
2. Select property (desktop version)
3. Left sidebar → Indexing → Coverage

### Step 2: Analyze Four Coverage Categories

**CATEGORY 1: ERROR (Red) — Fix Immediately**
These pages failed to index due to errors.

Click "Error" to see breakdown:
- **Server error (5xx)** — Your hosting is down or slow; contact hosting provider
- **Redirect error** — Redirect chain broken or loops; check redirect path
- **Not found (404)** — Page deleted but still linked internally; update links or restore page
- **Submitted URL not found** — You submitted URL in GSC that doesn't exist; remove from sitemap

**Action**: For each error, note the URL count. If <10 URLs, fix manually. If >100 URLs, check if pattern exists (example: all errors on URLs with `?page=2` suggests pagination blocking).

**CATEGORY 2: VALID WITH WARNINGS (Yellow/Orange) — Monitor & Plan Fixes**
These indexed but have issues:
- **Duplicate without user-selected canonical** — Multiple URLs with same content; add canonical tag
- **Alternate page with proper redirect** — Mobile/AMP versions; verify canonical tags correct
- **Blocked by robots.txt** — Page exists but robots.txt blocks it; check if intentional

**Action**: Warnings don't prevent indexation but may prevent ranking. Prioritize canonical issues.

**CATEGORY 3: VALID (Green) — Healthy**
Pages successfully indexed with no errors/warnings.

**Target**: Aim for 95%+ of important pages in "Valid" (some errors are normal).

**CATEGORY 4: EXCLUDED (Grey) — Usually OK**
Google didn't index these (usually intentional):
- **Noindex tag** — Document intentionally doesn't want indexation
- **Soft 404** — Looks like error page; check if it should be indexed
- **Duplicate** — Canonical tag points elsewhere; working as intended
- **Sitemap entries are not valid pages** — Malformed sitemap

**Action**: Review "Soft 404" category. Some might be accidentally noindexed.

### Coverage Audit Checklist
- [ ] Error count = 0 or <5 (acceptable level)
- [ ] Warnings reviewed and documented
- [ ] No pattern of redirect errors
- [ ] Valid pages = 80%+ of submitted URLs
- [ ] Excluded pages are intentionally excluded (verify with noindex checks)

---

## Part 3: Fetch as Google / URL Inspection (10 minutes)

### Step 1: Test Critical Pages
In GSC, use "URL Inspection" tool (top search bar).

Test these pages:
1. Homepage
2. Key service/product pages (3-5)
3. Blog post example (1-2 recent)
4. Category/archive page

### Step 2: Examine Fetch Results

**What to Check**:

1. **Crawlable?**
   - Status should show "URL is crawlable"
   - If error: note error type (blocked by robots.txt, redirect error, timeout)

2. **Rendered Content**
   - Click "View rendered HTML"
   - Confirm all important text/links appear
   - If JavaScript-dependent content missing → problem (see JavaScript SEO)

3. **Mobile vs. Desktop**
   - Fetch page as "Mobile" user-agent
   - Compare content to desktop fetch
   - Should be identical (Google mobile-first indexes mobile version)

### Step 3: Check for Common Issues

**Issue 1: Content Missing on Mobile Fetch**
```
Desktop fetch: Shows full article
Mobile fetch: Shows only headline + ad
```
**Problem**: Mobile content hidden by overlays or lazy loading failure
**Fix**: Ensure mobile viewport is set; content loads before scroll

**Issue 2: Links Missing**
```
URL Inspection → View rendered HTML → No links visible
```
**Problem**: Links are JavaScript-rendered
**Fix**: Pre-render critical links in HTML

**Issue 3: Mixed Content (HTTPS site loading HTTP)**
```
Console shows: "Mixed Content: The page at X was loaded over HTTPS, but requested an insecure resource Y"
```
**Problem**: HTTPS site loading insecure resources
**Fix**: Update all internal links to HTTPS; update external CDNs to HTTPS

### URL Inspection Checklist
- [ ] Homepage crawlable with full content
- [ ] Key pages have mobile fetch identical to desktop
- [ ] No mixed content warnings (HTTP on HTTPS site)
- [ ] Links present and crawlable (not JavaScript-hidden)
- [ ] Recent pages show correct dates/content

---

## Part 4: Internal Link Structure Audit (10 minutes)

### Step 1: Check for Broken Internal Links
Use Screaming Frog (free tier crawls up to 500 URLs):
1. Enter domain
2. Start crawl
3. Check "Response Codes" column
4. Filter for 404s (broken internal links)

**What to Do**:
- If internal link to deleted page → update/remove the link
- If legitimate 404 → restore page or replace with redirect

### Step 2: Audit Link Flow
Check if important pages are reachable:
- Homepage should link to all major categories
- Categories should link to important posts
- Recent posts should be within 3 clicks of homepage

**Manual check**:
1. Open site homepage
2. How many clicks to reach important pages?
   - Homepage → Service page: should be 1 click
   - Homepage → Blog post: should be 2-3 clicks

**Issue**: If important pages require 5+ clicks → hard for Google to crawl and pass authority

**Fix**: Add breadcrumb navigation or footer links to important pages

### Step 3: Identify Crawl Traps
**Crawl trap**: Infinite number of new URLs that loop back (example: calendar widgets that generate infinite date URLs)

**Check**:
1. Do paginated archives create endless URL variations? (example: `?page=1`, `?page=2`, ..., `?page=999`)
2. Use robots.txt to block non-essential pagination:
```
Disallow: /*?page=2
Disallow: /*?page=3
```

**Alternative**: Use rel="next" and rel="prev" for paginated content instead of blocking.

### Internal Link Audit Checklist
- [ ] No 404s from internal links (or <5 acceptable)
- [ ] Important pages reachable in <3 clicks from homepage
- [ ] Pagination doesn't create infinite URL variations
- [ ] Site map/footer includes links to key pages
- [ ] Breadcrumb navigation present and correct

---

## Part 5: Robots Meta Tag Audit (5 minutes)

### What Robots Meta Tags Do
The `<meta name="robots" content="...">` tag in page `<head>` controls indexation/crawling per page.

### Check Critical Pages
Use Chrome DevTools:
1. Open page
2. Right-click → Inspect
3. Search for `<meta name="robots"`

### Values to Check For

**Correct Usage**:
- `<meta name="robots" content="index, follow">` — Standard (page indexed, links followed)
- `<meta name="robots" content="noindex, follow">` — Intentional non-indexation (privacy pages, test pages)

**Problem Indicators**:
- `<meta name="robots" content="noindex, nofollow">` — Page excluded; verify if intentional
- Missing entirely — OK; defaults to "index, follow"

### Pages That Should Have noindex
- Login/registration pages
- Thank you pages (after form submission)
- Internal search results pages
- Print-friendly versions
- Duplicate content pages (use canonical instead)

### Pages That Should NEVER Have noindex
- Service pages
- Blog posts
- Product pages
- Category pages

### Robots Meta Checklist
- [ ] Service/product pages: NO noindex tag (or `index, follow` if explicitly set)
- [ ] Blog posts: NO noindex tag
- [ ] Admin/login pages: HAVE noindex tag
- [ ] Test pages: HAVE noindex tag (if not removed before launch)
- [ ] No duplicated directives (meta tag AND X-Robots-Tag header)

---

## Part 6: Redirect Chain Analysis (5 minutes)

### Why Redirect Chains Matter
Each redirect = Google crawl request. Too many redirects waste crawl budget + slow down site.

**Example of bad chain**:
```
yourdomain.com → old-domain.com → another-domain.com → final-domain.com
```
This is a **3-hop redirect chain**. Every user/bot follows all 3 redirects.

### Audit Redirects
Use Redirect Checker tool (online):
1. Enter main domain URL
2. Check redirect path
3. Should show max 1 redirect (zero is ideal)

**Best Practice**:
- Old domain → New domain (1 redirect) ✓
- Domain.com → domain.com/path (1 redirect) ✓
- Paginated old URLs → new paginated URLs (1 redirect per page) ✓

**Problem**:
- A → B → C (2 hops, wasteful) ✗
- Domain → subdomain → folder → subdomain (multiple hops) ✗

### Fix Redirect Chains
1. Identify the final destination
2. Update ALL redirects to point directly to final destination
3. Remove intermediate redirects

Example:
```
BEFORE (bad):
old-domain.com/page → new-domain.com/page → new-domain.com/posts/page

AFTER (good):
old-domain.com/page → new-domain.com/posts/page (direct)
```

### Crawlability Audit Summary Report

Compile findings into single document:

| Issue Category | Finding | Status | Priority |
|---|---|---|---|
| robots.txt | Search blocked by `Disallow: /search?` | Needs Fix | High |
| Coverage | 5 pages with 5xx errors | Investigating | High |
| Fetch Testing | Mobile content missing (lazy load) | Needs Fix | Medium |
| Internal Links | 3 broken internal links to deleted pages | Needs Fix | Medium |
| Robots Meta | 2 service pages have noindex tag | Needs Fix | High |
| Redirects | 2-hop redirect on main domain URLs | Needs Fix | Low |

**Action Items** (ordered by impact):
1. Remove noindex from service pages
2. Fix robots.txt search parameter blocking
3. Investigate 5xx errors with hosting provider
4. Update broken internal links
5. Consolidate redirect chains
