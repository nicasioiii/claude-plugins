# Topical Authority Framework -- Complete Reference (Koray Gubur)

## THE COST-OF-RETRIEVAL THESIS

Core axiom: The cost of ranking a website cannot be higher than the cost of NOT ranking it.

**Practical implications:**
- A search engine satisfying 200K queries from one source costs less than 200K different sources
- Shorter URLs, clearer sentences, consistent templates = lower processing cost
- Google prefers the cheapest-to-serve source that meets quality thresholds
- Every optimization in this framework reduces the search engine's cost while increasing information value

---

## THE THREE PILLARS: VASTNESS, DEPTH, MOMENTUM

| Pillar | Definition | When to Emphasize | Case Study |
|---|---|---|---|
| **Vastness** | Number of entity-attribute pairs covered | Budget allows broad production | Visa site: 30+ countries |
| **Depth** | Granularity per attribute | Budget limited -- go deeper on fewer topics | Svalbard: 27 YMYL articles beat Healthline |
| **Momentum** | Publication frequency + crawl rate acceleration | Always | Patternless publishing keeps crawler attention |

**Decision rule:** Cannot go wider? Go deeper. Cannot go deeper? Go faster.

---

## TOPICAL MAP ANATOMY -- 5 COMPONENTS

### 1. Central Entity
- Appears in every article site-wide
- Examples: "Germany" (visa site), "water" (health site)
- Creates site-wide n-gram patterns across title tags, headings, internal links

### 2. Central Search Intent
- Overarching user purpose reflected in all content
- Expressed as predicates: "know + go" for visa site = visiting, learning, traveling, living
- Determines the contextual lens for all content

### 3. Source Context
- Brand identity + monetization model
- Determines which attributes are relevant to YOUR site
- Visa consultancy vs academic encyclopedia = same entity, different relevant attributes
- This is what separates a topical map from an encyclopedia

### 4. Core Section
- Monetizable heart of the topical map
- Deep coverage of attributes directly tied to source context
- Visa site: visa types, application requirements, processing times
- Water site: health benefits, purity methods, sourcing

### 5. Outer Section
- Broader entity attributes building topical relevance
- Politics, culture, geography (for Germany)
- Historical data accumulates here
- Links flow INWARD from outer to core sections

---

## RAW VS PROCESSED TOPICAL MAPS

**Raw topical map:** Entity + Attribute pairs only
- Example: "Germany religion," "Germany climate," "Germany economy"
- Quick to create but lacks implementation detail

**Processed topical map:** Verbalized with full implementation detail
- Macro context assignment, title tag methodology, URL structure
- Publication dates, internal link architecture
- Requires understanding contextual zones, knowledge domains, contextual layers
- Dramatically better results but much harder to create

---

## ATTRIBUTE FILTRATION -- THREE CRITERIA

| Criterion | Definition | Example (Entity: Germany) |
|---|---|---|
| **Prominence** | Can entity be defined without this attribute? If no = prominent | Population = prominent. Football league = not |
| **Popularity** | Does attribute have significant search demand? | Football league = popular. Population = popular |
| **Relevance** | Is attribute connected to YOUR source context? | Population = relevant (visa consultancy). Football = not |

**Priority rule:** Cover attributes scoring ALL three criteria first. Skip attributes that are popular but neither prominent nor relevant.

### Attribute Types for Question Generation

| Type | Definition | Priority |
|---|---|---|
| **Unique** | Appear in ONLY ONE instance (Paris = Eiffel Tower) | Highest -- use first for definitions |
| **Root** | Appear in ALL instances of entity class (every city has population) | High -- provide accuracy |
| **Rare** | Appear in SOME instances (not every city has beaches) | Medium -- qualify and signify |

---

## THREE-LAYER INFORMATION ARCHITECTURE

