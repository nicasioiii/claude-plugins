---
name: "SEO Analytics, GA4 & Reporting"
description: >
  MANDATORY TRIGGERS: GA4, Google Analytics, GTM, Google Tag Manager, SEO reporting, SEO KPIs,
  Looker Studio, Search Console, GSC, SEO dashboard, conversion tracking, UTM parameters,
  consent mode, BigQuery, SEO metrics, monthly SEO report, organic ROI, e-commerce tracking,
  key events.
  FOR: SEO practitioners setting up or auditing analytics infrastructure. Marketing managers
  building SEO performance dashboards. Teams implementing GA4 from scratch or migrating from
  Universal Analytics. Anyone needing to prove SEO ROI to stakeholders.
  Do NOT use for: AI search optimization strategy (use geo-ai-search-optimization), keyword
  research and competitive analysis (use keyword-research-intent), technical SEO fixes / crawl /
  indexation (use technical-seo-audit), content creation or optimization (use content-production
  or on-page-optimization).
---

# SEO Analytics, GA4 & Reporting

Analytics is where SEO becomes accountable. Without proper measurement, every other SEO activity is guesswork. This skill covers the complete measurement stack from tag deployment through executive dashboards.

## Core Philosophy

Track BOTH macro and micro conversions from the start. Most companies focus exclusively on macro conversions (purchases, leads), but micro conversions (video views, add-to-cart, newsletter signups) provide insights into user behavior and help optimize the full customer journey.

GA4 renamed "conversions" to **key events** in the interface. All metrics (page views, sessions) are derived from events and users -- the event-based model is the foundation of everything.

## When to Read Reference Files

Before setting up or auditing analytics:
- Read **ref-ga4-setup-configuration.md** for the complete GA4 architecture, event types, consent mode v2, data privacy checklist, and e-commerce tracking
- Read **ref-gtm-seo-reporting.md** for GTM configuration, reporting architecture (Looker Studio, BigQuery), SEO KPI definitions, metric tracking phases, and the Reddit-informed measurement loop

## GA4 Architecture Overview

### Account > Property > Data Stream

- **Account** -- top-level organizational unit (max 100 per Google account)
- **Property** -- the data repository (max 2,000 per account); collects from one or more data streams
- **Data stream** -- tells GA4 where data comes from (Web, Android, iOS); each has a unique **measurement ID**

**Key decision:** For multiple subdomains or top-level domains, use ONE data stream with the same measurement ID on all sites to enable coherent user tracking. Max 20 data streams per property, but keep as few as possible (multiple streams hurt report generation performance).

### Events Are the Foundation

GA4 is entirely event-based. Every user action is an event. The most important linking parameter is the **user** (unique identifier).

**Four types of events:**
1. **Automatically recorded** -- collected without configuration (page_view, session_start, first_visit)
2. **Enhanced measurement** -- toggled on in data stream settings (scroll, outbound clicks, site search, video engagement, file downloads)
3. **Recommended events** -- Google-suggested names for specific industries (add_to_cart, purchase, sign_up)
4. **Custom events** -- any event you define for unique tracking needs

### Three Setup Methods

1. **CMS/Store plugin** -- WordPress Site Kit, Shopify native; enter measurement ID; verify consent handling
2. **Google tag (gtag) directly** -- JavaScript snippet in `<head>` of every page
3. **Google Tag Manager** -- GTM loads the Google tag; more complex initial setup but superior management for multiple tracking codes

> **Cross-reference:** For technical implementation of tracking code deployment, see `technical-seo-audit`. For content performance measurement of Reddit-optimized pages, see `ai-seo-content-automation`.

## Consent Mode v2 (Mandatory)

The EU's Digital Markets Act (2024) made consent mode v2 mandatory for Google tags. This is not optional.

**How it works:**
- Consent mode transmits the user's selected consent status with each measurement call
- Without consent, GA4 uses **modeling** to extrapolate "missing" data from measured users
- You need a **consent management platform (CMP)** like Usercentrics or OneTrust
- The CMP alone is not enough -- actual tracking prevention must be implemented in GTM or code
- **Server-side tagging** is the future: your own tracking server accepts data and forwards to marketing services

## Data Privacy Configuration Checklist

1. Obtain consent via CMP before firing tracking tags
2. Enable user objection (opt-out) in consent box
3. Update privacy policy to list all analytics services
4. IP addresses are automatically anonymized in GA4 (city-level only)
5. Set data retention period: 14 months is fine (no regulation mandates 2 months)
6. Enable "Reset user data on new activity" to extend retention with each return visit
7. Conclude data processing agreement (accepted during account creation)
8. Appoint primary contact and data protection officer in account settings
9. Delete non-compliant data if collected before proper setup

## Account Data Sharing -- Recommended Defaults

Turn OFF all four options for best data privacy:
- Google products & services -- OFF (separate from Google Ads linking)
- Benchmarking -- OFF (data too general to be useful)
- Technical support -- optional (activate only when filing support request)
- Account manager -- OFF (allows Google sales staff to access your data)

No noticeable restrictions from deactivating all four. Better for data privacy audits.

