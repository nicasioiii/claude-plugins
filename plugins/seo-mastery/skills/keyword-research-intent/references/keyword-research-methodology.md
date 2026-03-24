# Keyword Research Methodology

Complete step-by-step framework for conducting professional keyword research with validation gates.

## Complete Research Workflow

### Phase 1: Seed Keyword Generation (2-3 days)

**Goal:** Extract 50-100 foundation keywords from your business offering.

**Step 1A: Business Analysis**
1. List all products, services, or solutions you offer
2. For each offering, write down 5 ways a customer might describe their problem
3. Write down 5 ways YOU would describe the solution
4. Compare: These two lists reveal the language gap

**Example:**
- Your framing: "Natural probiotic supplement for canine GI health"
- Customer framing: "Best food for dog diarrhea," "Dog probiotics," "Soft stools dog food"

**Step 1B: Seed Keyword Extraction**
Create three columns in a spreadsheet:

| Business Problem | Customer Search Term | Keyword Variant |
|---|---|---|
| Sensitive digestion | Sensitive stomach dog food | Best food for sensitive stomach |
| | | Dog food for upset stomach |
| | | Limited ingredient dog food |
| | | Easily digestible dog food |
| Skin allergies | Dog skin allergies | Best dog food for itchy skin |
| | | Dog food for allergic reactions |
| | | Hypoallergenic dog food |

**Minimum 5-8 keywords per problem area.**

**Step 1C: Competitive Validation**
For each seed keyword, perform quick SERP check:
1. Google the keyword
2. Observe: Are there ranking small sites (not just Amazon/Walmart)?
3. Count: How many commercial results (reviews, comparisons, buying guides) appear?

If answer is NO to #2 or <3 commercial results, that keyword is likely not viable.

**Step 1D: Organize Seeds into Clusters**
Group related seeds together. Example cluster:

**CLUSTER: "Dog Digestive Issues"**
- Best dog food for sensitive stomach
- Best dog food for diarrhea
- Best dog food for vomiting
- Dog food for upset stomach
- Limited ingredient dog food
- Easily digestible dog food
- Probiotic dog food
- Best dog food for IBS dogs

**Target:** 3-5 clusters of 8-12 seeds each.

### Phase 2: Keyword Expansion & Tool-Based Research (3-4 days)

**Goal:** Expand seeds to 200-400 total keywords, then filter to 80-120 targets.

**Step 2A: Tool Selection & Setup**
Choose ONE tool and go deep (switching tools mid-project wastes time):

**Ahrefs (Recommended)**
- Keyword Explorer: 100+ keyword suggestions per seed
- Data: Volume, KD, global vs. local, SERP features
- Export: Download full CSV for offline analysis
- Cost: $99/month minimum

**SEMrush**
- Keyword Magic Tool: 1M+ keywords per seed
- Data: Volume, difficulty, intent, trend
- Export: CSV with competitive analysis
- Cost: $120/month minimum

**Moz Keyword Explorer**
- Limited: ~40 suggestions per seed, but accurate difficulty
- Data: Volume, KD (0-100 scale), SERP features
- Cost: Included in Pro subscription ($99/month)

**Step 2B: Bulk Expansion**
For each seed keyword:

1. Open Keyword Tool (Ahrefs Keyword Explorer, SEMrush Keyword Magic, or Moz)
2. Enter seed keyword
3. Generate suggestions (typically 100-1000 depending on tool)
4. Apply filters:
   - **Search Volume:** 50+ monthly minimum
   - **Keyword Difficulty:** < 60 (you can adjust based on domain authority)
   - **Language:** English (or target language)
   - **Region:** United States (or target region)
5. Export all results to CSV
6. Save with naming convention: `[date]_[seed-keyword]_expansion.csv`

