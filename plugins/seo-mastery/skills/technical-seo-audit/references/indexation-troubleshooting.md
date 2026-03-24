# Indexation Troubleshooting: Fix "Not Indexed" Pages

## Why Pages Aren't Indexed (And How to Fix)

Pages go missing from Google's index for specific reasons. This guide diagnoses and fixes each one.

---

## Problem 1: Accidental Noindex Tag

### Diagnosis

**In GSC Coverage Report**:
- Click "Excluded"
- Select "Noindexed by user"
- See list of pages Google didn't index

**Verify the Page**:
1. Visit URL in browser
2. Right-click → Inspect
3. Search for `<meta name="robots"`
4. Look for: `content="noindex"`

### Why It Happened

Most common causes:
1. **WordPress draft/private settings** — Post set to "Private" instead of "Public"
2. **SEO plugin default** — Plugin set noindex on all posts by default
3. **Yoast/Rank Math settings** — Advanced setting accidentally turned on
4. **Staging site indexed** — Site copied from staging (which had noindex); forgot to remove tag

### Fix

**For WordPress**:
1. Edit post
2. Check post status: Should be "Published" (not Draft/Private/Pending)
3. Check SEO plugin settings (Yoast/Rank Math)
   - Look for "Allow search engines to index this post"
   - Should be: **YES** (checkmark)
4. Save changes
5. Remove the noindex tag

**Verify Fix**:
```
Edit post > Inspect > Search for <meta name="robots"
Should NOT contain: "noindex"
```

**After Removing Tag**:
- Go to GSC
- Click "Request Indexing" on the page
- Google will re-crawl within 1-7 days

---

## Problem 2: Robots.txt Blocking

### Diagnosis

**In GSC Coverage**:
- Click "Excluded"
- Select "Blocked by robots.txt"

**Verify Robots.txt**:
1. Open `site.com/robots.txt`
2. Look for line blocking this page
3. Example: `Disallow: /blog/` blocks all blog posts

### Why It Happened

Usually unintentional:
- SEO agency added overly broad rule
- Developer blocked category/directory and forgot to remove
- Pagination parameter blocking (example: `Disallow: /?page=2` blocks all paginated content)

### Fix

**To Allow Content in Blocked Directory**:
```
# BAD: Blocks entire blog
Disallow: /blog/

# GOOD: Allow blog but block admin
Disallow: /admin/
Disallow: /blog/archives/
Allow: /blog/
```

**To Allow Specific Parameters**:
```
# BAD: Blocks all URLs with parameters
Disallow: /?*

# GOOD: Block only search parameters
Disallow: /*?s=
Allow: /*?utm_source=
```

**After Editing robots.txt**:
1. Save changes (takes 24-48 hours to fully propagate)
2. Request indexing in GSC for blocked pages
3. Check GSC "Coverage" report in 7 days to confirm unblocked

---

## Problem 3: Duplicate Content & Canonical Issues

### Diagnosis

**In GSC Coverage**:
- Click "Excluded"
- Select "Duplicate" or "Duplicate without user-selected canonical"

**Check Canonical Tag**:
1. Open page
2. Inspect → Search for `<link rel="canonical"`
3. Check where it points

### Common Scenarios

**Scenario A: Page Canonicalized to Wrong URL**
```html
<!-- BAD: Page points to different page as canonical -->
<link rel="canonical" href="https://yoursite.com/different-page/">
```
**Result**: Google indexes the other page instead

**Scenario B: Self-Referencing Canonical**
```html
<!-- GOOD: Page references itself (correct) -->
<link rel="canonical" href="https://yoursite.com/this-page/">
```

**Scenario C: No Canonical (Relies on URL structure)**
```html
<!-- Google treats /page/ and /page?tracking=param as duplicate -->
<!-- Need canonical to pick one -->
<link rel="canonical" href="https://yoursite.com/page/">
```

### Fix

**If Wrong Canonical**:
1. Edit page
2. Check SEO plugin canonical setting
3. Should point to page's own URL
4. Save changes

**If URL Parameters Creating Duplicates**:
Use robots.txt to tell Google which version to index:
```
# Tell Google to prefer version without tracking parameters
Disallow: /*?utm_source=
Disallow: /*?utm_medium=
Disallow: /*?utm_campaign=
```