## SEO Metric Tracking Phases

SEO results follow a predictable timeline. Set stakeholder expectations accordingly:

| Phase | Timeline | Metrics to Report | Reality Check |
|-------|----------|-------------------|---------------|
| **Foundation** | Months 1-2 | Rankings only | Organic traffic change unlikely; focus on indexation and ranking movement |
| **Traction** | Months 2-4 | Rankings + traffic | Early traffic gains from quick wins; most keywords still climbing |
| **Performance** | Months 4+ | Rankings + traffic + revenue | Full measurement stack active; ROI calculable |

**Important:** Do not promise revenue impact before month 4. Report on leading indicators (rankings, impressions) during the foundation phase.

## SEO KPI Definitions

### Primary KPIs (report every month)

| KPI | Definition | Source | Target Direction |
|-----|-----------|--------|-----------------|
| Organic sessions | Visits from organic search | GA4 | Up |
| Organic revenue / leads | Revenue or lead count from organic | GA4 key events | Up |
| Keywords in top 10 | Count of keywords ranking positions 1-10 | Rank tracker | Up |
| Organic CTR | Clicks / impressions for organic search | GSC | Up |
| Indexed pages | Pages eligible to appear in search | GSC | Stable or up |

### Secondary KPIs (report monthly or quarterly)

| KPI | Definition | Source |
|-----|-----------|--------|
| Average position | Mean ranking across tracked keywords | GSC / rank tracker |
| Organic engagement rate | Engaged sessions / total sessions for organic | GA4 |
| Pages per session (organic) | Average pages viewed per organic visit | GA4 |
| Referring domains | Count of unique domains linking to site | Ahrefs / SEMrush |
| Core Web Vitals pass rate | % of URLs passing CWV assessment | GSC / PageSpeed Insights |
| AI search visibility | Brand mentions in LLM responses | Manual monitoring / tools |

### Content-Specific KPIs

| KPI | What It Measures |
|-----|-----------------|
| Page-level engagement rate | Which pages hold attention (Reddit-optimized vs generic) |
| Key event conversion rate | Pages with comparison tables, FAQs, "What to Know" sections |
| Organic impressions + CTR for long-tail keywords | Reddit-derived keyword performance |
| Supporting cluster page contribution | Internal link click-through to main service page |
| AI Overview appearances | Which content gets featured in AIOs |

> **Cross-reference:** For AI visibility monitoring across LLM platforms, see `geo-ai-search-optimization`.

## GA4 as Central Database

GA4 connects to the Google ecosystem:
- **Google Ads** -- import key events as conversions for campaign optimization
- **Google Search Console** -- enriches GA4 with organic search data (queries, impressions, CTR)
- **Google Display & Video 360** -- programmatic campaign data
- **Looker Studio** -- external dashboarding connected to GA4 data

Data collected once in GA4 feeds all these tools without additional tags.

## UTM Parameter System

Use UTM parameters to identify traffic sources beyond default attribution:

| Parameter | Purpose | Example |
|-----------|---------|---------|
| utm_source | The referrer | newsletter, facebook, linkedin |
| utm_medium | Marketing medium | email, cpc, social |
| utm_campaign | Specific campaign name | spring-sale-2026 |
| utm_term | Paid search keyword (optional) | best-crm-software |
| utm_content | Ad variation (optional) | banner-v2 |

GA4 uses source/medium/campaign to classify traffic into channels. Consistent UTM discipline is critical for accurate attribution.

## E-Commerce Tracking in GA4

### Standard E-Commerce Events

| Event | When It Fires |
|-------|--------------|
| view_item | User views a product page |
| add_to_cart | User adds item to cart |
| begin_checkout | User starts checkout process |
| purchase | Transaction completes |

### Item-Level Parameters

Each event carries: item_id, item_name, item_category, price, quantity. Custom dimensions can extend default tracking. Data import feature allows uploading product catalog data for enrichment.

### What to Track

- Shopping cart additions and abandonments
- Wish list additions
- Each checkout step
- Purchase completion with revenue
- Voucher/coupon usage
- Registration/login events
- Repeat buyer identification
- User lifetime value

## Reporting Architecture

### Four Reporting Layers

1. **Standard reports** -- pre-built GA4 dashboards (Home, Reports, Explore, Advertising)
2. **Explorations** -- custom analyses with segments, funnels, path analysis
3. **Looker Studio** -- external dashboarding connected to GA4; acts as frontend for BigQuery
4. **BigQuery** -- raw GA4 data export for SQL analysis; enables queries impossible in the GA4 UI

### Search Console Integration

Link GSC to GA4 to enrich reports with organic search data. This surfaces:
- Which queries drive traffic
- Impression and click trends by keyword
- Average position changes over time
- Pages performing above/below expectation

## AI Capabilities in GA4

1. **Anomaly detection** -- compares actual data against AI-generated forecasts; configurable sensitivity
2. **Predictive audiences** -- segments based on predicted purchase/churn probability
3. **Traffic and conversion modeling** -- reconstructs data lost from users who declined tracking
4. **ChatGPT analysis** -- export GA4 data as CSV, upload to ChatGPT for ad-hoc analysis (deactivate training data usage to protect privacy)

