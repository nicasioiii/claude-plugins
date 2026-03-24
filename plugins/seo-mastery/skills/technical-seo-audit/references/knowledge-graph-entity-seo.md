# Knowledge Graph & Entity SEO: Building Factual Authority

Entity-based SEO is Google's core framework for understanding the factual world. Unlike traditional keyword-focused SEO, entity optimization focuses on clearly defining WHAT things are, not just using their names. This reference guide covers building knowledge graphs, implementing entity stacking, and leveraging semantic web fundamentals to improve rankings.

---

## Part 1: Entity Fundamentals

### What Are Entities in SEO?

Entities are **uniquely identifiable concepts** that Google understands and tracks. They represent real things in the world:

**Tangible Entities** (physical objects):
- Products (Laptop, Tesla Model 3)
- People (Steve Jobs, Elon Musk)
- Places (New York City, The Eiffel Tower)
- Organizations (Apple Inc., Google)

**Abstract Entities** (concepts, ideas):
- Services (Plumbing, Consulting, Dental Work)
- Concepts (SEO, Artificial Intelligence, Meditation)
- Qualities (Professionalism, Trustworthiness, Speed)

**Key Principle:** Entities have standardized definitions, relationships to other entities, and documented properties. They are NOT keywords—keywords describe entities, but entities are the actual things Google cares about.

### Why Entity SEO Matters Now

Google's RankBrain algorithm doesn't prioritize keyword mentions. Instead, it:
1. Identifies entities in your content
2. Verifies factual accuracy through knowledge graphs (Wikidata, Freebase)
3. Maps entity relationships and attributes
4. Ranks pages based on entity authority and semantic relationships

**Business Impact:** A page optimized for keywords but with confused entity definitions will underperform. A page with clear, factually correct entities ranks better.

---

## Part 2: Building Your Knowledge Graph

### The Glossary as Your Knowledge Foundation

The most effective way to build a knowledge graph is through a **comprehensive glossary** of terms used in your industry.

**Process:**
1. List all industry terms and concepts you use
2. Create a glossary page for each term with factual definitions
3. Reference glossary definitions in schema markup on product/service pages
4. Link internally between related terms

**Example: Roofing Company Glossary**
- Shingles (definition, types, durability)
- Flashing (definition, material options, why it matters)
- Pitch (definition, optimal ranges, local codes)
- Installation (definition, process, timeline)
- Warranty (definition, coverage types)

**Key Requirements:**
- Write like Wikipedia (factual, neutral, no marketing language)
- Include relationships to other entities ("Shingles are a type of Roofing Material")
- Add external references (Wikipedia links as authority)
- Update regularly to maintain freshness

### Leveraging Wikipedia Entity Alignment

**Strategy:** Connect your glossary to existing Wikipedia entities.

**Process:**
1. Identify Wikipedia pages for terms you use
2. Link your glossary definitions to these Wikipedia pages as sources
3. Make YOUR glossary the primary source, Wikipedia the secondary source
4. This positions your site as an authoritative source alongside Wikipedia

**Agency Power Move:** Create your AGENCY'S knowledge graph, then point all client glossaries to your agency's definitions. This makes the agency the authority source across all client properties.

**Implementation Tool - Zimrider Bookmarklet:**
1. Use Zimrider to extract entities from Wikipedia pages
2. Copy relevant Wikipedia URLs
3. Summarize each page with Penny Arcade summarization
4. Import summaries via CSV into WordPress Glossary plugin
5. Use "handle duplicates" setting to avoid re-imports

### Creating Custom Entities (Non-Wikipedia Terms)

Not all specialized terms exist on Wikipedia. You can create custom entities in your glossary.

**Example:** "Vacation Rental Cleaning Company" doesn't have Wikipedia article.

**Solution:**
1. Create glossary entry for this custom term
2. Reference Wikipedia entities that compose it (Vacation Rental + Cleaning Company)
3. Use schema `DefinedTerm` type to establish YOUR definition
4. Treat this as a real entity in all schema markup
5. Reference this definition consistently across your site

**Advantage:** You're creating YOUR dictionary. Once defined in schema, it becomes a recognized entity for ranking purposes.

---

## Part 3: Entity Attributes & Semantic Structure

### Entity-Attribute-Value (EAV) Model for Content

The EAV model structures entity information in a way Google understands: **Entity → What Property → Value**.

**Structure:** Use tables with three columns in your content:

| Entity | Attribute | Value |
|--------|-----------|-------|
| Emergency Plumbing | Hours Available | 24/7 |
| Emergency Plumbing | Response Time | 1 Hour |
| Emergency Plumbing | Service Areas | Los Angeles County |

