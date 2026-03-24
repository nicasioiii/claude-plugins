# Location Page Templates: Complete Architecture & Content Formulas

**Length:** ~400 lines
**Purpose:** Ready-to-use templates for location pages + structural examples

---

## Part 1: When Location Pages Work (& When They Don't)

### Location Pages Rank When:
- Service-based business (not transactional)
- Geographic expansion target (multiple cities)
- Consistent search volume per location (50+ monthly searches minimum)
- Distinct content angles per location (client base, competitor landscape, local pain points differ)

### Don't Build Location Pages If:
- Single location business (invest in GBP instead)
- Low volume per location (<20 monthly searches)
- Pure e-commerce (inventory not location-specific)
- All content identical per location (Google penalizes thin content)

---

## Part 2: URL Structure Decision Matrix

Choose ONE structure and commit (switching later breaks indexation).

### Structure A: Flat Hierarchy (Recommended for Beginners)

**URL Pattern:** `/[city]-[service]`

**Examples:**
- `/madison-carpet-cleaning`
- `/austin-personal-injury-attorney`
- `/denver-tax-preparation`

**Pros:**
- Simple to implement
- Flat structure = easy crawlability
- City pages don't compete for authority
- Fast to scale (no nested directories)

**Cons:**
- Longer URL slugs
- Harder to organize semantically (can't group cities by state)
- State-level pages harder to create

**Best for:** 10-50 location pages per region

**On-page implementation:**
```
Folder structure: /locations/ (optional subfolder)
URL: /locations/madison-carpet-cleaning
OR /madison-carpet-cleaning
```

### Structure B: Hierarchical (Recommended for Scale)

**URL Pattern:** `/[state]/[city]/[service]`

**Examples:**
- `/wisconsin/madison/carpet-cleaning`
- `/texas/austin/personal-injury-attorney`
- `/colorado/denver/tax-preparation`

**Pros:**
- Semantic grouping (state pages parent all city pages)
- State pages can aggregate cities
- Easy to add breadcrumb navigation
- Google understands geographic hierarchy

**Cons:**
- Longer URLs
- More nested structure = crawl depth increases
- Requires more internal linking strategy

**Best for:** 50+ locations across multiple states

**On-page implementation:**
```
Folder structure: /locations/wisconsin/madison/
URL: /locations/wisconsin/madison/carpet-cleaning/
```

### Structure C: Pillar + Sections (For Giant Sites)

**URL Pattern:** `/[state]-locations` with H2 sections per city

**Examples:**
- `/wisconsin-store-locations` (single page with all WI cities)
- `/texas-service-areas` (all TX cities in one page)

**Pros:**
- Authority concentration (single page ranks for multiple cities)
- SEO-efficient (one page, not 50)
- Easy navigation (table of contents)
- Reduces duplicate content risk

**Cons:**
- Page becomes massive (5,000+ words)
- Mobile experience suffers
- Each city doesn't get unique URL
- Limited by page length

**Best for:** 10-20 locations in single state

**On-page implementation:**
```
URL: /locations/wisconsin-store-locations
H1: "Goodwill Bins in Wisconsin"
H2s: Austin, Dallas, Houston, etc. (internal anchor links)
Each H2 links to dedicated city page (/madison-carpet-cleaning)
```

---

## Part 3: Template A - Individual City Pages (Most Common)

Use this template for Structure A or B.

### Full Page Template

```html
---
TITLE TAG (60 chars):
"Professional [Service] in [City], [State] | [Brand]"
Example: "Carpet Cleaning in Madison, WI | Joe's Cleaners"

META DESCRIPTION (160 chars):
"Expert [service] in [City]. [Unique value]. Free quote.
[Phone]. Available [day range]."
Example: "Expert carpet cleaning in Madison, WI. Eco-friendly
solutions. Free quote. (608) 555-1234. Available today."

URL SLUG:
/[city]-[service]
Example: /madison-carpet-cleaning
---

H1 (Include Primary Keyword):
"Professional [Service] in [City], [State]"
Example: "Professional Carpet Cleaning in Madison, WI"

INTRO SECTION (100-150 words):
[Hook - the local problem]
"Madison homeowners battle [specific problem]. Whether it's
[problem examples], professional help restores your carpets."

[Why we specialize in Madison]
"Our team has served Madison and surrounding areas—Sun Prairie,
Fitchburg, Middleton—for 20+ years. We understand [local context]."

[Unique value]
"Unlike big-box cleaners, we use [specific method/product] that's
safe for [Madison-specific factor - kids/pets/hardwood]."

[CTA]
"Schedule your free in-home consultation today. No obligations.
Same-week appointments available."
---

H2: "[Service] Solutions for [City] Homes"
[150-200 words describing service + local variations]

Key points to include:
- Service methodology (what makes us different)
- Local problem specificity (what Madison faces that other cities don't)
- Results/outcomes (how customers benefit)
- Local competitor differentiation (why not [big brand]?)

Example paragraph:
"Our deep cleaning process extracts embedded soil from carpet
fibers that vacuums miss. In Madison's humid climate, this
prevents mold growth and extends carpet life by 3-5 years.
We target high-traffic areas—living rooms, hallways—where Madison
families see fastest wear."
---

H2: "Why Madison Families Choose Us"
[100-150 words]
- Local team credentials
- Number of years serving Madison
- Awards/certifications
- Customer testimonials (1-2 short quotes)
- Guarantees ("100% satisfaction or we re-clean for free")

Example:
"Madison homeowners trust us because we're local and invested in
the community. Our owner, Joe Smith, has cleaned over 2,000 Madison
homes. We're certified by [association]. And every customer gets
our 30-day satisfaction guarantee."
---

H2: "Our [Service] Process"
[200-250 words with step-by-step]

Example (Carpet Cleaning):
"Step 1: Inspection (10 min)
We inspect your carpet for stains, wear, and fiber type.
This determines our best cleaning approach."

"Step 2: Pre-treatment (15 min)
We apply eco-friendly pre-treatment solution to high-traffic
areas and stains. This breaks down soil for extraction."

"Step 3: Hot Water Extraction (30-45 min)
We use truck-mounted equipment (different from rental machines)
to extract deep soil and moisture."

"Step 4: Deodorizing & Protection (Optional)
We apply deodorizer and optional protective coating to repel
future stains."

"Timeline: Most Madison homes completed in 2-4 hours. Carpets
dry within 12 hours."
---

H2: "Service Areas in Madison"
[150 words - hyperlocal]

List neighborhoods, districts, surrounding cities:
"We proudly serve all of Madison, including:
- Downtown & University District
- Eastside (including near UW Hospital)
- Westside (including Middleton border)
- Fitchburg area
- Sun Prairie corridor

Need service in [surrounding city]? We service the entire
Greater Madison area. Call for quote."

Internal links in this section:
- Link to /fitchburg-carpet-cleaning (if page exists)
- Link to /sun-prairie-carpet-cleaning
- Link to state-level page (/wisconsin-carpet-cleaning if exists)
---

H2: "Our Pricing [in Madison]"
[100-150 words]

Include:
- Base price range (e.g., "Starting at $200 for most Madison homes")
- Factors affecting price (square footage, number of rooms, stains)
- New customer discount ("First-time customers receive 15% off")
- Guarantee (no surprise charges)

Example:
"Most Madison homes range $200-500 depending on square footage
and soil level. New customers receive 15% off first service.
We provide free quotes over phone with no obligation.
Pricing is transparent—no surprise charges."
---

H2: "Frequently Asked Questions (Madison)"
[200-300 words]

Include 5-8 location-specific questions:

Q: "How quickly can you service my Madison home?"
A: "We typically schedule within 3 business days.
For emergency same-day service, call and ask about availability."

Q: "Are your products safe for pets in Madison?"
A: "Yes. All products are pet-safe and eco-friendly, safe for
the whole family."

Q: "What's the cost for a typical Madison 1,500 sq ft home?"
A: "Typical cost is $250-350. We provide free phone quote
before service."

Q: "Do you service my neighborhood in Madison?"
A: "We service all Madison neighborhoods including downtown,
UW area, eastside, westside, Fitchburg, and Sun Prairie."

Q: "What if I'm not satisfied with the cleaning?"
A: "We guarantee 100% satisfaction. If you're not happy,
we'll re-clean at no charge within 30 days."
---

CTA SECTION (Below fold):

"Ready for Professional Carpet Cleaning in Madison?"

[Button] "Book Your Free Consultation"
[Text] "Call (608) 555-1234 or click above"
[Text] "Available same-week in Madison"

Optional: "Or message us"
---

SCHEMA MARKUP:
[Embed LocalBusiness + Service schema]
```

### Schema for Location Pages

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "[Business Name]",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[Street Address]",
    "addressLocality": "[City]",
    "addressRegion": "[State]",
    "postalCode": "[ZIP]"
  },
  "telephone": "[Phone]",
  "url": "[Website]",
  "areaServed": "[Service Cities/Region]",
  "serviceArea": ["[City 1]", "[City 2]", "[City 3]"],
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "[Rating]",
    "reviewCount": "[Count]"
  }
}
```

---

## Part 4: Template B - Pillar + City Sections

Use this for Structure C (single page, multiple cities).

```html
---
TITLE TAG:
"[Service] in [State]: [Brand] - Serving All [State] Cities"
Example: "Carpet Cleaning in Wisconsin: Joe's Cleaners -
Madison to Milwaukee"

