# Entity Optimization -- Complete Reference (Casey Keith + Koray Gubur)

## ENTITY-ATTRIBUTE-VALUE (EAV) MODEL (Casey Keith)

Core framework for structured on-page content using HTML tables.

| Column 1 (Entity) | Column 2 (Attribute) | Column 3 (Value) |
|---|---|---|
| Emergency services | 24-hour availability | Yes |
| X-rays | Type | Digital |
| Braces | Follow-up interval | Quarterly |

**Key insight:** EAV tables are semantic triples in visual form. Subject-Predicate-Object = Entity-Attribute-Value. Every table feeds the search engine structured data parseable without schema markup.

**Practical uses:**
- Service comparison tables (features by version)
- Product specification tables
- Yes/no service availability matrices
- Recommended product lists with brand entities

**CONTRARIAN:** Even listing brands you DON'T serve creates entity associations. "We don't repair Ferrari" still associates your business with Ferrari as a named entity.

---

## ENTITY SALIENCE (Casey Keith -- Google Research Paper)

From "A New Entity Salience Task with Millions of Training Examples" (Dunietz & Gillick):

- **Entity salience** = importance of an entity within a document
- Coreference-based features (how often entity is referenced, even by pronoun) outperform simple word count
- **First-sentence presence is a strong salience signal**
- Entity centrality (PageRank-style computation on co-occurring entities) provides additional improvement

**Practical rule:** Place primary entity in the first sentence. Reference it frequently using both the entity name and pronouns/synonyms throughout.

---

## KEYWORD AND ENTITY PLACEMENT FRAMEWORK (Casey)

| Location | What Goes There |
|---|---|
| **H1** | Primary keyword/entity at the beginning. E.g., "Trusted [Service] in [City]" |
| **H2s** | Secondary keywords/entities, placed early in headers |
| **Topic sentences** | Start with primary or secondary keywords/entities |
| **Body** | Use keywords naturally; avoid stuffing |

### Template Structure
```
H1: Trusted [Service] in [City]
  H2: Emergency [Service] in [City]
    Topic sentence: [City] [service] providers offer 24/7 emergency...
  H2: Residential [Service] in [City]
    Topic sentence: ...
```

---

## GOOGLE SEMANTIC SUGGESTIONS AS FREE RESEARCH (Casey)

Methods for finding semantically related terms without paid tools:

1. **SERP bold terms:** Google bolds related terms in results = terms Google considers semantically equivalent
2. **Google Images top bar:** Shows semantically related concepts as filter chips
3. **Google Videos "related topics":** Related topics from embedded videos
4. **PAA scraping:** Chrome extension "PAA Scraper" extracts 30+ questions. Each PAA generates 3 sub-questions when expanded.

**CONTRARIAN:** Most paid semantic SEO tools just scrape Google's bold highlights and repackage them. The source data is free.

---

## PAA AS GOOGLE'S BETA TEST (Casey)

- PAA is Google's way of beta-testing new content
- Google offers alternatives when unsure main results answer your query
- Click + stay = validates content. Bounce = downgrades it.
- ~20% of daily queries are brand new. PAA tests content against novel queries.
- Most PAA results from content published within last 90 days
- PAA = content audition system

**Practical use:** PAAs become H2 subsections OR separate supporting articles. Decision: is the PAA broad enough for its own article?

---

## TOPICAL MAPS VIA "THINGS TO KNOW" (Casey)

1. Search your topic in quotes (exact match)
2. Google shows "Things to Know" sections with subtopics
3. Each subtopic = potential article or major section
4. Follow "Related Searches" at bottom for adjacent articles
5. Repeat for each subtopic to build complete content silo

---

## E-E-A-T IMPLEMENTATION FRAMEWORK (Casey)

### Experience
- "Practical familiarity" (official Google definition)
- Demonstrate through: years in industry, journeyman background, specific project history
- If lacking direct experience, relate to analogous local/personal experience
- Working knowledge counts -- does not require hands-on application

### Expertise
- Cite your sources. Follow academic citation practices.
- Point to closest-to-source data: manufacturer specs > peer-reviewed > aggregator > blog
- Match cited sources with Google Knowledge Graph entries when possible
- **Schema properties:** `reviewedBy`, `citation`, `hasCredential`

### Authoritativeness
- Earned through others citing you: backlinks, academic citations, industry mentions
- Put industry citations in schema ("named in Top 10 SEO list")
- Google Knowledge Graph likely uses citation cross-referencing for entity profiles

### Trustworthiness
- HTTPS, HSTS preloading
- Transparency page: employee counts, fair trade, quarterly reports
- Return/RMA policies, contact information, business address
- Material hazard data sheets (creates downloadable content = engagement signal)
- Author bios with real credentials

---

## SCHEMA TYPES FOR E-E-A-T (Casey)

Six schema.org properties directly supporting E-E-A-T:

