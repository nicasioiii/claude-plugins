# Competitive Intelligence -- Complete Reference

## AHREFS COMPETITOR REVERSE ENGINEERING (Nat Eliason)

### Full Process
1. Identify 2-5 competitors by searching your target topics in Google
2. Plug each competitor into Ahrefs Site Explorer
3. Go to Organic Keywords tab
4. Apply filters:
   - Position: 3+ (to find keywords they rank for but don't dominate)
   - OR Position: 10-50 (if too many results, focus on lower positions = easier to overtake)
   - Volume: 500+ (minimum worth targeting)
   - Keyword Difficulty: below 40-60
5. Export promising keywords to master spreadsheet
6. For each competitor page, click through to "Also rank for" to discover subtopic keywords
7. Repeat for ALL competitors

### What to Extract Per Competitor
- Total organic keywords count
- Total estimated organic traffic
- Top 10 highest-traffic pages (identify their content pillars)
- Keywords they rank position 4-20 for (vulnerable rankings you can overtake)
- Content they have that you do not (gap analysis)

---

## DATAFORSEO BULK COMPETITIVE ANALYSIS (Gorrono)

### SERP Parser for Competitor Discovery
1. Enter target keyword + specific location + language into DataForSEO SERP Parser
2. Returns top 10 organic results with absolute position vs organic position
3. Shows how many paid results sit above organic
4. Identifies competitors you may not have found through manual search

### Bulk Data Collection (4-5 Competitors)
For each competitor, pull:
1. **Organic traffic estimation** (DataForSEO bulk -- handles up to 10,000 domains)
2. **Referring domains count** (DataForSEO bulk referring domains)
3. **All ranked keywords + positions** (DataForSEO ranked keywords -- set max 400)

### GPT Projects Integration
Upload all competitor data into a single GPT Project. Run prompts:
- "Identify keywords competitors rank for that [my site] does not"
- "Find untapped content opportunities based on competitor gaps"
- "Generate a 90-day content roadmap prioritized by gap difficulty and opportunity"

**Example output:** "None of your competitors rank for 'financial advisor Mesa AZ' or 'retirement planning Mesa.' Your home turf. Action: Build dedicated Mesa landing pages."

---

## BACKLINK PROFILE COMPARISON

### Key Metrics to Compare
1. **Total referring domains** -- the true measure of link diversity (not total backlinks)
2. **DR distribution** -- what quality of sites link to each competitor?
3. **Link velocity** -- are they actively building or coasting on old links?
4. **Deep links vs homepage** -- competitors with mostly homepage links have weak individual pages
5. **Anchor text profile** -- over-optimized anchors reveal manipulative link building (vulnerability)

### Domain Authority Reality Check
Third-party DR/DA scores are approximations. They are NOT Google's actual authority metric.
- Google uses internal signals unavailable to tools
- DR is useful for relative comparison only
- A DR 30 site with strong topical authority beats DR 60 generalists regularly
- Always verify with actual SERP performance, not just tool scores

### Practical Competitive Link Assessment
| Competitor Referring Domains | Your Required Link Building Effort |
|---|---|
| Under 10 | Minimal -- content quality + internal links can win |
| 10-50 | Moderate -- HARO + guest posting over 3-6 months |
| 50-200 | Significant -- dedicated link building campaign |
| 200+ | Long-term -- need outstanding content + sustained effort |

---

## CONTENT GAP IDENTIFICATION

### Process
1. List all keywords/topics competitor ranks for (Ahrefs Organic Keywords export)
2. List all keywords/topics you currently rank for
3. Subtract: their keywords minus your keywords = GAP LIST
4. Prioritize gaps by:
   - Search volume (higher = more traffic potential)
   - Keyword difficulty (lower = easier to capture)
   - CPC / commercial value (higher = more revenue potential)
   - Relevance to your business (must be worth creating)
5. Cluster gaps into content themes for efficient batch production

### Content Quality Gaps (Beyond Keywords)
- Competitor has thin content (under 500 words) on a topic = depth opportunity
- Competitor has no images/video = media richness opportunity
- Competitor has no schema markup = rich result opportunity
- Competitor has stale content (2+ years old) = freshness opportunity
- Competitor has no original data = original research opportunity

---

## MARKET SATURATION ASSESSMENT

### Saturation Signals (Proceed with Caution)
- All top 10 from high-DR domains (60+)
- No small/independent sites on page 1
- Multiple well-funded competitors with deep content
- KD 40+ across most niche keywords
- YMYL restrictions blocking small sites

### Opportunity Signals (Green Light)
- Mixed DR in top 10 (some under 30)
- Thin or outdated content currently ranking
- Meta title gaps (competitors missing keyword)
- Low allintitle counts (under 1,000)
- No dedicated niche sites (only general sites covering tangentially)
- Fragmented Google Maps categories (directory signal)
- Active Reddit threads asking questions = unmet demand

---

## NICHE QUALIFICATION CRITERIA (Authority Hacker)

### The 6-Factor Framework

**Factor 1: Competition**
- Are there low-competition keywords available?
- Use allintitle + KD + SERP analysis
- Green: KD under 10 keywords exist. Red: everything KD 40+

**Factor 2: Monetization**
- Affiliate programs paying 3%+ commission?
- Programs beyond Amazon Associates?
- Top marketers cluster in same niches = highest payouts
- Physical tech = terrible niche (very low commissions despite high interest)

**Factor 3: SEO Achievability**
- Can small sites actually rank?
- Search keywords, look for independent sites in top 10
- If only big media appears, new sites will struggle

**Factor 4: Community**
- Active Facebook groups, subreddits?
- Passionate, high-spending members = easier monetization
- Dead communities = hard to build audience

**Factor 5: Evergreen**
- Will niche exist in 3+ years?
- Avoid trend-dependent topics (fidget spinners, specific meme products)
- Check Google Trends for stable or growing demand

**Factor 6: YMYL Risk**
- Is Google restricting small/new sites?
- Check SERPs: if only hospitals, gov sites, major media rank = high YMYL risk
- Niche may still be viable but requires stronger E-E-A-T signals

### The 4 Niche Archetypes (Authority Hacker)

**1. Broad/General** (e.g., verywellfit.com)
- Wide topic umbrella. Highest ceiling (7 figures/month). Big media dominates. Needs massive link profile.

**2. Community-Based** (e.g., authorityhacker.com)
- Smaller but passionate audience. Higher word-of-mouth. Must be face of brand. Stickier business.

**3. Product-Based** (e.g., dronerush.com)
- Single product category. Pure affiliate. Easy to outsource. Good for portfolio approach.

**4. Problem-Based** (e.g., peststrategies.com)
- Solving specific problems. Very high conversion rates. Mix of tutorials + product recs. Pure SEO play.

---

## DIRECTORY COMPETITIVE RESEARCH (Frey Chu)

### Ahrefs Site Explorer Process
1. Google target keyword + city name
2. Find other directories in results (skip Reddit, Yelp, major platforms)
3. Paste competitor directory URL into Ahrefs Site Explorer
4. Evaluate: monthly visitors, backlinks, referring domains, traffic trend chart

### Yelp Outranking Strategy
- Yelp is NEVER a reason to abandon a niche
- Outrank through topical authority: 100% of your site = your niche
- Yelp has millions of unrelated pages diluting its topical authority for your specific niche
- Even 100,000 low-quality backlinks from Yelp should not intimidate

### Competitor Discovery via Ahrefs
- Look up any top-ranking directory site
- Scroll to "Top organic competitors" section
- Find additional directory competitors you did not know existed
- Repeat to build comprehensive competitive map

### Intimidation Threshold
**Should worry you:** DR 90+ backlinks to competitor, hundreds of monthly visitors on linking pages, deep original data/content
**Should NOT worry you:** High backlink count from low-quality sources, Yelp/Reddit presence, competitors with generic thin content
