---
name: PPC Campaign Structures & Financial Tactics
description: >
  Campaign type templates with naming conventions, bid optimization decision matrix,
  placement report analysis framework, DSP audience types and funnel mapping, DSP
  budget allocation template, credit card stacking strategy for ad spend, supplier
  payment via Melio, advanced reporting tools (SUPA v3.0, PTD), module-by-module
  Incrementum course architecture, and bulksheet operations guide.
---

# PPC Campaign Structures & Financial Tactics

---

## Campaign Naming Convention

Use a standardized format encoding all key information:

**Template:** `[ProductName]-[MatchType]-[TargetType]-[Date]`

**Examples:**
- `CoffeeMug-Exact-Keyword-2026Q1`
- `CoffeeMug-Auto-Discovery-2026Q1`
- `CoffeeMug-ASIN-Competitor-2026Q1`
- `CoffeeMug-Branded-Keyword-2026Q1`

### Why It Matters
- Enables filtering and sorting at scale
- Makes bulksheet operations manageable
- New team members can understand campaign purpose immediately
- Critical once you exceed 20-30 active campaigns

---

## Campaign Type Templates

### 1. Auto Campaign (Discovery)
- **Targeting:** Automatic (Amazon chooses matches)
- **Bid:** Start low ($0.30-$0.75)
- **Budget:** $5-10/day
- **Purpose:** Find converting search terms; mine for manual campaigns
- **Harvest:** Weekly -- move winning search terms to manual exact campaigns

### 2. Branded Keyword Campaign
- **Targeting:** Manual exact match on your brand name + variations
- **Bid:** Low ($0.25-$0.50) -- you should rank organically
- **Budget:** $3-5/day
- **Purpose:** Defend branded search from competitors
- **Note:** If competitors bid on your brand, you must bid too

### 3. Branded Product Targeting
- **Targeting:** Your own ASINs
- **Bid:** Low ($0.20-$0.40)
- **Budget:** $3-5/day
- **Purpose:** Cross-sell your catalog; own your product detail pages

### 4. Manual Keyword Campaigns
- **Broad match:** Cast wide net; use + modifier to force word inclusion
- **Phrase match:** Moderate targeting; keyword order preserved
- **Exact match:** Tightest targeting; highest conversion; highest CPC
- **Bid progression:** Broad < Phrase < Exact
- **Budget:** Split based on keyword priority tiers

### 5. Competitor Targeting
- **Targeting:** Competitor ASINs and competitor brand keywords
- **Bid:** Moderate ($0.50-$1.50)
- **Budget:** $5-15/day
- **Purpose:** Show on competitor product pages and search results
- **Note:** Conversion typically lower than keyword campaigns

---

## Bid Optimization Decision Matrix

| Metric Combination | Action | Reasoning |
|---|---|---|
| High impressions + high clicks + low conversion | Lower bid or check listing | Traffic quality is fine; listing not converting |
| High impressions + low clicks + any conversion | Improve main image / title | Not compelling enough to click |
| Low impressions + any clicks + high conversion | RAISE bid | Great keyword; need more visibility |
| High ACOS + high volume + decent conversion | Lower bid incrementally | Finding efficient price point |
| Zero impressions | Raise bid or check indexing | Bid too low or not indexed for keyword |
| Impression rank improving + organic rank improving | Maintain or slightly reduce | PPC is working; organic catching up |

---

## Placement Report Analysis Framework

### How to Pull
Advertising Reports -> Sponsored Products -> Placement Report

### Three Placement Types
1. **Top of Search (TOS):** Highest visibility; usually highest conversion
2. **Rest of Search (ROS):** Mid-page results; moderate performance
3. **Product Detail Pages (PDP):** On competitor/related product pages; often lowest conversion

### Optimization Strategy (Brandon Young)
- Compare conversion rates across all three placements
- If TOS converts at 17% but PDP at 6%, PDP is HURTING your organic rank
- Use base bid + TOS modifier to concentrate spend on best-converting placement
- Start conservatively: 60% reduction on underperforming placements, then adjust

---

## DSP Audience Types and Funnel Mapping

### Audience Types
| Audience | Description | Funnel Position |
|---|---|---|
| In-Market | Actively shopping in category | Top/Middle |
| Lifestyle | Behavioral profiles from purchase history | Top |
| Cross-Layered | Combine audiences (e.g., parents + keto) | Middle |
| Competitor ASIN Viewers | People who viewed competitor products | Middle |
| Competitor ASIN Purchasers | People who bought competitor products | Middle |
| Your Product Viewers (non-purchasers) | Retargeting pool | Bottom |
| Your Past Purchasers | Retention marketing pool | Bottom |

