# GTM, SEO Reporting & Measurement Reference

Reference file for the `seo-analytics-reporting` skill. Covers GTM operational model, tag categories, GA4 reporting architecture, Looker Studio, BigQuery, SEO KPI definitions, metric tracking phases, error analysis, the Reddit-informed measurement loop, and migration analytics.

---

## GTM Operational Model

### What GTM Does
Google Tag Manager controls what pages tags appear on and when they fire. All tag management happens inside GTM. No code deploys needed per tag change.

### Five Core Concepts

**Tags** -- the code snippets that fire (GA4 tracking, Facebook pixel, LinkedIn insight tag, Hotjar, etc.)

**Triggers** -- conditions that tell GTM when to fire a tag. Examples:
- Page View (fires on every page load)
- Click (fires when user clicks specific elements)
- Form Submission (fires when form is submitted)
- Custom Event (fires on data layer events)
- Timer (fires after specified interval)

**Variables** -- dynamic values GTM uses in tags and triggers. Two categories:
- Built-in: Page URL, Page Path, Click Classes, Click ID, etc.
- User-defined: Data layer variables, JavaScript variables, lookup tables

**Data Layer** -- a JavaScript object that passes structured data from the website to GTM. Example:
```javascript
dataLayer.push({
  'event': 'purchase',
  'ecommerce': {
    'transaction_id': 'T12345',
    'value': 49.99,
    'currency': 'USD'
  }
});
```

**Container** -- the GTM workspace holding all tags, triggers, and variables for a site. Each website gets its own container with a unique container ID (GTM-XXXXXXX).

### Three Tag Categories

**1. Google Tags (built-in templates)**
- Google Analytics (GA4)
- Google Ads (remarketing + conversions)
- Floodlight (enterprise platforms)
- Conversion Linker (improves conversion tracking accuracy)

**2. Third-Party Tag Templates**
Pre-built templates for: Microsoft Advertising, LinkedIn, Pinterest, Crazy Egg, Hotjar, MouseFlow, AdRoll, Perfect Audience, and many more.

**3. Custom Tags**
Use when no template exists:
- **Custom HTML** -- use this in most cases; allows adding any JavaScript tag
- **Custom Image** -- for adding image/pixel tags to the container

### Best Practice
Create a **demo container** in GTM to test tags without impacting live data collection. Publish changes to the demo container first, verify in preview mode, then replicate to production.

---

## GA4 Reporting Architecture

### Four Reporting Layers

**1. Standard Reports**
Pre-built dashboards available immediately:
- **Home** -- snapshot of key metrics, recent trends
- **Reports** -- organized by lifecycle (Acquisition, Engagement, Monetization, Retention)
- **Real-time** -- live user activity

**2. Explorations**
Custom data analyses for deeper questions:
- **Free-form exploration** -- custom tables with any dimension/metric combination
- **Funnel exploration** -- visualize conversion steps and drop-off
- **Path exploration** -- trace user navigation paths
- **Segment overlap** -- compare user segments
- **Cohort exploration** -- analyze user groups over time

**3. Looker Studio (External Dashboarding)**
- Connected directly to GA4 data via connector
- Build custom dashboards for stakeholder reporting
- Combine GA4 data with GSC, Google Ads, and other sources
- Acts as frontend for BigQuery data
- Shareable via link (no GA4 access needed for viewers)

**4. BigQuery (Raw Data Analysis)**
- Raw GA4 data export for SQL analysis
- Enables queries impossible in the GA4 UI
- Ideal for: cross-session analysis, custom attribution models, large-scale data processing
- Requires Google Cloud project and basic SQL knowledge
- Free tier handles most small-to-medium sites

### Search Console Link
Enriches GA4 reports with organic search data:
- Which queries drive traffic
- Impression and click trends by keyword
- Average position changes over time
- Pages performing above/below expectation

Set up in GA4 Admin > Product links > Search Console.

---

## SEO KPI Definitions

### Primary KPIs (Report Every Month)

**Organic Sessions**
- Definition: Visits from organic search sources (Google, Bing, etc.)
- Source: GA4 > Reports > Acquisition > Traffic acquisition (filter: organic search)
- Target: Month-over-month growth aligned with content publication and seasonal patterns