**Step 2C: Deduplicate & Consolidate**
1. Copy all expanded keywords into single master spreadsheet
2. Remove duplicates: Data → Remove duplicates (in Excel) or similar
3. Remove single-word keywords for now (we'll add them in Phase 3)
4. Result: 200-400 total keywords

**Step 2D: Add Intent Classification**
Add column: "INTENT" with values:
- **C:** Commercial (buyer intent: review, best, comparison, where to buy)
- **I:** Informational (learning: how to, what is, guide to)
- **N:** Navigational (brand search, "[brand] review")

Classification rules:
- If keyword contains: "best," "top," "review," "vs," "buy," "price," "where to" → C
- If keyword contains: "how to," "what is," "guide to," "why," "definition" → I
- If keyword is brand name or brand + modifier → N

Use formula in spreadsheet to auto-classify:
```
=IF(OR(SEARCH("best",A1),SEARCH("review",A1),SEARCH("buy",A1)),"C",IF(OR(SEARCH("how to",A1),SEARCH("guide",A1)),"I","N"))
```

**Step 2E: Rank by Opportunity Score**
Add columns:
- Volume Score (0-3)
- Difficulty Score (0-3, inverted)
- Intent Score (0-4)
- Total Score (sum of above, 0-10)

Use spreadsheet formulas to auto-calculate:
```
Volume Score: =IF(A1<50,0,IF(A1<200,1,IF(A1<1000,2,3)))
Difficulty Score: =IF(B1>60,0,IF(B1>40,1,IF(B1>20,2,3)))
Intent Score: =IF(C1="C",4,IF(C1="I",2,0))
Total Score: =SUM(volume_col,difficulty_col,intent_col)
```

Sort by Total Score descending.

### Phase 3: SERP Analysis & Validation (3-4 days)

**Goal:** Validate that your top 50-80 keywords are actually rankable.

**Step 3A: Target Keyword Selection**
From sorted list, identify keywords with:
- Total Opportunity Score ≥ 6
- Volume ≥ 100 monthly (minimum threshold for effort)
- Difficulty ≤ 45 (adjust based on your domain age)

Target: 50-80 keywords for detailed SERP analysis.

**Step 3B: SERP Composition Audit**
For each target keyword, do manual Google search (incognito mode):

Record in spreadsheet:
1. **Top 3 Domains:** List domain names (domain.com)
2. **Domain Authority (DA):** Use Ahrefs or Moz extension to check DA of top 3
3. **Small Site Count:** Do small sites (<DA 40) rank in top 10?
4. **Commercial Result Count:** How many reviews/comparisons/buying guides appear?
5. **SERP Features:** Any featured snippets, image carousels, knowledge graphs?
6. **Verdict:** RANK NOW / SECONDARY / SKIP

**Verdict Criteria:**

**RANK NOW** (Start immediately, expect 3-6 month timeline):
- Top 3 DA <50
- ≥3 commercial results visible
- At least 1 small site in top 10
- No knowledge graph or featured snippet blocking organic results

**SECONDARY** (Queue after quick wins):
- Top 3 DA 50-65
- 2 commercial results visible
- 1-2 small sites in top 10
- Featured snippet present (but not blocking clicks)

**SKIP** (Not viable for your domain):
- Top 3 DA >70
- <2 commercial results
- Zero small sites in top 10
- Featured snippet or knowledge graph dominates (e.g., "what is X" returns graph only)
- All top 10 are brand authorities or massive publishers

**Step 3C: Content Gap Identification**
For each RANK NOW keyword, examine top 3 results:

1. **Common elements:** What do all top 3 articles cover?
2. **Unique elements:** What does winner have that others don't?
3. **Missing elements:** What logical section is missing from all three?
4. **Format:** List, comparison table, expert interviews, video, etc.?
5. **Depth:** Average word count of top 3?
6. **Your advantage:** How can you do this better/different?

Example:
- Keyword: "Best dog food for sensitive stomach"
- Common: Price range, ingredient list, feeding guidelines
- Winner has: Customer testimonials, vet recommendation
- Missing: Transition guide (how to switch foods without digestive upset)
- Your advantage: Add transition guide (differentiator)

### Phase 4: Keyword Organization & Publishing Plan (2-3 days)

**Goal:** Organize keywords into content clusters and publishing roadmap.

**Step 4A: Cluster Organization**
Group your 50-80 target keywords by topic similarity:

**Cluster Template:**

| Pillar Keyword | Monthly Volume | KD | Satellites | Total Articles | Timeline |
|---|---|---|---|---|---|
| Best dog food for sensitive stomach | 180 | 35 | Food for diarrhea (120), Ingredient guide (80), Transition tips (60) | 4 | Month 1 |
| Best dog food for allergies | 240 | 42 | Beef allergy (90), Grain-free debate (70) | 3 | Month 2 |

**Cluster size:** 3-5 satellites per pillar = 4-6 articles per cluster

**Step 4B: Publishing Cadence**
Rule: Publish entire cluster at once (if ≤8 articles) or stagger if larger.

Recommended timeline:
- **Weeks 1-2:** 8-10 articles (first cluster)
- **Weeks 3-4:** 8-10 articles (second cluster)
- **Weeks 5-6:** 8-10 articles (third cluster)
- **Weeks 7+:** Monitor rankings, interlink, update based on performance

**Step 4C: Master Keyword Database**
Create final tracking sheet with columns:
- Article title (will be determined later)
- Target keyword
- Intent (C/I/N)
- Opportunity Score
- Cluster assignment
- Pillar or satellite?
- Publishing week
- Status (Not started / In progress / Published / Ranking)
- Current ranking (track weekly)
- Current traffic (track weekly)

This becomes your single source of truth for content planning.

**Step 4D: Quick Win Strategy**
Identify 10-15 keywords with:
- Score 8-10
- KD <25
- Monthly volume 100+
- Commercial intent

Publish these first (weeks 1-3). Ranking typically happens in 4-8 weeks, building momentum and showing results.

## Validation Gates & Quality Checks

**Gate 1: Seed Validation (End of Phase 1)**
Before expanding, confirm:
- [ ] 5+ keywords per business problem identified
- [ ] Each seed has ≥1 small site in SERP
- [ ] 3-5 clusters defined
- [ ] Team agrees clusters align with business priorities

**Gate 2: Expansion Validation (End of Phase 2)**
Before SERP analysis, confirm:
- [ ] 200+ unique keywords collected
- [ ] Intent classification complete (100% of keywords tagged)
- [ ] Opportunity scoring done and reviewed
- [ ] Top 80 keywords selected for SERP analysis

**Gate 3: SERP Validation (End of Phase 3)**
Before content production, confirm:
- [ ] ≥50 keywords with RANK NOW verdict
- [ ] SERP analysis for all targets documented
- [ ] Content gap analysis complete for top 20 keywords
- [ ] Team consensus on viability

**Gate 4: Content Plan Validation (End of Phase 4)**
Before publishing, confirm:
- [ ] Master keyword database complete
- [ ] Publishing schedule assigned
- [ ] Cluster interlinking mapped
- [ ] Content outline for first 10 articles approved

## Tools & Resources

**Essential Tools:**
- Ahrefs: $99/month (primary tool)
- Google Sheets: Free (organizing research)
- Google Incognito Mode: Free (SERP checking)

**Optional Tools:**
- Ahrefs Chrome Extension: Check DA on any domain
- Moz Keyword Explorer: Free 10 queries/month for DA/KD validation
- Google Search Console: Free (track queries getting impressions)
- Google Trends: Free (identify seasonal patterns)

**Automation:**
- Zapier + Ahrefs: Auto-export keyword updates to Sheets
- Google Sheets formulas: Auto-classify intent and score

## Common Mistakes to Avoid

**Mistake 1: Targeting only high-volume keywords**
- High-volume = high competition = slow ranking
- Long-tail keywords (3-5 words, 50-200/month volume) = faster wins
- Rule: 30% broad, 50% mid-tail, 20% long-tail

**Mistake 2: Ignoring intent**
- Ranking for a keyword doesn't matter if you can't monetize it
- Always validate commercial intent before investing content effort
- Rule: 70%+ of your content targets commercial intent keywords

**Mistake 3: Copying competitors' keywords without validation**
- Just because competitor ranks for it doesn't mean it's profitable for you
- Their domain authority and monetization may be different
- Always run your own SERP analysis

**Mistake 4: Relying only on keyword tools**
- Tools estimate volume; actual search volume varies by region/season
- Always check Google Search Console for real query data
- Tools show estimated KD; real ranking difficulty varies by your authority

**Mistake 5: Researching but never publishing**
- Analysis paralysis is common
- At Gate 3, you have enough data; publish your first article
- You learn more from one published article than 100 hours of research

## Timing & Effort Expectations

**Total time for complete keyword research:** 2-3 weeks full-time, or 6-8 weeks part-time

**Breakdown:**
- Phase 1 (Seed generation): 3-5 days
- Phase 2 (Expansion & filtering): 4-6 days
- Phase 3 (SERP analysis): 5-7 days
- Phase 4 (Organization & planning): 3-5 days
- Validation & review: 2-3 days

**Team involvement:**
- SEO strategist: Leads all phases
- Content manager: Validates intent classification, reviews cluster organization
- Optional subject matter expert: Reviews for niche accuracy

---

*Synthesis from: Nicolas Gorrono (Modules 00-07), AuthorityHacker TASS 3.0, Koray Tugberk Gubur*