### DSP Placement Options
- **On Amazon** -- more expensive CPM (users in buying mode)
- **Off Amazon (third-party sites)** -- lower CPM
- **Amazon Owned & Operated** -- Twitch, IMDB/FreeView
- **Streaming TV (OTT)** -- targeted video ads
- **Virtual product placements** -- digitally inserted into FreeView shows

### Budget Allocation Template
| Funnel Stage | Budget % | Goal |
|---|---|---|
| Bottom (Retargeting + Retention) | 60% | Highest ROAS; close known shoppers |
| Middle (Consideration + Competitors) | 20% | Convert interested shoppers |
| Top (Awareness + Audiences) | 20% | New customer acquisition |

### Cost and Access
- Brands generally don't get self-service DSP access
- Run through Amazon directly or through agencies
- **Cheaper to run through an agency** than Amazon direct
- DSP data provides rich customer insights useful for Facebook targeting too

---

## Credit Card Stacking Strategy for Ad Spend (Josh Haley -- BDSS 2025)

### PPC Billing Threshold Hack
1. Default Amazon billing threshold: $500 in ad spend
2. **Contact Amazon Advertising support** to increase threshold to $10,000
3. Pay ads with credit cards, NOT from Amazon payouts (preserves cash flow + earns rewards)

### Recommended Credit Cards for Ad Spend
| Card | Reward | Best For |
|---|---|---|
| AMEX Gold | 4x points on first $150K/year | Primary ad spend card |
| AMEX Plum | 60 days after statement close to pay | Extended float |
| Chase Business Preferred | 3x on first $150K | Secondary card |
| Chase Business Premier | 2.5% back on charges >$5K | High-volume months |
| Capital One Spark Cash | Flat cashback | Simple alternative |

### Stacking Strategy
1. Open multiple cards on staggered dates (7 days apart)
2. Only charge during first 5 days of each statement period
3. Result: 55-60 day payback on Gold; up to 90 days on Plum
4. Effectively float $10K+ in ad spend interest-free for 2-3 months

### Supplier Payment Extension (Melio)
- Pay supplier invoices via credit card through Melio
- 2.9% processing fee, offset by 2.5% card rewards = 0.4% net cost
- Combined with negotiated net-60 supplier terms: effective net-150 day payment terms
- Dramatically improves Cash Conversion Cycle

---

## Advanced Reporting Tools

### SUPA v3.0 (Search Query Performance Analyzer)
- Custom analysis tool from Incrementum Digital
- Uses Search Query Performance data from Brand Analytics
- Deep keyword-level analysis

### Product Tracking Dashboard (PTD)
- Step-by-step creation guide in Incrementum course
- Tracks BSR and keyword ranking over time
- Visualizes PPC impact on organic performance

### Root Cause Analysis Framework
- For diagnosing: falling sales + rising ACOS/TACOS
- Systematic approach: is it market-wide, keyword-specific, or listing-specific?
- Check: competition changes, seasonal shifts, listing suppression, review velocity

---

## Bulksheet Operations (Incrementum Digital)

### What Bulksheets Enable
- Create/update hundreds of campaigns simultaneously
- Standardize naming and structure
- Faster than manual campaign creation
- Essential once managing 50+ campaigns

### Operations
1. **Reading and interpreting** bulksheet data
2. **Creating Auto Targeting** campaigns via bulksheet
3. **Creating Manual Keyword Targeting** campaigns via bulksheet
4. **Creating Manual Product Targeting** campaigns via bulksheet
5. **Updating existing campaigns** via bulksheet
6. **Performing bid optimization** via bulksheet

### Best Practice
Download current campaigns as bulksheet first. Make changes in spreadsheet. Upload modified bulksheet. Always verify changes took effect.

---

## Incrementum Course Architecture (13 Modules) -- Reference

| Module | Topic |
|---|---|
| 1 | Introduction to Amazon Advertising |
| 2 | Introduction to Sponsored Products |
| 3 | Keyword & Competitor Research |
| 4 | Setting Up SP Foundation Campaigns |
| 5 | Bid Optimization |
| 6 | Sponsored Products Reports |
| 7 | Bulksheets |
| 8 | Products with Advertising History |
| 9 | PPC Ranking Strategy for New Products |
| 10 | Sponsored Brands |
| 11 | Sponsored Display |
| 12 | Advanced Bonus Reports |
| 13 | Introduction to DSP |

### Restructuring Existing Campaigns (Module 8)
For products with advertising history:
1. Map campaigns and search terms to ASINs
2. Clean up and restructure old campaigns
3. Analyze search terms (winners, losers, opportunities)
4. Launch new campaigns from proven search terms
5. Identify untargeted keywords (gaps)
6. Identify unique converting search terms
7. Monitor BSR and keyword ranking impact