1. **`reviewedBy`** -- who reviewed the content
2. **`citation`** -- sources cited in content
3. **`knowsAbout`** -- author's area of expertise
4. **`hasCredential`** -- certifications, degrees, licenses
5. **`ClaimReview`** -- fact-checking markup; gets checkmark badge in SERPs
6. **`awards`** -- industry awards

**ClaimReview hack:** Cited source does not need to be major publication. A credible Facebook post technically counts as cited source backing a claim.

---

## KNOWLEDGE GRAPHS AS GLOSSARIES (Casey)

### The Cascade
Wikipedia -> Wikidata (owned by Google) -> Google Knowledge Graph -> RankBrain -> Search Results

### Implementation
1. Create glossary page with definitions for every entity/term you use
2. Source from Wikipedia but REWRITE for original content (use summarization tool)
3. In schema: point entity definitions to YOUR glossary first, then Wikipedia/Wikidata

**Critical rule:** Always point to your OWN definition first in schema. Large corporations do this. Google stops evaluating at first authoritative source -- cite yourself first.

### Agency Knowledge Graph Strategy
- Add every client's glossary terms to your agency knowledge graph
- In client schema: point to BOTH Wikipedia/Wikidata AND your agency KG
- Permanently embeds your agency as a cited authority on every client site

### Practical Workflow
1. Go to Wikipedia page for your niche (e.g., "Roofing")
2. Extract all linked entities using bookmarklet -> spreadsheet
3. Import URLs into summarization tool for original summaries
4. Import summaries via CSV into WordPress glossary plugin
5. Plugin auto-pulls Wikipedia definitions to supplement

---

## GOOGLE STACKING -- GOOGLE DRIVE ENTITY STRATEGY (Casey)

Using Google's own properties (DA 100) for entity reinforcement:

**Properties to use:**
- Google Docs: one article per service per city; hyperlinks to specific anchor text on your site
- Google Sheets: structured data (NAP, map data, sitemap mirror)
- Google Slides: presentations on safety, benefits, risks
- Google My Maps: custom maps with pins; pre-fill destination address to your business
- PDFs: Material hazard data sheets, product specs, downloadable guides

**Rules:**
1. Share folder publicly
2. Link back to exact service pages with proper anchor text
3. Include business name, address, logo; label everything
4. Use unique images
5. Link to Google Drive from "Helpful Information" footer menu on website
6. Stack across ALL Google properties

**Competitive tactic:** Place Google Maps pins ON TOP of competitor locations. When someone near competitor searches, your pre-filled directions lead them to your client.

---

## HEADING VECTORS (Google Patent -- Casey)

From Google's patent "Context scoring adjustments for answer passages":

- Google uses heading tags (H1-H6) to create "heading vectors" (mathematical content hierarchy representations)
- These vectors determine: relevance matching, thin/spam detection, UX priority
- **Rules:**
  - Use headings only when structurally necessary
  - Each heading must be unique
  - Maintain strict hierarchical order (H1 > H2 > H3)
  - Headings must accurately describe content below
  - Descriptive headings aligned with page theme rank better than generic ones

---

## RDF SEMANTIC TRIPLES (W3C Foundation)

- **Subject-Predicate-Object** = atomic unit of meaning on the web
- Resources (anything with URI) + Properties (characteristics) + Statements (assertions) form triples
- Powers: Linked Data, Semantic Search, Knowledge Graphs
- Every piece of structured data, schema markup, entity relationship reduces to triples
- Casey's simplification: an EAV table IS a set of semantic triples in visual form

---

## WHERE KORAY AND CASEY AGREE

1. **Entities > Keywords.** Both center on entity optimization.
2. **Source context determines relevance.** Brand identity filters which attributes matter.
3. **Structured data = semantic triples.** Both use EAV in different forms.
4. **Definitions are power.** Both aim to be the definitional authority.
5. **Cost reduction principle.** Both aim to reduce what the search engine must process.
6. **Internal links carry most ranking weight.** Both emphasize strategic internal linking.
7. **Quality thresholds > keyword difficulty.** Both reject simple KD scores.
8. **PAA/query networks build topical maps.** Both use Google's suggestions for architecture.

## WHERE THEY DIFFER

| Aspect | Koray | Casey |
|---|---|---|
| Approach | Theory-first; reads patents 7 hours/day | Practice-first; reverse-engineers from SERPs |
| Content creation | Manual 200-rule algorithmic authorship | AI-assisted with human editing |
| Schema emphasis | Minimal (content structure IS schema) | Heavy (schema.org as primary entity signal) |
| Knowledge graphs | Implicit through content | Explicit through glossary + schema |
| Backlinks | Ranks without them | Google Stacking for DA-100 links |
| Focus | National/international niche sites | Local SEO, service-area businesses |
| Complexity | Extremely dense, linguistic aptitude required | Accessible, designed for agency operators |
