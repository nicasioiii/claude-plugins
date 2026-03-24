---
name: Research Keywords
description: "Interactive keyword research workflow that guides you through seed generation, expansion, SERP analysis, and content planning"
---

# Research Keywords Command

Interactive workflow for discovering, validating, and prioritizing keywords for your SEO strategy.

## Pre-Research Questions

Before starting, answer these questions:

**Question 1: What business problem are you solving?**
(e.g., "I sell dog food online and want to rank for relevant keywords")

**Question 2: Who is your target customer?**
(e.g., "Dog owners with picky/allergic dogs")

**Question 3: What's your budget for tools?**
(e.g., "$0 (free only)" or "$100-200/month (Ahrefs)")

**Question 4: How much time can you dedicate?**
(e.g., "2-3 hours/week for research")

**Question 5: What's your domain age and authority?**
(e.g., "New site (DA 5)" or "Established site (DA 35)")

---

## Phase 1: Seed Keyword Generation

**Task:** Extract 50-100 foundation keywords from your business offering

**Output:** Spreadsheet with seeds organized into 3-5 clusters

**Process:**
1. List all products/services you offer
2. For each, write how customers describe their problem
3. Write how you describe the solution
4. Compare the two—note the language gap
5. Extract keywords from both lists
6. Organize into logical clusters

**Reference:** Read **keyword-research-methodology.md** → "Phase 1: Seed Keyword Generation"

**Time:** 2-3 hours

**Deliverable:** "seeds_[date].csv" with columns:
- Business Problem
- Customer Search Term
- Keyword Variant
- Estimated Volume (guess)
- Cluster

---

## Phase 2: Keyword Expansion & Filtering

**Task:** Use tools to expand seeds to 200-400 keywords, then filter to 80-120 priority targets

**Output:** Filtered keyword list with volume, difficulty, intent classification

**Process:**

**Step 1:** Choose your tool
- Free: Google Suggest, AnswerThePublic
- Budget: Ubersuggest ($15/month)
- Standard: Ahrefs ($99/month) or SEMrush ($120/month)

**Step 2:** For each seed, expand to 50-100 variants
- Tool generates suggestions
- Export to CSV
- Note: Volume, Keyword Difficulty, Intent

**Step 3:** Consolidate all expansions
- Combine all CSVs
- Remove duplicates
- Final list: 200-400 keywords

**Step 4:** Classify by intent
- Commercial (C): "best," "review," "vs," "price," "buy"
- Informational (I): "how to," "what is," "guide"
- Navigational (N): brand name, "[brand] review"

**Step 5:** Score each keyword
- Volume Score (0-3)
- Difficulty Score (0-3, inverted)
- Intent Score (0-4)
- Total (0-10)

**Step 6:** Filter to opportunities
- Keep keywords scoring 6+ out of 10
- Target: 80-120 keywords

**Reference:** Read **keyword-research-methodology.md** → "Phase 2: Keyword Expansion"

**Time:** 4-6 hours

**Deliverable:** "keywords_expansion_[date].csv" with columns:
- Keyword
- Volume
- Difficulty
- Intent (C/I/N)
- Volume Score
- Difficulty Score
- Intent Score
- Total Score
- Action (RANK NOW / SECONDARY / SKIP)

---

## Phase 3: SERP Analysis & Validation

**Task:** Manually validate top 50-80 keywords by examining SERP composition

**Output:** Go/No-Go decision for each keyword + content gap identification

**Process:**

**Step 1:** Select top 50-80 keywords (Score 6+)

**Step 2:** For each keyword, perform SERP analysis:
- Google the keyword (incognito)
- Record top 3 domains + DA
- Count: How many small sites (DA <40) in top 10?
- Check: Is authority spread or concentrated?
- Note: SERP features (featured snippet, ads, local pack)

**Step 3:** Identify content gaps
- What do top 3 articles cover?
- What's missing from all 3?
- Can you write something better?

**Step 4:** Classify each keyword:
- **RANK NOW:** Top 3 average DA <50, multiple small sites ranking, clear content gap
- **SECONDARY:** Top 3 average DA 50-65, 1-2 small sites ranking
- **SKIP:** All top 10 are huge brands (DA >70), no differentiation possible

**Reference:** Read **serp-analysis-workflow.md** → "SERP Data Collection & Analysis"

**Time:** 5-8 hours (for 50 keywords)

