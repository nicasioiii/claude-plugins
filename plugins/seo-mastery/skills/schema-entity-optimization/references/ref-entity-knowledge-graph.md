# Entity & Knowledge Graph Strategy -- Complete Reference

## BUILDING YOUR OWN KNOWLEDGE GRAPH (Casey Keith)

### The Cascade
Wikipedia -> Wikidata (owned by Google) -> Google Knowledge Graph -> RankBrain -> Search Results

Understanding this cascade is critical: Google's Knowledge Graph is built primarily from Wikipedia/Wikidata. If you can position your definitions alongside or ahead of Wikipedia's, you gain entity authority.

### Implementation: Glossary-as-Knowledge-Graph

**Step 1: Create Glossary Page**
Build a glossary on your website with definitions for every entity/term you use.

**Step 2: Source and Rewrite**
Source definitions from Wikipedia but rewrite for original content. Use summarization tools for unique phrasing.

**Step 3: Schema Pointing**
In your schema markup, point entity definitions to YOUR glossary FIRST, then to Wikipedia/Wikidata.

**Critical rule:** Always cite your OWN definition first. Large corporations (Apple, Dell, Microsoft) do this. Google stops evaluating at the first authoritative source. If you cite yourself, your site becomes the authority for that definition.

### Practical Workflow
1. Go to Wikipedia page for your niche (e.g., "Roofing")
2. Extract all linked entities using a bookmarklet that copies entities + URLs to spreadsheet
3. Import URLs into summarization tool; generate unique summaries
4. Import summaries via CSV into WordPress glossary plugin
5. Plugin auto-pulls Wikipedia definitions to supplement your originals
6. Add schema markup pointing to your glossary entries first

### Agency Knowledge Graph Strategy
- Add every client's glossary terms to your agency knowledge graph too
- In client schema: point to BOTH Wikipedia/Wikidata AND your agency's KG
- This permanently embeds your agency as a cited authority on every client site
- Compounds over time as more clients = more entity authority for your agency

---

## GOOGLE STACKING -- GOOGLE DRIVE ENTITY STRATEGY (Casey Keith)

Using Google's own properties (all DA 100) for entity reinforcement.

### Properties to Use

**Google Docs:**
- One article per service, per city
- Include hyperlinks to specific anchor text on your website
- Write genuine, useful content (not thin placeholder text)

**Google Sheets:**
- Structured data: NAP information, map data, sitemap mirror
- Tables with entity-attribute-value structure

**Google Slides:**
- Presentations on safety, benefits, risks relevant to your service
- Include images, citations, and links back to your site

**Google My Maps:**
- Custom maps with pins for your business locations
- Pre-fill destination address to direct users to your business
- **Competitive tactic:** Place pins ON TOP of competitor locations

**PDFs:**
- Material hazard data sheets (legally required for service businesses using chemicals)
- Product specs and downloadable guides
- Creates engagement signal (downloads)

### Google Stacking Rules
1. Share folder publicly (accessible to crawlers)
2. Link back to exact service pages with proper anchor text
3. Include business name, address, logo; label everything
4. Use unique images (not stock photos)
5. Link TO Google Drive from a "Helpful Information" footer menu on your website
6. Stack across ALL Google properties (not just one)

### Why It Works
- All Google properties have DA 100
- Google crawls its own properties more frequently
- Links from Google properties are treated as legitimate citations
- Creates entity reinforcement across multiple Google-owned platforms
- Low risk: you are using Google's own tools for their intended purpose

---

## WIKIPEDIA-WIKIDATA-KNOWLEDGE GRAPH RELATIONSHIP

### How Google Builds Knowledge Panels
1. Entity mentioned on Wikipedia
2. Wikipedia entity mapped to Wikidata entry
3. Wikidata feeds Google Knowledge Graph
4. Knowledge Graph entries may earn Knowledge Panels
5. Knowledge Panel appearance = Google recognizes your entity