## Error Analysis and QA

### Five QA Methods

1. **Tag presence check** -- inspect page source or GTM tag coverage report
2. **Browser developer tools** -- inspect "collect" calls in Network tab; use Adswerve dataLayer Inspector+
3. **Tag Assistant** -- start debugging for a domain; use Tag Assistant Companion plugin
4. **GA4 DebugView** -- enable debug mode to track events in real-time
5. **Data quality dashboards** -- customized Looker Studio monitors + GA4 Insights for automated alerts

### Common Issues

- No data in reports (tag not firing)
- Too little data (consent blocking)
- Missing pages (tag not on all pages)
- "(not set)" entries (missing parameters)
- "(other)" entries (cardinality limits)
- Missing campaigns (broken UTM parameters)

## GTM Operational Model

Google Tag Manager controls what pages tags appear on and when they fire. All tag management happens inside GTM without code deploys.

### Key Concepts

| Concept | What It Does |
|---------|-------------|
| **Tags** | Code snippets that fire (GA4 tag, Facebook pixel, etc.) |
| **Triggers** | Conditions that tell GTM when to fire a tag |
| **Variables** | Dynamic values used in tags and triggers |
| **Data layer** | JavaScript object passing structured data from website to GTM |
| **Container** | GTM workspace holding all tags, triggers, and variables for a site |

### Three Tag Categories

1. **Google tags** -- built-in templates for GA4, Google Ads, Floodlight, Conversion Linker
2. **Third-party templates** -- pre-built for Microsoft Ads, LinkedIn, Pinterest, Hotjar, etc.
3. **Custom tags** -- Custom HTML (most common) or Custom Image for pixels

**Best practice:** Create a demo container in GTM to test tags without impacting live data collection.

## The Closed-Loop Measurement System

The Reddit Sniper method creates a measurement loop that compounds:

1. **Reddit data informs content** -- real user language, pain points, competitor intelligence feed content creation
2. **GA4 measures content performance** -- which Reddit-optimized pages outperform generic content
3. **Insights feed back** -- refine the next round of Reddit-based content creation
4. **AI Overview optimization** -- both GA4 (measuring featured content) and Reddit data (natural language patterns) serve the goal of ranking in AI Overviews

### Key Metrics for Reddit-Informed Content

- Page-level engagement rate: Reddit-data-optimized pages vs generic content
- Key event conversion rate on pages with comparison tables, FAQ sections, "What to Know" sections
- Organic search impressions and CTR for long-tail keywords derived from Reddit threads
- Supporting cluster page contribution to main service page rankings
- AI Overview feature appearances via Search Console performance report

> **Cross-reference:** For the full Reddit Sniper extraction method, see `ai-seo-content-automation`. For AI visibility monitoring, see `geo-ai-search-optimization`.

## Cookie and Browser Privacy Impact

All major browsers now restrict data collection:
- Apple's ITP massively restricts cookies in Safari
- Chrome and Firefox have increasing privacy functions
- Predictions: cookies less widespread, more anonymized/aggregated data, less individual conversion measurement

GA4's response: consent mode modeling + server-side tagging.

## Monthly SEO Reporting Template

### Executive Summary (1 page)

- Organic revenue/leads: [amount] ([% change] MoM)
- Organic sessions: [amount] ([% change] MoM)
- Keywords in top 10: [count] ([+/- change] MoM)
- Top win: [keyword/page achievement]
- Top risk: [issue requiring attention]

### Performance Metrics Section

| Metric | This Month | Last Month | Change | YoY |
|--------|-----------|------------|--------|-----|
| Organic sessions | | | | |
| Organic revenue | | | | |
| Organic CTR | | | | |
| Keywords top 10 | | | | |
| Indexed pages | | | | |
| Referring domains | | | | |

### Keyword Analysis Section

Top 20 keywords by traffic, including: position, change, impressions, clicks, CTR, landing page.

### Technical Health Section

Core Web Vitals status, crawl errors, indexation changes, page speed metrics.

### AI Visibility Snapshot

Brand mention tracking across ChatGPT, Perplexity, Google AI Mode (manual or tool-based).

### Recommendations (3 actions)

1. Quick win (implement this week)
2. Strategic initiative (this month)
3. Long-term project (this quarter)

## Relaunch / Migration Analytics Checklist

- Decision: create new GA4 property or keep existing?
- New URLs require updating all tracking configurations
- New design/templates may break tag placements
- New forms need new event tracking
- Always set up a test property before going live
- Benchmark Core Web Vitals BEFORE migration with screenshots

> **Cross-reference:** For migration technical SEO requirements, see `technical-seo-audit`.

## What This Skill Does NOT Cover

- AI search optimization strategy (GEO tactics) -> use `geo-ai-search-optimization`
- Keyword research and competition analysis -> use `keyword-research-intent`
- Technical SEO fixes (crawl errors, indexation) -> use `technical-seo-audit`
- Content creation or on-page optimization -> use `content-production` or `on-page-optimization`
- Link building measurement -> use `link-authority-building` for strategy, this skill for metrics
