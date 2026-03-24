---
name: "Local SEO, Ecommerce & Programmatic Scale"
description: "Optimize for local search, scale product catalogs, and automate content generation. GBP mastery, location pages, citation strategy, ecommerce product schema, programmatic SEO playbooks, parasite SEO, and AI content at scale. Triggers: local SEO, Google Business Profile, ecommerce SEO, product pages, programmatic SEO, parasite SEO, location pages, citations. Covers: local search optimization, GBP setup, location pages, product schema, programmatic content generation, AI scaling. Does NOT cover: paid ads, e-commerce platform setup."
Triggers:
  - local SEO
  - Google Business Profile
  - ecommerce SEO
  - product pages
  - programmatic SEO
  - parasite SEO
  - location pages
  - citations
---

# SKILL 8: Local SEO, Ecommerce SEO & Programmatic Scale

**Workflow Stage:** Scale
**Complexity:** High
**Lines:** ~450

---

## Core Philosophy

This skill consolidates three massive SEO domains under one skill because they share identical technical foundations and operational workflows:

1. **Local SEO** - Optimizing for geographic, "near me" search intent
2. **Ecommerce SEO** - Product pages, category pages, schema optimization at scale
3. **Programmatic SEO** - Automating content generation across templates while maintaining unique value

All three require: NAP/entity consistency, schema markup mastery, internal linking architecture, and scale-oriented thinking.

---

## When to Use This Skill

**User Asks:**
- "How do I optimize for local search?"
- "I need to rank multiple location pages—what's the strategy?"
- "How do I set up Google Business Profile for maximum visibility?"
- "Should I build location pages or location schema?"
- "How do I optimize product pages for rank and sales?"
- "Can I automate content generation without Google penalizing me?"
- "What's the deal with directory sites and programmatic SEO?"
- "How do I scale content to 100+ pages without looking like spam?"

**Routing Logic:**
- If user is building a directory → See references: `programmatic-seo-playbook.md`
- If user needs GBP optimization → See references: `google-business-profile-mastery.md`
- If user is scaling ecommerce → See references: `ecommerce-product-schema.md`
- If user needs location page templates → See references: `location-page-templates.md`
- If complex technical questions → Hand off to `technical-seo-audit` skill

---

## Part 1: Local SEO Fundamentals

### NAP Consistency (The Foundation)

**NAP** = Name, Address, Phone. These three signals must be **identical** everywhere:
- Google Business Profile (primary source)
- Your website (header, footer, contact page)
- Citations (directories, Yelp, Apple Maps, Bing Places)
- Social profiles (Facebook, LinkedIn, Instagram)

Even minor variations ("Street" vs "St." or "(555) 123-4567" vs "555-123-4567") confuse Google's algorithm and split your local authority signals.

**Action:** Create a master NAP document you copy-paste everywhere. Version control it.

### Google Business Profile (GBP) - The Ranking Engine

**Profile completeness** directly correlates with local ranking. Google rewards profiles filled 100% vs. 50%.

**Critical setup fields:**
1. **Business Name** - Exact legal name (or name + service area for franchises)
2. **Category** - Most specific match (e.g., "Personal Injury Attorney" > "Lawyer")
3. **Secondary Categories** - Up to 9 additional (shows up in related searches)
4. **Address** - Physical street address (never virtual office; limited GMB per address)
5. **Phone** - Local number matching service area
6. **Website** - Full HTTPS URL
7. **Business Hours** - Exact hours + special holiday hours
8. **Service Area** - Cities/radius served (if service-based)

**Profile content optimization:**
- **Description (750 chars max):** Primary keyword in first sentence + list services naturally + brand voice
- **Photos:** 5-25 minimum. Types: exterior, interior, team, products/services, before-after. Geo-tag all. Use keyword filenames (e.g., "carpet-cleaning-madison-wi.jpg")
- **Logo & Profile Photo:** High-res, consistent branding
- **Attributes:** Wheelchair accessible, online appointments, women-led, etc.
- **Q&A Section:** Seed 20+ keyword-rich questions + answers
- **Products/Services Section:** If applicable, list with descriptions
- **Messaging:** Enable for engagement signals

### GBP Post Strategy (5+ posts/week minimum)

