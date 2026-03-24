---
name: Competitive Landscape & SERP Analysis
description: >
  MANDATORY TRIGGERS: competitor analysis, SERP analysis, competitive research,
  content gap, backlink analysis, domain authority, DR, DA, market saturation,
  niche qualification, competitor keywords, competitor reverse engineering,
  DataForSEO competitor, backlink profile, niche viability, competition assessment,
  who ranks for, top competitors, SERP features, competitive intelligence,
  niche archetypes, Google Ads data for SEO, directory competitive research.
  FOR: Analyzing the competitive SEO landscape before committing resources.
  Covers SERP competitor evaluation (what to look for in top 10), domain authority
  benchmarking, backlink profile comparison, content gap identification, market
  saturation assessment, niche qualification criteria (6 factors), Authority Hacker's
  4 niche archetypes, DataForSEO bulk competitive analysis, and directory competitive
  research (Ahrefs Site Explorer process).
  Do NOT use for: Keyword list building (use keyword-research-intent), link building
  strategy (use link-authority-building), content planning (use content-cluster-strategy),
  topical authority strategy (use topical-authority-semantic).
---

# Competitive Landscape & SERP Analysis

## Quick Navigation
- **SERP competitor evaluation, content format detection** -> ref-serp-analysis-workflow.md
- **Competitor reverse engineering, backlink profiles, niche qualification** -> ref-competitive-intelligence.md

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| How to analyze SERP results, what to look for in top 10 | ref-serp-analysis-workflow.md |
| Content format detection, meta title gap analysis | ref-serp-analysis-workflow.md |
| Authority score checking, competitor content structure | ref-serp-analysis-workflow.md |
| Google Ads data for SEO prioritization | ref-serp-analysis-workflow.md |
| Competitor reverse engineering with Ahrefs or DataForSEO | ref-competitive-intelligence.md |
| Backlink profile comparison, domain authority reality check | ref-competitive-intelligence.md |
| Content gap identification, market saturation signals | ref-competitive-intelligence.md |
| Niche viability, niche qualification, 4 archetypes, YMYL risk | ref-competitive-intelligence.md |
| Directory competitive research, Yelp outranking, mom-and-pop analysis | ref-competitive-intelligence.md |

---

## Cross-References

| When the conversation turns to... | Route to this skill | Trigger |
|---|---|---|
| "Now I need to find keywords for this niche" | keyword-research-intent | Competition analyzed, need keyword list |
| "How do I build links like these competitors?" | link-authority-building | Backlink analysis complete, need strategy |
| "How should I structure my content to compete?" | content-cluster-strategy | Gaps identified, need architecture plan |
| "Is this niche worth building a directory in?" | directory-programmatic-seo | Niche qualification question |
| "What topical authority do competitors have?" | topical-authority-semantic | Need entity/topical analysis |

---

## SERP COMPETITOR EVALUATION FRAMEWORK

### What to Look For in the Top 10 Results

For every target keyword, analyze the first page of Google:

1. **Content type distribution:** How many are blog posts vs product pages vs tools vs videos?
2. **Domain authority range:** What DR/DA do top results have? (Ahrefs toolbar)
3. **Content depth:** Word count, number of images, embedded videos, tables
4. **Content freshness:** When was each piece last updated?
5. **Schema/rich results:** Star ratings, FAQs, product carousels, featured snippets
6. **Meta title optimization:** Does competitor have the exact keyword in title? Front-loaded?
7. **Internal linking:** How many internal links point to this page? (Ahrefs)
8. **Backlink count:** How many referring domains point to this specific URL?

### Meta Title Gap Analysis (Cromwell)
If top-ranking pages do NOT have your target keyword in their meta title, the keyword is wide open. This is the single fastest competition check you can do.

### Google Ads Data for SEO Prioritization (Cromwell / Gorrono)
- High CPC keywords = high commercial value = worth SEO investment
- DataForSEO SERP parser shows paid result positions above organic
- More paid ads = harder to rank organically but more valuable when you do
- Use CPC data to prioritize which keywords to target first

---

## NICHE QUALIFICATION CRITERIA (Authority Hacker)

Six factors to evaluate before entering a niche:

| Factor | Question | Green Flag | Red Flag |
|---|---|---|---|
| **Competition** | Are there low-competition keywords? | KD under 10 available | All keywords KD 40+ |
| **Monetization** | Affiliate programs paying 3%+? Beyond Amazon? | Multiple high-paying programs | Amazon-only at 1-3% |
| **SEO** | Can small sites rank? Achievable traffic? | Small sites in top 10 | Only big media in results |
| **Community** | Active Facebook groups, subreddits? | Passionate, engaged audience | Dead communities |
| **Evergreen** | Will niche exist in 3+ years? | Stable, long-term demand | Trend-dependent (fidget spinners) |
| **YMYL Risk** | Are small/new sites blocked from ranking? | Small sites appear in SERPs | Only hospitals, gov sites rank |

### The 4 Niche Archetypes (Authority Hacker)