**Why This Matters:**
- Breaks up dense text (improves readability)
- Creates semantic triples Google understands
- Shows clear yes/no answers (use icons/checkmarks)
- Makes information scannable for AI extraction

**Examples by Industry:**

**Dentistry:**
| Entity | Attribute | Value |
|--------|-----------|-------|
| Root Canal | Pain Level | Minimal with anesthesia |
| Root Canal | Duration | 1-2 hours |
| Root Canal | Recovery | Same-day return to normal |

**Automotive:**
| Entity | Attribute | Value |
|--------|-----------|-------|
| Toyota Service | Brands Served | Toyota, Lexus |
| Toyota Service | Foreign/Domestic | Yes |
| Toyota Service | Warranty | 24 months |

**Local Services:**
| Entity | Attribute | Value |
|--------|-----------|-------|
| Emergency Services | Hours | 24/7 availability |
| Emergency Services | Service Areas | Downtown, Suburbs |
| Emergency Services | Aftercare | Yes |

**Implementation:** Use HTML tables, not images. Ensure clear headers so Google identifies each column.

### Entity Properties & Relationships

Every entity has:

**Core Properties:**
- **Name** - Official, unique identifier
- **Alternative Names** - Aliases, acronyms, translations
- **Definition** - Factual description
- **Category** - What type of thing it is
- **Properties** - Measurable characteristics

**Relationship Properties:**
- **Related Entities** - Other entities it connects to
- **Parent Entity** - What larger category it belongs to
- **Child Entities** - What things are part of it
- **Related Services** - What it pairs with

**Example - Metal Roofing:**
- Name: Metal Roofing
- Alternative Names: Steel Roofing, Metal Panels, Standing Seam
- Definition: Roofing system using sheet metal as primary material
- Category: Roofing Material
- Parent: Roofing
- Child Entities: Steel Roofing, Aluminum Roofing, Copper Roofing
- Properties: Lifespan (40-70 years), Cost (Premium), Energy Efficiency (High)
- Related: Installation, Warranty, Durability

---

## Part 4: Advanced Schema Implementation for Entity Authority

### Multi-Entity Schema Nesting

**Key Principle:** Multiple entities can work together on a single page. Don't force one entity to do everything.

**Example: Roofing Company Service Page**

This page should include nested schema for:
1. **Organization** (top level) - The company itself
2. **Service** type - The specific service offered
3. **LocalBusiness** - Address, phone, hours
4. **AggregateRating** - Customer reviews
5. **Review** items (multiple) - Individual ratings

Each entity is separate but related. No single "mainEntity" required.

**JSON-LD Structure:**
```json
{
  "@context": "https://schema.org/",
  "@graph": [
    {
      "@type": "LocalBusiness",
      "name": "ABC Roofing",
      "telephone": "555-1234",
      "address": { ... }
    },
    {
      "@type": "Service",
      "name": "Metal Roof Installation",
      "provider": { "@id": "#company" },
      "areaServed": { "@id": "#serviceArea" },
      "aggregateRating": { "@id": "#rating" }
    },
    {
      "@type": "AggregateRating",
      "@id": "#rating",
      "ratingValue": "4.8",
      "ratingCount": "247"
    }
  ]
}
```

### Semantic Relationship Markup

Use schema properties to define HOW entities relate:

**aboutPage Property:** Page's main topic
```json
{
  "@type": "WebPage",
  "about": {
    "@type": "Thing",
    "name": "Metal Roofing"
  }
}
```

**mentions Property:** Entities discussed but not main topic
```json
{
  "@type": "Article",
  "mentions": [
    { "@type": "Thing", "name": "Shingles" },
    { "@type": "Thing", "name": "Flashing" },
    { "@type": "Thing", "name": "Installation Process" }
  ]
}
```

**isPartOf Property:** Hierarchical relationships
```json
{
  "@type": "Service",
  "name": "Metal Roof Installation",
  "isPartOf": {
    "@type": "Service",
    "name": "Roofing Services"
  }
}
```

---

## Part 5: Content Strategy for Entity Authority

### Entity Placement in Content

**Hierarchy of Importance:**
1. **H1** - Your primary entity/service
2. **H2** - Secondary entities
3. **Topic sentences** - Begin with primary/secondary entity
4. **Body text** - Use naturally

**Example Structure:**

```
H1: Metal Roof Installation Services in Los Angeles

H2: Benefits of Metal Roofing in Los Angeles
Content discusses: Metal Roofing entity, durability, energy efficiency...

H2: Metal Roof Maintenance in Los Angeles
Content discusses: Maintenance entity, cleaning, inspection, lifespan...

H2: Metal vs. Asphalt Shingles: Which is Right for You
Content discusses: Comparison between Metal Roofing and Shingles entities...
```