### Influencing Knowledge Panels (Indirect)
- Cannot directly edit Knowledge Graph
- CAN improve Wikipedia presence (following Wikipedia guidelines)
- CAN improve Wikidata entries (structured data about your entity)
- CAN cite authoritative sources that mention your entity
- Schema markup on your site helps Google connect your content to KG entries

---

## RDF SEMANTIC TRIPLES FOUNDATION

From W3C's RDF specification:
- **Subject-Predicate-Object** = the atomic unit of meaning on the web
- Resources (anything with a URI) + Properties (characteristics) + Statements (assertions)
- Powers: Linked Data, Semantic Search, Knowledge Graphs

### Practical Application
Every piece of structured data, every schema markup, every entity relationship reduces to triples:
- "Acme Plumbing" (subject) "offers" (predicate) "24-hour emergency service" (object)
- "Dr. Smith" (subject) "hasCredential" (predicate) "Board Certification in Dermatology" (object)

Casey's simplification: an EAV table IS a set of semantic triples in visual form.

---

## ENTITY SALIENCE OPTIMIZATION

### First-Position Rule (Casey -- Google Research)
From "A New Entity Salience Task" (Dunietz & Gillick):
- Entities in the first sentence are weighted as most salient
- Coreference (how often entity is referenced, even by pronoun) outperforms word count
- Place primary entity in first sentence, reference frequently

### On-Page Entity Placement
| Position | What to Place |
|---|---|
| First sentence of page | Primary entity name |
| H1 | Primary keyword/entity at beginning |
| H2s | Secondary entities, front-loaded |
| Topic sentences | Start with primary/secondary entity |
| Throughout body | Natural references including pronouns and synonyms |

---

## SEMANTIC SPIDER FRAMEWORK (Casey)

Schema implementation decision tree:

1. **What is the primary purpose of this page?** -> determines main schema type
2. **Is there a person entity?** -> add `Person` schema with `author`, `publisher`
3. **Is it a collection/list page?** -> `CollectionPage` with `hasPart` or `ItemList`
4. **Is it a single creative work?** -> `CreativeWork` with person as `author`
5. **Is it a portfolio?** -> `CollectionPage` linking to individual `CreativeWork` pages
6. **Is it a local business page?** -> most specific `LocalBusiness` subtype

### Validation Rule
Always use BOTH:
- schema.org validator (structural correctness)
- Google Rich Results Test (rich result eligibility)

They test DIFFERENT things. A page can pass one and fail the other.

---

## HEADING VECTORS AND ENTITY SIGNALS (Google Patent)

From "Context scoring adjustments for answer passages":

Google creates mathematical representations ("heading vectors") from H1-H6 tags.

**What heading vectors determine:**
- Content relevance matching to queries
- Detection of thin/spam content
- UX priority in rankings

**Rules from the patent:**
- Use headings only when structurally necessary
- Each heading must be unique
- Maintain strict hierarchical order (H1 > H2 > H3)
- Headings must accurately describe content below
- Descriptive headings aligned with page theme rank better than generic ones

---

## SCHEMA FOR AI SEARCH -- ORCHESTRATOR LAYER

### Key Insight (brightonSEO -- James Hocking)
LLMs do NOT directly process schema. But the orchestrator layer that fetches and processes pages for LLMs DOES use schema.

**Without schema:** Orchestrator scrapes raw text, guesses content type, cannot find author/date/structure.
**With schema:** Orchestrator immediately grabs structured data, passes cleaner context to LLM.

### Implications
1. Schema increases your chances of being cited by AI search
2. Good semantic HTML also helps (article tags, proper H1/H2, ARIA markup)
3. Timeliness triggers web search: fast-moving products = LLM more likely to search = schema more impactful
4. Update `dateModified` in schema regularly

### What Does NOT Help
- llms.txt has no measurable impact (brightonSEO data)
- Schema.org validator passing does not guarantee AI citation
- AI crawlers still do not interact with JavaScript -- duplicate data in HTML
