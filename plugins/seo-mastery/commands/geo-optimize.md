---
name: "GEO Optimize"
description: "Optimize content for AI search engines (ChatGPT, Perplexity, Google AI Overviews, Gemini). Applies fact optimization, FAQ mirroring, meta description spoiling, semantic URL review, and schema enhancements for maximum LLM citation probability."
triggers:
  - geo optimize
  - optimize for AI search
  - AI search optimization
  - ChatGPT optimization
  - Perplexity optimization
  - AI Overview optimization
  - GEO audit
  - LLM citation optimization
for:
  - Content teams optimizing existing pages for AI search visibility
  - SEOs running GEO audits on key landing pages
  - Brands building citation strategies across LLM platforms
exclusions:
  - Traditional SEO audits (crawl, indexation) -> use /seo-audit
  - Content creation from scratch -> use /write-content
  - Monthly performance reporting -> use /seo-report
  - Keyword research -> use /research-keywords
---

# /geo-optimize -- Optimize Content for AI Search Engines

**Type:** Slash command
**Purpose:** Audit and optimize a page (or set of pages) for maximum AI search citation probability across ChatGPT, Perplexity, Google AI Overviews, Gemini, and Grok
**Duration:** 45-90 minutes per page
**Skills activated:** `geo-ai-search-optimization`, `schema-entity-optimization`, `on-page-optimization`

---

## What This Command Does

Takes an existing page and systematically optimizes it for AI search engines using the brightonSEO 2025 GEO framework. Produces a prioritized set of changes with expected impact.

**Outputs:**
1. GEO audit scorecard (current state assessment)
2. Fact-optimized content revisions
3. FAQ mirror section (AI-extractable Q&A)
4. Spoiled meta description
5. Schema enhancement recommendations
6. Brand mention distribution plan

---

## How to Use

**In Claude Code:**
```
/geo-optimize
```

**You'll be asked for:**
1. URL of the page to optimize (or paste the content)
2. Target keyword / query
3. Primary LLM target (ChatGPT, Perplexity, Google AI Mode, or all)
4. Business type (SaaS, e-commerce, local service, content/media)

---

## The GEO Optimization Workflow

### Phase 1: Audit (Current State Assessment)

Score the page on each GEO factor:

| Factor | Check | Score (0-3) |
|--------|-------|-------------|
| **Semantic URL** | Is the slug 5-7 words, natural language? | |
| **Meta description spoiling** | Does meta contain the direct answer/claim? | |
| **Recency signal** | Does title/H1 include current year (if time-sensitive)? | |
| **Fact density** | How many self-contained claim sentences per section? | |
| **FAQ section** | Does page mirror key facts in FAQ format at bottom? | |
| **Answer blocks** | Are key answers in 40-60 word self-contained blocks? | |
| **JS dependency** | Can key content be read without JavaScript? | |
| **Comparison format** | Does page include listicle/comparison elements? | |
| **Author bio** | Real person with schema, not AI persona? | |
| **Schema markup** | Structured data helping orchestrator layer? | |

**Scoring:** 0 = absent, 1 = partial, 2 = good, 3 = optimized
**Total possible:** 30 points

**Priority tiers:**
- 25-30: Well-optimized for GEO (maintain and monitor)
- 18-24: Good foundation (address gaps for quick wins)
- 10-17: Significant optimization needed (prioritize top 5 factors)
- 0-9: Major rebuild required (start with technical foundation)

### Phase 2: Fact Optimization

**Step 1: Identify existing facts**
Highlight every self-contained claim sentence in the current content. Count fact density per section.

**Step 2: Increase fact density**
Rewrite vague or filler paragraphs to include specific, extractable claims:

Before: "It's important to consider your budget when choosing a CRM."
After: "The average CRM costs $12-$150 per user per month, with enterprise plans exceeding $300. For teams under 10 people, tools under $50/user deliver 90% of the functionality."

**Step 3: Position facts strategically**
- Strongest facts above the fold (first 2 paragraphs)
- 50-60 word summary snippet at page top
- Each H2 section should open with a fact, not a transition

### Phase 3: FAQ Mirror

Create 3-4 Q&A entries for the bottom of the page that mirror key facts from the body:

**Rules:**
- Question-format H2 or H3 headers
- Each answer: 2-3 sentences, self-contained
- Answers should be extractable independently (no "as mentioned above" references)
- Match how users ask AI systems ("What is the best X for Y?")

### Phase 4: Meta Description Spoiling

Rewrite the meta description to contain the direct answer/claim:

**Before:** "Learn about the best CRM options for small businesses in our comprehensive guide."
**After:** "HubSpot CRM is the best free CRM for small businesses under 10 employees, with Salesforce Essentials ($25/user/mo) best for teams needing advanced automation."

The spoiled meta tells ChatGPT's WebGPT filter that this page contains a direct, useful answer -- increasing the chance it gets fetched and cited.

### Phase 5: Schema Enhancement

Recommend schema additions that help the AI orchestrator layer:

- **Article schema** -- with author, datePublished, dateModified
- **FAQ schema** -- for the FAQ mirror section
- **HowTo schema** -- for step-by-step content
- **Review/Rating schema** -- for product comparisons
- **Author schema** -- linked to real person with credentials

> Read `schema-entity-optimization` reference files for implementation details.

### Phase 6: Brand Mention Distribution Plan

For the optimized page, create a distribution plan:

| Platform | Action | Expected Impact |
|----------|--------|----------------|
| Reddit | Post/comment in relevant subreddit with page insights | LLM training data + direct citation |
| LinkedIn | Publish Pulse article summarizing key findings | AI search indexing + brand mention |
| Quora | Answer related questions citing page data | Google AIO citation (0.5% of AIO sources) |
| YouTube | Create short video summarizing key facts | Video citation in AI Overviews |
| Review platforms | Ensure brand presence on Trustpilot (ChatGPT) and G2 (AIO) | Platform-specific citation |

---

## Output Format

### Deliverable 1: GEO Audit Scorecard
Markdown table with scores for all 10 factors, total score, and priority tier.

### Deliverable 2: Optimized Content Sections
Rewritten paragraphs with increased fact density, answer blocks, and summary snippet.

### Deliverable 3: FAQ Mirror Section
3-4 Q&A entries ready to add to page bottom.

### Deliverable 4: Spoiled Meta Description
Rewritten meta description (150-160 characters) containing the direct answer.

### Deliverable 5: Schema Recommendations
JSON-LD snippets for recommended schema additions.

### Deliverable 6: Distribution Plan
Platform-by-platform action items for brand mention building.

---

## Tips

- Run on your top 10 organic pages first (highest ROI)
- Re-run after 30 days to measure citation changes
- Test target queries in ChatGPT and Perplexity before AND after optimization
- Pair with `/seo-report` to track AI visibility metrics over time
- For e-commerce product pages, product grid optimization may matter more than GEO -- see `ecommerce-seo`
- For local service pages, combine with Reddit Sniper data from `ai-seo-content-automation`
