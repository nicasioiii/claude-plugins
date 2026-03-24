---
name: Research Keywords
description: "Full keyword research workflow from brainstorm to prioritized list. Activates keyword-research-intent and competitive-landscape-analysis skills."
---

# /research-keywords -- Keyword Research Workflow

## INTAKE QUESTIONS (Ask All Before Researching)

### Question 1: Business Context
**Describe your business in 2-3 sentences:**
- What you sell or do
- Who your target customer is
- Your geographic focus (local, national, global)

### Question 2: Current State
**Where are you in your SEO journey?**

| Choice | Implication |
|--------|------------|
| A) Brand new site, no content | Start with low-KD keywords, build from scratch |
| B) Existing site, some content, want more traffic | Mine GSC for secondary keywords + find gaps |
| C) Established site, want to dominate a new topic | Competitor reverse engineering + cluster planning |
| D) E-commerce store, need product/collection keywords | Collections-first strategy, sub-collection multiplier |
| E) Directory or programmatic SEO project | 7-filter framework, "near me" keywords |

### Question 3: Known Competitors
**List 2-5 competitors (URLs) you know about.** If unknown, say "none" and we will find them.

### Question 4: Tools Available
**Which tools do you have access to?**
- [ ] Ahrefs
- [ ] SEMrush
- [ ] DataForSEO
- [ ] Answer Socrates
- [ ] Clicks.so
- [ ] Google Search Console (existing site)
- [ ] None (will use free methods only)

---

## WORKFLOW (After Intake)

### Phase 1: Seed Keyword Generation
**Skill activated:** `keyword-research-intent`

1. Generate 30-50 seed keywords using:
   - AI brainstorm (Layer 1 of three-layer system)
   - Business context analysis
   - Customer problem/solution mapping
2. Classify each seed by intent: informational, commercial, transactional

### Phase 2: Competitor Keyword Mining
**Skill activated:** `competitive-landscape-analysis`

1. Identify 3-5 competitors from SERP analysis
2. Extract competitor keyword data (Ahrefs or DataForSEO)
3. Filter: Position 3+, Volume 500+, KD under 40
4. Add promising keywords to master list
5. Check "also rank for" for subtopic expansion

### Phase 3: Validation & Expansion
**Skill activated:** `keyword-research-intent`

1. Validate all keywords with volume + KD data (DataForSEO or Ahrefs)
2. Run allintitle check on top candidates
3. Check meta title gaps in SERPs
4. Expand with CONCATENATE method if applicable
5. Run through Answer Socrates for deep clustering (if available)

### Phase 4: Prioritization
**Skills activated:** `keyword-research-intent` + `competitive-landscape-analysis`

1. Score each keyword: Volume x (1/KD) x CPC = Opportunity Score
2. Classify by intent and content type needed
3. Group into clusters (potential pillar-cluster relationships)
4. Select top 50 target keywords
5. Flag long-term targets (high volume, high KD)

---

## OUTPUT DELIVERABLE

A structured keyword spreadsheet with:

| Column | Data |
|--------|------|
| Keyword | Target phrase |
| Volume | Monthly search volume |
| KD | Keyword difficulty (0-100) |
| CPC | Cost per click (commercial value indicator) |
| Intent | Informational / Commercial / Transactional |
| allintitle | Competition count |
| Content Type | Blog post / Pillar page / Product page / Collection |
| Priority | High / Medium / Low / Long-term |
| Cluster | Which topic cluster this belongs to |
| Notes | SERP observations, meta title gaps, competitor weaknesses |

**Next step suggestion:** "Your keyword research is complete. Run `/content-plan` to turn this into a content architecture with clusters, internal linking, and a publishing calendar."