**Key Principle:** Entity placement > keyword placement. Google looks for factually correct entities, not keyword frequency.

### Internal Linking for Entity Authority

**Technique: Concentrated Link Juice**

You can use internal linking to boost entity authority on specific pages.

**Strategy:**
1. Identify which pages currently rank for an entity term
2. If you want to boost a DIFFERENT page for that entity:
   - Find other pages mentioning that entity
   - Create internal links to your target page
   - Use anchor text variations (entity name, full description)

**Example: Boosting "Metal Roofing" Authority**

Current situation: Blog post ranks for "metal roofing" but service page doesn't.

Solution:
- Find 5-10 internal pages that mention "metal roofing"
- Add links from those pages to the service page
- Use varied anchor text: "metal roofing," "metal roof installation," "learn about metal roofing systems"

**Result:** Over 2-3 months, the service page gains authority for the "metal roofing" entity.

### The Hyper-Local Entity Rotation Strategy (Advanced)

**Timeline:** 3-6 month consolidated authority strategy

**Phase 1 (Months 0-3): Build Authority Through Hyper-Local Pages**
- Create location-specific pages: "[Service] in [Neighborhood]" (100-200+ variations)
- Each page ranks independently for that specific location
- All pages accumulate authority signals (links, mentions, engagement)

**Phase 2 (Months 3-6): Let Authority Consolidate**
- Pages build topical authority and backlinks
- Monitor rankings for stability
- Allow authority to distribute evenly

**Phase 3 (Month 6): Redirect Authority**
- Delete indexing for hyper-local pages
- Implement 301 redirects to main service pages
- All accumulated authority flows to main service pages

**Example:**
- Create 150 pages: "Plumbing in Santa Monica," "Plumbing in Beverly Hills," etc.
- After 6 months, all have ranking authority
- Redirect all to main "Plumbing Services in Los Angeles" page
- Main page suddenly has link juice from 150+ ranking pages

**Result:** Main service pages solidify ranking in competitive markets.

**Important:** Wait 3-6 months for rankings to stabilize before redirecting. Premature consolidation loses ranking benefits.

---

## Part 6: Knowledge Panels & Visibility

### Understanding Knowledge Panels

A **Knowledge Panel** is Google's display of entity information in the search results sidebar.

**What Triggers Panels:**
- Factual entities in search results (not keywords)
- First set of entities Google identifies in content
- Verified, accurate information across multiple sources
- Entity consistency across web

**Example:** Search "Abraham Lincoln" → Knowledge panel shows biographical facts.

**For Your Business:**
- Ensure content is factually accurate
- Use clear schema to define entities
- Focus on factual presentation, not keyword optimization
- Build entity relationships (links to related entities)

### Knowledge Graph Data Structure

A complete knowledge graph entry for an entity should include:

**Required:**
- Official name
- Definition (factual, Wikipedia-style)
- Category (what type of entity)
- Key properties/attributes

**Recommended:**
- Alternative names (aliases, acronyms)
- Related entities (links)
- External references (Wikipedia, Wikidata)
- Images (official logos, product photos)
- Contact information (if applicable)
- Founded date/history (if applicable)

**Best Practice Implementation:**
Use glossary + schema combination:
1. **Glossary page** - Comprehensive definition
2. **Schema markup** - Structured data reference
3. **Internal links** - Connect related entities
4. **Citations** - External validation

---

## Part 7: RDF & Semantic Web Fundamentals

### Understanding RDF (Resource Description Framework)

RDF is the W3C standard for describing entities and relationships. It uses simple triples:

**Subject → Predicate → Object**

Examples:
- "Casey Keith" → "worksFor" → "Worldwide Web"
- "Metal Roofing" → "hasProperty" → "Lifespan of 50 years"
- "Los Angeles" → "locatedIn" → "California"

**Key Components:**

**Resources:** Anything with a unique identifier (URI/URL)
- Web pages, people, products, concepts
- Can be any entity with a unique identifier

**Properties:** Specific aspects or relationships
- "worksFor," "locatedIn," "hasColor," "author"

**Values:** The result of property + resource
- Can be another resource or a literal (text, number, date)

### XML/JSON-LD Serialization

RDF concepts translate to schema markup:

**RDF Triple:**
```
Resource: John Smith
Property: knows
Value: Jane Doe
```

**JSON-LD Implementation:**
```json
{
  "@type": "Person",
  "name": "John Smith",
  "knows": {
    "@type": "Person",
    "name": "Jane Doe"
  }
}
```

