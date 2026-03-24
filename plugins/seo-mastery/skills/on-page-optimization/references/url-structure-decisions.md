# URL Structure Decisions

Master URL optimization and structure decisions to maximize keyword signals and prevent common URL mistakes.

## Why URLs Matter for SEO

**Ranking Factor**: Yes (Tier 1) - Keywords in URL are weighted heavily
**User Signal**: Yes - Users make click decisions based on URL keywords visible in SERP
**Crawlability**: Yes - Clear URL structure helps Google understand site hierarchy
**Brand Recognition**: Yes - Readable URLs are more shareable and memorable

## URL Component Structure

```
https://example.com/category/blog-post-title/
        ↑              ↑       ↑
    Protocol       Domain    Path (slug)
```

**You Can Control**: Domain, path/folder names, page slug
**You Cannot Control**: Protocol (use HTTPS), domain after purchase

## Domain Name Selection

### Good Domain Characteristics

**Option 1: Exact Match Domain (EMD)** ⭐⭐⭐⭐
- Contains primary keyword
- Example: "natural-sunscreen.com" for sunscreen site
- Pros: Strong keyword signal, memorable
- Cons: Fewer good EMDs available, may be expensive

**Option 2: Branded Domain** ⭐⭐⭐⭐⭐
- Your brand name
- Example: "skincare-pro.com"
- Pros: Build brand authority, flexible niche pivoting
- Cons: No keyword signal in domain, more SEO work needed

**Option 3: Partial Match Domain** ⭐⭐⭐
- Contains partial keyword
- Example: "pro-sunscreen.com" for sunscreen
- Pros: Balance keyword + brand
- Cons: Keyword signal not as strong as EMD

### Domain Mistakes to Avoid

```
❌ Hyphens make it harder: sun-screen-hq.com
✓ Better: sunscreenhq.com (if available)

❌ Numbers confuse users: sunscreen4you.com (is that "for" or "4"?)
✓ Better: sunscreenforyou.com (spells out words)

❌ Too long: bestnatural-organic-reef-safe-sunscreen-brand.com
✓ Better: naturalreef.com (concise, memorable)

❌ Hard to pronounce: snscrn.com
✓ Better: Clear, pronounceable domain
```

## Path/Folder Structure

### Flat vs Nested Hierarchy

**Flat Structure** (All in one folder):
```
/blog-post-1/
/blog-post-2/
/product-1/
/product-2/
```
Pros: Simple, easy to manage
Cons: Messy, hard to organize at scale

**Nested Structure** (Organized by category):
```
/blog/topic-1/post-title/
/blog/topic-2/post-title/
/products/category-1/product-name/
/products/category-2/product-name/
```
Pros: Organized, reflects site structure
Cons: Deeper URLs (slightly weaker)

**Best Practice**: Light nesting (1-2 levels max)
```
✓ Good: /blog/sunscreen-guide/
✓ Good: /products/sunscreen/natural-reef-safe/
❌ Bad: /blog/skincare/sun-protection/beach-use/natural-options/
```

### Folder Naming

**Apply Same Rules as Slug**:
- Include relevant keywords
- Use hyphens (not underscores)
- Lowercase only
- Concise

**Examples**:
```
✓ /blog/ (main blog folder)
✓ /blog/sunscreen-guides/ (topic folder)
✓ /products/skincare/ (category folder)

❌ /blogposts/ (unclear)
❌ /sun_screen/ (underscore not hyphen)
❌ /BLOG/ (uppercase)
```

## Page Slug Optimization

### Slug Basics

**Definition**: The part of URL after domain and folder

```
https://example.com/blog/best-sunscreen-for-sensitive-skin/
                              ↑ This is the slug
```

**Critical Rule**: Change slug BEFORE publishing (changing after breaks SEO + all links)

### Slug Best Practices

**Include Target Keyword**:
- Primary keyword should appear in slug
- Front-load keyword (put it first or early)
- Exact match preferred but variations okay

```
✓ "best-sunscreen-for-sensitive-skin" (contains all keywords)
✓ "natural-sunscreen-guide" (contains primary keywords)
✓ "sunscreen-reef-safe" (keyword forward, concise)

❌ "article-123" (no keyword)
❌ "page-about-sunscreen-things" (weak)
```

**Length**: 3-5 words typical
```
❌ Too long (30+ characters): "the-ultimate-complete-guide-to-choosing-best-sunscreen-for-sensitive-skin-protection"

✓ Concise (20-50 characters): "best-sunscreen-for-sensitive-skin"

❌ Too short: "sunscreen" (too broad, multiple meanings)
✓ Better: "sunscreen-sensitive-skin" (specific intent)
```

