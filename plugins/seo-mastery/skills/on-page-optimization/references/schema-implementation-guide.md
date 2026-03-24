# Schema Implementation Guide

Master JSON-LD schema markup to enable rich snippets, improve CTR from search results, and signal E-E-A-T to Google.

## What Is Schema Markup?

**Simple Definition**: Structured data that tells Google exactly what information is on your page.

**Analogy**: Without schema, Google sees "The Bread Guide | Best Recipes". With schema, Google sees:
- This is an article
- Published by: The Bread Guide
- Topic: Sourdough Bread Recipes
- Author: John Smith
- Published date: 2024-03-11
- Word count: 2,500

**Format Used**: JSON-LD (JavaScript Object Notation for Linked Data)
- Human-readable, easy to read and write
- Placed in `<script>` tag in page head or body
- Google's preferred format (will read dynamically injected)

## Why Schema Matters for SEO

**Ranking Factor**: Indirect - Google uses schema to understand content, doesn't directly boost rankings

**SERP Appearance**: Major - Rich snippets (stars, price, availability) appear ONLY with schema

**Click-Through Rate**: Major - Rich snippets increase CTR 20-30% vs plain links

**AI Overviews**: Critical - Google AI Overviews use schema data for context

**E-E-A-T Signals**: Important - Author, credentials, review schema enhance trustworthiness

## Schema Validation Tools

**Google Rich Results Validator**: https://search.google.com/test/rich-results
- Tests what Google will actually display
- Shows errors (must fix) vs warnings (nice to fix)
- Tests live pages (production only, not staging)

**Schema.org Validator**: https://validator.schema.org/
- Tests if schema is valid JSON-LD
- Shows syntax errors
- Different requirements than Google (Google is stricter)

**Semantic Spider Browser Extension**: Analyze competitor schema markup

**Important Distinction**: Schema.org validator may approve code that Google won't display rich snippets for. Always test with Google's tool.

## Core Schema Types for SEO

### 1. Article Schema (Blog Posts)

**When to Use**: Any blog post, news article, or written content

**What It Displays**: Title, publish date, author, featured image in search results

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "{{PAGE_TITLE}}",
  "description": "{{META_DESCRIPTION}}",
  "image": [
    "{{FEATURED_IMAGE_URL}}"
  ],
  "datePublished": "{{PUBLISH_DATE_YYYY-MM-DD}}",
  "dateModified": "{{LAST_UPDATED_DATE_YYYY-MM-DD}}",
  "author": {
    "@type": "Person",
    "name": "{{AUTHOR_NAME}}",
    "url": "{{AUTHOR_PROFILE_URL}}"
  },
  "publisher": {
    "@type": "Organization",
    "name": "{{BUSINESS_NAME}}",
    "logo": {
      "@type": "ImageObject",
      "url": "{{LOGO_URL}}"
    }
  },
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "{{PAGE_URL}}"
  }
}
```

**Required Fields**: headline, image, datePublished, author, publisher, mainEntityOfPage

**Best Practices**:
- Use actual publish/update dates (not fixed dates)
- Author should link to profile page or bio
- Image should be at least 1200x630px
- Test with Google Rich Results Validator

### 2. Organization Schema (Homepage)

**When to Use**: Every homepage should have this

**What It Displays**: Business name, logo, contact info in knowledge panel

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "@id": "{{WEBSITE_URL}}",
  "name": "{{BUSINESS_NAME}}",
  "url": "{{WEBSITE_URL}}",
  "logo": "{{LOGO_URL}}",
  "description": "{{BUSINESS_DESCRIPTION}}",
  "telephone": "{{PHONE_NUMBER}}",
  "email": "{{EMAIL_ADDRESS}}",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "{{STREET_ADDRESS}}",
    "addressLocality": "{{CITY}}",
    "addressRegion": "{{STATE}}",
    "postalCode": "{{ZIP_CODE}}",
    "addressCountry": "{{COUNTRY_CODE}}"
  },
  "sameAs": [
    "{{FACEBOOK_URL}}",
    "{{TWITTER_URL}}",
    "{{LINKEDIN_URL}}"
  ]
}
```

**Required Fields**: name, url, logo

**Pro Tip**: sameAs links should point to official social media pages, Wikipedia, or other authoritative profiles

### 3. LocalBusiness Schema (Location Pages)

**When to Use**: Service businesses with physical locations

