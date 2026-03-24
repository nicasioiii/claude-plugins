---
name: "GEO & AI Search Optimization"
description: >
  MANDATORY TRIGGERS: GEO, generative engine optimization, AI search, AI Overviews, ChatGPT ranking,
  Perplexity optimization, LLM visibility, AI citations, AI mode, AIO, mentions as backlinks,
  brand mentions for AI, AI search branding, relevance engineering.
  FOR: Optimizing content for AI-powered search engines (ChatGPT, Perplexity, Google AI Overviews,
  Gemini, Grok). Measuring or improving AI search visibility. Building citation strategies across
  LLM platforms. Adapting content to the probabilistic search era.
  Do NOT use for: Traditional on-page SEO mechanics (use on-page-optimization), schema markup
  implementation (use schema-entity-optimization), GA4 analytics setup and dashboards
  (use seo-analytics-reporting), technical crawlability fixes (use technical-seo-audit).
---

# GEO & AI Search Optimization

Generative Engine Optimization is the practice of making content discoverable, citable, and authoritative within AI-powered search engines. This is not "just SEO" -- 81% of ChatGPT citations do NOT overlap with Google's top results.

## Core Thesis

Search has shifted from **deterministic to probabilistic**. The same query can produce different results each time. AI search answers come from a content ecosystem (Reddit, YouTube, multiple page passages), not single pages. Think "raffle tickets" -- you want as many entries as possible across platforms.

AI search channels are **branding channels, not performance channels**. Impressions matter more than clicks. Average AI search CTR is 0.1%, but conversion rates from AI search visitors equal organic traffic conversion rates -- fewer but better-qualified visitors.

## When to Read Reference Files

Before optimizing any content for AI search:
- Read **ref-geo-fundamentals.md** for how each LLM selects sources, the 81% non-overlap data, and platform-specific preferences
- Read **ref-geo-implementation.md** for the technical requirements, "facts" optimization strategy, FAQ mirroring, and AI Overview measurement

## The AI Search Landscape (brightonSEO 2025 Data)

### Key Statistics

| Metric | Value | Source |
|--------|-------|--------|
| ChatGPT-Google citation overlap | 19% only | Profound (4B citations) |
| Semantic URL citation boost | +11.4% | Profound top 50K vs bottom 50K |
| Listicle share of all AI citations | 25% | Profound (2.6B citations) |
| AI search average CTR | 0.1% | PromptWatch |
| AIO prevalence (US commercial) | 19% of SERPs | STAT/Moz |
| AIO click-through rate | ~1% of users | Pew Research |
| LLM customer acquisition (Surfer case) | 22% of new customers | Surfer internal |
| Wikipedia traffic change after AIOs | -34.5% | iPullRank |
| Adults using LLMs | 52%, 34% daily | iPullRank |
| ChatGPT weekly active users | 800M | iPullRank |

### The Fundamental Shift

1. **81% of ChatGPT citations do NOT appear in Google's top results** -- traditional SEO does not map 1:1 to AI search
2. **Google positions 5-10 are as valuable as 1-3 in AI search** -- flips the traditional click-curve model
3. **Different LLMs cite different pages AND different domains** for the same prompts -- no single optimization strategy works everywhere
4. **Mentions are the new backlinks** -- unlinked brand mentions in context matter more than hyperlinks for AI citations
5. **llms.txt has no measurable impact** -- multiple independent studies confirmed this (use robots.txt for LLM crawlers)

## The Three-Layer GEO Framework

### Layer 1: Technical Foundation (Be Crawlable by AI)

AI crawlers have different requirements than Googlebot:

- **No JavaScript dependency** -- AI crawlers do NOT interact with JS. Duplicate key data as HTML tables alongside JS visualizations
- **Server response time under 300ms** -- static pages preferred
- **Semantic URLs**: 5-7 word natural-language slugs get 11.4% more citations
- **Three ChatGPT bot types**: citation bot (real-time queries, most important), search bot (web search phase), training bot (model training)
- **Most crawled page types by AI bots**: (1) Homepage, (2) Listicles, (3) Statistics/unique data pages, (4) Free tools, (5) Downloadable content

> **Cross-reference:** For technical implementation of server response optimization, see `technical-seo-audit`. For schema markup that helps the AI orchestrator layer, see `schema-entity-optimization`.

