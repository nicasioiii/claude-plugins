---
name: Schema Markup & Entity Optimization
description: >
  MANDATORY TRIGGERS: schema markup, structured data, JSON-LD, schema.org,
  rich results, product schema, FAQ schema, LocalBusiness schema, ClaimReview,
  entity optimization, knowledge graph, Google Knowledge Graph, semantic spider,
  schema validation, Rich Results Test, schema for E-E-A-T, Google Stacking,
  entity reinforcement, schema for AI, AI Overviews schema, orchestrator layer,
  has-varying schema, product-varying, feed consistency, organic product grid.
  FOR: Dedicated skill for structured data implementation and entity-level
  optimization. Covers schema types for E-E-A-T (reviewedBy, citation, knowsAbout,
  hasCredential, ClaimReview, awards), product schema for e-commerce (mandatory
  base + competitive advantage fields), FAQ schema, the semantic spider framework,
  AI-assisted schema generation workflow (3-step: analyze, identify, generate+validate),
  schema validation process, schema's role in AI search orchestration, Google
  Stacking for entity reinforcement, and knowledge graph construction via glossaries.
  Do NOT use for: On-page content optimization (use on-page-optimization), topical
  authority strategy (use topical-authority-semantic), technical crawlability
  issues (use technical-seo-audit), content writing (use content-production).
---

# Schema Markup & Entity Optimization

## Quick Navigation
- **Schema types, implementation, AI-assisted workflow** -> ref-schema-implementation-guide.md
- **Knowledge graphs, Google Stacking, entity reinforcement** -> ref-entity-knowledge-graph.md

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| What schema types to implement, how to add schema | ref-schema-implementation-guide.md |
| E-E-A-T schema properties, ClaimReview, reviewedBy | ref-schema-implementation-guide.md |
| Product schema, e-commerce schema, FAQ schema | ref-schema-implementation-guide.md |
| AI-assisted schema generation, GPT workflow | ref-schema-implementation-guide.md |
| Schema validation, Rich Results Test, schema.org validator | ref-schema-implementation-guide.md |
| Schema for AI search, orchestrator layer, AI Overviews | ref-schema-implementation-guide.md |
| Building knowledge graph, glossary approach, entity definitions | ref-entity-knowledge-graph.md |
| Google Stacking, Google Drive strategy, entity reinforcement | ref-entity-knowledge-graph.md |
| Wikipedia-Wikidata-KG cascade, RDF triples | ref-entity-knowledge-graph.md |
| Entity salience, entity authority, semantic spider framework | ref-entity-knowledge-graph.md |

---

## Cross-References

| When the conversation turns to... | Route to this skill | Trigger |
|---|---|---|
| "How do I build topical authority around this entity?" | topical-authority-semantic | Need topical map strategy |
| "How do I optimize the page content itself?" | on-page-optimization | Need title/meta/header optimization |
| "My schema isn't rendering / crawl issues" | technical-seo-audit | Need technical debugging |
| "How do I optimize for AI Overviews?" | geo-ai-search-optimization | Need GEO strategy beyond schema |
| "What product schema fields boost organic product grids?" | ecommerce-seo | Need e-commerce specific strategy |

---

## WHY SCHEMA IS NON-NEGOTIABLE (Gorrono / brightonSEO)

- Google explicitly confirmed AI Overviews leverage structured data
- Rich results (star ratings, FAQs, product info) dramatically increase CTR
- Search engines understand page content more precisely with schema
- Supports voice search and AI tools with machine-readable context
- The **orchestrator layer** (which fetches pages for LLMs) uses schema to assess content -- even though LLMs themselves do not directly process schema

**CONTRARIAN (Koray):** Content structure IS the schema. Properly structured content with EAV tables creates machine-parseable data without markup. **Resolution:** Implement BOTH -- structured content AND explicit schema.

---

## THE 3-STEP AI-ASSISTED SCHEMA WORKFLOW (Gorrono)

### Step 1: Analyze
Use Google Rich Results Test (free) to check if any page has existing schema. Compare against competitors to find gaps.

### Step 2: Identify
Paste URL into ChatGPT 4o with search enabled. Prompt:
"Analyze the link. Understand the page, the services provided, and tell me what are all the types of schema markup I can place on this page to improve searchability."

GPT identifies specific schema types (e.g., FinancialService, not just LocalBusiness).

### Step 3: Generate & Validate
1. Ask GPT to build the schema JSON-LD code
2. Paste output into schema.org validator to verify zero errors/warnings
3. Check all details (hours, address, services) are correct
4. Paste into Google Rich Results Test (tests different things than schema.org validator)
5. Inject into page header

**Important:** Schema types are extremely granular. Not "LocalBusiness" but "FinancialService" specifically. GPT handles this nuance well.

---

## SIX E-E-A-T SCHEMA PROPERTIES (Casey Keith)

| Property | What It Signals | Example |
|---|---|---|
| `reviewedBy` | Expert review of content | `"reviewedBy": {"@type": "Person", "name": "Dr. Jane Smith"}` |
| `citation` | Source backing claims | Link to research paper, study, or authoritative source |
| `knowsAbout` | Author's expertise areas | `"knowsAbout": ["SEO", "Content Marketing", "Digital Strategy"]` |
| `hasCredential` | Certifications, degrees | `"hasCredential": {"@type": "EducationalOccupationalCredential"}` |
| `ClaimReview` | Fact-checking markup | Gets checkmark badge in SERPs. Free authority signal. |
| `awards` | Industry recognition | "Named in Top 10 SEO consultants" -- cite in schema |