Posts signal freshness and entity activity to Google's algorithm.

**Post types:**

1. **What's New posts (3-5 weekly)**
   - Target ONE secondary keyword each
   - 1,500 character limit
   - Anatomy: Headline keyword → body text with secondary terms → business name → owner name → specific location/neighborhood → nearby landmarks
   - Inject contextual entities (local organizations, landmarks)
   - Never include phone numbers (Google rejects as policy violation; use CTA button instead)

2. **Event posts (1-2 weekly)**
   - Create repeating events (e.g., "Weekly consultation," "Monthly demo")
   - Set once, repeat perpetually
   - Target primary service keyword

3. **Offer posts (1-2 weekly)**
   - Monthly-rotating discounts or bundles
   - Target primary keyword

**Analytics:** Monitor "How people discovered you" in GBP Analytics tab to find keywords actually driving search traffic.

### Citation Strategy (Authority Building)

**Citation** = Online mention of NAP (with or without backlink).

**Tier 1: Critical directories**
1. Google Business Profile (already set up)
2. Bing Places
3. Apple Maps
4. Facebook Business
5. Yelp
6. Yellow Pages
7. Foursquare/Swarm
8. Industry-specific (Healthgrades, TripAdvisor, Angi)

**Citation cadence:**
- Start with top 10-20 directories manually
- If performing well, batch-submit 50 citations
- Wait 2 weeks for indexation
- Scale to max 350 citations total (balances speed with naturalness)

**Citation management tools:**
- LocalRank.io (one-click submission + consistency checking)
- BrightLocal / Moz Local (paid, syndication across directories)
- Manual (sufficient for 10-20 starting)

**Critical step:** Citations don't auto-index. Use indexer tools (Speedy Index Bot, Speed Links) after creation.

---

## Part 2: Location Page Strategy

### When to Build Location Pages?

**Build if:**
- Service-based business with multiple locations
- Geographic expansion target (want to rank in multiple cities)
- Local intent keywords show high search volume per city

**Don't build if:**
- Single location (invest in GBP instead)
- Low search volume per location (<20 monthly searches)

### Location Page Architecture

**Two patterns:**

**Pattern A: Pillar page**
- Single long-form page covering all locations in a state/region
- URL: `/goodwill-bins-texas-store-locations`
- H1: "Goodwill Bins in Texas" (state-level keyword)
- H2s: Each city (Austin, Dallas, Houston, etc.)
- Internal links: Each H2 links to dedicated city page if it exists
- Pros: Easier to manage, authority concentration
- Cons: Long pages (5,000+ words), harder to rank for specific city

**Pattern B: Individual city pages**
- Dedicated page per city
- URL: `/carpet-cleaning-madison-wisconsin`
- H1: "Professional Carpet Cleaning in Madison, WI"
- Content: Service area intro → why choose us → process → testimonials → FAQs specific to Madison
- Pros: Easier to rank individual pages, location-specific content
- Cons: More pages to maintain

**Recommended:** Pattern B for competitive markets, Pattern A for low-competition niches.

### Location Page Content Formula

**Minimum 300 words, structured:**

1. **Intro (50-100 words):** "We serve [City], [County], [Region]. Here's what makes us different."
2. **Service description (100-150 words):** Explain service + local context. "In Madison, homeowners dealing with [specific problem]. We use [solution]."
3. **Why choose us (75-100 words):** Unique value prop.
4. **FAQ section (150-200 words):** 5-8 location-specific questions. "What areas of Madison do you serve?" "How much do we charge in Madison?"
5. **CTA:** "Contact us for free quote in Madison."

**Internal linking:** Link to related service pages, other nearby cities, and pillar content.

