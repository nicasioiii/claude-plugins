---
name: "SEO Analytics & Reporting"
description: "Set up GA4, Google Search Console, track SEO KPIs, measure ROI, and create monthly reports. Attribution models, Looker Studio dashboards, AI visibility monitoring, rank tracking, and organic ROI calculation. Triggers: SEO analytics, GA4, Google Search Console, SEO report, rankings, KPIs, attribution, dashboard, organic traffic, AI visibility. Covers: GA4 setup, KPI tracking, attribution models, dashboard creation, ROI measurement. Does NOT cover: paid ads analytics, customer data platforms."
Triggers:
  - SEO analytics
  - GA4
  - Google Search Console
  - SEO reporting
  - KPIs
  - attribution
  - dashboard
  - organic ROI
  - AI visibility
---

# SKILL 9: SEO Analytics & Reporting

**Workflow Stage:** Optimize / Measure
**Complexity:** High
**Lines:** ~450

---

## Core Philosophy

This skill bridges the gap between SEO execution and business results.

Too many SEO teams operate blind: They build content, get backlinks, optimize pages—but can't prove ROI.

This skill teaches:
1. **Setup:** GA4 + GSC + tracking infrastructure
2. **Measurement:** Define what matters (KPIs that prove SEO value)
3. **Attribution:** Credit SEO for actual revenue
4. **Reporting:** Monthly dashboards that get stakeholder buy-in
5. **Analysis:** Find optimization opportunities from data

---

## When to Use This Skill

**User Asks:**
- "How do I set up GA4 for SEO tracking?"
- "How do I prove SEO is driving revenue?"
- "What KPIs should I track?"
- "How do I create an SEO report for my boss?"
- "What's our organic traffic worth?"
- "Why are we ranking well but not converting?"
- "How do I track AI search visibility?"
- "What attribution model should I use for SEO?"

**Routing Logic:**
- If user needs GA4 setup → See references: `ga4-setup-and-configuration.md`
- If user needs GSC mastery → See references: `google-search-console-mastery.md`
- If user needs dashboard → See references: `looker-studio-dashboard-templates.md`
- If user needs KPIs → See references: `seo-kpi-definitions.md`
- If user needs monthly checklist → See references: `monthly-seo-review-checklist.md`
- If user is measuring AI visibility → See references: `ai-visibility-monitoring.md`

---

## Part 1: Analytics Foundation

### Three Pillars of SEO Measurement

**Pillar 1: Visibility**
- Keyword rankings
- Search impression share
- AI visibility (ChatGPT, Perplexity, Google AI)
- SERP feature performance (featured snippets, etc.)

**Pillar 2: Traffic**
- Organic sessions
- Organic users
- Session duration (engagement)
- Click-through rate from SERP
- Traffic by keyword, page, topic

**Pillar 3: Conversion**
- Revenue from organic
- Leads from organic
- Cost per acquisition (CPA)
- Return on ad spend (ROAS) for organic
- Lifetime value (LTV) of organic customers

### Measurement Stack (Tools)

**Tier 1: Required**
- Google Analytics 4 (GA4) - Free
- Google Search Console (GSC) - Free
- Google Tag Manager (GTM) - Free

**Tier 2: Recommended**
- Looker Studio - Free
- Rank tracking tool (Ahrefs, SEMrush, Moz)

---

## Part 2: GA4 Setup for SEO

### Account Architecture

```
Google Account
└── GA4 Property (Main website)
    ├── Data Stream 1: Web (main domain)
    ├── Data Stream 2: Web (staging/testing)
    └── Settings: Internal traffic filter, referrer exclusion, consent mode
```

### Critical GA4 Configurations

1. **Enable Enhanced Measurement** (automatic events)
   - Page views ✅
   - Scroll tracking ✅
   - Outbound click tracking ✅
   - Site search tracking ✅
   - File download tracking ✅

