# SERP Analysis Workflow

Complete systematic process for analyzing search results and extracting competitive intelligence.

## Phase 1: SERP Data Collection (20-30 minutes per keyword)

### Step 1: Clean SERP View

**Why incognito?**
- Removes personalization bias (Google shows different results to logged-in users)
- Removes search history influence
- Shows "average" SERP, not your personalized one

**Process:**
1. Open private/incognito window (Ctrl+Shift+N on Windows, Cmd+Shift+N on Mac)
2. Clear address bar suggestions (don't use previously searched keywords)
3. Search your target keyword
4. Wait for results to fully load
5. Screenshot the SERP (includes ads and features for context)

**Record the following for top 10:**

| Rank | Domain | URL | DA | RDs | Content Type | Format |
|---|---|---|---|---|---|
| 1 | competitor.com | /buying-guide | 68 | 1,200 | Article | Comparison |
| 2 | blog.com | /reviews | 28 | 45 | Article | List |
| ... | ... | ... | ... | ... | ... | ... |

### Step 2: Domain Authority Extraction

**Using Ahrefs Extension:**

1. Install Ahrefs Chrome Extension (free, requires Ahrefs account)
2. As you view SERP, hover over each domain
3. Extension shows: DA, backlinks, organic traffic estimate
4. Record DA and RDs (referring domains) in spreadsheet

**Manual method (without extension):**

1. Copy domain (e.g., competitor.com)
2. Go to Ahrefs.com (or SEMrush)
3. Paste in Site Explorer
4. Note DA, backlinks, referring domains
5. Record in spreadsheet

**Time cost:** 2-3 minutes per domain (slower but accurate)

### Step 3: URL Structure Analysis

Record whether result is:
- **Root domain:** competitor.com (homepage gets all domain authority)
- **Subdomain:** blog.competitor.com (separate domain authority)
- **Subpage:** competitor.com/blog/keyword (shares domain authority with root)

**Why this matters:**
- Root domain ranking = higher authority, harder to outrank
- Subpage ranking = easier to outrank, lower authority flow
- Subdomain = separate authority calculation

**Strategic insight:** If competitors rank with subpages, you can compete with better subpage + root linking.

### Step 4: Content Format Identification

Classify each top result:

| Format | Characteristics | Ranking Signal |
|---|---|---|
| Buying Guide | "Best X for Y," comparison tables, product reviews | Commercial intent |
| How-to Article | Step-by-step instructions, "how to," tutorial | Informational intent |
| Listicle | Numbered or bulleted list, "5 ways to," "10 tips" | Scannable format |
| Comparison | Side-by-side features, "vs," specification matrix | Decision support |
| Resource Page | Comprehensive list of tools/resources, minimal narrative | Authority/link target |
| News/Blog | Recent information, often dated, topical | Freshness signal |
| Webinar/Video | Embedded video, transcript-heavy | Multimedia content |

**Strategic insight:** If 6/10 top results are buying guides, user intent is commercial (write buying guide). If 6/10 are how-tos, intent is informational.

### Step 5: SERP Features Inventory

Note which features appear:

**Feature Types:**
- **Featured Snippet (Position 0):** ~10-40 word answer above #1 organic result
- **Knowledge Graph:** Entity information box (usually right side for branded searches)
- **Local Pack:** 3-5 local business results (for "near me" keywords)
- **Image Carousel:** Picture grid of relevant images
- **Video Carousel:** Multiple video results
- **News Section:** Recent news articles
- **Ads:** Paid search results (Google Ads)
- **People Also Ask:** "Questions people ask" expandable section

**Strategic implications:**

| Feature | Impact | Strategy |
|---|---|---|
| Featured Snippet | Blocks 10-20% of clicks from position 1 | Target snippet format, answer in 40-50 words |
| Knowledge Graph | Blocks 30%+ of clicks for branded searches | Less relevant for non-branded keywords |
| Local Pack | Blocks organic for "near me" keywords | Optimize Google Business Profile if local |
| Image Carousel | Shows for product/visual keywords | Include high-quality images in content |
| Video Carousel | Shows for tutorial/how-to keywords | Create YouTube video or embed video |
| Ads | Takes up 20-30% of above-fold space | Affects click distribution |
| People Also Ask | Actually HELPS—shows related keywords | Mine for long-tail keyword variants |

### Step 6: Click Distribution Estimate

Estimate traffic distribution in SERP:

**Typical distribution without features:**
- Position 1: 28-32% of clicks
- Position 2: 14-16% of clicks
- Position 3: 10-12% of clicks
- Position 4: 6-8% of clicks
- Position 5: 4-6% of clicks
- Positions 6-10: 1-3% each

**Adjusted for featured snippet:**
- Featured snippet: 8-12% (takes from position 1)
- Position 1: 18-22% (reduced by snippet)
- Positions 2-10: Same relative distribution

**Strategic implication:** If featured snippet exists, you're not just competing for position 1; you're competing for snippet + position 1.

## Phase 2: Top 3 Results Deep-Dive (45-60 minutes)

### Step 7: Content Structure Analysis

Open each top 3 result. Document structure:

**Structure Template:**

**Article 1 (Position #1):**
- URL: example.com/keyword
- Title: "[Title tag]"
- H1: "[Article headline]"
- Introduction: [Brief summary of intro]
- Main sections:
  - Section 1: "[H2 title]"
  - Section 2: "[H2 title]"
  - Section 3: "[H2 title]"
  - Section 4: "[H2 title]"
- Conclusion: [Brief summary]
- CTA: [Call to action if present]

**Repeat for positions #2 and #3.**

**Why this matters:** Common structure among top 3 = Google-preferred structure.

### Step 8: Content Metrics Comparison

**Metric 1: Word Count**
- Tool: Use browser word counter or copy-paste into Google Docs
- Record: Word count for each article
- Analysis: Is length correlated with ranking? (often yes)

**Metric 2: Readability**
- Tool: Hemingway App (free) or Grammarly
- Check: Average sentence length, passive voice percentage, grade level
- Analysis: Is content more readable than competitors?

**Metric 3: Multimedia**
- Count: Number of images, videos, tables, charts
- Analysis: How much multimedia does winning content include?

**Metric 4: Internal Links**
- Count: How many internal links in each article?
- Analysis: Do articles link to related content?

**Template comparison table:**

| Metric | Article #1 (1st place) | Article #2 (2nd place) | Article #3 (3rd place) | Average |
|---|---|---|---|---|
| Word Count | 2,800 | 1,950 | 2,100 | 2,283 |
| Sentences | 142 | 98 | 106 | 115 |
| Avg Sentence | 19.7 | 19.9 | 19.8 | 19.8 |
| Images | 8 | 5 | 6 | 6.3 |
| Tables | 1 | 0 | 1 | 0.7 |
| Videos | 0 | 0 | 1 | 0.3 |
| Internal Links | 12 | 3 | 5 | 6.7 |

**Strategic insight:** If first place has 8 images and 1 table, your content should include images and tables.

### Step 9: Unique Content Elements

Analyze what each top result does differently:

**Element Categories:**

**Comparison Elements:**
- Does it have a comparison table? (Winning element for comparison keywords)
- Does it compare to competitors/alternatives?
- Does it quantify differences?

**Social Proof Elements:**
- Customer testimonials/reviews?
- Expert quotes or interviews?
- Statistics or research cited?
- Case studies or real examples?

**Educational Elements:**
- Step-by-step instructions?
- Diagrams or visual explanations?
- Checklists or worksheets?
- Glossary or definitions?

**Practical Elements:**
- Tools or resources mentioned?
- Templates provided?
- Cost breakdown or calculator?
- Where-to-buy information?

**Example analysis:**

| Element Type | Article #1 | Article #2 | Article #3 | Opportunity |
|---|---|---|---|---|
| Testimonials | Yes (5) | No | Yes (2) | Expected |
| Expert quotes | Yes (2) | No | No | OPPORTUNITY—add expert quotes |
| Comparison table | Yes, detailed | Yes, basic | No | Detailed table expected |
| Step-by-step | No | Yes (8 steps) | Yes (5 steps) | OPPORTUNITY—add detailed steps |
| Tools mentioned | 5 tools | 0 tools | 2 tools | Add tools review |
| Where to buy | Yes | No | Yes (basic) | OPPORTUNITY—detailed buying guide |

**Strategic insight:** Articles lacking expert quotes = opportunity for you to add interviews. Articles lacking "where to buy" = add buyability/shopping links.

### Step 10: Outdatedness Check

Identify opportunities to provide fresher content:

**Checks:**
- Publication date of article
- Last update date (if shown)
- Are statistics/data current?
- Have products/prices changed?
- Are examples still relevant?

**Example:**
- Article published 2023 (over 2 years old)
- Cites 2021 statistics
- Product recommendations are outdated models
- Pricing is no longer accurate

**Your advantage:** Update with 2026 data, current product recommendations, current pricing.

## Phase 3: Backlink Source Analysis (30-45 minutes)

### Step 11: Top Competitor Backlink Export

Using Ahrefs:

1. Site Explorer → top competitor URL
2. Backlinks tab → View all backlinks
3. Filter by "backlink type" = external dofollow
4. Sort by "domain authority" descending
5. Export CSV (if available) or record top 20-30 referring domains

**Record:**

| Referring Domain | DA | Link Type | Anchor Text | Page Relevance |
|---|---|---|---|---|
| topicalblog.com | 42 | Editorial | "best dog food" | High |
| roundupsite.com | 35 | Editorial | "dog food guide" | High |
| generalforum.com | 28 | Editorial | "dog food" | Medium |
| niche directory | 22 | Directory | Site name | Low |

### Step 12: Link Source Pattern Recognition

Identify themes in where links come from:

**Common patterns:**
- Blog mentions/roundups (specific to topic)
- Industry directories
- News mentions
- Academic or research links
- Competitor comparison pages
- General resource pages
- Podcast show notes
- YouTube video descriptions
- Forum discussions
- Guest posts

**Ask for each link source:**
- Is this a blog or publisher? (Can you get a link too?)
- Is this a directory? (Can you submit?)
- Is this a roundup/resource? (Can you reach out to author?)
- Is this a forum/comment? (Can you participate?)

**Example finding:**
- Top competitor has 8 links from dog health blogs
- Insight: Dog health blogs link to dog food content
- Action: Create list of 20+ dog health blogs to reach out to

### Step 13: Link Outreach Template Discovery

Look at competitor links and reverse-engineer their outreach:

**Example:** Competitor got link from dog health blog with anchor "best food for allergies"
- Blog published article: "Dog allergy solutions guide"
- Likely trigger: Competitor created comprehensive dog food guide, blog linked to it as resource

**Action:** Create similar comprehensive resource that dog health blogs would want to link to.

## Phase 4: Decision Making (10-15 minutes)

### Step 14: Competitive Difficulty Score

Using all data, score the keyword:

**Scoring Matrix:**

| Factor | Score | Notes |
|---|---|---|
| Your DA vs. Top 3 average | 0-3 | If average top 3 DA is 45, you need DA ~35-40 to compete |
| Content gap identified | 0-3 | Major gap = 3, no gap = 0 |
| Link sources available | 0-2 | Multiple link sources = 2, few sources = 0 |
| Timeline acceptable | 0-2 | 8-12 weeks = 2, 16+ weeks = 0 |
| Monetization potential | 0-2 | High commercial value = 2, low = 0 |

**Total score: 0-15**

- 12-15: High priority (pursue immediately)
- 9-11: Secondary (queue for later)
- 6-8: Tertiary (long-term play)
- 0-5: Skip (not worth effort)

### Step 15: Go/No-Go Decision

**GO if:**
- Content gap is significant (you can create better)
- Your DA is close to top 3 average (within 10 points)
- Multiple link sources identified
- Timeline matches your project schedule
- Monetization potential is clear

**NO-GO if:**
- All top 10 have DA >70 (too competitive)
- No clear content gap (you'd just match competitors)
- No link sources available
- Timeline is 16+ weeks (opportunity cost)
- Monetization unclear

### Step 16: Content Advantage Definition

If you decide to pursue, define your competitive advantage:

**Template:**

**Keyword:** Best dog food for sensitive stomach

**Competitive advantages:**
1. Original research: Test 10 dog foods on 20 dogs with sensitivities, document results
2. Content depth: 3,000+ words vs. 2,100 average (expand sections on transition process)
3. Unique element: Step-by-step transition guide competitors lack
4. Updates: 2026 product recommendations vs. 2023 data in top results
5. Expertise signal: Expert interview with veterinary nutritionist

**One advantage is often enough.** Multiple advantages compound your chances.

## SERP Analysis Checklist

Before declaring analysis complete:

- [ ] Top 10 domains and DA recorded
- [ ] SERP features documented
- [ ] Top 3 content structure analyzed
- [ ] Content metrics compared (word count, images, tables, etc.)
- [ ] Unique content elements identified
- [ ] Outdatedness/freshness gaps noted
- [ ] Top 2 competitors' backlinks analyzed
- [ ] Link source patterns identified
- [ ] Competitive difficulty scored
- [ ] Go/No-Go decision made
- [ ] Content advantage defined (if pursuing)

## Tools for SERP Analysis

**Essential:**
- Ahrefs Site Explorer ($99-399/month)
- Ahrefs Chrome Extension (free with account)
- Google Search (free)
- Google Incognito mode (free)

**Optional:**
- SEMrush (alternative to Ahrefs, $120+/month)
- Moz Keyword Explorer (limited free version)
- Hemingway App (readability analysis, free)
- Grammarly (writing quality, free tier available)

**No-cost analysis:**
- Manual SERP inspection
- Word count: Copy-paste into Google Docs
- Domain authority: Check once per month in batch (not every analysis)

## Time Investment Summary

**Complete SERP analysis for 1 keyword:** 90-120 minutes
- Phase 1 (Data collection): 20-30 min
- Phase 2 (Top 3 deep dive): 45-60 min
- Phase 3 (Backlink analysis): 30-45 min
- Phase 4 (Decision): 10-15 min

**Efficiency tips:**
- Batch analyze 5-10 keywords (reduces tool-switching time)
- Use templates (copy-paste speeds up recording)
- Skip backlink analysis for low-priority keywords
- Focus deep analysis on top 20 keywords only

---

*Synthesis from: Ahrefs Academy, Nicolas Gorrono SERP analysis methods, Real ranking data*