**Semantic Triple Structure:**
Every schema property represents an RDF triple:
- Subject = The entity being described (@type)
- Predicate = The property name (knows, worksFor, etc.)
- Object = The value (another entity or literal)

### Applying Semantic Web to SEO

**Semantic Optimization Workflow:**

1. **Map All Entities** in your content
   - List every entity mentioned
   - Categorize by type (Service, Product, Organization, Location)

2. **Define Relationships**
   - What entities are related? (Parent/child, related services)
   - What properties describe each entity?

3. **Implement Schema Markup**
   - Use appropriate schema types for each entity
   - Include all relevant properties
   - Create relationships through nested schema

4. **Internal Linking**
   - Connect entity definitions (glossary)
   - Link related topics
   - Create entity clusters

5. **Verify Coverage**
   - Ensure all important entities are marked up
   - Check schema with validator
   - Monitor Knowledge Panel (if applicable)

---

## Part 8: Entity Stacking & Authority Building

### Entity Stacking Concept

Entity stacking means building multiple authoritative references to an entity across your site, creating a concentrated authority signal.

**Example: "Metal Roofing" Entity Stacking**

**Layer 1: Glossary Definition**
- URL: `/glossary/metal-roofing`
- Comprehensive definition
- Schema: DefinedTerm markup

**Layer 2: Service Page**
- URL: `/services/metal-roof-installation`
- Service details
- Schema: Service type
- Links to glossary definition

**Layer 3: Product Specification Page**
- URL: `/products/metal-roof-panels`
- Product details
- Schema: Product type
- Links to glossary + service page

**Layer 4: Blog Content**
- URL: `/blog/benefits-of-metal-roofing`
- In-depth coverage
- Links to all layers above

**Layer 5: FAQ Content**
- URL: `/faq/#metal-roofing`
- Common questions
- Schema: FAQPage
- Links to all layers

**Result:** Search for "metal roofing" → Your entity receives concentrated authority from 5 interlocked sources.

### Building Entity Authority Checklist

- [ ] Create glossary definition for entity
- [ ] Mark up definition with DefinedTerm schema
- [ ] Create service/product page for entity
- [ ] Link all references to glossary definition
- [ ] Create supporting blog content
- [ ] Create FAQ covering common questions
- [ ] Ensure all schema properties populated
- [ ] Link related entities internally
- [ ] Monitor rankings for entity + variations
- [ ] Update content quarterly for freshness

---

## Part 9: Tools & Validation

### Schema Validation Tools

- **Google Rich Results Tester** (search.google.com/test/rich-results)
  - Test what Google sees in schema
  - Catch missing required properties

- **Schema.org Validator** (w3.org)
  - Official schema validation
  - Check property requirements

- **Semantic Spider** (browser extension)
  - View competitor schema
  - Compare markup approaches

### Knowledge Graph Monitoring

- **Google Search Console**
  - Monitor indexation of glossary pages
  - Track entity-related query performance

- **Google Knowledge Panel Insights** (if you have a panel)
  - View how your entity appears to users
  - Identify information gaps

- **Wikidata / Freebase**
  - Check if your entities exist
  - Update/add entity information if eligible

---

## Implementation Checklist: Building Entity Authority

### Week 1: Audit & Plan
- [ ] List all industry entities your business uses
- [ ] Identify which have Wikipedia pages
- [ ] Map entity relationships and hierarchy
- [ ] Review current schema implementation

### Week 2-4: Build Glossary Foundation
- [ ] Create glossary page for top 10-15 entities
- [ ] Write Wikipedia-style definitions (neutral, factual)
- [ ] Add external references (Wikipedia links)
- [ ] Implement DefinedTerm schema
- [ ] Internal link between related terms

### Week 5-8: Enhance Page Schema
- [ ] Add entity references to service/product pages
- [ ] Update schema with mentions property
- [ ] Link to glossary definitions
- [ ] Create nested schema for complex pages
- [ ] Validate all schema with Google tool

### Week 9-12: Content Layer Strategy
- [ ] Create supporting blog content
- [ ] Develop FAQ around entities
- [ ] Build comparison content (entity vs. alternatives)
- [ ] Create how-to guides referencing entities
- [ ] Link all new content to glossary

### Ongoing: Monitor & Maintain
- [ ] Monthly: Update glossary entries (add new information)
- [ ] Monthly: Review entity rankings
- [ ] Quarterly: Audit schema for accuracy
- [ ] Quarterly: Add new entity layers as needed
- [ ] Quarterly: Check for Knowledge Panel appearance
