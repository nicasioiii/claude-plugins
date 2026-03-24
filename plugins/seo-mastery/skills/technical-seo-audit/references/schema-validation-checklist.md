# Schema Validation Checklist: Structured Data for Rankings

## What Is Schema Markup?
Code that tells Google what type of content a page contains (article, product, recipe, job, etc.)

## Why Schema Matters
1. **Rich snippets**: Schema can trigger special SERP features (star ratings, pricing, FAQs)
2. **AI search**: Schema helps AI models understand content
3. **Knowledge graphs**: Schema feeds entity data to knowledge panels

---

## Part 1: Common Schema Types & When to Use

### Article Schema (Blog Posts)
**Use When**: Blog articles, news posts, guides
**Rich Snippet**: Article snippet in SERP
**Required Fields**:
- headline
- image
- datePublished
- dateModified
- author
- description (optional but recommended)

**Example**:
```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "How to Train a Dog",
  "image": "https://example.com/image.jpg",
  "datePublished": "2024-01-15",
  "dateModified": "2024-03-11",
  "author": {
    "@type": "Person",
    "name": "John Doe"
  },
  "description": "Complete guide to training your dog"
}
```

### Product Schema (E-commerce)
**Use When**: Product pages on ecommerce sites
**Rich Snippet**: Product card with price, rating, availability
**Required Fields**:
- name
- image
- description
- offers (price, currency, availability)
- aggregateRating (if you have reviews)

**Example**:
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Blue Dog Bed",
  "image": "https://example.com/product.jpg",
  "description": "Comfortable orthopedic dog bed",
  "offers": {
    "@type": "Offer",
    "price": "49.99",
    "priceCurrency": "USD",
    "availability": "InStock"
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.5",
    "reviewCount": "120"
  }
}
```

### FAQ Schema (FAQ Pages)
**Use When**: Pages with Frequently Asked Questions section
**Rich Snippet**: Expandable FAQ snippets in SERP
**Required Fields**:
- mainEntity (array of questions)
- name (question text)
- acceptedAnswer (answer text)

**Example**:
```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "How often should I feed my dog?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Most adult dogs should be fed 1-2 times per day"
      }
    }
  ]
}
```

### LocalBusiness Schema (Local SEO)
**Use When**: Local business pages (offices, stores, service areas)
**Rich Snippet**: Business info card with address, phone, hours
**Required Fields**:
- name
- address (streetAddress, addressLocality, postalCode)
- telephone
- image
- url

**Example**:
```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "Dog Training Co",
  "telephone": "+1-555-123-4567",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Main St",
    "addressLocality": "San Francisco",
    "addressRegion": "CA",
    "postalCode": "94102"
  },
  "image": "https://example.com/image.jpg",
  "url": "https://example.com"
}
```

### Organization Schema (Homepage)
**Use When**: Homepage or about page
**Rich Snippet**: Organization info in knowledge panels
**Required Fields**:
- name
- logo
- url
- sameAs (social profiles)
- address (if physical location)
- telephone (if applicable)

---

## Part 2: How to Add Schema Markup

### Method 1: WordPress SEO Plugin (Easiest)
Use Yoast SEO or Rank Math:
1. Install plugin
2. Edit post
3. Go to plugin schema section
4. Select content type (Article, Product, etc.)
5. Fill in fields
6. Plugin generates JSON-LD automatically

### Method 2: Code Inspector / Schema Markup Generator
1. Visit `schema.org`
2. Find your schema type
3. Fill out required fields
4. Copy generated code
5. Add to page `<head>` as JSON-LD:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Title",
  ...
}
</script>
```

### Method 3: Google Structured Data Markup Helper
1. Go to `Google Structured Data Markup Helper`
2. Select schema type
3. Paste HTML of your page
4. Highlight and label content
5. Google generates JSON-LD
6. Copy/paste to page

---

## Part 3: Validation & Testing

### Google Rich Results Test
1. Visit `search.google.com/test/rich-results`
2. Paste URL or raw HTML
3. Google shows:
   - Validation errors
   - Warnings
   - Rich results preview

**Red flags**:
- "Missing required field X"
- "Invalid value for field Y"
- Schema valid but "No preview available"

### Schema.org Validator
1. Visit `validator.schema.org`
2. Paste raw HTML or URL
3. Shows validation errors
4. **Note**: Schema.org validator is more lenient than Google's test

### Testing Workflow

**Step 1: Validate Syntax**
- Paste in Google Rich Results Test
- Fix any errors until validation passes

**Step 2: Check Requirements**
- Google requires more fields than schema.org spec
- **Example**: Product schema requires image for rich snippets
- **Solution**: Add optional fields that Google expects

**Step 3: Preview Rich Results**
- Google test shows how snippet will appear in SERP
- Check if content looks correct
- If "No preview available" = Google can't show snippet (yet)

---

## Part 4: Common Schema Mistakes & Fixes