### Layer 2: Content Optimization (Be Selected by AI)

The single most impactful optimization: **"facts"** -- self-contained sentences that make a claim or statement.

**Fact optimization rules:**
- Pages with higher fact density rank higher in both SERPs and LLM citations
- Facts above the fold carry slightly more weight
- Mirror key facts in FAQ sections at page bottom -- LLMs show a strong preference for reading FAQ sections
- Each FAQ answer should be 2-3 sentences answering a single user-intent question
- Use 40-60 word answer blocks (sweet spot for both users and AI retrieval)
- Keywords are less important than facts for LLM optimization

**Meta description strategy ("spoil your content"):**
- Put the answer directly in the meta description
- Highly cited pages do this explicitly
- Example: "The best business credit card is [Brand X]" in the meta
- ChatGPT's WebGPT model decides whether to fetch a page based on URL, title, and meta description ALONE

**Recency signals:**
- ChatGPT appends the current year to 20-30% of fan-out queries
- Having the year in your title/H1 significantly increases citation probability
- AI search cites new content within days (1840 & Co case study: top-cited within one week)

**Format preferences:**
- 25% of all AI search citations are listicles and comparative content -- a 2x skew
- Comparison-style content ranks very well in Google AI Overviews
- Build comparison tables directly from research data

> **Cross-reference:** For content production workflows, see `content-production`. For Reddit-based pain point mining that feeds comparison content, see `ai-seo-content-automation`.

### Layer 3: Brand & Distribution (Be Mentioned Everywhere)

AI search rewards **brand presence across the content ecosystem**, not just your own site.

**Brand as ranking factor:**
- Branded traffic is highly active in the last 3-6 months while non-branded is struggling
- Editorial mentions (even unlinked) can trigger AI citations
- Brand mentions in the right context establish category authority for both Google and LLMs
- Don't use AI/fake personas for author bios -- use real author schema pointing to real people

**Platform-specific strategies:**
- **Reddit**: Organic commenting (not shilling) produced 5% increase in LLM visibility. When GPT-5 launched, Reddit citations increased 87%
- **LinkedIn Pulse**: Underrated placement for AI search optimization
- **Quora**: 0.5% of Google AI Overview citations -- don't only focus on Reddit (1.3%)
- **YouTube/Video**: Google AI Overviews increasingly serve video answers; repurpose content into video
- **Wikipedia**: Traffic increased after ChatGPT (users fact-checking AI) but decreased after AI Overviews

**Review platform preferences (they differ by LLM):**
- ChatGPT prefers **Trustpilot**
- Google AI Overviews prefers **G2**
- Yelp ranks top for AIO food queries but never appears in ChatGPT/Perplexity
- TripAdvisor is the reverse (ChatGPT/Perplexity but not AIO)

> **Cross-reference:** For link-based brand authority building, see `link-authority-building`. For local review strategy, see `local-seo`.

## LLM Platform Differences

Each LLM has distinct source preferences. Optimizing for one does not guarantee visibility in others.

| Platform | Key Behavior |
|----------|-------------|
| **ChatGPT** | Hybrid index via SERP API (not Bing). WebGPT pre-filters by URL/title/meta. Prefers Trustpilot for reviews. Citations dropped from ~12 to 4-5 per response after Sept 2025 update |
| **Google AI Overviews** | 40% of sources are NOT from Google SERPs. Prefers G2 for reviews. Includes TikTok/Facebook citations (unique). YMYL keywords have the MOST AIOs |
| **Perplexity** | Different domain preferences from ChatGPT for same queries. Susceptible to brand presence in competitor comparison articles |
| **Grok** | Relies incredibly heavily on X/Twitter. In one case, almost word-for-word cited a tweet while ignoring 25 websites |
| **Gemini** | Application integrations (e.g., apartment searches) bypass traditional rankings entirely |

## AI Overview Impact Assessment

**AIO prevalence and trends (Tom Capper/Moz, STAT data):**
- Grew from 11% to 19% of US SERPs (Jan-Oct 2025)
- YMYL keywords have the MOST AIOs (law, health, science) -- Google is NOT being cautious with high-risk topics
- 1 in 7 AIOs are now position 2+ (not always position 1) -- increasing trend
- AIO traffic loss: 20-60% depending on vertical

