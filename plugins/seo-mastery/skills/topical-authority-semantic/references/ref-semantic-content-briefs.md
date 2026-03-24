# Semantic Content Briefs -- Complete Reference (Koray Gubur)

## CONTENT BRIEF ARCHITECTURE -- FOUR COLUMNS

### Column 1: Contextual Vector
- Ordered sequence of questions/headings from first to last
- Nothing is random; each heading connects to the next
- First heading to last must flow as one continuous, connected line of context
- Every subsection's last sentences create a "contextual bridge" to the next heading

**Question types used as headings:**
1. **Definitional** -- "what is X"; use at top for definitions
2. **Grouping** -- multiple instances with shared context; use for listicles
3. **Comparative** -- superlative/comparative words; use for comparisons
4. **Boolean** -- yes/no; use at bottom or as context expansions

**The rule:** The shortest grammatically correct question that specifies context is the best heading.

### Column 2: Contextual Hierarchy
- Heading levels (H1-H6) determine weight distribution
- H2 = high weight; H4 = lower prominence for less important links
- Top 9-10 headings of an article are the most important
- Bottom sections can be lower quality

### Column 3: Contextual Structure
- Format instructions for answering each question
- Options: table, list, paragraph, exact definitive answer, list definition + listing
- Correct format in the correct web page: if 5 pages mention "benefits of X," only ONE should use the structured list format

### Column 4: Contextual Connection
- Internal links with anchor text
- Annotation text (text surrounding the anchor)
- Link placement rules
- Red-colored links = article not yet written (placeholder for future link)

---

## CONTEXTUAL VECTOR RULES

### Flow Requirements
- First heading to last: one continuous connected line of context
- No jumps or disconnections between sections
- Each heading must bridge from the previous one

### Contextual Bridges
- Last sentences of each subsection create the bridge to the next heading
- If you extract one key sentence from each subsection and they form a coherent summary, the flow is correct
- If they do not form a coherent summary, the article has broken context

---

## MACRO CONTEXT VS MICRO CONTEXT

**Macro context** = main content area
- ~70-80% of document
- Processes the primary entity-attribute pair
- Most important anchor text appears here
- All answer terms, context terms, topical entries appear here

**Micro context** = supplementary content area
- ~20-30% of document
- Processes related but slightly different topics
- Creates contextual bridges to other articles
- Uses antonyms, related entities, alternative contexts
- Internal links to other nodes placed here

**Critical rule:** The line between macro and micro is NOT at the midpoint. Most of the document is macro context.

**Test for correct coverage:** If an AI summarizer described your article and did not mention your main purpose, the coverage is wrong.

---

## RELEVANCE CONFIGURATION (MICRO-SEMANTICS)

Koray's most distinctive technique: changing word order within sentences to increase relevance.

**Example:** For query "financial advisor" in family context:
- "Financial advisor helps families achieve financial independence" = higher relevance for "financial advisor"
- "Families achieve financial independence with the help of a financial advisor" = higher relevance for "families"

**The rule:** Put the target entity/concept earlier in the sentence for heavier weight.

Even 0.1% relevance increase per sentence, multiplied across 1 million sentences in a content network, creates massive cumulative advantage.

---

## ALGORITHMIC AUTHORSHIP RULES (14 CORE)

Koray has 200+ rules; 39-40 implementable with human authors. The 14 most critical:

1. **Be certain.** "Sun rises every day" = fact. "Sun will rise tomorrow" = opinion. Never use will/should/may for facts.
2. **Cut the fluff.** Every word must have contextual relevance. Remove filler and purposeless qualifiers.
3. **Use numeric values.** "6 severe symptoms" not "many symptoms." Expertise requires numbers, percentages, units.
4. **Understand verb contexts.** "Increase" = health. "Improve" = health + skill. "Develop" = skill only. Match verb to contextual domain.
5. **Give examples after every enumeration.** Don't say "40 cryptocurrencies on Coinbase" -- name them.
6. **Use part-of-speech tags in lists.** If question starts with "how to," every list item starts with a verb.
7. **Optimize subordinate text.** First sentence after a heading is critical. If not responsive, engine may skip entire section.
8. **Put conditions at the end.** "Do X because Y" not "If Y, do X." Lead with instruction/declaration.
9. **Match anchor text to target page title.** Anchor text phrase must appear in both source heading and target page H1.
10. **Do not delay the answer.** If asked "benefits of vision boards," do not define vision boards first.
11. **Bold the answer, not the search term.** Query = "what is a penguin" -> bold "flightless seabird," not "penguin."
12. **Be cheaper for the search engine.** Clearer sentences = lower processing cost = higher rank.
13. **Use consensus language.** Align with dominant factual consensus. Deviate only after achieving authority.
14. **Declaration-Evidence pattern.** State answer, then support with research/citation. Repeat.

