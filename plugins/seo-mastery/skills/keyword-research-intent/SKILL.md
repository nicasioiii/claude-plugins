---
name: Keyword Research & Search Intent
description: >
  MANDATORY TRIGGERS: keyword research, keyword ideas, keyword list, search volume,
  keyword difficulty, KD, search intent, informational intent, commercial intent,
  transactional intent, navigational intent, allintitle, CONCATENATE method,
  keyword validation, keyword clustering, Answer Socrates, DataForSEO keywords,
  long-tail keywords, search funnel, keyword opportunities, keyword generator,
  demand validation, keyword expansion, "near me" keywords, keyword brainstorm.
  FOR: Complete keyword research workflows from brainstorm through validation.
  Covers the three-layer keyword research system (AI ideas, DataForSEO validation,
  Answer Socrates clustering), intent classification (informational/commercial/
  transactional/navigational), competitor keyword mining, allintitle competition
  assessment, Google Search Console secondary keyword mining, CONCATENATE formulaic
  keyword generation, demand-driven product validation, and directory niche
  keyword selection (7-filter framework).
  Do NOT use for: Content architecture or clustering decisions (use content-cluster-strategy),
  competitive backlink analysis (use competitive-landscape-analysis), topical map
  construction (use topical-authority-semantic), content writing (use content-production).
---

# Keyword Research & Search Intent

## Quick Navigation
- **Three-layer research system** -> ref-keyword-research-methodology.md
- **Intent classification & mapping** -> ref-search-intent-classification.md

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| How to find keywords, keyword research process, where to start, keyword tools | ref-keyword-research-methodology.md |
| Keyword validation, allintitle, competition assessment, keyword difficulty | ref-keyword-research-methodology.md |
| CONCATENATE method, formulaic keyword generation, keyword expansion | ref-keyword-research-methodology.md |
| DataForSEO setup, Answer Socrates, clustering keywords | ref-keyword-research-methodology.md |
| Demand validation, niche validation, directory keywords, 7-filter framework | ref-keyword-research-methodology.md |
| Search intent types, informational vs commercial, SERP-based intent detection | ref-search-intent-classification.md |
| Intent-content format mapping, e-commerce intent, "best/top" modifier rules | ref-search-intent-classification.md |
| Sub-collection strategy, search funnel positioning | ref-search-intent-classification.md |

---

## Cross-References

| When the conversation turns to... | Route to this skill | Trigger |
|---|---|---|
| "How do I organize these keywords into clusters?" | content-cluster-strategy | Keyword list exists, need architecture |
| "Who else ranks for these keywords?" | competitive-landscape-analysis | Need SERP/competitor analysis |
| "How do I build topical authority around these?" | topical-authority-semantic | Need entity/topical map strategy |
| "What backlinks do competitors have?" | competitive-landscape-analysis | Need link profile analysis |
| "Should I build a directory for this niche?" | directory-programmatic-seo | Niche validation question |

---

## THE THREE-LAYER KEYWORD RESEARCH SYSTEM (Gorrono)

The most comprehensive keyword research workflow. Use all three layers for thorough research; Layer 1 alone is sufficient for quick brainstorms.

### Layer 1: AI-Generated Keyword Ideas
1. Use a Role-Context-Output prompt in ChatGPT with business details, services, and website URL
2. GPT generates keyword ideas organized by: main keyword, sub-keywords, search intent (informational, investigational/commercial, transactional)
3. Copy into a Google Sheet for validation in Layer 2

### Layer 2: DataForSEO Validation
1. Paste keywords into DataForSEO Google Sheets template
2. Pull search volume (cost: $0.075 per 1,000 keywords)
3. Pull keyword difficulty (use KD metric, NOT competition index -- KD aligns better with Ahrefs/SEMrush)
4. Pull CPC data
5. Set date range to 12 months prior for accurate volume data

### Layer 3: Answer Socrates Deep Clustering
1. Paste each main keyword into Answer Socrates ($29/month, one month usually sufficient)
2. Generates 1,000+ questions/long-tail keywords per main keyword
3. Clusters using AI (DeepSeek R1) into topic groups with aggregate volume, CPC, competition
4. Export clustered CSV and import as new sheets in master keyword research spreadsheet
5. Link each cluster back to the main keyword sheet for navigation

**Content hierarchy that emerges:**
- Main keyword = service page / pillar page
- Sub-keywords = content pillars
- Cluster keywords = supporting blog posts linking to pillar content

---

## COMPETITOR KEYWORD MINING (Nat Eliason / Authority Hacker)

### Process
1. Identify top 2-5 competitors (search your topics, note who ranks)
2. Ahrefs Site Explorer -> plug in each competitor URL
3. Filter organic keywords: Position 3+, Volume 500+, Difficulty below 40-60
4. Add promising keywords to master list
5. Go deeper: check "also rank for" to find related keywords their ranking pages capture
6. Repeat for 2-5 competitors
7. **Aim for 100-150 keywords before filtering**

### Selecting Top 50 Opportunities (Nat Eliason)
- Filter for max difficulty ~20-40, min volume ~500
- If list too small, increase difficulty to 30-40
- Mark high-difficulty keywords for long-term targeting
- Note emerging "themes" (e.g., "[tea type] caffeine") -- these become content series
- Validate every keyword in Google: ensure it is not a product name, song, or brand you cannot compete against

---