2. **Create Custom Events** (SEO-specific)
   - form_submission (key event)
   - contact_form (key event)
   - guide_download (key event)
   - pricing_page_view
   - product_view
   - organic_conversion

3. **Create Custom Dimensions** (segmentation)
   - keyword (captured from Google via parameter)
   - content_type (blog, product, service page)
   - traffic_source (organic, paid, direct)

4. **Mark Key Events** (conversion points)
   - contact_form_submitted
   - purchase
   - newsletter_signup
   - guide_downloaded

### UTM Parameter Strategy

For organic, use:
```
utm_source=google
utm_medium=organic
utm_campaign=[campaign_name]
utm_content=[page_type]
utm_term=[keyword_target]
```

**Note:** GA4 captures these automatically from Google Search, but manual UTMs help with other sources (social, email driving to SEO content).

---

## Part 3: Google Search Console Mastery

### GSC Data You Need

**Performance Report:**
- Keyword (query) rankings and positions
- Click-through rate (CTR) by query
- Impressions (how many times your page showed in SERP)
- Ranking position (average position for keyword)
- Top pages (which pages get most impressions)

**Coverage Report:**
- Pages indexed vs. excluded
- Crawl errors
- Indexation rate (how much of your site is indexed)
- Issues preventing indexation

**Experience Report:**
- Core Web Vitals (LCP, FID, CLS)
- Mobile usability issues
- HTTPS coverage
- Mobile vs. desktop performance

### Critical GSC Workflows

**Workflow 1: Find Top-Traffic Queries**
1. GSC → Performance
2. Sort by Impressions (descending)
3. Identify keywords with high impressions but low CTR (optimization opportunity)
4. Find keywords where you rank #2-5 (push to #1)

**Workflow 2: Find Indexation Issues**
1. GSC → Coverage
2. Filter for "Excluded" pages
3. Identify pages that should be indexed but aren't
4. Fix issues (robots.txt, noindex tags, redirect chains)

**Workflow 3: Monitor Page Experience**
1. GSC → Page Experience
2. Filter for "Poor" experiences
3. Prioritize fixing Core Web Vitals
4. Re-test after fixes

---

## Part 4: SEO KPIs (What Actually Matters)

### Top-Level KPIs (Board-level metrics)

| KPI | Calculation | Target |
|-----|-----------|--------|
| **Organic Revenue** | Total revenue from organic sessions | Grows 20-30% YoY |
| **Organic ROAS** | Organic revenue / SEO spend | >300% |
| **Organic Cost per Conversion** | SEO budget / conversions | Lower month-over-month |
| **Organic Traffic** | Total organic sessions | Grows 10-15% QoQ |

### Mid-Level KPIs (Team-level metrics)

| KPI | Calculation | Target |
|-----|-----------|--------|
| **Keyword Rankings** | Keywords in top 3 positions | Grow #1 keywords 10% monthly |
| **Organic Traffic by Goal** | Sessions → Conversion events | 2-5% conversion rate (industry dependent) |
| **Average Ranking Position** | Mean position across top keywords | Improve from 15→8 |
| **Click-through Rate (SERP)** | Clicks / Impressions | Improve 10-15% via title/desc optimization |

### Operational KPIs (Tactical metrics)

