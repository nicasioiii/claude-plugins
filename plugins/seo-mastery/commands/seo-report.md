---
name: SEO Report
description: "Generate monthly SEO performance report from Google Analytics and Search Console data with KPIs, rankings, and recommendations."
---

# /seo-report — Monthly SEO Performance Report

**Type:** Slash command
**Purpose:** Generate monthly SEO performance report from Google Analytics & GSC data
**Duration:** 30-60 minutes
**Frequency:** Monthly

---

## What This Command Does

Generates a comprehensive monthly SEO report including:
- Traffic & revenue trends
- Keyword ranking changes
- Technical health status
- Competitive positioning
- Actionable recommendations

---

## How to Use

**In Claude Code:**
```
/seo-report
```

**Provides:**
1. Executive summary (1 page)
2. Performance metrics (GA4 data)
3. Keyword analysis (GSC data)
4. Technical health (Core Web Vitals)
5. Recommendations (3 actions)

---

## Prerequisites

- GA4 property set up and tracking organic traffic
- Google Search Console linked to property
- Rank tracking tool (Ahrefs/SEMrush) optional but recommended

## Output Format

**Markdown report with:**
- KPI cards (traffic, revenue, ROAS)
- Line charts (12-month trends)
- Tables (top keywords, top pages, technical issues)
- Commentary (what changed, why, what to do)

## Example Report Structure

```
# Monthly SEO Report - March 2026

## Executive Summary
- Organic revenue: $45,000 (+12% MoM)
- Organic ROAS: 4.5x
- Top ranking: 165 keywords in top 10 (+15 MoM)

## Performance Metrics
[Table of KPIs]

## Keyword Analysis
[Top 20 keywords by traffic]

## Technical Health
[Core Web Vitals status]

## Recommendations
1. [Quick win]
2. [Strategic initiative]
3. [Long-term project]
```

## Tips

- Run monthly on same day (e.g., 1st of month)
- Export data from GA4/GSC before running
- Share with stakeholders via Looker Studio dashboard
- Use report to identify optimization priorities
