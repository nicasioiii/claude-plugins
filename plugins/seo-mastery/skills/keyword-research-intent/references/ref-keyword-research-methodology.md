# Keyword Research Methodology -- Complete Reference

## THE THREE-LAYER SYSTEM IN DETAIL (Gorrono)

### Layer 1: AI-Generated Keyword Ideas

**Prompt structure (Role-Context-Output):**
- Role: "You are an expert SEO strategist specializing in [industry]"
- Context: Business details (services, location, target audience, website URL)
- Output: "Generate keyword ideas organized by main keyword, sub-keywords, and search intent"

**Intent categories for organization:**
- Informational: how-to, what-is, guides, tutorials
- Investigational/Commercial: best, top, reviews, comparisons, alternatives
- Transactional: buy, price, cost, near me, hire, book

**Layer 1 output format:** Google Sheet with columns: Keyword | Intent | Priority (H/M/L)

### Layer 2: DataForSEO Validation

**Setup:**
1. Create DataForSEO account ($1 free credit on signup, $50 minimum top-up)
2. Install DataForSEO API Connector Chrome extension
3. Use Google Sheets template with pre-built API calls

**Key API calls:**
- Keyword suggestions (related but different seed words)
- Similar keywords (contain the seed word)
- Keyword search volume (Google)
- Keyword difficulty (more accurate than competition index)
- CPC data

**Critical setting:** Set date range to 12 months prior for accurate volume data

**DataForSEO vs Ahrefs/SEMrush advantages:**
- Pay-as-you-go pricing (2 API calls cost under $0.04)
- Google Sheets integration (no separate tool)
- Can integrate into Make.com automations and Claude MCP
- $50 top-up lasts most users a full year

### Layer 3: Answer Socrates Deep Clustering

**Process:**
1. Paste each main keyword into Answer Socrates ($29/month basic plan)
2. Tool generates 1,000+ questions and long-tail variations
3. AI clustering (DeepSeek R1) groups into topic clusters
4. Each cluster includes: aggregate volume, CPC, competition score
5. Export clustered CSV -> import as new sheet in master spreadsheet
6. Link each cluster back to main keyword sheet

**Content hierarchy from clusters:**
- Main keyword = service/pillar page
- Sub-keywords = content pillars (category-level pages)
- Cluster keywords = supporting blog posts that link UP to pillar
- Can recurse: take any sub-keyword through Answer Socrates again for deeper clusters

**Depth vs breadth decision:** "This is enough for 99% of use cases. If you're not going to use that granular data, there's no point in collecting it." (Gorrono)

---

## COMPETITOR KEYWORD MINING (Nat Eliason)

### Step-by-Step Process
1. Identify 2-5 competitors (search your topics in Google, note who ranks consistently)
2. Ahrefs Site Explorer -> enter each competitor URL
3. Go to Organic Keywords tab
4. Apply filters:
   - Position: 3+ (or 10-50 if too many results)
   - Volume: 500+
   - Keyword Difficulty: below 40-60
5. Add all promising keywords to master list
6. Go deeper: click into each competitor's ranking page, check "also rank for"
7. These related keywords reveal subtopics and long-tail variations
8. Repeat for ALL competitors (minimum 2, ideally 5)