**Contrarian finding:** AIOs mainly hit keywords that were already zero-click. The traffic loss may be lower than feared because these queries were not driving clicks anyway.

**At-risk queries** (where AI absorbs traffic): definitions, calculations, brand/entity lookups, navigational queries.

**Opportunity queries** (where clicks increase): transactional, complex/niche topics, visual/multi-format queries.

## Advanced GEO Tactics

### Paid Advertorials Getting Cited
Paid advertorials on news sites are being cited by LLMs. A competitor in insurance was the #1 most cited source using advertorials from a major newspaper. Ethically gray but currently effective.

### Affiliate Commission Manipulation
If a news publisher's commercial content listicle is cited by LLMs, offering them a higher affiliate commission can get your brand included in that article. The LLM citation value exceeds the affiliate cost.

### Retail Media for LLM Citations
Retail media offerings on ecommerce sites can influence LLM citations. If an online shop's category text mentions your brand, LLMs may pick it up.

### Self-Inclusion in Competitor Comparisons
Case study: Financial services client went from 0% to 23% mention rate in Perplexity by adding themselves to their own competitor comparison article (they were already the top-cited source domain but were not mentioned as a brand).

### Semantic Anchor Points from Reddit Data
Mine Reddit threads for 4-5 key phrases that become structural H2/H3 headings. Each section answers a single user-intent question in 2-3 sentences, optimized for AI extraction.

> **Cross-reference:** For the full Reddit Sniper method, see `ai-seo-content-automation`.

## The Contrarian View: "GEO Is Just SEO"

Multiple brightonSEO speakers noted that most GEO advice is just basic SEO repackaged. For e-commerce specifically, product grid optimization matters more than GEO today.

**Resolution:** GEO IS largely good SEO, but the distinction matters because:
1. The 81% citation non-overlap means some pages rank in AI but not Google (and vice versa)
2. Facts, mentions, and format preferences are specific to AI search
3. Agencies that dismiss GEO entirely risk a Blockbuster-vs-Netflix moment
4. The market has named this GEO/AEO -- dismissing the term costs agencies clients

Michael King's proposed reframe: **"Relevance Engineering"** -- the confluence of AI, information retrieval, UX, content strategy, and digital PR.

## Instructor Disagreements

| Topic | Position A | Position B | Resolution |
|-------|-----------|-----------|------------|
| GEO as distinct discipline | King: "SEO is deprecated" -- better version emerging | Lockwood: GEO is "a big nothing burger" for e-commerce | Both right in context. GEO matters for content/SaaS; product grids matter more for e-commerce |
| Page speed for AI | Traditional: <4s is fine | brightonSEO: <300ms for AI crawlers | AI crawlers need faster responses than human visitors |
| llms.txt | Some advocate implementing | Multiple speakers: no measurable impact | Skip it. Robots.txt works fine for LLM crawlers |

## GEO Optimization Checklist

- [ ] Audit semantic URLs (5-7 word natural-language slugs)
- [ ] Spoil content in meta descriptions (put the answer in the meta)
- [ ] Add current year to title/H1 for time-sensitive content
- [ ] Increase fact density (self-contained claim sentences)
- [ ] Mirror key facts in FAQ section at page bottom
- [ ] Ensure no JS dependency for key content (duplicate as HTML)
- [ ] Target server response time under 300ms
- [ ] Create listicle/comparison versions of key content
- [ ] Build brand presence on Reddit, LinkedIn Pulse, Quora
- [ ] Ensure presence on relevant review platforms (Trustpilot, G2)
- [ ] Add real author bios with schema (no fake personas)
- [ ] Create 40-60 word answer blocks for key questions
- [ ] Repurpose content into video format
- [ ] Monitor AI visibility across multiple LLM platforms
- [ ] Include brand in own competitor comparison content

## What This Skill Does NOT Cover

- Traditional on-page SEO (title tags, headers, internal links) -> use `on-page-optimization`
- Schema markup implementation details -> use `schema-entity-optimization`
- GA4 setup, KPI dashboards, reporting -> use `seo-analytics-reporting`
- Technical crawl fixes, indexation issues -> use `technical-seo-audit`
- Content production workflows -> use `content-production`
