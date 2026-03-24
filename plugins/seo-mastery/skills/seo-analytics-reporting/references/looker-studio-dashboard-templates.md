# Looker Studio Dashboard Templates for SEO Reporting

**Length:** ~300 lines

## Why Looker Studio

- **Free** (Google product)
- **Integrates** with GA4, GSC, Google Sheets
- **Real-time** data updates
- **Stakeholder-friendly** (visual, not raw data)
- **Shareable** (send link to boss, auto-updates)

## Dashboard 1: Executive Dashboard

**Purpose:** Monthly board-level reporting (1 page)

**Layout:**
```
Top Row:
[Organic Revenue (Big number)] [ROAS (Big number)] [Organic CPA (Big number)]

Middle Section:
[Organic Traffic Trend (Line chart, 12 months)]
[Top 10 Keywords by Revenue (Bar chart)]

Bottom Section:
[Conversion Rate by Page Type (Pie chart)]
[Traffic by Traffic Type (Table: organic, referral, direct)]
```

**Key cards:**
- Organic Revenue: Sum of transaction_revenue where traffic_source="google"
- ROAS: Organic Revenue ÷ Budget (manual input as parameter)
- Organic CPA: Budget ÷ Conversions
- Organic Traffic Trend: Line chart, GA4 sessions, dimension=date

**Filters:**
- Date range (month-to-date, year-to-date options)
- Traffic source locked to "google"

---

## Dashboard 2: Keyword Performance Dashboard

**Purpose:** Weekly SEO team monitoring

**Layout:**
```
Top Row:
[Top 10 Rankings Count] [New Top 10 This Month] [Lost Top 10 This Month]

Middle Section:
[Keywords Ranking #1-3 (Table: keyword, position, CTR, traffic, revenue)]

Bottom Section:
[Opportunity Keywords (Position 11-30, high search volume)]
[Keyword Trend (Line: # of top 10 keywords by week)]
```

**Data source:** Google Search Console integration

**Key metrics:**
- Keyword position (sort ascending for top positions)
- Click-through rate by keyword
- Search impressions
- Organic traffic to page
- Revenue contribution

**Filters:**
- Position range
- Keyword contains (search specific keyword)

---

## Dashboard 3: Page Performance Dashboard

**Purpose:** Content performance tracking

**Layout:**
```
Top Row:
[Total Organic Sessions] [Total Organic Conversions] [Avg Conversion Rate]

Middle Section:
[Top 20 Pages by Traffic (Table: page, sessions, conversions, revenue, CR%)]
[Sessions by Page Type (Pie: Blog, Product, Service, etc.)]

Bottom Section:
[Page Performance Trend (Time-series: top 5 pages)]
[Pages with Traffic but No Conversions (Opportunity list)]
```

**Data source:** GA4 custom report

**Key metrics:**
- Sessions (traffic)
- Conversions (conversion events)
- Conversion rate (calculated: conversions/sessions)
- Revenue (transaction_revenue)

---

## Dashboard 4: Technical Health Dashboard

**Purpose:** Monitor Core Web Vitals, indexation, crawlability

**Layout:**
```
Top Row:
[% Good LCP] [% Good FID] [% Good CLS]

Middle Section:
[Indexation Rate (Big gauge: 90%)]
[Core Web Vitals Trend (Line chart, 13 weeks)]

Bottom Section:
[Pages with Poor LCP (Table: page, LCP, reason)]
[Crawl Issues (Table: issue type, count, trend)]
```

**Data source:** Google Search Console + CrUX data

**Key metrics:**
- LCP (Largest Contentful Paint) - target <2.5s
- FID (First Input Delay) - target <100ms
- CLS (Cumulative Layout Shift) - target <0.1
- Indexed pages / Published pages
- Crawl errors

---

## Dashboard 5: Attribution & ROI Dashboard

**Purpose:** Prove SEO value to finance team

**Layout:**
```
Top Section:
[Organic Revenue (Big number)] [YoY Growth %]
[SEO Budget (This Month)] [Organic ROAS]

Middle Section:
[Organic Revenue Trend (Line, 12 months)]
[Revenue by Traffic Phase (Bar: new user, returning user)]
[Customer LTV from Organic (vs other channels)]

Bottom Section:
[Attribution Model Comparison (Table)]
[Payback Analysis (Custom calculation)]
```

