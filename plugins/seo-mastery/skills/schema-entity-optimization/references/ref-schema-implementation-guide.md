# Schema Implementation Guide -- Complete Reference

## THE 3-STEP AI-ASSISTED WORKFLOW (Gorrono)

### Step 1: Analyze Current State
1. Visit Google Rich Results Test (free): search.google.com/test/rich-results
2. Enter your page URL
3. Check what schema (if any) currently exists
4. Repeat for top 3-5 competitors to identify their schema strategy
5. Note which competitors have rich results you lack

### Step 2: Identify Schema Opportunities
Paste URL into ChatGPT 4o (with search enabled). Use this prompt:

"Analyze the link. Understand the page, the services provided, and tell me what are all the types of schema markup I can place on this page to improve searchability."

GPT identifies specific schema types. Example output for a financial advisor page:
- FinancialService (not just LocalBusiness)
- FAQPage (if page has questions)
- Person (for advisor bio)
- Review / AggregateRating (if testimonials exist)
- BreadcrumbList
- Article (if blog content)

### Step 3: Generate, Validate, and Deploy
1. Ask GPT: "Generate the complete JSON-LD schema markup for this page including [types identified]"
2. Review output for accuracy (hours, address, services, names)
3. Paste into schema.org validator -- fix any structural errors
4. Paste into Google Rich Results Test -- fix any rich result eligibility issues
5. Inject validated JSON-LD into page `<head>` section

---

## E-E-A-T SCHEMA PROPERTIES (Casey Keith)

### 1. `reviewedBy`
Indicates expert review of content.
```json
"reviewedBy": {
  "@type": "Person",
  "name": "Dr. Jane Smith",
  "jobTitle": "Board-Certified Dermatologist",
  "url": "https://yoursite.com/about/dr-jane-smith"
}
```

### 2. `citation`
Links to sources backing your claims.
```json
"citation": {
  "@type": "ScholarlyArticle",
  "name": "Study Title",
  "url": "https://pubmed.ncbi.nlm.nih.gov/12345"
}
```

### 3. `knowsAbout`
Declares author's areas of expertise.
```json
"knowsAbout": ["SEO", "Content Marketing", "Digital Strategy", "E-commerce"]
```

### 4. `hasCredential`
Certifications, degrees, licenses.
```json
"hasCredential": {
  "@type": "EducationalOccupationalCredential",
  "credentialCategory": "degree",
  "name": "MBA in Digital Marketing"
}
```

### 5. `ClaimReview`
Fact-checking markup that earns checkmark badge in SERPs.
```json
{
  "@type": "ClaimReview",
  "claimReviewed": "We make the best pizza in Brooklyn",
  "author": {"@type": "Organization", "name": "Your Business"},
  "reviewRating": {
    "@type": "Rating",
    "ratingValue": "5",
    "bestRating": "5"
  },
  "itemReviewed": {
    "@type": "Claim",
    "author": {"@type": "Person", "name": "John Customer"}
  }
}
```

**ClaimReview hack (Casey):** The cited source does not need to be a major publication. A Facebook post from a credible person technically qualifies.

### 6. `awards`
Industry recognition.
```json
"awards": ["Best SEO Agency 2025 - Search Engine Journal", "Top 10 Digital Marketers - Forbes"]
```

---

## PRODUCT SCHEMA FOR E-COMMERCE

### Mandatory Base Schema
```json
{
  "@type": "Product",
  "name": "Organic SPF 50 Mineral Sunscreen",
  "description": "Reef-safe mineral sunscreen with zinc oxide",
  "image": "https://yourstore.com/images/sunscreen.jpg",
  "brand": {"@type": "Brand", "name": "YourBrand"},
  "sku": "SUN-SPF50-ORG",
  "offers": {
    "@type": "Offer",
    "price": "29.99",
    "priceCurrency": "USD",
    "availability": "https://schema.org/InStock",
    "url": "https://yourstore.com/products/organic-sunscreen"
  }
}
```

### Competitive Advantage Fields
Add these for organic product grid visibility:

- `aggregateRating` -- star ratings in SERPs (highest CTR impact)
- `review` -- individual reviews
- `has-varying` / `product-varying` -- for products with variants (size, color)
- `shippingDetails` -- shipping cost and delivery estimates
- `hasMerchantReturnPolicy` -- return policy details
- `material`, `color`, `size` -- product attributes

