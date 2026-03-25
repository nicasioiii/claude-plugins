---
name: Build Dashboard
description: "Design and build an Excel financial dashboard with Power Query data transformation, KPI cards, budget vs actuals, and automated refresh. Guides you through data architecture, formula setup, and visual design."
---

# /build-dashboard

Let's build an automated financial dashboard. I'll guide you through data architecture, Power Query transformation, formula setup, and visual design -- all in Excel.

**1. What type of dashboard do you need?**
- KPI card dashboard (key metrics at a glance)?
- Budget vs actuals (variance analysis with gauge charts)?
- Cash-out dashboard (when does cash go negative)?
- Break-even dashboard (when does the business turn profitable)?
- Spotlight dashboard (deep dive on one metric)?
- Management report (actual vs budget vs prior year vs prior period)?
- Pivot table dashboard (flexible, slicer-driven)?
- Full suite (summarized financials + KPIs + BvA)?

**2. Where does your financial data live?**
- QuickBooks / Xero / other accounting software?
- Existing Excel financial model?
- Raw trial balance exports?
- Multiple systems needing consolidation?

**3. What time periods should the dashboard cover?**
- Monthly (rolling 12 months)?
- Quarterly (trailing 4 quarters)?
- Annual (multi-year comparison)?
- All of the above (with collapsible grouping)?

**4. Who is the audience?**
- Just you (owner/CFO) -- detail-heavy is fine?
- Leadership team -- summary with drill-down?
- Board of directors -- high-level KPIs with trend charts?
- External stakeholders (investors, lenders)?

**5. Do you have a budget or forecast to compare against?**
- Yes, in a separate model/file
- Yes, in the same file as actuals
- No -- I need to build that first (start with `/build-forecast` then come back)

**6. Technical starting point:**
- I have data in tables already -- ready for Power Query
- I have raw exports that need transformation
- I'm starting from scratch -- need the full pipeline

---

## What I'll Deliver Based on Your Answers:

**Data Architecture**
- Summary Grouping column mapping for your chart of accounts
- Aggregation Mapping table (Sum vs Index per account)
- Power Query ETL pipeline (unpivot, date parse, merge, append)
- One-click refresh workflow

**Dashboard Formulas**
- Universal SUMPRODUCT formula (works for P&L and BS in one formula)
- Date architecture (annual/quarterly/monthly tiers)
- Period-over-period change calculations
- Variance formulas with correct favorable/unfavorable direction

**Visual Design**
- Grid setup for professional layout
- KPI card design with branded borders and directional indicators
- Chart selection (combo, gauge/donut, sparklines, waterfall)
- Brand guideline setup (colors, fonts, icons)

**Interactive Elements**
- Date selector dropdowns via Data Validation
- Dynamic metric selection (Account or Summary Grouping switching)
- Spill arrays with named range bridging for charts
- Pivot table slicers and timelines

> Cross-reference: If you need a financial model first, use `/build-model`. For Excel formula help during the build, use `/excel-help`. For presenting dashboard insights to stakeholders, use `/explain-to-stakeholder`.

**Share your answers above** and I'll build your dashboard step by step.