**If Multiple Versions (HTTP, HTTPS, www)**:
1. Pick one preferred version (usually: https://www.yoursite.com)
2. Set canonical on all other versions to point to preferred version
3. Set up 301 redirect from non-preferred to preferred

**After Fixing Canonical**:
- Request indexing in GSC
- Check GSC Coverage in 7 days
- Should move from "Duplicate" to "Valid"

---

## Problem 4: Soft 404 (Looks Like Error Page)

### Diagnosis

**In GSC Coverage**:
- Click "Excluded"
- Select "Soft 404"

**What is Soft 404?**
Page loads with 200 status code (success) but content is error-like (example: "Page not found" message).

**Verify**:
1. Open the URL
2. Check if page shows actual content or error message
3. Right-click Inspect → Network tab → Check status code
4. Should show "200" but content looks broken

### Why It Happens

1. **Deleted page** — Content removed but URL still exists with "no content" message
2. **Broken page** — JavaScript error prevents content from rendering
3. **Dynamic content missing** — Product/page data didn't load from database

### Fix

**Option 1: Delete the page (recommended)**
- If page has no value, delete it
- Set up 301 redirect to related page (if any backlinks)
- Remove from sitemap

**Option 2: Restore the page**
- If it's a legitimate page, restore its content
- Make sure it loads fully (test in browser)
- Verify no JavaScript errors (DevTools Console)

**Option 3: Fix the issue**
- If dynamic content, check database connectivity
- If JavaScript error, fix JavaScript
- Test in incognito window to avoid cache issues

**After Fix**:
- Request indexing in GSC
- Monitor GSC Coverage to confirm "Valid" status

---

## Problem 5: Redirect Issues

### Diagnosis

**In GSC Coverage**:
- Click "Excluded"
- Select "Alternate page with proper redirect"

**What This Means**:
Page has redirect pointing to another URL. Google prefers to index final destination.

**Check Redirect**:
1. Use `redirect-checker.com`
2. Enter URL
3. Follow redirect path
4. Should be: Original URL → Final URL (1 hop)

### Why It Happens

1. **Old URL structure** — Old URL redirects to new structure
2. **Pagination redirects** — Old pagination URLs redirect to new format
3. **Mobile redirects** — Mobile version redirects to mobile domain

### Should You Worry?

Usually **NO**. Google will index final destination.

**When to Fix**: If redirect chain is 2+ hops:
```
url-a.com → url-b.com → url-c.com (BAD)
Should be:
url-a.com → url-c.com (GOOD)
```

### Fix Redirect Chains

1. Identify final destination URL
2. Update ALL redirects to point directly there
3. Remove intermediate redirects

---

## Problem 6: New Domains / Low Authority

### Diagnosis

**In GSC Coverage**:
- Click "Excluded"
- Select "Discovered - currently not indexed"

**What This Means**:
Google found the URL but hasn't indexed it yet. Common for new sites.

**Check GSC**:
- Look at "Crawl stats" over time
- If crawling rate is low = Google not interested yet

### Why It Happens

1. **Brand new domain** — Domain <3 months old; Google moves slowly
2. **Low authority** — Site has few backlinks; not priority for Google
3. **No sitemaps** — Google not aware of all pages
4. **Slow ranking** — Page not ranking enough to index

### Fix (Patience + Authority)

**Short term** (1-2 weeks):
1. Submit sitemap to GSC (or update existing)
2. Request indexing for important pages in GSC
3. Internally link to pages you want indexed

**Medium term** (1-3 months):
1. Build high-quality backlinks (1-2 links from authority sites)
2. Create regularly updated content (shows site is active)
3. Get brand mentions in relevant publications

**Long term** (3-6 months):
1. Accumulate more authority over time
2. Pages will naturally start indexing faster
3. Crawl rate increases as Google recognizes site value

**Reality**: New sites take time. Don't panic if some pages aren't indexed in first month.

---

## Problem 7: Access Issues

### Diagnosis

**In GSC Coverage**:
- Click "Errors"
- Look for: "Unavailable (429)", "Server error (5xx)", "Unauthorized (401/403)"

**Check Page**:
1. Try accessing page in incognito window
2. Check if page loads
3. Check HTTP status code (DevTools Network tab)

### Common Issues

**401/403 (Access Denied)**:
- Page requires login
- IP is blocked
- SSL certificate issue

**Solution**: Remove login requirement; allow public access

**5xx Server Errors**:
- Web server crashed or overloaded
- Database disconnected
- Memory limit exceeded

**Solution**: Contact hosting provider; restart server

**429 (Rate Limited)**:
- Google crawler hitting rate limits
- Too many requests too fast

**Solution**: Increase bandwidth on server; contact provider if continues

---

## Quick Reference: Which Issue Is It?

| Symptom | Likely Cause | Fix |
|---|---|---|
| Page shows "noindex" in meta tag | Accidental noindex | Remove noindex tag; request indexing |
| GSC shows "Blocked by robots.txt" | Robots.txt blocking | Update robots.txt; request indexing |
| Page canonical points elsewhere | Wrong canonical | Fix canonical to self-reference; request indexing |
| Page loads with 200 but shows error | Soft 404 | Delete page or restore content |
| Page URL with redirects | Redirect issue | Usually fine; consolidate chains if 2+ hops |
| Brand new site; pages not indexed | Low authority + new domain | Wait 1-3 months; build backlinks |
| Error code 401/403/5xx | Access issue | Fix server issue; retry crawl |

---

## Indexation Audit Checklist

- [ ] GSC Coverage: <5% error rate (acceptable)
- [ ] No legitimate pages with noindex tag
- [ ] Robots.txt not blocking important content
- [ ] Canonical tags point to page's own URL (self-referencing)
- [ ] Important pages indexed within 1 month of publishing
- [ ] No soft 404 pages
- [ ] Redirect chains max 1 hop
- [ ] Server responding with 200 status (not 429/5xx)

---

## Monitoring Indexation Health

### Weekly Check
1. Open GSC Coverage report
2. Note: Total indexed pages trend
3. Check: Any new errors appeared?

### Monthly Deep Dive
1. Check "Excluded" section for new soft 404s
2. Verify pages published 30 days ago are indexed
3. Check "Crawl stats" for trends

### Quarterly Audit
1. Review all error categories
2. Identify patterns (example: all pagination URLs not indexing)
3. Fix root cause rather than individual pages
