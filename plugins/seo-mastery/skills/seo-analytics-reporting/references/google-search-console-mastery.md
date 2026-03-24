# Google Search Console Mastery: Complete Workflow

**Length:** ~280 lines

## Part 1: GSC Reports You Need

### Performance Report (PRIMARY)
**Location:** Search results → Performance

**Key data:**
- Queries (keywords) people search to find you
- Clicks (impressions that resulted in clicks)
- Impressions (times your page showed in SERP)
- Average position (rank)
- CTR (click-through rate)

**Critical workflow:**
1. Filter by top 100 queries (sort by impressions, descending)
2. Identify high-impression, low-CTR queries (optimization opportunity)
3. Note keywords where you rank #2-5 (push to #1)

**Example:**
- Keyword: "best running shoes"
- Position: 5
- Impressions: 5,000
- CTR: 1.5%
- Action: Improve title/description to increase CTR to 2.5%

### Coverage Report (SECONDARY)
**Location:** Indexation → Coverage

**Data:**
- Valid pages (indexed properly)
- Valid with warnings (indexed but some issues)
- Errors (not indexed)
- Excluded (intentionally not indexed)

**Critical workflow:**
1. Check "Valid" count (baseline)
2. Check "Errors" count (should be near zero)
3. Investigate excluded pages (any should be indexed?)

**Action:** If critical page shows as "Excluded," fix and request indexation.

### Page Experience Report (TERTIARY)
**Location:** Page experience → Report

**Data:**
- Core Web Vitals (LCP, FID, CLS)
- Mobile usability
- HTTPS coverage
- Safe browsing

**Critical workflow:**
1. Sort by "Poor" (worst performance first)
2. Note patterns (all poor pages slow on images? CSS rendering?)
3. Fix in priority order

---

## Part 2: GSC Workflows (Step-by-Step)

### Workflow 1: Find Low-CTR Keywords

**Goal:** Find keywords where you rank but people don't click.

**Steps:**
1. Performance → Top 100 queries (sort by impressions)
2. Filter: Clicks > 0 (must be ranking and getting clicks)
3. Sort by CTR (low CTR first)
4. Identify keywords with:
   - Impressions > 500
   - CTR < 1.5%
5. Example output: "best running shoes" - position 5, 5,000 impressions, 1.5% CTR

**Action:** Improve title tag and meta description for these keywords.

### Workflow 2: Find "Opportunity Zone" Keywords

**Goal:** Keywords where you're close to #1 (rank 6-15).

**Steps:**
1. Performance → Add filter: Average position between 6-15
2. Sort by impressions (highest first)
3. List top 20 keywords
4. Prioritize: High impression + high difficulty of improvement = easy wins

**Example:** "carpet cleaning Madison" - position 8, 3,000 impressions, 1.2% CTR
→ Small content update could push to #1 = +1,500 additional monthly clicks

### Workflow 3: Diagnose Indexation Issues

**Goal:** Fix pages not being indexed.

**Steps:**
1. Coverage → Filter "Errors"
2. Click each error type:
   - "Crawl anomaly" = Server issues
   - "Not found (404)" = Broken redirects
   - "Submitted URL not found" = URL changed after submission
3. Fix each issue type:
   - Crawl anomaly: Check server, fix slow/timeout issues
   - 404: Redirect to correct URL
   - Not found: Update GSC with new URL

### Workflow 4: Request Indexation for New Pages

**Goal:** Speed up indexing of newly published pages.

**Steps:**
1. Go to URL inspection (top search bar in GSC)
2. Paste URL of new article
3. Click "Request indexing"
4. Wait (Google will crawl within 24-48 hours typically)
5. Check status after 48 hours

**Why it works:** Tells Google to prioritize this URL in crawl queue.

### Workflow 5: Monitor Core Web Vitals

**Goal:** Track page speed/experience metrics.