**Organic Revenue / Leads**
- Definition: Revenue or lead count attributed to organic search visits
- Source: GA4 key events filtered by organic source
- Target: Aligned with business revenue goals

**Keywords in Top 10**
- Definition: Count of tracked keywords ranking positions 1-10 in Google
- Source: Rank tracker (Ahrefs, SEMrush, STAT)
- Target: Steady growth; temporary drops during algorithm updates are normal

**Organic CTR**
- Definition: Clicks divided by impressions for organic search
- Source: Google Search Console > Performance
- Target: Above industry average (varies by vertical); improving trend

**Indexed Pages**
- Definition: Pages eligible to appear in search results
- Source: GSC > Pages > Valid
- Target: Stable or growing; sudden drops indicate technical issues

### Secondary KPIs

**Average Position**
- Mean ranking across tracked keyword set
- Useful for trend detection, not absolute comparison

**Organic Engagement Rate**
- Engaged sessions (10+ seconds, 2+ pages, or key event) divided by total organic sessions
- GA4's replacement for bounce rate; more meaningful metric

**Referring Domains**
- Count of unique domains linking to your site
- Leading indicator of future ranking improvements

**Core Web Vitals Pass Rate**
- Percentage of URLs passing Google's CWV assessment
- GSC > Core Web Vitals report

**AI Search Visibility**
- Brand mentions in LLM responses for target queries
- Currently requires manual testing or specialized tools

---

## Metric Tracking Phases

### Phase 1: Foundation (Months 1-2)
**Report on:** Rankings, impressions, indexation
**Reality:** Organic traffic change unlikely. SEO changes take time to compound.
**Stakeholder message:** "We're building the foundation. Here are the leading indicators."

### Phase 2: Traction (Months 2-4)
**Report on:** Rankings + traffic
**Reality:** Early traffic gains from quick wins (title tag optimization, technical fixes). Most keywords still climbing.
**Stakeholder message:** "Traffic is growing. Revenue impact coming as rankings mature."

### Phase 3: Performance (Months 4+)
**Report on:** Rankings + traffic + revenue
**Reality:** Full measurement stack active. ROI calculable. Content investments producing returns.
**Stakeholder message:** "Here is your organic ROI. Here is what we should invest next."

**Critical:** Do not promise revenue before month 4. Report leading indicators during foundation phase to maintain stakeholder confidence.

---

## Error Analysis and QA Methods

### Method 1: Tag Presence Check
- Inspect page source code for GA4/GTM snippets
- Use GTM's tag coverage report
- Verify measurement ID matches expected property

### Method 2: Browser Developer Tools
- Open Network tab, filter by "collect" (GA4 hits)
- Inspect each request payload for correct event names and parameters
- Install Adswerve dataLayer Inspector+ browser extension for visual inspection

### Method 3: Tag Assistant
- Navigate to tagassistant.google.com
- Start debugging session for your domain
- Install Tag Assistant Companion browser plugin
- View real-time tag firing with status indicators

### Method 4: GA4 DebugView
- Enable debug mode in GTM (set debug_mode parameter to true)
- View events firing in real-time within GA4 interface (Admin > DebugView)
- Verify event names, parameters, and key event triggers

### Method 5: Data Quality Dashboards
- Build customized Looker Studio dashboards to monitor data quality
- Track metrics like: data completeness, "(not set)" rates, consent rates
- Use GA4 Insights for automated anomaly alerts

### Common Issues and Fixes

| Issue | Symptom | Fix |
|-------|---------|-----|
| Tag not firing | No data in reports | Verify GTM container code on all pages; check trigger conditions |
| Consent blocking | Too little data | Verify CMP integration; check consent mode configuration |
| Missing pages | Incomplete data | Audit tag coverage across all page templates |
| "(not set)" entries | Missing parameters | Check data layer implementation; verify variable definitions |
| "(other)" entries | Cardinality limits | Reduce custom dimension variety or use BigQuery for full data |
| Broken UTMs | Missing campaigns | Audit UTM parameter formatting; check for typos and case sensitivity |

---

## The Reddit-Informed Measurement Loop

### The Closed-Loop System

