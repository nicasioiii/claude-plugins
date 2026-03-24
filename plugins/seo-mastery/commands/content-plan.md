---
name: Content Plan
description: "Generate a content architecture plan with clusters, internal linking strategy, and publishing calendar. Activates content-cluster-strategy and topical-authority-semantic skills."
---

# /content-plan -- Content Cluster & Calendar Generator

## INTAKE QUESTIONS (Ask All Before Planning)

### Question 1: Keyword Data
**Do you have a keyword list ready?**

| Choice | Action |
|--------|--------|
| A) Yes, I have a prioritized keyword list | Proceed to planning |
| B) No, I need keywords first | Run `/research-keywords` first, then return |

### Question 2: Site Type
**What type of site are you building?**

| Choice | Architecture Model |
|--------|-------------------|
| A) Authority/content site | Soft silo + pillar-cluster (Authority Hacker) |
| B) Topical authority play (semantic SEO) | Three-layer root/seed/node (Koray) |
| C) E-commerce store | Collections-first with sub-collection multiplier |
| D) Local service business | Location-based clusters + GBP integration |
| E) Directory / programmatic SEO | Hub + sub-page template pattern |
| F) Publisher / media site | Three content buckets + quarterly sprints |

### Question 3: Content Capacity
**How much content can you produce per month?**

| Choice | Publishing Strategy |
|--------|-------------------|
| A) 1-2 articles/month | Depth over breadth; prioritize quality nodes |
| B) 4-8 articles/month | Standard cadence; mix pillar + cluster content |
| C) 12+ articles/month | Can build full clusters rapidly; consider patternless momentum |
| D) Programmatic / AI at scale | Bulk production with quality guardrails |

### Question 4: Existing Content
**How much content do you already have?**

| Choice | Action |
|--------|--------|
| A) None (starting fresh) | Build architecture from scratch |
| B) Under 20 articles | Audit existing, plan around gaps |
| C) 20-100 articles | Content decay audit first (keep-kill-merge-refresh) |
| D) 100+ articles | Full audit required before adding more |

---

## WORKFLOW (After Intake)

### Phase 1: Architecture Design
**Skill activated:** `content-cluster-strategy`

1. Group keywords into 5-8 topic clusters
2. Identify pillar page for each cluster (highest-volume keyword)
3. Map cluster pages (supporting keywords) under each pillar
4. Assign content type per page (info / commercial / support)
5. Design URL hierarchy reflecting cluster structure

### Phase 2: Topical Authority Mapping
**Skill activated:** `topical-authority-semantic`

1. Define central entity and central search intent
2. Identify source context (brand identity + monetization model)
3. Filter attributes by prominence, popularity, relevance
4. Designate quality nodes (placed closest to homepage, target hardest topics)
5. Plan content brief template for entity classes

### Phase 3: Internal Linking Plan
**Skill activated:** `content-cluster-strategy`

1. Map link flow: pillar -> cluster -> pillar (bidirectional)
2. Plan cross-cluster links where topically relevant
3. Assign anchor text per link using ratios (30% exact / 60% exact+filler / 10% partial)
4. Identify high-authority existing pages to link FROM (Ahrefs Best by Links)
5. Plan hub page / homepage links to root articles

### Phase 4: Publishing Calendar
**Skill activated:** `content-cluster-strategy`

1. Assign content to weeks (3 articles/week if capacity allows)
2. Sequence: lower-difficulty topics first for quick wins
3. Group related topics in series for efficient interlinking
4. Plan cornerstone/pillar content early (hub pages needed for cluster linking)
5. Build in refresh cycles (Gold tier = every 3 months)

---

## OUTPUT DELIVERABLE

### 1. Content Cluster Map
Visual representation of all clusters with:
- Pillar page (central node) per cluster
- Cluster pages (supporting nodes)
- Internal link connections
- Content type labels (info / commercial / support)

### 2. Internal Linking Plan
| Source Page | Target Page | Anchor Text | Anchor Type |
|------------|-------------|-------------|-------------|
| [Page A] | [Pillar 1] | exact keyword | Exact match |
| [Page B] | [Pillar 1] | keyword + filler | Exact + filler |

### 3. Publishing Calendar
| Week | Article | Keyword | Type | Cluster | KD | Priority |
|------|---------|---------|------|---------|-----|----------|
| 1 | Title | keyword | Info | Cluster A | 8 | High |
| 1 | Title | keyword | Commercial | Cluster A | 12 | High |

### 4. Content Decay Schedule (If Existing Content)
| Tier | Pages | Review Frequency | Next Review |
|------|-------|-----------------|-------------|
| Gold | [list] | Every 3 months | [date] |
| Silver | [list] | Every 6-12 months | [date] |
| Bronze | [list] | Every 12-18 months | [date] |

**Next step suggestions:**
- "Run `/optimize-on-page` to optimize individual pages as you publish."
- "Run `/seo-audit` to check technical readiness before publishing."
- "Run `/write-content` to generate SEO-optimized articles from your plan."