### Product Title Naming Rule (brightonSEO)
Name products after attributes, NOT internal merch codes.
- Formula: [Key Attribute] + [Product Type]
- Good: "Organic Mineral SPF 50 Sunscreen Lotion"
- Bad: "SKU-2847-SUN" or "Summer Collection Item 3"

### Feed-to-Page Consistency
**Mandatory for organic product grid visibility.**
- Price on feed MUST match price on page
- If feed price is LOWER than page price = product disapproved
- Availability must match
- Quick check: compare valid items in Merchant Center vs product snippets in Search Console

---

## FAQ SCHEMA

### Implementation
```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "How often should I apply sunscreen?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Apply sunscreen every 2 hours, or after swimming or sweating."
      }
    },
    {
      "@type": "Question",
      "name": "Is mineral sunscreen safe for coral reefs?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes, mineral sunscreens using zinc oxide and titanium dioxide are reef-safe."
      }
    }
  ]
}
```

### Rules
- Only for genuine questions answered on the page
- Do not fabricate questions for schema alone
- FAQ dropdowns increase SERP real estate and CTR
- LLMs have a "weird preference" for FAQ sections (Surfer/Roman Leliukh) -- mirror key facts here

---

## LOCALBUSINESS SCHEMA HIERARCHY

Always use the most specific subtype:
- `LocalBusiness` (generic -- avoid if specific type exists)
- `FinancialService` (financial advisors, accountants)
- `LegalService` (law firms, attorneys)
- `MedicalBusiness` > `Dentist`, `Physician`, etc.
- `Restaurant` > `FastFoodRestaurant`, `CafeOrCoffeeShop`, etc.
- `HomeAndConstructionBusiness` > `Plumber`, `Electrician`, `RoofingContractor`
- `AutomotiveBusiness` > `AutoRepair`, `AutoDealer`

Check schema.org/LocalBusiness for full hierarchy.

---

## SCHEMA FOR AI SEARCH (brightonSEO)

### How the Orchestrator Layer Uses Schema
- LLMs do NOT directly process schema
- The orchestrator (fetches pages for LLM) DOES use schema as metadata
- Without schema: orchestrator guesses content type, cannot find author/date
- With schema: orchestrator grabs structured data, passes cleaner context

### Technical Requirements for AI Crawlers
- No JavaScript rendering required (AI bots do not execute JS)
- Server response time under 300ms
- Static pages preferred
- Duplicate key data as HTML tables alongside JS visualizations

### Timeliness and Schema
- Fast-moving products with purchase intent = LLM searches web (schema matters MORE)
- Slow-cycle enterprise = LLM relies on training data (schema matters less)
- Update `dateModified` in schema regularly to signal freshness

### llms.txt Impact
- llms.txt has NO measurable impact in current data (brightonSEO -- PromptWatch)
- Schema and structured data serve the same purpose more effectively
- Do not invest time in llms.txt over schema implementation

---

## BULK SCHEMA OPTIMIZATION (Gorrono)

### SEO Scraper GPT + Google Sheets
1. Custom Google Sheets tool scrapes any URL: title, meta description, H1, H2s, images, alt tags
2. Paired with GPT prompts for:
   - Schema Detector (identifies what schema a page currently has/needs)
   - Schema Generator (creates JSON-LD based on page content)
3. Process all site URLs in bulk through this pipeline
4. Export and implement across site

### Schema at Scale Best Practices
- Template schema by page type (all product pages share base schema)
- Use dynamic fields (price, availability, reviews) from CMS
- Validate a sample of 10-15 pages thoroughly before mass deployment
- Monitor Google Search Console for schema errors after deployment

---

## SCHEMA VALIDATION CHECKLIST

### Pre-Deployment
1. Schema.org validator: zero errors, zero warnings
2. Google Rich Results Test: eligible for rich results
3. All URLs are absolute (not relative)
4. All dates in ISO 8601 format
5. Prices match page content exactly
6. Names, addresses match business records
7. Images exist and are accessible

### Post-Deployment
1. Check Google Search Console > Enhancements for new errors
2. Wait 1-2 weeks for Google to recrawl
3. Search `site:yoursite.com` to check for rich result appearance
4. Compare before/after CTR in Search Console
5. Monitor Rich Results report for any warnings