| Archetype | Example | Ceiling | Link Needs | Best For |
|---|---|---|---|---|
| **Broad/General** | verywellfit.com | 7 figures/month | Massive (big media dominates) | Full-time single-site focus |
| **Community-Based** | authorityhacker.com | High (sticky audience) | Moderate (word-of-mouth) | Face-of-brand operators |
| **Product-Based** | dronerush.com | Moderate | Moderate | Hands-off portfolio approach |
| **Problem-Based** | peststrategies.com | High conversion rates | Moderate | Portfolio approach, pure SEO |

**Key insight:** Broader niche = more links needed to domain (inverse correlation). Sites sell for 30-40x monthly revenue.

---

## COMPETITOR REVERSE ENGINEERING (Nat Eliason / Gorrono)

### Ahrefs Method (Nat Eliason)
1. Plug competitor URL into Ahrefs Site Explorer
2. Go to Organic Keywords tab
3. Filter: Position 3+, Volume 500+, Difficulty below 40-60
4. Export all promising keywords
5. Click into competitor pages -> check "also rank for" for subtopic keywords
6. Repeat for 2-5 competitors

### DataForSEO Bulk Method (Gorrono)
1. Use DataForSEO SERP Parser: enter keyword + location + language
2. Returns top 10 organic with absolute vs organic position
3. For each competitor (4-5), collect:
   - Estimated monthly traffic (DataForSEO organic traffic estimation -- bulk, up to 10,000 domains)
   - Total referring domains (DataForSEO bulk referring domains)
   - All ranked keywords + positions (set to 400 max per domain)
4. Feed all data into GPT Projects for gap analysis

### GPT Projects Gap Analysis Output (Gorrono)
Feed competitor data into a GPT Project. Example output:
"None of your competitors rank for 'financial advisor Mesa AZ' or 'retirement planning Mesa.' Your home turf. Action: Build dedicated Mesa landing pages and cluster content for nearby suburbs."

---

## DIRECTORY COMPETITIVE RESEARCH (Frey Chu)

### Ahrefs Site Explorer Process
1. Google target keyword + city
2. Find other directories (skip Reddit, Yelp, major platforms)
3. Paste competitor URL into Ahrefs Site Explorer
4. Check: monthly visitors, backlinks count, referring domains, traffic chart

### Yelp Outranking Strategy
- Yelp is NEVER a reason to abandon a niche
- You can outrank Yelp through topical authority: 100% of your site = your niche vs Yelp's millions of unrelated pages
- Even 100,000 low-quality backlinks should not intimidate -- quality over quantity

### Mom-and-Pop Competitor Identification
- Look for simple-design, one-person directory operations -- these are beatable
- Use Ahrefs "Top organic competitors" section to discover more directory competitors
- What WOULD be intimidating: DR 90+ backlinks, hundreds of monthly visitors on linking pages

---

## MARKET SATURATION ASSESSMENT

### Signals of Saturation
- All top 10 results from high-DR domains (60+)
- No small/independent sites ranking on page 1
- Multiple well-funded competitors with deep content coverage
- High keyword difficulty (KD 40+) across most keywords in niche
- Niche dominated by YMYL restrictions (medical, financial, legal)

### Signals of Opportunity
- Mixed DR in top 10 (some under 30)
- Thin or outdated content ranking
- Meta title gaps (competitors missing keyword in title)
- Low allintitle counts (under 1,000)
- No dedicated niche sites (only general sites covering topic tangentially)
- Fragmented Google Maps categories (Frey Chu's directory signal)

---

## BACKLINK PROFILE COMPARISON

### What to Compare Across Competitors
1. **Total referring domains** (not total backlinks -- one domain with 1,000 links = still 1 referring domain)
2. **DR distribution** of linking domains
3. **Link freshness** -- are they still actively building? Or coasting on old links?
4. **Deep links vs homepage links** -- competitors with mostly homepage links may be weak on individual pages
5. **Anchor text diversity** -- over-optimized anchor profiles are vulnerable

### Domain Authority Reality Check
- Third-party DR/DA scores (Ahrefs, Moz, SEMrush) are approximations, NOT Google's actual authority metric
- Google uses internal signals not available to third-party tools
- DR is useful for relative comparison, not absolute judgment
- A DR 30 site can outrank DR 60 sites with better topical authority and on-page optimization

---

## SPECIFIC NUMBERS AND THRESHOLDS

| Metric | Value | Source |
|---|---|---|
| Niche qualification factors | 6 (competition, monetization, SEO, community, evergreen, YMYL) | Authority Hacker |
| Min affiliate commission worth targeting | 3%+ | Authority Hacker |
| Site sale multiplier | 30-40x monthly revenue | Authority Hacker |
| Max KD indicating opportunity for new sites | Under 10 | Authority Hacker |
| Competitors to reverse engineer | 2-5 minimum | Nat Eliason |
| DataForSEO max ranked keywords per domain | 400 | Gorrono |
| DataForSEO bulk traffic estimation capacity | 10,000 domains | Gorrono |
| Authority score threshold for "winnable" | Under 30 in top results | Cromwell |
| allintitle under 10 | Extremely low competition | Morrison/Hockman |
