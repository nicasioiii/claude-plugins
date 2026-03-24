# SEO Mastery v2.0 -- Routing & Operations

## Plugin Overview

Complete SEO knowledge engine built from 10 extraction files covering 25+ hours of expert training across Authority Hacker (TASS 3.0), Koray Tugberk Gubur (Topical Authority), Casey Keith (Treasure Map), Charles Floate, Greg Morrison, Derek Pierce, Nicolas Gorrono, Danny Postma, Kristina Azarenko, Nat Eliason, Maddy Osman, Vahe Arabian, Frey Chu, Jacky Chou, Mayank Kulkarni, brightonSEO 2025 speakers, and more. Provides end-to-end guidance from keyword research through AI search optimization, covering research, strategy, technical, content, links, scale, and measurement.

---

## Ambiguous Request Decision Tree

When a user's request could match multiple skills:

```
Is the user asking about KEYWORD RESEARCH or SEARCH INTENT?
  YES -> keyword-research-intent
  NO -> Continue

Is the user asking about COMPETITORS, SERP ANALYSIS, or NICHE VIABILITY?
  YES -> competitive-landscape-analysis
  NO -> Continue

Is the user asking about TOPICAL AUTHORITY, SEMANTIC SEO, or ENTITY STRATEGY?
  YES -> Is it about schema/markup implementation? -> schema-entity-optimization
       -> Is it about topical maps, Koray, Casey, EAV? -> topical-authority-semantic
  NO -> Continue

Is the user asking about CONTENT ARCHITECTURE, CLUSTERS, or INTERNAL LINKING?
  YES -> content-cluster-strategy
  NO -> Continue

Is the user asking about ON-PAGE elements (title tags, meta, headers, images)?
  YES -> on-page-optimization
  NO -> Continue

Is the user asking about TECHNICAL SEO (crawling, indexing, Core Web Vitals)?
  YES -> technical-seo-audit
  NO -> Continue

Is the user asking about SCHEMA MARKUP or STRUCTURED DATA?
  YES -> schema-entity-optimization
  NO -> Continue

Is the user asking about WRITING CONTENT or CONTENT BRIEFS?
  YES -> Is it about AI automation / tools / Make.com? -> ai-seo-content-automation
       -> Is it about manual writing / copywriting? -> content-production
  NO -> Continue

Is the user asking about LINK BUILDING?
  YES -> Is it about PBNs, parasite SEO, search stacks? -> pbn-advanced-link-strategy
       -> Is it about white-hat/gray-hat links? -> link-authority-building
  NO -> Continue

Is the user asking about LOCAL SEO or GOOGLE BUSINESS PROFILE?
  YES -> local-seo
  NO -> Continue

Is the user asking about E-COMMERCE SEO?
  YES -> ecommerce-seo
  NO -> Continue

Is the user asking about DIRECTORIES or PROGRAMMATIC SEO?
  YES -> directory-programmatic-seo
  NO -> Continue

Is the user asking about AI SEARCH, AI OVERVIEWS, or CHATGPT RANKINGS?
  YES -> geo-ai-search-optimization
  NO -> Continue

Is the user asking about GA4, GTM, ANALYTICS, or REPORTING?
  YES -> seo-analytics-reporting
  NO -> Ask clarifying questions
```

---

## Skill Routing Table (All 16 Skills)

### Layer 1: RESEARCH
| Skill | Display Name | Use When |
|---|---|---|
| `keyword-research-intent` | Keyword Research & Search Intent | Keyword ideas, search volume, KD, intent classification, CONCATENATE method, allintitle, DataForSEO keywords, demand validation |
| `competitive-landscape-analysis` | Competitive Landscape & SERP Analysis | Competitor analysis, SERP evaluation, content gaps, backlink profiles, niche qualification, market saturation |

### Layer 2: STRATEGY
| Skill | Display Name | Use When |
|---|---|---|
| `topical-authority-semantic` | Topical Authority & Semantic SEO | Topical maps, Koray framework, cost-of-retrieval, entity optimization, EAV model, contextual vectors, Casey Keith methods, E-E-A-T strategy |
| `content-cluster-strategy` | Content Cluster & Site Architecture | Pillar-cluster models, soft silos, internal linking architecture, anchor text ratios, content calendar, content decay, publishing cadence |

### Layer 3: TECHNICAL
| Skill | Display Name | Use When |
|---|---|---|
| `on-page-optimization` | On-Page SEO Optimization | Title tags, meta descriptions, headers, URL optimization, image SEO, body content, 20 placement spots, CSS class optimization |
| `technical-seo-audit` | Technical SEO Audit & Crawlability | Crawl issues, indexation, Core Web Vitals, robots.txt, canonicals, 301 redirects, JS rendering, site migration, edge SEO |
| `schema-entity-optimization` | Schema Markup & Entity Optimization | Schema JSON-LD, product schema, FAQ schema, E-E-A-T schema properties, ClaimReview, knowledge graphs, Google Stacking, AI search orchestrator |

### Layer 4: CONTENT
| Skill | Display Name | Use When |
|---|---|---|
| `content-production` | Content Production & SEO Copywriting | Writing process, content briefs, info/commercial templates, storytelling, fact-checking, brand style, content promotion |
| `ai-seo-content-automation` | AI SEO & Content Automation | GPT Projects, Claude MCP, Machined AI, Custom Blog Writer, Make.com automations, Reddit Sniper, interactive HTML tools |