H1:
"Professional [Service] Across [State]"
Example: "Professional Carpet Cleaning Across Wisconsin"
---

INTRO (200 words):
"We serve [State] residents and businesses from [major city 1]
to [major city 2]. With [X] years of experience, [team] has
completed [number] cleanings across [state]."

[List service areas]
"Our locations include Madison, Milwaukee, Green Bay, Madison,
Fitchburg, Sun Prairie, and surrounding areas."
---

TABLE OF CONTENTS:
- Madison Carpet Cleaning
- Milwaukee Carpet Cleaning
- Green Bay Carpet Cleaning
- [Other cities...]

Each links to H2 anchor below
---

[For each city, repeat this H2 structure]

H2: "[City] Carpet Cleaning"
[300 words per city]

Anatomy:
- 1-2 sentence opener specific to city
- Local problem statement (what this city faces)
- Our unique approach for [City]
- Local team credentials
- City-specific services (if applicable)
- Local CTA ("Book Madison appointment" / "Book Milwaukee appointment")
- Optional: Link to dedicated city page (/madison-carpet-cleaning)

Example (Madison H2):
"Our Madison team specializes in residential and commercial
cleaning. Madison homeowners battle [specific problem].
Our team has served Madison and surrounding areas for 20+ years."
---

BOTTOM CTA:
"Ready to Schedule Service in [Your City]?
[Cities served dropdown]"
```

---

## Part 5: Internal Linking Strategy

### Link Flow for Location Pages

**Pattern A: Flat structure**
```
Homepage → Service Page → Location Pages (all peer-linked)
Example:
/carpet-cleaning → links to /madison-carpet-cleaning
           → links to /milwaukee-carpet-cleaning
           → links to /fitchburg-carpet-cleaning