**Steps:**
1. Page experience → Report
2. View "Poor" pages (worst performers)
3. Click any page → See specific issues:
   - LCP (Largest Contentful Paint): Target < 2.5 seconds
   - FID (First Input Delay): Target < 100ms
   - CLS (Cumulative Layout Shift): Target < 0.1
4. Common fixes:
   - LCP: Compress images, remove render-blocking JS
   - FID: Remove heavy JavaScript
   - CLS: Add proper sizing attributes to images/ads

---

## Part 3: GSC Integrations

### Integrate GA4 for Keywords + Conversions

**Setup:**
1. GSC → Settings → Google Analytics property
2. Link your GA4 property
3. Verify connection

**Benefits:**
- See which keywords drive conversions
- See conversion rate by keyword
- See revenue by keyword (if ecommerce)

**Usage:**
1. GA4 → Acquisition → Google Organic Search
2. Click "Queries" (shows top keywords)
3. See: keyword | sessions | conversions | CR%

### Export Full Dataset

**For analysis in spreadsheets:**

1. Performance → Select date range (up to 16 months)
2. Download CSV (includes all rows, not just top 1,000)
3. Use for:
   - Historical trend analysis
   - Competitive keyword tracking
   - Custom reporting

---

## Part 4: Common GSC Issues & Fixes

| Issue | Cause | Fix |
|-------|-------|-----|
| Site not verified | GSC account not authenticated | Re-verify: Settings → Ownership verification |
| No data showing | Property not linked to website | Check installation: Settings → Verify property |
| "Crawl errors" spike | Server returning 5xx errors | Check server logs, restart server |
| Pages marked "Excluded" | Duplicate content or rel="canonical" pointing elsewhere | Review canonical tags, check robots.txt |
| Rankings down | Algorithm update or lost backlinks | Check ranking trend, audit backlinks |
| CTR dropping | Title/description needs refresh | A/B test new titles in GSC |

---

## Part 5: Monthly GSC Reporting

### Create Simple Dashboard

Spreadsheet with monthly tracking:

```
| Month | Queries | Clicks | Impressions | Avg CTR | Avg Position | Coverage % |
|-------|---------|--------|-------------|---------|--------------|-----------|
| Jan   | 2,450   | 10,200 | 500,000     | 2.0%    | 12.5         | 92%       |
| Feb   | 2,580   | 11,500 | 520,000     | 2.2%    | 12.1         | 93%       |
| Mar   | 2,720   | 12,800 | 545,000     | 2.3%    | 11.8         | 94%       |
```

**Interpret:** Upward trends = healthy growth. Downward trends = investigation needed.

---

## Part 6: Optimization Workflow (Weekly)

**Every Monday:**
1. Check Performance (top 100 queries)
2. Identify 2-3 keywords for optimization
3. Create list of title/meta description improvements
4. Assign to content team

**Example list:**
```
Keyword: "best running shoes"
Current: Position 5 | Impressions: 5,000 | CTR: 1.5%
Action: New title: "Best Running Shoes 2026: Top Brands Compared"
Expected: CTR increase to 2.5% = +500 clicks

Keyword: "carpet cleaning near me"
Current: Position 12 | Impressions: 2,000 | CTR: 0.8%
Action: Add location-specific title + include "free estimate"
Expected: CTR increase to 2% = +240 clicks
```

---

## Checklist: GSC Mastery

- [ ] GSC property verified
- [ ] GA4 linked (keywords → conversions visible)
- [ ] Performance report reviewed monthly
- [ ] Coverage report checked monthly (errors < 10)
- [ ] Page experience monitored (Core Web Vitals)
- [ ] Top 100 keywords identified
- [ ] Opportunity zone keywords found (rank 6-15)
- [ ] Low-CTR keywords marked for title optimization
- [ ] Indexation issues investigated and fixed
- [ ] Monthly GSC report created (dashboard)
- [ ] Team trained on GSC workflows