**What It Displays**: Business name, address, phone, hours, map link

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "@id": "{{WEBSITE_URL}}",
  "name": "{{BUSINESS_NAME}}",
  "url": "{{WEBSITE_URL}}",
  "telephone": "{{PHONE_NUMBER}}",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "{{STREET_ADDRESS}}",
    "addressLocality": "{{CITY}}",
    "addressRegion": "{{STATE}}",
    "postalCode": "{{ZIP_CODE}}"
  },
  "image": "{{BUSINESS_IMAGE_URL}}",
  "openingHoursSpecification": {
    "@type": "OpeningHoursSpecification",
    "dayOfWeek": "Monday",
    "opens": "09:00",
    "closes": "17:00"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "{{LATITUDE}}",
    "longitude": "{{LONGITUDE}}"
  }
}
```

**Required Fields**: name, address, telephone

**For Multiple Locations**: Create separate schema for each location page (not one global schema)

### 4. Product Schema (E-Commerce)

**When to Use**: Product pages with price and availability

**What It Displays**: Product image, price, availability, rating

```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "{{PRODUCT_NAME}}",
  "description": "{{PRODUCT_DESCRIPTION}}",
  "image": "{{PRODUCT_IMAGE_URL}}",
  "brand": {
    "@type": "Brand",
    "name": "{{BRAND_NAME}}"
  },
  "offers": {
    "@type": "Offer",
    "url": "{{PRODUCT_PAGE_URL}}",
    "priceCurrency": "USD",
    "price": "{{PRICE}}",
    "availability": "https://schema.org/InStock",
    "seller": {
      "@type": "Organization",
      "name": "{{STORE_NAME}}"
    }
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "{{AVERAGE_RATING}}",
    "ratingCount": "{{NUMBER_OF_REVIEWS}}"
  }
}
```

**Required for Rich Snippet**: name, image, offers (with price, priceCurrency, availability), brand

**Availability Options**: InStock, OutOfStock, PreOrder

**Important**: Image must be at least 300x300px (Google requirement, not schema.org requirement)

### 5. FAQ Schema (FAQ Pages/Sections)

**When to Use**: Any page with FAQ section

**What It Displays**: FAQ in featured snippet format

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "{{QUESTION_1}}",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "{{ANSWER_1}}"
      }
    },
    {
      "@type": "Question",
      "name": "{{QUESTION_2}}",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "{{ANSWER_2}}"
      }
    }
  ]
}
```

**When Google Displays FAQ Schema**: Search results show FAQ questions, user can click to expand answers

**Requirements**:
- Each question must have a visible on-page corresponding answer
- Answers must be actual text (not images or videos)
- Minimum 2 Q&A pairs (though 1 acceptable)

**Pro Tip**: Use for actual FAQ sections users see on page, not hidden schema

### 6. BreadcrumbList Schema (Navigation)

**When to Use**: Any site with hierarchical navigation

**What It Displays**: Breadcrumb trail in search results

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "https://example.com/"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "Natural Skincare",
      "item": "https://example.com/natural-skincare/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "Sunscreen",
      "item": "https://example.com/sunscreen/"
    }
  ]
}
```

**Benefits**: Shows site structure in SERP, helps users navigate

### 7. Service Schema (Service Businesses)

**When to Use**: Service-based businesses (plumbing, consulting, etc.)

**What It Displays**: Service description, price range, service area

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "serviceType": "{{SERVICE_NAME}}",
  "provider": {
    "@type": "LocalBusiness",
    "name": "{{BUSINESS_NAME}}",
    "telephone": "{{PHONE}}"
  },
  "areaServed": {
    "@type": "State",
    "name": "{{SERVICE_AREA}}"
  },
  "priceRange": "{{PRICE_RANGE_EXAMPLE}}",
  "offers": {
    "@type": "Offer",
    "url": "{{SERVICE_PAGE_URL}}"
  }
}
```

**Example Service Types**: Plumbing, SEO Consulting, Web Design, HVAC Repair

## Implementation Workflow

### Step 1: Audit Current Schema

**Tools**:
- Google Rich Results Validator (test production pages)
- Google Search Console > Search Results > Rich Results status
- Screaming Frog (crawl site, identify pages with/without schema)

**Questions to Ask**:
- Which pages have schema? Which don't?
- Are there errors or warnings?
- Are rich snippets displaying for your pages?
- What schema types does your competitor use?

### Step 2: Identify What Schema You Need

**By Page Type**:
- Homepage: Organization schema (required)
- Blog posts: Article schema + Organization schema (nest org inside article)
- FAQ page: FAQPage schema
- Product pages: Product schema + Organization schema
- Service pages: Service schema + LocalBusiness schema
- Local pages: LocalBusiness schema + Organization schema
- All pages: BreadcrumbList schema (optional but recommended)

### Step 3: Generate or Write Schema

**Option A: ChatGPT/Claude**
```
Prompt: "Generate Article schema for this blog post:
Title: {{TITLE}}
URL: {{URL}}
Publish Date: {{DATE}}
Author: {{AUTHOR}}
Featured Image: {{IMAGE_URL}}

Output as JSON-LD in code format only."
```

**Option B: Schema Generator Tools**
- SchemeLauncher.com
- JSON-LD.org validator + generator
- Yoast SEO (generates automatically)

**Option C: Manual Copy-Paste**
- Use templates above
- Replace {{VARIABLES}} with your actual data

### Step 4: Validate Schema

1. Copy generated schema JSON
2. Go to Google Rich Results Validator
3. Paste in code
4. Fix any errors (red = errors, yellow = warnings)
5. Check "Preview" to see how rich snippet displays