### Location Page Schema

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "[Business Name]",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[Street]",
    "addressLocality": "[City]",
    "addressRegion": "[State]",
    "postalCode": "[ZIP]"
  },
  "telephone": "[Phone]",
  "url": "[Website]",
  "serviceArea": "[Service Area Cities]",
  "areaServed": "[Service Region]"
}
```

---

## Part 3: Ecommerce SEO Fundamentals

### Ecommerce Site Structure

**Homepage → Category pages → Subcategory pages → Product pages**

**Category page strategy:**
- Target primary keywords (e.g., "running shoes," "hiking boots")
- 300+ words intro + filtered product listings
- Internal links to subcategories + featured products
- Schema: CollectionPage + Product schema for items displayed

**Subcategory pages:**
- Target secondary keywords (e.g., "women's running shoes," "trail running shoes")
- Filter products by relevant attributes
- Link to parent category + sibling categories

**Product pages:**
- Target long-tail keywords (e.g., "Nike Air Zoom Pegasus 40 women's running shoe")
- Product schema (critical for rich results)
- Specifications, reviews, images, related products

### Product Page Optimization

**Title tag formula:** `[Product Name] | [Brand] - [Unique Attribute]`
- Example: "Nike Air Zoom Pegasus 40 Women's Running Shoe | Premium Cushioning & Durability"

**Meta description:** `[Product] with [key benefit]. [Unique value]. Free shipping. [CTA]`

**H1:** Product name (include primary keyword variation)

**Content structure:**
1. **Above fold:** High-res product image, price, star rating, "Add to Cart" button
2. **Intro:** What this product is + primary benefit (50-100 words)
3. **Key features:** Bulleted list with keywords
4. **Specifications:** Table with dimensions, weight, materials, colors, sizes
5. **Reviews section:** Star rating + customer reviews (social proof)
6. **Related products:** Upsells, complementary items
7. **FAQ:** "Is this item returnable?" "What size should I choose?" "How long does shipping take?"

### Product Schema (Critical for Rich Results)

```json
{
  "@context": "https://schema.org/",
  "@type": "Product",
  "name": "[Product Name]",
  "image": ["[URL]"],
  "description": "[Product description]",
  "brand": {
    "@type": "Brand",
    "name": "[Brand Name]"
  },
  "offers": {
    "@type": "Offer",
    "url": "[Product URL]",
    "priceCurrency": "USD",
    "price": "[Price]",
    "availability": "https://schema.org/InStock"
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "[Rating]",
    "reviewCount": "[Count]"
  }
}
```

**Schema elements that trigger rich results:** Availability, price, rating, reviews, images.

### Category Page Optimization

**Category pages are often overlooked but rank equally to product pages.**

**Faceted navigation best practices:**
- Filter by attribute (size, color, brand, price range)
- Use URL parameters smartly: `/shoes?size=10&color=red` (not duplicates if using rel="canonical")
- Each filter combo creates unique content (slight intro paragraph variation)

**Pagination:**
- Use `rel="next"` and `rel="prev"` for multi-page results
- OR consolidate to single page if <100 products
- Avoid duplicate content signals

**Category schema:**
```json
{
  "@context": "https://schema.org",
  "@type": "CollectionPage",
  "name": "[Category Name]",
  "description": "[Category description]",
  "url": "[Category URL]"
}
```

---

## Part 4: Programmatic SEO Scaling

### Core Principle

**Programmatic SEO** = Generating template-based pages that maintain unique value through data + AI.

**Not thin content because:** Each page includes unique data, local context, or user-generated content.

### The 12 Programmatic SEO Playbooks

(Reference `programmatic-seo-playbook.md` for full details—summary here)

1. **Template Playbook:** Blog post templates with keyword variations
2. **Curation Playbook:** Aggregate content from multiple sources with unique editorial angle
3. **Comparison Playbook:** Product/service comparisons (A vs. B)
4. **List Playbook:** Ranked listicles ("Top 10 X in [City]")
5. **Example Playbook:** Real-world examples with unique analysis
6. **Location Playbook:** Location pages (covered above, full template in reference)
7. **Persona Playbook:** Content for specific user personas (beginner, advanced, enterprise)
8. **Integration Playbook:** How-to guides for tool combinations ("X + Y = Better results")
9. **Glossary Playbook:** Define niche-specific terms with examples
10. **Translation Playbook:** Multi-language expansion (be careful with hreflang)
11. **Directory Playbook:** Listing aggregation with curation layer
12. **Profile Playbook:** Individual profiles (people, companies, products)

### What Google Penalizes (Thin Content Signals)

- **Duplicate copy-paste descriptions** (even across locations)
- **Templated FAQs** with zero local variation
- **Auto-generated content** with no human review
- **Keyword stuffing** in unique fields
- **Zero original analysis** (pure aggregation without angle)

### What Google Rewards (Unique Value Signals)

- **Unique descriptions** per page (AI-rewritten OK, but must vary)
- **Local context** (references to city names, neighborhoods, landmarks)
- **Original data** (statistics, research, surveys you conducted)
- **Human curation** (you filtered/ranked the aggregated content)
- **Enriched fields** (not just name/address, but features unique to each location)

### Scaling Workflow

1. **Define template:** URL structure, page sections, required fields
2. **Gather data:** Scrape APIs, manual research, or vendor feeds
3. **Enrich data:** Add unique fields (compensation for plasma centers, shade/benches for dog parks)
4. **Generate content:** Use AI per page for descriptions (not copy-paste)
5. **Quality check:** Random sample QA, fact-checking critical data
6. **Publish:** Stagger if 100+ pages (avoids spam signals)
7. **Monitor:** Track indexation, ranking, engagement metrics per page type

---

## Part 5: AI-Powered Content at Scale

### When to Use AI for Ecommerce/Local Content

**Safe to use AI for:**
- Product descriptions (rewritten per product, not templated)
- Location page intro paragraphs (unique to each city)
- FAQ answer variation (each location gets unique answers)
- Blog content expanding on topics

**Not safe for:**
- Exact copy-paste of competitor content
- Zero human review
- Keyword stuffing under guise of "AI-generated"

### AI Workflow for Location Pages

1. **Create base template:** H1, intro structure, CTA
2. **Feed AI context:** "Write a unique 200-word intro to Madison carpet cleaning market. Include: Madison-specific problems, competitor landscape, our unique angle."
3. **Generate per location:** Repeat for Dallas, Austin, Houston with city-specific data
4. **Edit for accuracy:** Fact-check claims, remove generic language
5. **Publish:** Each page now has unique, localized content

### Quality Thresholds

- **Product descriptions:** Minimum 120 words, unique per product
- **Location page intros:** Minimum 200 words, must include local context (city name 3+ times)
- **FAQs:** Minimum 8 questions per location, with location-specific answers

---

## Part 6: Parasite SEO (Alternative Scaling Strategy)

**Parasite SEO** = Distributing content across high-authority third-party platforms to rank without building your own domain authority.

**Platforms ranked by authority:**
1. Reddit (DR ~90)
2. LinkedIn (professional credibility)
3. Facebook (broad reach)
4. Instagram (visual, high authority)
5. YouTube (video, discovery)
6. Google properties (Google Sites, Sheets, Docs)

**Best for:** SaaS tools, affiliate offers, brand awareness (not local businesses)

**Risk:** Account suspension if platform detects spam. Conservative approach recommended.

Reference: `parasite-seo-google-properties.md` for detailed setup.

---

## Navigation & Handoffs

**User is optimizing GBP for local service business?**
→ Use `google-business-profile-mastery.md` reference

**User is building directory site with 500+ listings?**
→ Use `programmatic-seo-playbook.md` reference

**User is scaling ecommerce to 1,000+ products?**
→ Use `ecommerce-product-schema.md` reference

**User needs location page content templates?**
→ Use `location-page-templates.md` reference

**User has technical questions about schema, crawlability, indexation?**
→ Hand off to `technical-seo-audit` skill

**User is doing link building for ecommerce brand?**
→ Hand off to `link-authority-building` skill

---

## Key Takeaways

1. **NAP consistency** is foundation for all local SEO
2. **GBP is the ranking engine** for local search (more important than website)
3. **Location pages scale authority** to multiple geographic markets
4. **Programmatic SEO works** when you maintain unique value (data, curation, local context)
5. **Product schema** directly influences visibility in shopping results
6. **AI content at scale** requires human review and local variation
7. **Parasite SEO** is tactical for authority-rich platforms, not primary strategy

---

## Tools Referenced

- LocalRank.io (citation management)
- BrightLocal (citation syndication)
- Screaming Frog (technical audit)
- Schema.org (validation)
- Google Search Console (indexation monitoring)
- AI platforms (Claude, ChatGPT for content generation)