**ClaimReview hack:** The cited source does not need to be a major publication. A credible social media post from a known person technically qualifies as a cited source.

---

## PRODUCT SCHEMA FOR E-COMMERCE (Cromwell / brightonSEO)

### Mandatory Base Fields
- `name` (product title -- use attribute-first naming: "[key attribute] + [product type]")
- `description`
- `image`
- `offers` (price, availability, currency)
- `brand`
- `sku` or `gtin`

### Competitive Advantage Fields
- `aggregateRating` (star ratings in SERPs)
- `review` (individual reviews)
- `has-varying` / `product-varying` schema (significant performance increase -- brightonSEO case study)
- Shipping details
- Return policy

### Feed-to-Page Consistency (brightonSEO -- Lockwood)
**Mandatory for organic product grid visibility.**
- Price mismatches between feed and page cause disapprovals
- If feed price is lower than on-page price, product gets disapproved
- Quick check: compare valid items in Merchant Center listings vs product snippets in Search Console

### Case Study Results
74% increase in clicks, 15% increase in revenue from three optimizations alone: product titles, product schema, feed consistency.

---

## FAQ SCHEMA

### When to Use
- Pages with genuine FAQ sections
- Service pages with common questions
- Blog posts with structured Q&A sections

### Implementation
```json
{
  "@type": "FAQPage",
  "mainEntity": [{
    "@type": "Question",
    "name": "Question text here",
    "acceptedAnswer": {
      "@type": "Answer",
      "text": "Answer text here"
    }
  }]
}
```

### Best Practice
- Only add FAQ schema for questions genuinely answered on the page
- Do not fabricate questions just for schema -- Google penalizes mismatched markup
- FAQ dropdowns in SERPs increase visual real estate and CTR

---

## SCHEMA'S ROLE IN AI SEARCH (brightonSEO -- James Hocking)

### The Orchestrator Layer
- LLMs themselves do NOT directly process schema
- But the **orchestrator layer** (fetches and processes pages for the LLM) DOES use schema
- Without schema: orchestrator scrapes raw text, guesses content type, cannot find author/date
- With schema: orchestrator immediately grabs structured data, passes cleaner context to LLM

### Semantic HTML Also Helps
- Good semantic HTML (article tags, main tags, proper H1/H2, ARIA) helps orchestrator extract cleaner text
- Even without schema, semantic HTML improves AI search visibility

### Timeliness Triggers
- Fast-moving consumer goods with high purchase intent = LLM more likely to search web
- Enterprise/slow-cycle products = LLM relies on training data
- Update timestamps in schema to signal freshness

---

## SCHEMA VALIDATION PROCESS

### Two-Step Validation (Use BOTH)

**Step 1: schema.org Validator**
- URL: validator.schema.org
- Tests: structural correctness, property validity, nesting rules
- Does NOT test whether Google will show rich results

**Step 2: Google Rich Results Test**
- URL: search.google.com/test/rich-results
- Tests: whether YOUR specific schema qualifies for Google rich results
- May flag missing images (not a schema error -- rich results NEED images to display)
- Tests different things than schema.org validator

### Common Validation Issues
- Missing required fields (name, image for products)
- Incorrect nesting (items inside wrong parent type)
- URL formatting issues (relative vs absolute URLs)
- Date formatting mismatches
- Price/availability mismatches between page and schema

---

## LOCALBUSINESS SCHEMA HIERARCHY

For local/service businesses, use the most specific type:

| Business Type | Schema Type |
|---|---|
| General business | `LocalBusiness` |
| Financial advisor | `FinancialService` |
| Dentist | `Dentist` |
| Restaurant | `Restaurant` |
| Law firm | `LegalService` |
| Plumber | `Plumber` |
| Auto repair | `AutoRepair` |

Always check schema.org for the most specific subtype available. GPT is good at identifying the correct granular type.

---

## SEMANTIC SPIDER FRAMEWORK (Casey Keith)

Casey's schema implementation approach:

1. Ask: "What is the primary purpose of this page?" -> determines main schema type
2. Person entities need `Person` schema with `author`, `publisher` properties
3. Collection pages use `CollectionPage` with `hasPart` or `ItemList` via `mainEntity`
4. Individual project pages = `CreativeWork` with person as `author`
5. Portfolio pages = `CollectionPage` linking to individual `CreativeWork` pages
6. Always use schema.org validator AND Google Rich Results validator (test different things)

---

## SPECIFIC NUMBERS

| Metric | Value | Source |
|---|---|---|
| Product schema click increase | 74% | brightonSEO (Lockwood) |
| Product schema revenue increase | 15% | brightonSEO (Lockwood) |
| AI Overview informational keyword schema rate | 66% show AIOs | brightonSEO (Lockwood) |
| Commercial browsing product grid rate | 63% show grids | brightonSEO (Lockwood) |
| E-E-A-T schema properties | 6 (reviewedBy, citation, knowsAbout, hasCredential, ClaimReview, awards) | Casey Keith |