---

## CONTENT FORMAT SELECTION RULES

- **Correct format in correct web page:** If 5 pages mention "benefits of drinking water," only ONE uses structured list format (where it is the macro context).
- **First structured element (table/list) must appear in macro context.** Placing it in supplementary content signals the wrong page.
- Tables use Entity-Attribute-Value structure -- semantic triples in visual form.

---

## THE SEMANTIC CONTENT NETWORK (SCN) -- SCALING

The SCN is the collection of all content briefs for all entities of the same type.

### Template Principle
Create ONE content brief template for a class of entities (e.g., all European countries). Apply uniformly, varying only for unique/rare attributes.

**Benefits of templating:**
- Same heading order across all entities reduces management cost
- If one question position consistently fails, swap it across ALL briefs simultaneously
- Track performance across SCN to identify which positions, formats, or links need adjustment

### Entity-Specific Queries
Even if a query does not exist as a search term (e.g., "religion in France"), it IS a valid phrase taxonomy derived from a known query ("religion in Germany"). The template approach ensures coverage.

---

## TITLE TAG WRITING METHODOLOGIES

| Pattern | Example | Use Case |
|---|---|---|
| **Conjunctive (and)** | "Costs and Conditions of Living in Germany" | Conditional synonym phrases |
| **Entity set + attributes** | "German Singers: Works and Awards" | Plural entity with root attributes |
| **Mixed** | "German Literature and Writers" | Entity + highly relevant unnamed entity |
| **Class + instances** | "German Celebrities: Poets, Authors, Actors" | Hypernym + hyponyms |

**Site-wide signal:** Aggregate all words across all title tags to see site-level topicality. Core section titles repeat key terms; outer section titles vary for breadth.

---

## IMAGE OPTIMIZATION FOR SEMANTIC SEO

- **Image URLs:** 2-3 words max, no stop words, most important context terms
- **Image alt tags:** Verbalized expansion of URL terms; include context terms not in page URL or title
- **Featured images:** Must be unique (first image engine has seen), text overlay (shorter H1), brand mark, license the image
- **Central object in image** should match alt tag
- Check indexing with `src:` search operator
- Alt tags consolidate macro context by overlapping phrase patterns with title and URL

---

## META DESCRIPTION STRATEGY (KORAY)

Not a ranking factor but serves as:
1. **Document flow preview:** Reflect the order of your contextual vector
2. **Context term distribution:** Include vocabulary variations not in title tag
3. **Micro context signal:** Place supplementary topic at end to signal its position

Whatever order content appears in document, reflect that same order in meta description.

---

## INTERNAL LINK CONFIGURATION RULES

1. Most important anchor text in the **root** document
2. First anchor text in a document has most weight; last has least
3. Put distance between links -- one link per heading section, not clusters
4. Top 9-10 headings are most important. Bottom sections can be lower quality.
5. Fewer links per page = more weight per link
6. **Anchor text must appear in target page's H1** AND in source page's heading section
7. Same anchor text maximum 3 times across entire SCN
8. **No reciprocal links by default.** Only link back when PageRank return is strategically justified.
9. Justify every internal link with contextual relevance -- mention concept 1-5 times near the link

---

## DATA-TO-WEBSITE FUTURE (Koray's Predicted Workflow)

1. Fine-tune a language model on your domain
2. Create a topical map
3. Create a semantic content network
4. Generate content with the LLM
5. Expert human reviews and modifies
6. Improve knowledge base iteratively
7. Make knowledge base conversational (site-specific AI chatbot)