### Mistake 1: Missing Required Fields
**Error**: "Missing required property X"
**Example**: Product schema without "offers" (price)

**Fix**: Add all required fields:
```json
"offers": {
  "@type": "Offer",
  "price": "49.99",
  "priceCurrency": "USD"
}
```

### Mistake 2: Wrong Field Types
**Error**: Price as text instead of number
**Bad**: `"price": "$49.99"`
**Good**: `"price": "49.99"` (number, not currency symbol)

### Mistake 3: Outdated dateModified
**Problem**: dateModified older than datePublished (impossible)
**Fix**: Ensure dateModified >= datePublished

### Mistake 4: Image URLs Missing
**Problem**: Product/Article schema without images
**Impact**: No rich snippets displayed
**Fix**: Add image URL:
```json
"image": "https://example.com/image.jpg"
```

### Mistake 5: Invalid URL Format
**Problem**: Relative URLs instead of absolute
**Bad**: `/blog/article/`
**Good**: `https://example.com/blog/article/`

### Mistake 6: Multiple Schema Types Conflicting
**Problem**: Page has Article schema but also Product schema (confuses Google)
**Fix**: Use only one primary schema per page
**Exception**: Can nest types (Example: Article containing FAQPage)

---

## Part 5: Priority Schema Implementation

### Tier 1: Do First (Biggest Impact)
1. **Article schema** on blog posts
2. **Product schema** on product pages
3. **Organization schema** on homepage
4. **LocalBusiness schema** if local business

### Tier 2: Add Next (Medium Impact)
1. **FAQ schema** on FAQ pages
2. **BreadcrumbList** for navigation
3. **Review/AggregateRating** if applicable

### Tier 3: Advanced (Lower Priority)
1. **Video schema** if video content
2. **Event schema** if events
3. **JobPosting schema** if hiring

---

## Part 6: Schema Audit Workflow (30 minutes)

### Step 1: Identify Key Pages
List 5-10 most important pages:
- Homepage
- Top 3 blog posts
- Top 2 product pages
- FAQ page (if exists)
- About page

### Step 2: Test Each Page
For each page:
1. Copy URL
2. Open Google Rich Results Test
3. Note errors/warnings
4. Screenshot preview

### Step 3: Document Findings
Create audit report:

| Page | Content Type | Schema Present? | Errors | Impact |
|---|---|---|---|---|
| Homepage | Organization | ✓ Yes | None | Knowledge panel eligible |
| Blog post | Article | ✓ Yes | Missing dateModified | Can add freshness signal |
| Product page | Product | ✗ No | N/A | No rich snippets (HIGH PRIORITY) |

### Step 4: Prioritize Fixes
Fix in order:
1. Missing schemas on important pages
2. Errors on existing schemas
3. Optimization (add optional fields)

---

## Part 7: Real-World Implementation Examples

### Example 1: Blog Post Article Schema (Yoast)
1. Open blog post editor
2. Scroll to Yoast SEO section
3. Look for "Schema" tab
4. Select "Article"
5. Fill in:
   - Headline (auto-filled from post title)
   - Image (upload featured image)
   - Author (auto-filled)
   - Publication date (auto-filled)
6. Save post

### Example 2: Product Page Schema (WooCommerce)
1. Edit product
2. Fill product data normally:
   - Name
   - Price
   - Image
   - Description
3. WooCommerce automatically generates Product schema
4. No manual schema needed

### Example 3: Homepage Organization Schema (Manual)
1. Edit homepage
2. Go to page source
3. Add to `<head>`:
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Your Business",
  "logo": "https://example.com/logo.png",
  "url": "https://example.com",
  "telephone": "+1-555-123-4567",
  "sameAs": ["https://facebook.com/yourbusiness", "https://twitter.com/yourbusiness"]
}
</script>
```
4. Save

---

## Schema Implementation Checklist

- [ ] Homepage has Organization schema
- [ ] All blog posts have Article schema
- [ ] All product pages have Product schema
- [ ] FAQ pages have FAQPage schema
- [ ] Local pages have LocalBusiness schema
- [ ] All schemas pass Google Rich Results Test
- [ ] No validation errors
- [ ] All required fields present
- [ ] Images included in schemas
- [ ] dateModified correct on articles
- [ ] Prices formatted correctly (numbers, no $)
- [ ] URLs are absolute (https://example.com/page, not /page)

---

## Monitoring Schema Health

### Weekly Check
1. Pick random page
2. Test in Google Rich Results Test
3. Verify schema still validates

### Monthly Audit
1. Retest top 10 pages
2. Check for new errors
3. Monitor if rich snippets appearing in SERP

### Quarterly Deep Dive
1. Full site schema audit
2. Identify missing opportunities
3. Plan next schema additions

---

## Key Takeaway
Schema doesn't directly rank pages, but it enables rich snippets which increase CTR. Better CTR + better user experience = ranking improvements. Plus, it helps AI search engines understand your content.