**Deliverable:** "serp_analysis_[date].csv" with columns:
- Keyword
- Top 3 Avg DA
- Small Sites in Top 10 (count)
- Content Gap (yes/no)
- Verdict (RANK NOW / SECONDARY / SKIP)
- Competitive Advantage (1-2 sentence summary)

---

## Phase 4: Content Roadmap & Publishing Plan

**Task:** Organize keywords into clusters and create publishing roadmap

**Output:** Content cluster plan with pillar + satellites, prioritized by opportunity

**Process:**

**Step 1:** Group "RANK NOW" keywords into clusters
- Look for thematic relationships
- 1 pillar (broad keyword) + 4-6 satellites (specific long-tail)
- Example cluster: "Dog Food" pillar + satellites for allergies, costs, types

**Step 2:** Prioritize clusters
- Cluster 1 (Week 1-2): Easiest to rank (lowest KD, clearest gap)
- Cluster 2 (Week 3-4): Medium difficulty
- Cluster 3+ (Week 5+): Longer timeline

**Step 3:** Define pillar + satellite keywords
- Pillar: Broad keyword (highest volume in cluster)
- Satellites: Long-tail variants (100-300 monthly searches each)

**Step 4:** Identify content advantage
- What gap do all competitors miss?
- What unique element will you include?
- How will you make content better?

**Step 5:** Create publishing timeline
- Week 1-2: Cluster 1 (pillar + 2-3 satellites)
- Week 3-4: Cluster 2
- Week 5-6: Cluster 3
- Adjust based on your writing capacity

**Reference:** Read **content-cluster-strategy.md** → "Cluster Design & Publishing"

**Time:** 3-4 hours

**Deliverable:** "content_roadmap_[date].csv" with columns:
- Cluster Name
- Pillar Keyword
- Satellite 1-6 Keywords
- Target Week
- Competitive Advantage
- Estimated Traffic/Cluster
- Content Gap Summary

---

## Implementation Checklist

Before starting content production:

- [ ] Seed keywords extracted (50+)
- [ ] Keywords expanded (200+ via tool)
- [ ] Intent classified (100% keywords tagged)
- [ ] Opportunity scored (top 80-120 selected)
- [ ] SERP analysis complete (top 50 analyzed)
- [ ] Clusters organized (3-5 clusters defined)
- [ ] Pillars selected (one per cluster)
- [ ] Content advantages identified (for each cluster)
- [ ] Publishing timeline created
- [ ] Team agrees on keyword priorities

---

## Common Outcomes by Site Authority

### New Site (DA 5-15)
- Target: Long-tail keywords (KD <30)
- Expected: 20-30 keywords ranking in first 6 months
- Timeline: 8-16 weeks per keyword
- Strategy: Batch long-tail, skip competitive keywords

### Growing Site (DA 15-30)
- Target: Mix of long-tail (KD <40) + medium keywords (KD 30-45)
- Expected: 40-60 keywords ranking in first 6 months
- Timeline: 6-12 weeks per keyword
- Strategy: Balanced approach, some competitive keywords viable

### Established Site (DA 30+)
- Target: Mix across all difficulties (KD <60)
- Expected: 80-120+ keywords ranking in first 6 months
- Timeline: 4-8 weeks per keyword
- Strategy: Can tackle competitive keywords, lots of opportunities

---

## Next Steps After Keyword Research

Once you complete keyword research:

1. **Use skill:** `content-cluster-strategy`
   - Design your content cluster architecture
   - Plan pillar + satellite structure
   - Map interlinking strategy

2. **Use skill:** `competitive-landscape-analysis`
   - Analyze top competitors for each keyword
   - Identify content gaps you can fill
   - Discover link sources for outreach

3. **Start content production**
   - Write articles following your content roadmap
   - Implement internal linking strategy
   - Monitor rankings weekly

---

## Timeline Summary

- **Phase 1 (Seed generation):** 2-3 hours → 50-100 seeds
- **Phase 2 (Expansion & filtering):** 4-6 hours → 80-120 priority keywords
- **Phase 3 (SERP analysis):** 5-8 hours → Go/No-Go decisions + content gaps
- **Phase 4 (Content roadmap):** 3-4 hours → Prioritized clusters + publishing plan

**Total research time:** 14-21 hours (2-3 weeks part-time)

**Payoff:** Clear direction for 3-6 months of content production