1. **Reddit data informs content** -- extract real user language, pain points, competitor intelligence
2. **GA4 measures performance** -- track which Reddit-optimized pages outperform generic content
3. **Insights feed back** -- refine next round of Reddit-based content
4. **AI Overview optimization** -- GA4 measures which content gets featured; Reddit data provides natural language patterns AI prefers

### Key Metrics for Reddit-Informed Content

**Page-Level Comparison:**
- Engagement rate: Reddit-optimized pages vs generic content pages
- Average session duration: pages with comparison tables vs without
- Key event conversion rate: pages with FAQ sections and "What to Know" blocks

**Organic Search Performance:**
- Impressions and CTR for long-tail keywords derived from Reddit threads
- Ranking velocity for Reddit-derived keyword targets
- Click-through rate improvements from Reddit-informed meta descriptions

**Supporting Cluster Contribution:**
- Internal link click-through from supporting pages to main service page
- Main service page ranking changes after publishing supporting cluster content
- Combined impression growth across cluster (main page + supporting pages)

**AI Overview Tracking:**
- Monitor which Reddit-optimized pages appear in AI Overviews
- Track via GSC performance report (look for AIO-specific metrics as they emerge)
- Manual testing of target queries in Google AI Mode

---

## Monthly SEO Reporting Workflow

### Data Collection (Day 1-2 of month)

1. Export GA4 organic traffic data for previous month
2. Export GSC performance data (queries, pages, impressions, clicks, CTR, position)
3. Pull rank tracker data (keyword positions, changes, SERP features)
4. Pull referring domain count from Ahrefs/SEMrush
5. Check Core Web Vitals status in GSC
6. Run 20-30 target queries through ChatGPT/Perplexity for AI visibility check

### Report Assembly (Day 2-3)

1. **Executive summary** -- 3-5 bullets on performance, wins, and risks
2. **KPI dashboard** -- table with MoM and YoY comparisons
3. **Keyword analysis** -- top 20 by traffic + notable movers (up and down)
4. **Content performance** -- top pages by organic traffic + new content performance
5. **Technical health** -- CWV status, crawl errors, indexation changes
6. **AI visibility snapshot** -- brand mention tracking across LLM platforms
7. **Recommendations** -- 3 prioritized actions (quick win, strategic, long-term)

### Stakeholder Presentation Tips

- Lead with business impact (revenue, leads), not SEO metrics
- Explain ranking changes in business terms ("Our product page is now #3 for [keyword], which drives an estimated [X] visits/month")
- Use visuals (charts, tables) over paragraphs
- Always include next month's plan with expected outcomes
- Acknowledge algorithm updates or market shifts that affected performance

---

## Relaunch / Migration Analytics Checklist

### Pre-Migration

1. Document current GA4 configuration completely
2. Screenshot current Core Web Vitals results
3. Export baseline traffic data (3+ months)
4. Decision: new property or keep existing?
5. Set up test property for new site

### During Migration

6. Verify tracking code on all new page templates
7. Test all event tracking on staging environment
8. Verify consent mode functions correctly
9. Test cross-domain tracking if applicable
10. Verify e-commerce tracking with test transactions

### Post-Migration

11. Compare real-time GA4 data against pre-migration baselines
12. Check for "(not set)" or missing data in first 48 hours
13. Verify GSC property for new domain/URLs
14. Monitor indexation status in GSC daily for first 2 weeks
15. Continue monitoring old GSC property (may receive clicks for months)
16. Compare Core Web Vitals against pre-migration screenshots

---

## Cookie and Browser Privacy Impact

### Current State
- Apple's ITP massively restricts cookies in Safari
- All major browsers now have privacy functions restricting data collection
- Third-party cookies are effectively deprecated

### Near-Term Predictions
- Cookies will become less widespread and less important
- Companies will work more with anonymized and aggregated data
- Clear individual measurement of conversions will decrease
- Server-side solutions will become the standard for accurate tracking

### GA4's Response
- **Consent mode modeling** -- statistical extrapolation of missing data
- **Server-side tagging** -- tracking server you control
- **Google Signals** -- cross-device tracking via signed-in Google users
- **User-ID tracking** -- your own authentication-based user identification