Each city page links back to /carpet-cleaning
Each city page links to neighboring cities
```

**Pattern B: Hierarchical**
```
Homepage → Service Page → State Page → City Pages
Example:
/services → /carpet-cleaning → /wisconsin/carpet-cleaning
  → links to /wisconsin/madison/carpet-cleaning
  → /wisconsin/milwaukee/carpet-cleaning

City pages link back up to state page + sibling cities
```

### Anchor Text Guidelines

| Anchor Text | Example | Best For |
|-------------|---------|----------|
| City + Service | "Carpet cleaning Madison" | Location page to service page |
| City + Modifier | "Madison carpet cleaning company" | Location page to state page |
| Branded + City | "Joe's cleaners Madison" | Navigation, sister pages |
| "Visit Madison" | "Visit our Madison location" | Cross-linking cities |

---

## Part 6: Content Variation Checklist

Ensure each location page is unique (not copy-paste):

- [ ] H1 includes specific city
- [ ] Intro paragraph mentions city name + local context
- [ ] "Why choose us" includes local credentials/team
- [ ] Process section includes city-specific benefits
- [ ] FAQ includes city-specific questions
- [ ] Neighborhood/area served section specific to city
- [ ] Local competitor references (if applicable)
- [ ] City-specific images (storefront, team, local landmarks)
- [ ] Minimum word count: 300 words unique per page

---

## Part 7: Publishing Workflow

### Single City Launch

1. Write location page (400-600 words minimum)
2. Create schema markup (LocalBusiness)
3. Add internal links from service pages
4. Publish as draft
5. Verify: Title, meta, H1 all include city
6. Publish live
7. Submit URL to Google Search Console
8. Monitor indexation (2-7 days typical)

### Multi-City Scale (50+ pages)

1. Create content template (reusable structure)
2. Research unique local data for first 5 cities (manual)
3. Build location pages for first 5 (highest volume cities)
4. Publish all 5 simultaneously (not staggered)
5. Monitor rankings for 2-4 weeks
6. If performing well, create next batch of 10
7. Stagger publishing: batch of 10 every 2-3 weeks
8. Use internal linking to distribute authority from pillars

### Publishing Cadence

- Batch of 1-5: All at once
- Batch of 10-20: All at once
- Batch of 50+: 10-20 at a time, 1-2 weeks apart

---

## Summary

Location pages are **authority multipliers** when done right.

Each page needs:
- Unique city-specific content (not templated)
- Local context (neighborhoods, competitor landscape)
- CTA specific to city
- Schema markup (LocalBusiness + Service)
- Internal links (to service pages + related cities)

Avoid:
- Copy-paste descriptions across cities
- Generic FAQs ("Is shipping available?" for local service)
- Zero local keyword variation

Result: 10-20 well-built location pages can drive 2-3x traffic to service-based sites.
