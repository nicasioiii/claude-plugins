---
name: "SEO Report"
description: "Generate a monthly SEO performance report covering organic traffic, revenue, keyword rankings, technical health, AI search visibility, and prioritized recommendations. Synthesizes GA4, GSC, rank tracker, and LLM citation data into stakeholder-ready output."
triggers:
  - SEO report
  - monthly SEO report
  - SEO performance report
  - organic traffic report
  - SEO dashboard
  - quarterly SEO review
for:
  - SEO practitioners creating monthly/quarterly reports for clients or leadership
  - Marketing managers proving organic ROI to stakeholders
  - Teams tracking AI search visibility alongside traditional SEO metrics
exclusions:
  - AI search optimization strategy -> use /geo-optimize
  - Keyword research -> use /research-keywords
  - Technical SEO audit -> use /seo-audit
  - Content planning -> use /content-plan
---

# /seo-report -- Monthly SEO Performance Report

**Type:** Slash command
**Purpose:** Generate a comprehensive monthly (or quarterly) SEO performance report with KPIs, rankings, technical health, AI visibility, and recommendations
**Duration:** 30-60 minutes
**Frequency:** Monthly (first week of month)
**Skills activated:** `seo-analytics-reporting`, `geo-ai-search-optimization`

---

## What This Command Does

Produces a stakeholder-ready SEO report that covers both traditional organic performance AND AI search visibility. Structured for executive consumption with clear business impact language.

**Outputs:**
1. Executive summary (1 page)
2. KPI dashboard with MoM and YoY comparisons
3. Keyword analysis (top performers + notable movers)
4. Content performance (top pages + new content ROI)
5. Technical health status
6. AI search visibility snapshot
7. Prioritized recommendations (3 actions)

---

## How to Use

**In Claude Code:**
```
/seo-report
```

**You'll be asked for:**
1. Reporting period (e.g., "March 2026" or "Q1 2026")
2. GA4 organic traffic data (paste or describe)
3. GSC performance data (queries, impressions, clicks, CTR)
4. Rank tracker data (optional but recommended)
5. Business context (any launches, algorithm updates, seasonal factors)

---

## Prerequisites

- GA4 property set up and tracking organic traffic
- Google Search Console linked to property and GA4
- Rank tracking tool (Ahrefs, SEMrush, STAT) optional but recommended
- For AI visibility: manual query testing results or monitoring tool data

---

## Report Structure

### Section 1: Executive Summary

3-5 bullet points covering:
- Organic revenue/leads: [amount] ([% change] MoM, [% change] YoY)
- Organic sessions: [amount] ([% change] MoM)
- Keywords in top 10: [count] ([+/- change] MoM)
- Top win of the month
- Top risk or issue requiring attention

**Tone:** Business impact first, SEO metrics second. Lead with revenue, not rankings.

### Section 2: KPI Dashboard

| Metric | This Month | Last Month | MoM Change | YoY Change |
|--------|-----------|------------|------------|------------|
| Organic sessions | | | | |
| Organic revenue / leads | | | | |
| Organic CTR | | | | |
| Keywords in top 10 | | | | |
| Indexed pages | | | | |
| Referring domains | | | | |
| Organic engagement rate | | | | |
| Core Web Vitals pass rate | | | | |

**Phase-appropriate reporting:**
- Months 1-2 (Foundation): Report rankings and impressions only. Message: "Building foundation."
- Months 2-4 (Traction): Add traffic. Message: "Traffic growing, revenue impact coming."
- Months 4+ (Performance): Full KPI stack with revenue. Message: "Here is your organic ROI."

### Section 3: Keyword Analysis

**Top 20 keywords by traffic:**

| Keyword | Position | Change | Impressions | Clicks | CTR | Landing Page |
|---------|----------|--------|-------------|--------|-----|-------------|
| | | | | | | |

**Notable movers:**
- Biggest gainers (top 5 keywords that improved most)
- Biggest losers (top 5 keywords that declined most)
- New top-10 entries
- Keywords lost from top 10

**Context:** Explain ranking changes in business terms. "Our product page moved from #8 to #3 for [keyword], which represents approximately [X] additional monthly visits worth [$ estimate]."

### Section 4: Content Performance

**Top 10 pages by organic traffic:**

| Page | Sessions | Change | Avg Position | Key Events | Revenue |
|------|----------|--------|-------------|------------|---------|
| | | | | | |

**New content performance:**
- Pages published this month: [count]
- Indexed within 30 days: [count]
- Already generating traffic: [count]
- Top new page: [URL] with [X] sessions

**Reddit-informed content comparison (if applicable):**
- Reddit-optimized pages engagement rate vs generic pages
- Conversion rate on pages with comparison tables and FAQ sections
- Supporting cluster page contribution to main service page

### Section 5: Technical Health

- Core Web Vitals: [X]% of URLs passing (change from last month)
- Crawl errors: [count] (change from last month)
- Indexation: [X] pages indexed (change from last month)
- Pages removed from index: [count] and reasons
- Server response time: [average ms]

**Action items:** List any technical issues requiring developer attention.

### Section 6: AI Search Visibility Snapshot

| Query | ChatGPT | Perplexity | Google AI Mode | Brand Mentioned? |
|-------|---------|------------|---------------|-----------------|
| [target query 1] | [cited/not cited] | [cited/not cited] | [AIO present/absent] | [yes/no] |
| [target query 2] | | | | |

**Monthly comparison:**
- Queries where brand is cited: [X] of [Y] tested (vs [Z] last month)
- New citations gained: [list]
- Citations lost: [list]
- Competitor citation changes: [notable shifts]

**Method:** Test 20-30 target queries across ChatGPT, Perplexity, and Google AI Mode. Record citation presence and position. Compare against previous month.

> For detailed AI search optimization recommendations, run `/geo-optimize` on specific pages.

### Section 7: Recommendations

**1. Quick Win (this week)**
[Specific, actionable item with expected impact]

**2. Strategic Initiative (this month)**
[Larger project with timeline and resource estimate]

**3. Long-Term Project (this quarter)**
[Investment-level initiative with business case]

Each recommendation should include: what to do, why (data supporting it), expected impact, and effort estimate.

---

## Output Format

**Markdown report** with:
- KPI tables (copy-paste ready)
- Trend indicators (arrows or +/- percentages)
- Commentary explaining what changed, why, and what to do
- Visualizations described (for Looker Studio implementation)

---

## Looker Studio Dashboard Setup

For ongoing automated reporting, build a Looker Studio dashboard with these data sources:

1. **GA4 connector** -- organic traffic, engagement, conversions
2. **GSC connector** -- queries, impressions, clicks, CTR, position
3. **Sheets connector** -- rank tracker data (export weekly)
4. **Sheets connector** -- AI visibility tracking (manual monthly input)

**Dashboard pages:**
- Page 1: Executive overview (KPI scorecards + trend charts)
- Page 2: Keyword performance (table + position distribution chart)
- Page 3: Content performance (top pages + new content tracking)
- Page 4: Technical health (CWV status + crawl metrics)
- Page 5: AI visibility (citation tracking + competitor comparison)

---

## Tips

- Run on the same day each month (e.g., 1st business day)
- Export GA4 and GSC data before running the command
- Always include business context (launches, seasonality, algorithm updates)
- Share with stakeholders via Looker Studio for real-time access
- Pair with `/geo-optimize` to action AI visibility findings
- For Reddit-informed content measurement, track pages with comparison tables and FAQ sections separately in GA4 (use content groups or custom dimensions)
- Use GA4 anomaly detection to flag unexpected changes between reports