**Format Rules**:
- **Hyphens Only** (not underscores, no spaces)
- **Lowercase** (URLs are case-sensitive; use lowercase)
- **No Special Characters** (no @, #, !, ?, etc.)
- **No Dates** (avoid "/2024/sunscreen" - breaks if updated)

### Slug Formula by Content Type

**Blog Post**:
```
[Primary Keyword] + [Modifier]

"how-to-choose-sunscreen" (how-to angle)
"best-sunscreen-2024" (best/comparison angle)
"sunscreen-for-sensitive-skin" (modifier angle)
```

**Product/E-Commerce**:
```
[Product Name] + [Variant/Modifier]

"sunscreen-spf30-reef-safe" (specific product)
"natural-moisturizer-all-skin-types" (universal version)
"dog-food-sensitive-stomach" (variant)
```

**Category/Collection**:
```
[Category Name] [Optional Qualifier]

"natural-skincare" (main category)
"organic-sunscreen-products" (specific category)
```

**Service Page**:
```
[Service Name] + [Location or Focus]

"web-design-services" (service type)
"seo-services-startup" (service + audience)
"plumbing-austin" (service + location)
```

### Slug Mistakes

**Mistake 1: Keyword Stuffing**
```
❌ "best-natural-sunscreen-reef-safe-organic-chemical-free-sunscreen"

✓ "best-natural-reef-safe-sunscreen" (clean, keyword-rich)
```

**Mistake 2: Changing Slug After Publishing**
```
❌ Publish at /sunscreen-guide/, later change to /best-sunscreen-guide/
Result: Old URL broken, backlinks point to broken page, rankings drop

✓ Plan slug carefully BEFORE publishing
✓ If must change: Set up 301 redirect from old to new
```

**Mistake 3: Using Underscores Instead of Hyphens**
```
❌ "best_sunscreen_for_sensitive_skin"
Google reads as: "bestscreenscreenskin" (treats underscore as no separator)

✓ "best-sunscreen-for-sensitive-skin"
Google reads as: "best" "sunscreen" "for" "sensitive" "skin"
```

**Mistake 4: Including Year in URL**
```
❌ "/best-sunscreen-2024/"
Problem: When you update in 2025, URL becomes outdated

✓ "/best-sunscreen/" (timeless)
Or: Update all content in 2025, keep URL same
```

**Mistake 5: Inconsistent Formatting**
```
❌ Some URLs capitalized, some lowercase
❌ Some use hyphens, some underscores

✓ Consistent format across entire site
✓ All lowercase, all hyphens
```

## Canonicalization & URL Consolidation

### What Are Duplicate URLs?

**Scenario 1: Parameter Duplicates**
```
https://example.com/sunscreen (actual page)
https://example.com/sunscreen?utm_source=facebook (tracking parameter)
https://example.com/sunscreen?sort=price (sorting variant)

Result: Google sees 3 different URLs, dilutes ranking power
```

**Scenario 2: Protocol/WWW Duplicates**
```
http://example.com/sunscreen (HTTP)
https://example.com/sunscreen (HTTPS)
http://www.example.com/sunscreen (WWW)
https://www.example.com/sunscreen (HTTPS + WWW)

Result: Google confused about canonical version
```

**Scenario 3: Multiple Slugs Same Content**
```
/best-sunscreen/ (original)
/sunscreen-buying-guide/ (renamed, but didn't set up redirect)
Both indexed separately
```

### Canonical Tags

**Purpose**: Tell Google which version is the "real" one

**When to Use**:
- Site serves same content at multiple URLs
- Tracking parameters create URL variations
- Mobile vs desktop versions

**HTML Implementation**:
```html
<head>
  <link rel="canonical" href="https://example.com/best-sunscreen/">
</head>
```

**Best Practices**:
- Point to HTTPS version (not HTTP)
- Point to non-WWW or WWW consistently (pick one)
- Point to URL without tracking parameters
- Point to original URL (not a subdomain version)

### URL Parameter Handling

**Handling Tracking Parameters**:
```
Use: https://example.com/sunscreen/?utm_source=fb
BUT set canonical to: https://example.com/sunscreen/

Google ignores parameters, follows canonical
```

**In Google Search Console**:
- Go to Settings > URL Parameters
- Tell Google to ignore utm_*, session, affiliate params
- Result: Google treats all variations as same URL

## HTTPS & Security

### HTTPS Requirement

**Status**: Effectively required (Google ranks HTTPS sites higher)

**Impact**: Slight ranking boost (1% of ranking signals)

**How to Implement**:
- Contact hosting provider (most offer free SSL now)
- Modern hosting includes automatic HTTPS
- Costs: Free (Let's Encrypt) or included in hosting

**SSL Certificate Types**:
- **Free**: Let's Encrypt (sufficient for blogs/ecommerce)
- **Paid**: EV (Extended Validation) - shows company verified (not necessary)

### HTTP to HTTPS Migration

If switching from HTTP:

1. **Get SSL Certificate** (from hosting provider)
2. **Set Up 301 Redirects** (HTTP → HTTPS)
   ```
   http://example.com/page → https://example.com/page
   ```
3. **Update Google Search Console** to HTTPS property
4. **Update Internal Links** to use HTTPS
5. **Test** all pages load correctly

## Subdomain vs Subfolder Strategy

### Subdomains
```
blog.example.com
shop.example.com
help.example.com
```

**Pros**: Separate management, clear organization
**Cons**: Doesn't pass authority (Google treats as separate domain), more complex

**When to Use**: Rarely. Only if truly different domain (like Shopify multivendor)

### Subfolders (Better)
```
example.com/blog/
example.com/shop/
example.com/help/
```

**Pros**: Passes authority, simpler setup, clearer hierarchy
**Cons**: Slightly more complex content organization

**Best Practice**: Use subfolders, not subdomains

**Common Mistake**: Using blog subdomain when subfolder would be better
```
❌ blog.example.com (separate domain, loses homepage authority)
✓ example.com/blog/ (same domain, inherits authority)
```

## URL Length & Readability

### Length Limits

**Soft Limit**: 75 characters
- URLs visible in SERP up to ~75 characters
- Anything beyond is truncated "..."

**Hard Limit**: 2000+ characters (URL still works)
- Not a practical limit for normal sites

**Target**: Keep under 75 characters
```
✓ https://example.com/best-sunscreen-sensitive-skin/ (62 characters)
✓ https://example.com/blog/natural-skincare/ (41 characters)

❌ https://example.com/blog/skincare/guides/sunscreen/reef-safe-products-sensitive-skin/ (89 characters - truncates)
```

### Readability in SERP

Users see URLs in search results. Readable URLs get more clicks:

```
✓ READABLE:
https://example.com/best-sunscreen-sensitive-skin/

❌ NOT READABLE:
https://example.com/product?id=12345&cat=skincare&var=1
```

## URL Change Management

### Best Practice: Never Change URLs After Publishing

**If You Must**:
1. Set up 301 redirect (old URL → new URL)
2. Update internal links to new URL
3. Update Google Search Console
4. Wait 3-6 months (Google processes change)
5. Monitor for ranking changes

### Redirect Chaining (Avoid)

```
❌ Bad practice:
/old-url → /newer-url → /newest-url → /final-url
(4 hops, loses authority)

✓ Good practice:
/old-url → /final-url (direct redirect)
/newer-url → /final-url (direct redirect)
```

## URL Structure Checklist

- [ ] Primary keyword appears in slug
- [ ] All URLs use HTTPS (not HTTP)
- [ ] All URLs lowercase (no capitals)
- [ ] All URLs use hyphens (not underscores)
- [ ] No special characters or spaces
- [ ] URLs under 75 characters
- [ ] No trailing parameters (utm, ?ref=)
- [ ] Canonical tags set (if duplicates exist)
- [ ] Consistent folder structure (not random)
- [ ] No URLs with dates (unless necessary)
- [ ] Subfolders used instead of subdomains
- [ ] 301 redirects in place for old URLs
- [ ] WWW vs non-WWW consistent (pick one, redirect other)
- [ ] No keyword stuffing in slugs
- [ ] Slugs are concise and descriptive

## Tools for URL Analysis

- **Google Search Console** - Monitor URL changes, set canonical
- **Screaming Frog** - Crawl site, identify duplicate/broken URLs
- **Ahrefs** - Analyze competitor URL structures
- **SEMrush** - Site audit for URL issues
- **MozBar** - Quick URL structure analysis

## Expected Outcomes

- **Ranking Improvement**: 1-2 positions from keyword signals in URL
- **CTR Improvement**: 5-10% from readable, keyword-rich URLs
- **Crawl Efficiency**: Better indexation from clear hierarchy
- **Time Investment**: 30 minutes to audit, 15-30 minutes to plan new structure, implement on new content