**Common Errors**:
- Missing required fields
- Invalid date format (must be YYYY-MM-DD)
- Image URL broken
- Incorrect schema type for content

### Step 5: Implement on Website

**WordPress**:
- Use Yoast SEO / Rank Math (auto-generate)
- Manual: Add to `<head>` section via plugin or theme editor
- Best: Let plugins handle it (simpler, auto-updated)

**Shopify**:
- Yoast Shopify app or built-in Shopify settings
- Most themes support schema automatically
- Check theme docs

**Custom Sites**:
- Add `<script type="application/ld+json">` in `<head>` section
- Developer adds to site template
- Ensure consistent placement

**Implementation Example - HTML**:
```html
<head>
  <title>Best Natural Sunscreen Guide</title>
  <meta name="description" content="...">

  <!-- Schema Markup -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "Article",
    "headline": "Best Natural Sunscreen Guide",
    ...
  }
  </script>
</head>
```

### Step 6: Monitor & Verify

**After Publishing** (24-48 hours):
1. Go to Google Rich Results Validator
2. Test your page URL (production only)
3. Confirm schema detected and no errors
4. Check Google Search Console → Rich Results status
5. Wait 1-2 weeks for rich snippets to appear in SERPs

## E-E-A-T Signals Through Schema

### Author Credentials

```json
"author": {
  "@type": "Person",
  "name": "{{AUTHOR_NAME}}",
  "url": "{{AUTHOR_PROFILE_URL}}",
  "knowsAbout": ["{{EXPERTISE_1}}", "{{EXPERTISE_2}}"],
  "jobTitle": "{{TITLE}}",
  "hasCredential": {
    "@type": "EducationalOccupationalCredential",
    "name": "{{CERTIFICATION_NAME}}"
  }
}
```

### ReviewedBy (Third-Party Verification)

```json
"reviewedBy": {
  "@type": "Organization",
  "name": "{{REVIEW_BODY_NAME}}",
  "url": "{{REVIEW_BODY_URL}}"
}
```

### Aggregate Rating (Trust Signal)

```json
"aggregateRating": {
  "@type": "AggregateRating",
  "ratingValue": "4.8",
  "ratingCount": "247",
  "bestRating": "5",
  "worstRating": "1"
}
```

## Common Implementation Mistakes

**Mistake 1: Using Incorrect Data**
```
❌ WRONG: Price field has "$49.99 (on sale)"
✓ CORRECT: Price field = "49.99" (number only), separate note for sale

❌ WRONG: Rating "4.8 out of 5 stars"
✓ CORRECT: ratingValue = "4.8", bestRating = "5"
```

**Mistake 2: Missing Required Fields**
```
❌ WRONG: Article schema without image (Google won't display rich snippet)
✓ CORRECT: Include all required fields for that schema type
```

**Mistake 3: Hardcoded Dates**
```
❌ WRONG: datePublished always "2024-01-01"
✓ CORRECT: Use actual publish date, update dateModified when you edit
```

**Mistake 4: Hiding Schema Content from Users**
```
❌ WRONG: Schema says different info than visible page content
✓ CORRECT: Schema mirrors what users actually see on page
```

**Mistake 5: Not Testing with Google Tool**
```
❌ WRONG: Only using Schema.org validator
✓ CORRECT: Test with Google Rich Results Validator (Google's actual requirements)
```

## Schema Implementation Checklist

- [ ] Homepage has Organization schema
- [ ] All blog posts have Article schema
- [ ] All product pages have Product schema (if applicable)
- [ ] All service pages have Service schema (if applicable)
- [ ] FAQ pages have FAQPage schema
- [ ] All pages with location have LocalBusiness schema (if applicable)
- [ ] All schema validated in Google Rich Results Validator
- [ ] No errors (warnings are acceptable)
- [ ] All required fields completed (no empty {{VARIABLES}})
- [ ] Image URLs are correct and images load
- [ ] Dates in YYYY-MM-DD format
- [ ] Author names and URLs are accurate
- [ ] Schema reflects actual page content
- [ ] Rich snippets appearing in Google Search Console after 1-2 weeks
- [ ] Test pages on mobile + desktop

## Expected Outcomes

- **CTR Improvement**: 20-30% increase from rich snippets in SERPs
- **Ranking Lift**: Indirect (0-1 position) from improved CTR signals
- **Visibility**: Eligibility for featured snippets, knowledge panels, AI Overviews
- **Trust**: Enhanced E-E-A-T signals with author/review schema
- **Implementation Time**: 1-2 hours for 5-10 pages, faster with automation tools

## Tools for Schema Management

- **Yoast SEO / Rank Math** - Auto-generate and manage schema (WordPress)
- **Google Rich Results Validator** - Test implementation
- **Schema.org Validator** - Syntax checking
- **Screaming Frog** - Audit schema across entire site
- **Ahrefs** - See what schema competitors use
- **ChatGPT/Claude** - Generate custom schema