| KPI | Calculation | Target |
|-----|-----------|--------|
| **Content Published** | New articles / pages per month | 8-16 high-quality pages |
| **Backlink Velocity** | New referring domains / month | 5-10 new domains monthly |
| **Pages Ranking (#1-3)** | # of pages in top 3 SERP positions | Grow by 5-10 per month |
| **Indexation Rate** | Indexed pages / Published pages | 90%+ |

---

## Part 5: Attribution Models

### GA4 Attribution Models

**Last Click (Default)**
- Gives 100% credit to last touchpoint
- **Problem:** Undervalues organic (users often click organic after research)
- **Use:** Quick estimate, not true value

**First Click**
- Gives 100% credit to first touchpoint
- **Problem:** Ignores middle content journey
- **Use:** Understanding acquisition source

**Linear**
- Distributes equal credit to all touchpoints
- **Better for:** Multi-touch journeys
- **Use:** E-commerce with research → comparison → purchase

**Time Decay**
- Gives more credit to recent touchpoints
- **Better for:** Understanding final decision-maker
- **Use:** SaaS with long sales cycles

**Position-Based (Data-Driven)**
- GA4's AI model: weights position + content contribution
- **Best for:** Enterprises with sufficient data (10K+ conversions)
- **Use:** Most accurate for mature accounts

### SEO Attribution Strategy

**Recommendation:** Use **Linear + Data-Driven** for true SEO value:

1. **Set up GA4 with Data-Driven attribution** (requires 10K+ conversions)
2. **Create organic-specific audiences** (organic traffic only)
3. **Compare conversion rates** (organic vs. other channels)
4. **Calculate organic-attributed revenue** = organic sessions × conversion rate × avg order value

**Example:**
```
Organic sessions: 10,000
Conversion rate: 3%
Average order value: $150
Organic revenue: 10,000 × 0.03 × $150 = $45,000
```

---

## Part 6: Monthly SEO Report Components

### Executive Summary (1 page)

- **Headline metric:** Total organic revenue YTD
- **Key wins:** Top 3 ranking improvements + new keywords
- **Challenges:** Top 3 underperforming areas
- **Forecast:** Projected revenue next 3 months

### Performance Summary (1-2 pages)

**Traffic metrics table:**
```
| Metric | This Month | Last Month | Change | Trend |
|--------|-----------|-----------|--------|-------|
| Organic sessions | 45,000 | 42,000 | +7% | ↑ |
| Organic conversions | 1,350 | 1,260 | +7% | ↑ |
| Avg ranking position | 12.5 | 14.2 | +1.7 | ↑ |
| CTR from SERP | 2.3% | 2.1% | +0.2% | ↑ |
```

**Key metrics dashboard** (visual):
- Organic traffic trend (line chart, 12 months)
- Top keywords by traffic (bar chart, top 10)
- Revenue by page type (pie chart)

### Content Performance (1 page)

**Top performing pages:**
- Page title
- Organic traffic
- Conversions
- Conversion rate

**Top ranking improvements:**
- Keyword
- Previous position
- Current position
- Traffic gained

### Technical & SEO Health (1 page)

- **Indexation rate:** % of site indexed
- **Core Web Vitals:** LCP, FID, CLS status
- **Backlink profile:** New referring domains + lost domains
- **Issues:** Any crawl errors, indexation issues, security issues

### Recommendations (1 page)

- **Quick wins:** 3-5 optimization opportunities (high impact, low effort)
- **Medium-term:** 3-5 strategic initiatives (3-6 month projects)
- **Long-term:** 2-3 strategic direction changes (12+ month vision)

---

## Part 7: Organic ROI Calculation

### The Formula

```
Organic Revenue = Organic Sessions × Conversion Rate × Average Order Value

Organic Profit = Organic Revenue - SEO Budget

Organic ROAS = Organic Revenue / SEO Budget

Organic CPA = SEO Budget / Conversions
```

### Real Example

**SaaS company:**
```
Organic sessions/month: 10,000
Conversion rate: 2% (visitors → free trial signup)
Customer value: $5,000 (annual contract value)

Monthly organic revenue value: 10,000 × 0.02 × $5,000 = $1,000,000 annualized

Monthly SEO spend: $15,000 (3 FTE + tools)
Annual SEO spend: $180,000

Organic ROAS: $1,000,000 / $180,000 = 5.5x (or 550% ROI)
```

### Payback Period

```
Months to break even = SEO budget / Monthly organic profit

Example:
SEO setup cost: $20,000 (content, technical audit, setup)
Monthly organic profit: ($1M/12 months) - $15K = $68,333
Payback period: $20,000 / $68,333 = 0.29 months (= 1 week)
```

---

## Part 8: AI Visibility Measurement

New metric for 2026+: **AI Search Visibility**

### What to Track

1. **AI Citations** - How many times your content appears in AI responses
   - Tools: Promptwatch, Profound
   - Metric: Monthly citations across models

2. **AI Search Rankings** - Position in AI-generated answers
   - Models: ChatGPT, Perplexity, Google AI Overviews, Claude
   - Metric: # of queries where you rank in top 3 citations

3. **AI Visibility Score** - Overall presence across AI models
   - Weighted by model popularity
   - Weighted by position (top cite > bottom cite)

### Measurement Workflow

**Monthly:**
1. Use Promptwatch/Profound to monitor AI citations
2. Count citations across 5+ major AI models
3. Compare trend month-over-month
4. Identify keywords gaining/losing AI visibility

**Quarterly:**
1. Audit top 50 queries for AI visibility
2. If missing citations, create content specifically for AI
3. Optimize for AI ranking signals (data, statistics, unique insights)

---

## Part 9: Dashboards & Visualization

### Looker Studio Dashboard Structure

**Page 1: Executive Summary**
- KPI cards (organic traffic, revenue, ROAS)
- Traffic trend line chart
- Top 10 keywords bar chart

**Page 2: Keyword Performance**
- Table: Keywords | Position | Traffic | CTR | Conversions
- Sortable/filterable

**Page 3: Page Performance**
- Table: Page | Organic Traffic | Conversions | Conversion Rate | Revenue
- Filter by page type

**Page 4: Technical Health**
- Core Web Vitals status
- Indexation rate
- Crawl errors

**Page 5: Traffic Attribution**
- Organic traffic by source (organic search vs. organic referral)
- Organic traffic by landing page
- Conversion flow

---

## Part 10: Avoiding Common Mistakes

### Mistake 1: Tracking vanity metrics
❌ "We got 100K impressions!"
✅ "We converted 500 impressions into 15 customers at $5K ACV = $75K revenue"

### Mistake 2: Using last-click attribution
❌ "Paid search gets credit for all conversions"
✅ "Organic content initiates, paid search converts. Both deserve credit."

### Mistake 3: Not tracking revenue
❌ "Traffic up 20%"
✅ "Traffic up 20%, revenue up 45% due to higher-intent keywords"

### Mistake 4: Not segmenting by traffic source
❌ "Organic traffic averaged 3% conversion rate"
✅ "Blog traffic: 1% CR | Product pages: 8% CR | Category pages: 5% CR"

---

## Navigation & Handoffs

**User needs GA4 implementation guidance?**
→ Use `ga4-setup-and-configuration.md` reference

**User needs KPI definitions?**
→ Use `seo-kpi-definitions.md` reference

**User needs dashboard templates?**
→ Use `looker-studio-dashboard-templates.md` reference

**User needs monthly workflow?**
→ Use `monthly-seo-review-checklist.md` reference

**User needs rank tracking guidance?**
→ Use `rank-tracking-and-serp-analysis.md` reference

**User has questions about organic ROI?**
→ Use `organic-roi-calculation.md` reference

---

## Key Takeaways

1. **Analytics setup** matters as much as SEO tactics
2. **KPIs should be business-aligned** (revenue, not just traffic)
3. **Attribution models** need sophistication (not last-click)
4. **Monthly reporting** drives stakeholder buy-in and budget
5. **AI visibility** is new measurement frontier (2026+)
6. **Organic ROI** is now measurable and impressive (5-10x typical)

---

## Tools & Resources

- GA4 (Google Analytics 4) - Free
- Google Search Console - Free
- Google Tag Manager - Free
- Looker Studio - Free
- Rank tracking: Ahrefs, SEMrush, Moz
- AI visibility: Promptwatch, Profound
- Attribution: GA4 native, Littledata, Ruler Analytics