### Target: 100-150 Keywords Before Filtering
- This gives you enough raw material to filter down to ~50 targets
- Mix of high-volume cornerstone topics + low-volume long-tail opportunities
- Mark high-difficulty keywords for long-term targeting (don't discard)

---

## KEYWORD GENERATOR: CONCATENATE METHOD (Nat Eliason)

For niches with repeating entity + modifier patterns:

**Spreadsheet setup:**
```
         | benefits | how to train | best food for | lifespan of |
poodle   | =CONCAT  | =CONCAT      | =CONCAT       | =CONCAT     |
labrador | =CONCAT  | =CONCAT      | =CONCAT       | =CONCAT     |
beagle   | =CONCAT  | =CONCAT      | =CONCAT       | =CONCAT     |
```

**Formula:** `=CONCATENATE($A2, " ", B$1)` produces "poodle benefits"

**Practical examples:**
- Tea site: [tea type] + [benefits, caffeine, how to brew, vs other tea, side effects]
- Dog site: [breed] + [temperament, size, diet, training, health issues]
- Directory site: [niche] + [near me, in city, best, reviews, cost]

**Output:** 100+ keywords in under 1 hour. Plug all into Ahrefs for volume + KD.

---

## ALLINTITLE COMPETITION ASSESSMENT (Hockman / Morrison / Cromwell)

### The allintitle Method
Search `allintitle:[your keyword]` in Google. The result count shows how many pages have that exact keyword in their title tag.

**Competition benchmarks:**
| allintitle Result Count | Assessment | Action |
|---|---|---|
| 0-10 | Almost no competition | Rank with on-page alone |
| 10-100 | Very low competition | Good on-page + 2-3 internal links |
| 100-1,000 | Moderate | On-page + internal links + a few backlinks |
| 1,000-10,000 | High | Needs strong on-page + 10+ quality backlinks |
| 10,000+ | Very competitive | Authority site with significant link profile needed |

### E-Commerce SERP Verification (Cromwell)
1. Search keyword in Google
2. Check competitor authority scores (free Ahrefs/SEMrush Chrome toolbar)
3. Authority scores under 30 in top results = winnable for new site
4. Check meta titles: no keyword in competitor titles = wide open opportunity
5. If CPC is low AND difficulty is low, legitimately easy keyword confirmed

### The "Skip" Rule for E-Commerce (Cromwell)
- Keywords like "best [product]" or "top [product]" rank listicle/affiliate sites (Forbes, Healthline)
- E-commerce stores should target direct purchase-intent keywords instead
- Exception: if you also run a content blog alongside your store

---

## DEMAND-DRIVEN VALIDATION (Postma)

### The 6-Step Validation Checklist
1. **Low KD check** -- must be low enough to compete
2. **User intent match** -- can you actually build what people search for?
3. **Monetization signal** -- CPC exists (advertisers bidding = money in niche)
4. **Global volume check** -- not just US; 50%+ from Western countries = higher spending power
5. **Manual SERP review** -- visit google.us, assess top 3 results: can you build a better page?
6. **Keyword expansion** -- Ahrefs "keyword ideas" + "also ranks for" reveals full keyword universe

### pSEO Keyword Goldmine Identification
**The expansion pattern:**
1. Start with short-tail keyword (e.g., "AI tattoo generator") with low KD
2. Check Ahrefs "keyword ideas" for related semantic keywords -- sum all volumes
3. Check "also ranks for" for parent topics and adjacent categories
4. Look for templatizable patterns: "[X] tattoo ideas", "[style] tattoo meaning"
5. If 600K+ monthly searches for templatizable queries = pSEO goldmine

---

## DIRECTORY NICHE KEYWORD SELECTION (Frey Chu)

### Filter 1: KD + Search Volume
- Target KD under 20 (Ahrefs 0-100 scale), under 5 is ideal
- Balance low KD with adequate search volume
- For display-ad directories: aim for 20,000-50,000 monthly visitors (~$1,000/month ad threshold)
- Check location sub-keywords: consistent 90-150 searches per city at KD 0-2 = massive green flag
- Ahrefs zero-volume caveat: keywords showing 0-10 often have real traffic

### "Near Me" Keyword Research
- Search "[niche] near me" for local demand gauge
- Check Google Maps category accuracy: mismatched categories = fragmented SERPs = opportunity
- Validate on Reddit: search keyword, look for location questions
- Validate on TikTok: viral videos, "where is this?" comments = confirmed demand

### Example (Frey Chu case study)
- "Amazon bin stores" = 14,000 monthly searches at KD 3
- Total related keyword volume: 27,000
- Led to ~$300/month passive directory income

---

## GOOGLE SEARCH CONSOLE KEYWORD MINING (Hockman)

### Secondary Keyword Discovery Process
1. Google Search Console -> Performance -> Pages
2. Click any page to see all queries driving impressions
3. Identify secondary keywords you did not explicitly target
4. Two actions for each secondary keyword:
   - **High-impression, related to page topic:** Optimize existing page (add to H2s, body content)
   - **High-impression, deserves own coverage:** Create new content piece targeting that keyword

### When to Mine GSC
- After content has been indexed for 30+ days
- When a page has stabilized in rankings (2-3 weeks post-publish)
- During quarterly content audits

---

## CONTENT PLAN SPREADSHEET (Nat Eliason)

### Six-Sheet Structure
1. **High Level Topics** -- 3-10 broad authority topics (from brainstorm)
2. **Related Keywords** -- From Ahrefs "also rank for" data
3. **Competitor Keywords** -- Position 4-100, volume 250+, difficulty below 60
4. **All KWs** -- Combined master list: keyword, volume, difficulty, target Y/N
5. **Target Keywords** -- Filtered top 50 with validation notes
6. **Content Plan** -- Keyword, Week (1-13), Outline link, Status

### Planning Cadence
- Plan 4 weeks initially, targeting 3 articles per week
- From 50 keywords, pick 12 to start (4 weeks x 3)
- Mix broad cornerstone + narrow long-tail each week
- Put lower-difficulty topics earlier (rank faster for new sites)
- Related topics in series for easy interlinking
- 50 keywords = roughly 1 year of content
- Total planning process: a couple of hours

---

## SPECIFIC NUMBERS QUICK REFERENCE

| Metric | Value | Source |
|---|---|---|
| DataForSEO cost per 1K keywords | $0.075 | Gorrono |
| DataForSEO 2-API-call cost | Under $0.04 | Gorrono |
| Answer Socrates keywords per main term | 1,000+ | Gorrono |
| Minimum keywords before filtering | 100-150 | Nat Eliason |
| Target keywords to select | Top 50 | Nat Eliason |
| Articles per week target | 3 | Nat Eliason |
| Max KD for new content sites | Under 10 | Authority Hacker |
| Max KD for directories | Under 20, ideally under 5 | Frey Chu |
| Min volume for content sites | 500 | Nat Eliason |
| Min volume per city for directories | 90-150 | Frey Chu |
| Display ad traffic threshold | 20,000-50,000 monthly visitors | Frey Chu |
| Ahrefs subscription use period | 2 months then cancel | Authority Hacker |