**Data source:** GA4 + Google Sheets (for budget input)

**Key metrics:**
- Organic revenue by month
- Organic revenue YoY growth
- SEO budget (input via Google Sheet parameter)
- ROAS calculation
- Organic customers by LTV cohort

---

## Dashboard 6: Competitive Intelligence (Advanced)

**Purpose:** Monitor ranking changes vs competitors

**Layout:**
```
[Keyword Position Comparison (Table: keyword, your rank, competitor A rank, competitor B rank)]
[Market Share Estimation (Who's winning position 1-3?)]
[New Keywords We Rank For (This month vs last)]
[Lost Rankings (Keywords we were top 3, now not)]
```

**Data source:** Ahrefs/SEMrush export + Google Sheets import

**Setup:**
1. Export keyword rank data from Ahrefs weekly
2. Import to Google Sheet
3. Create calculated columns for rank changes
4. Connect Google Sheet to Looker Studio

---

## Dashboard 7: Organic to Paid Funnel (E-Commerce)

**Purpose:** Understand how organic drives paid conversion

**Layout:**
```
[Traffic Funnel: Organic → Product View → Add to Cart → Checkout → Purchase]
[Conversion Rate by Stage (%)]]
[Revenue by Traffic Mix (organic-first vs organic-only)]
[AOV: Organic vs Paid]
```

**Data source:** GA4 funnel + UTM analysis

---

## Building Your First Dashboard (Step-by-Step)

### Step 1: Create Data Source
1. Looker Studio → Create new report
2. Add data source: Google Analytics 4
3. Select GA4 property
4. Click "Create"

### Step 2: Add KPI Cards
1. Insert → Scorecard
2. Metric: Sessions (or other KPI)
3. Comparison: Previous month
4. Style: Color-code by performance

### Step 3: Add Line Chart
1. Insert → Chart (Line)
2. Dimension: Date
3. Metric: Sessions (or revenue)
4. Time: 12 months
5. Add trend line (visual indicator of trajectory)

### Step 4: Add Tables
1. Insert → Table
2. Dimensions: Page path, Keyword
3. Metrics: Sessions, Conversions, Revenue
4. Sort by highest revenue (default)
5. Add conditional formatting (color cells if conversion rate <2%)

### Step 5: Add Filters
1. Insert → Filter
2. Filter type: Date range
3. Make filter apply to all charts

### Step 6: Share & Update Schedule
1. Click Share (top right)
2. Add stakeholder email
3. Set auto-email schedule (weekly, monthly)
4. Set permissions (view only, edit as needed)

---

## Dashboard Sharing Best Practices

**For executives:** Executive dashboard only (not technical details)
**For team:** Full dashboard (all KPIs, technical metrics)
**For stakeholders:** Auto-update weekly via email

**Email subject line:** "Weekly SEO Report: Organic Traffic +12%, Revenue $45K"

**Email body:** "Attached: Your weekly SEO report. Key highlights: [Metric 1], [Metric 2]. Questions? Meet with SEO team."

---

## Troubleshooting

| Problem | Cause | Fix |
|---------|-------|-----|
| Data not updating | GA4 delay | GA4 reports 24-48hr lag; wait or use real-time report |
| Charts blank | No data | Verify GA4 is tracking; check date range includes data |
| Wrong metrics | Wrong dimension | Re-check dimension (should be "page path" not "page title") |
| Charts look ugly | Default styling | Customize colors, fonts to match brand |
| Performance slow | Too much data | Reduce date range or filter to relevant data subset |

---

## Monthly Reporting Workflow

**1st of month (Data collection):**
- Pull Looker Studio dashboards (auto-updates overnight)
- Export top 10 keywords from GSC
- Calculate ROAS (budget ÷ revenue)

**2nd of month (Analysis):**
- Identify 3 wins (what's working)
- Identify 3 problems (what's not working)
- Create 3 recommendations

**3rd of month (Reporting):**
- Send dashboard to stakeholders (auto-emailed)
- Schedule brief call to discuss results
- Create monthly PDF report (if needed for records)