| Layer | Role | Example | Link Direction |
|---|---|---|---|
| **Root** | Connected to homepage, links to all seeds, highest quality | "What to know before going to Germany" | Receives PageRank from homepage |
| **Seed** | Mid-level articles linking to root and nodes | "Germany visa types" | Links up to root, down to nodes |
| **Node** | Individual entity-attribute articles | "Germany student visa requirements" | Links up to seeds |

**Key distinction:** Not silos, not hubs. Koray uses BOTH taxonomy (hierarchical) AND ontology (relational) simultaneously.

---

## QUALITY NODES -- THE AUTHORITY ACCELERATOR

Quality nodes are specific articles designed to exceed quality thresholds and force a re-ranking event.

**Properties:**
- Placed closest to homepage (linked directly from homepage)
- Target YMYL or competitive query networks where top authorities rank
- Extremely long, detailed, research-backed with citations, studies, expert quotes
- Multiple content formats: tables, lists, diagrams, infographics, scientific charts

**Three competitor columns per quality node:**
1. The site to be CLASSIFIED WITH (authority peer you want to be grouped with)
2. The site to OUTRANK (direct competitor)
3. An educational/government source (establishes factual grounding)

**CONTRARIAN:** Start with the hardest topics first. Most SEOs target easy keywords. Koray targets hardest YMYL queries to force classification alongside top authorities. Once classified as an authority peer, easier topics become trivial.

---

## PUBLICATION FREQUENCY (MOMENTUM) RULES

1. **Be patternless.** Never publish at regular intervals. Sometimes 3 articles in one day, then wait 4 days, then 7 articles, then 3 days.
2. **Never publish during core algorithm updates.** Wait for "flat algorithmic season."
3. **Initial launch:** 20+ articles simultaneously to create a state change the engine must re-evaluate.
4. **Crawl rate correlates with positive rankings.** More frequent crawling = fresher data = cheaper to rank you.
5. **Historical data accrues per article.** Publishing one-by-one lets earlier articles accumulate impressions/clicks that boost later articles.
6. **Sweet spot:** 20 articles initially, then "human-like" -- 2/day sometimes, 5/10-days other times.
7. **Do NOT publish 400-500 AI articles per day.** Bing will delist. Google will penalize eventually.

---

## CORE ALGORITHM UPDATE TIMING

**CONTRARIAN:** You will NOT see results until a core algorithm update.

- Before core update: traffic may drop even while optimizing
- After core update: traffic surges to new ceiling
- Each update creates new upper and lower bounds for rank-ability
- Average wait: ~6 months between core updates
- **Patience is mandatory.** Continue publishing during the wait.

---

## CONTEXTUAL DOMAINS AND KNOWLEDGE DOMAINS

- **Knowledge domain:** A field of knowledge (health, finance, education)
- **Contextual domain:** Connector between two knowledge domains using a shared entity/attribute
- **Contextual layer:** Adding specificity (e.g., "fruits for children" -> "fruits for children OVER SIX with SEVERE insomnia")

To traverse from knowledge domain 1 to domain 7, create a semantic path through intermediate domains. This shapes your topical map.

---

## URL STRUCTURE RULES

- Single words in URLs, never repeat words
- Shorter URLs preferred (if two duplicates exist with no canonical, Google picks shorter)
- URLs = first thing crawlers see; determine whether to crawl or skip
- URL hierarchy reflects contextual hierarchy: `/germany/life/culture/religion`
- Shared words across URL branches signal internal link connections

---

## ANTI-PATTERNS (Things That Destroy Rankings)

1. Creating concept maps instead of topical maps (mirroring SERPs vs changing perception)
2. Using encyclopedic structure without source context
3. Diluting macro context (50% of article on a tangential topic)
4. Breaking contextual vector (random topic jumps between headings)
5. Publishing 400+ AI articles per day
6. Same anchor text more than 3 times across SCN
7. Linking from supplementary content when main content exists
8. Going for easy keywords first (gets classified with low-quality blogs)
9. Publishing during core algorithm updates
10. Creating predictable publishing patterns
11. Boilerplate internal links (nav/sidebar carry less weight than in-content)
12. Opening new pages without sufficient search demand