## KEYWORD GENERATOR METHOD -- CONCATENATE (Nat Eliason)

For niches with repeating patterns (tea types, dog breeds, city names):

1. Column A = root terms (e.g., "poodle," "german shepherd")
2. Row 1 = modifiers (e.g., "benefits," "how to train a")
3. Use CONCATENATE to auto-generate: "poodle benefits," "how to train a german shepherd"
4. Plug generated keywords into Ahrefs for volume and difficulty
5. This method generated 100+ keywords in under 1 hour for Cup & Leaf tea site

---

## ALLINTITLE COMPETITION ASSESSMENT (Hockman / Morrison)

Use `allintitle:[keyword]` in Google to count pages with exact keyword in title:

| allintitle Count | Competition Level | Strategy |
|---|---|---|
| Under 10 | Extremely low | On-page alone gets page 1 |
| 10-100 | Very low | On-page + internal links |
| 100-1,000 | Moderate | On-page + some backlinks |
| 1,000-10,000 | High | Excellent on-page + significant link building |
| 12,000+ | Very high | Authority site required |

**E-commerce verification process (Cromwell):**
1. Search keyword, check competitor authority scores (Ahrefs/SEMrush Chrome plugin)
2. If top results have authority scores under 30, keyword is winnable for new site
3. Check meta titles: if top results do NOT have your keyword in title, it is wide open

---

## DEMAND-DRIVEN PRODUCT DEVELOPMENT (Postma)

Never build a product first. Always validate demand via SEO research.

**Validation checklist:**
1. **Low KD check** -- keyword difficulty must be low enough to compete
2. **User intent match** -- can you build what people are searching for?
3. **Monetization signal** -- does CPC exist? (people bidding = money in niche)
4. **Global volume check** -- not just US; check if 50%+ from Western countries
5. **Manual SERP review** -- visit google.us, search keyword, assess top 3: can you build better?
6. **Keyword expansion** -- use Ahrefs "keyword ideas" and "also ranks for" for full keyword universe

---

## DIRECTORY NICHE KEYWORD SELECTION (Frey Chu)

### The 7-Filter Framework (Filters 1 and 4 are keyword-focused)

**Filter 1: KD + Search Volume**
- Target KD under 20 (Ahrefs scale). Under 5 is ideal
- Check location sub-keywords: consistent 90-150 monthly searches per city at KD 0-2 = massive green flag
- Ahrefs zero-volume caveat: keywords showing 0-10 often have real traffic

**Filter 4: Search Intent Clarity**
- Broad keywords are traps -- seductive volume but foggy intent
- Go deeper: filter to KD 0-5 and discover sub-niches with crystal-clear intent
- Location-based keywords usually have inherently clear intent

### "Near Me" Keyword Research
- Search "[niche] near me" to gauge local demand
- Check Google Maps for category accuracy -- mismatched categories = fragmented results = opportunity
- Validate on Reddit (location questions) and TikTok (viral videos with "where is this?" comments)

---

## GOOGLE SEARCH CONSOLE SECONDARY KEYWORD MINING (Hockman)

After publishing and indexing content:
1. Open Google Search Console -> Performance -> Pages
2. Click on any page -> see all queries driving impressions
3. Identify secondary keywords the page ranks for that you did not explicitly target
4. Optimize the page for high-impression secondary keywords (add to H2s, body content)
5. Create new content targeting secondary keywords that deserve their own page

---

## CONTENT PLAN SPREADSHEET STRUCTURE (Nat Eliason)

Six sheets for organizing research output:
1. **High Level Topics** -- 3-10 broad authority topics
2. **Related Keywords** -- From Ahrefs "also rank for" data
3. **Competitor Keywords** -- Position 4-100, volume 250+, difficulty below 60
4. **All KWs** -- Combined master list with keyword, volume, difficulty, target Y/N
5. **Target Keywords** -- Filtered top 50 with validation
6. **Content Plan** -- Keyword, Week (1-13), Outline link

---

## TOOL STACK FOR KEYWORD RESEARCH

| Tool | Cost | Best For |
|---|---|---|
| DataForSEO | $50 min top-up, lasts ~1 year | Volume, KD, CPC, competitor keywords, SERP parsing |
| Ahrefs Lite | $99/month (use 2 months then cancel) | Competitor reverse engineering, "also rank for" |
| Answer Socrates | $29/month (1 month sufficient) | Deep clustering, 1,000+ long-tail per keyword |
| Clicks.so | $25/month | E-commerce keyword research, quick big-idea search |
| Google Search Console | Free | Secondary keyword mining from existing rankings |
| ChatGPT / Claude | Subscription | AI-generated keyword brainstorms (Layer 1) |

---

## SPECIFIC NUMBERS AND THRESHOLDS

| Metric | Target | Source |
|---|---|---|
| Keywords before filtering | 100-150 minimum | Nat Eliason |
| Target keywords to select | Top 50 | Nat Eliason |
| Max KD for new sites | Under 10 | Authority Hacker |
| Max KD for directories | Under 20, ideally under 5 | Frey Chu |
| Min search volume worth targeting | 500 (content sites), 90/city (directories) | Eliason / Frey Chu |
| DataForSEO cost per 1K keywords | $0.075 | Gorrono |
| Answer Socrates keywords per main term | 1,000+ | Gorrono |
| Articles from 50 keywords | ~1 year of content | Nat Eliason |