### Layer 5: LINKS
| Skill | Display Name | Use When |
|---|---|---|
| `link-authority-building` | Link Building & Authority Acquisition | HARO, guest posting, skyscraper, niche edits, entity stacks, anchor text ratios, link velocity, foundational links, outreach |
| `pbn-advanced-link-strategy` | PBN & Advanced Link Strategies | PBN construction, domain acquisition, anti-footprint, parasite SEO, search stacks, 301 redirects, social media parasites |

### Layer 6: SCALE
| Skill | Display Name | Use When |
|---|---|---|
| `local-seo` | Local SEO & Google Business Profile | GBP optimization, posting strategy, citations, NAP, reviews, rank and rent, syndication tiers, local ranking factors |
| `ecommerce-seo` | E-Commerce SEO | Category pages, faceted navigation, product schema, seasonal pages, product grids, sub-collection multiplier |
| `directory-programmatic-seo` | Directory SEO & Programmatic SEO | Directory business model, 7-filter framework, pSEO playbook, badge strategy, TattoosAI case study, authority site model |

### Layer 7: MEASURE
| Skill | Display Name | Use When |
|---|---|---|
| `geo-ai-search-optimization` | GEO & AI Search Optimization | AI Overviews, ChatGPT rankings, LLM citations, crawler analytics, facts as signals, mentions as backlinks, brand as ranking factor |
| `seo-analytics-reporting` | SEO Analytics, GA4 & Reporting | GA4 architecture, GTM, consent mode v2, e-commerce tracking, UTM parameters, KPI definitions, Looker Studio, BigQuery |

---

## Cross-Reference Map

| When user asks about... | Primary skill | Cross-reference to... |
|---|---|---|
| "topical map" or "topical authority" | topical-authority-semantic | content-cluster-strategy (for implementation) |
| "entity optimization" or "knowledge graph" | topical-authority-semantic | schema-entity-optimization (for schema implementation) |
| "internal linking" | content-cluster-strategy | on-page-optimization (for anchor text details) |
| "schema markup" | schema-entity-optimization | technical-seo-audit (for validation/implementation issues) |
| "AI content" or "content automation" | ai-seo-content-automation | content-production (quality guardrails) |
| "PBN" or "parasite SEO" | pbn-advanced-link-strategy | link-authority-building (foundational links first) |
| "Google Business Profile" | local-seo | link-authority-building (citation/backlink strategy) |
| "product pages" or "category pages" | ecommerce-seo | on-page-optimization (meta tag/header optimization) |
| "faceted navigation" | ecommerce-seo | technical-seo-audit (canonical/indexation issues) |
| "AI Overviews" or "ChatGPT ranking" | geo-ai-search-optimization | schema-entity-optimization (orchestrator uses schema) |
| "directory" or "niche site" | directory-programmatic-seo | keyword-research-intent (niche validation) |
| "GA4" or "GTM" | seo-analytics-reporting | technical-seo-audit (tracking code issues) |
| "brand mentions" or "brand authority" | geo-ai-search-optimization | link-authority-building (unlinked mentions) |
| "content decay" or "content refresh" | content-cluster-strategy | seo-analytics-reporting (measuring what needs refresh) |
| "site migration" | technical-seo-audit | seo-analytics-reporting (pre/post metrics) |

---

## Slash Commands

| Command | Skills Activated | Output |
|---|---|---|
| `/research-keywords` | keyword-research-intent, competitive-landscape-analysis | Prioritized keyword list with volume, difficulty, intent, opportunity |
| `/content-plan` | content-cluster-strategy, topical-authority-semantic | Content cluster map, internal linking plan, publishing calendar |
| `/optimize-on-page` | on-page-optimization, schema-entity-optimization | Optimized meta tags, headers, schema JSON-LD, image alt text |
| `/write-content` | content-production, ai-seo-content-automation | Complete article with SEO optimization and schema recommendations |
| `/link-outreach` | link-authority-building | Prospect list, outreach templates, tracking spreadsheet |
| `/seo-audit` | technical-seo-audit, on-page-optimization, schema-entity-optimization | Priority-ranked issue list with fix instructions |
| `/seo-report` | seo-analytics-reporting, geo-ai-search-optimization | Dashboard template, KPI summary, AI search visibility snapshot |
| `/geo-optimize` | geo-ai-search-optimization, schema-entity-optimization, on-page-optimization | Fact-optimized content, FAQ mirroring, schema enhancements |
| `/local-seo-audit` | local-seo | GBP audit, citation check, competitive positioning, action plan |

---

## Key Instructor Disagreements

These are the most impactful disagreements across instructors. Each skill documents relevant disagreements in its SKILL.md.

| Topic | Position A | Position B | Resolution |
|---|---|---|---|
| Start hard or easy keywords | Koray: hardest YMYL first (forces authority classification) | AH/Eliason/Frey: low-KD first | Context-dependent: Koray for authority play, low-KD for new sites |
| Schema emphasis | Koray: content structure IS schema | Casey/Gorrono: schema markup non-negotiable | Implement both |
| Page speed importance | Cromwell: nearly irrelevant | brightonSEO: server response <300ms for AI crawlers | Matters more for AI crawlers |
| Purchasing backlinks | Authority Hacker: never paid | Gorrono/Floate: standard practice | Both work; risk spectrum documented |
| Link velocity vs anchor text | Floate: velocity MORE important | Morrison: keyword anchors critical | Both matter; velocity mistakes harder to recover |
| GEO for e-commerce | Lockwood: "nothing burger" now | Leliukh: 22% customer acquisition from LLMs | Product grid optimization > GEO for e-commerce today |
