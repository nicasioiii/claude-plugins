---
name: Google PMax Campaign Strategy
description: PMax fundamentals, efficiency vs growth campaigns, campaign structure decision tree, audience signals, customer bidding options, optimization levers, feed-only vs full-asset, brand exclusion, Fire & Ice for lead gen, and performance-based segmentation.
---

# Google Performance Max (PMax) Strategy

## PMAX FUNDAMENTALS

### What PMax Is
Automated campaign type running across ALL Google properties: Search, Shopping, YouTube, Display, Discovery, Gmail, Maps. Only automated bidding available (no manual).

### Learning Period
- 2-6 weeks after launch. DO NOT make changes during this time.
- Smaller budgets = longer learning period.
- May not see impressions for first few days (normal).

### Minimum Budget
- **$100/day per PMax campaign** for it to be successful (Ezra/Brett).
- $50+/day recommended minimum (Shri).
- Campaigns need plenty of conversion data for smart bidding to work.
- Cannot optimize until 30 conversions in 30 days threshold is met.

---

## TWO PMAX STRATEGY TYPES (Ezra/Brett)

### 1. Efficiency-Focused Campaigns (Primary)
- Lean into Google Shopping.
- Bidding: Max Conversion Value -> Target ROAS.
- Expect 75-100% of spend/conversions from Shopping ads.
- Highest ROAS.

### 2. Growth-Focused Campaigns
- Focus on new customer acquisition.
- Bidding: Max Conversions -> Target CPA.
- Target CPA pushes into YouTube, Display, Discovery (beyond Shopping).
- Include only top/introductory products.
- Assets become more important (video, images, copy used more).
- Use "New Customer Only" mode for customer bidding.

---

## CAMPAIGN STRUCTURE DECISION TREE (Ezra/Brett)

### Low Budget (<$100/day per campaign)
| Scenario | Structure |
|---|---|
| One category or low SKU count | 1 campaign, 1 asset group |
| Multiple categories or hero product | 1 campaign, multiple asset groups |
| Varying ROAS goals | Exception: multiple campaigns even with low budget |

### High Budget ($100+/day per campaign)
| Scenario | Structure |
|---|---|
| Low SKU count | Multiple campaigns (1 per product), 1 asset group each |
| Large catalog | Multiple campaigns (1 per category), multiple asset groups |
| Single category, same purpose | 1 campaign even with high budget |

### Case Study
Supplement client at $150/day: Separating into 2 campaigns dropped to 300-350% ROAS; consolidating back to 1 campaign with 2 asset groups improved to 450-500% ROAS.

---

## PMAX LAUNCH STRATEGIES (Shri)

### Strategy 1: Phase-Based (With Existing Data)
- Testing Phase PMax -> Profitability Phase PMax -> Scaling Phase PMax.
- Can combine Profitability + Scaling into one (total: 2-3 campaigns).

### Strategy 2: Collection-Based (New Accounts)
- One PMax per product collection. E.g., "Dog Hair Removers" PMax, "Kitchen Gadgets" PMax.

### Strategy 3: Assets vs No Assets
- Campaign A: Shopping + Assets (images, headlines, descriptions).
- Campaign B: Shopping ONLY (no assets).
- Test which performs better. Shopping-only often wins.

### Launch Settings (Shri)
| Setting | Value |
|---|---|
| Conversion Goal | Purchase only (one primary action) |
| Bidding | Conversion Value (not Conversions) |
| Target ROAS | UNCHECKED initially (even with data) |
| Final URL Expansion | OFF |
| Budget | $50+/day |

---

## FEED-ONLY vs FULL-ASSET

### Feed-Only PMax
- Leave ALL asset fields empty (no images, logos, descriptions, headlines).
- Creates Shopping-only behavior.
- Shopping-only placement works best majority of the time for efficiency.

### Full-Asset PMax
- Required for growth campaigns that need YouTube/Display/Discovery reach.
- Asset recommendations: 3-5 images, 1-2 logos, 0-2 videos, 3-5 headlines, 3 long headlines, 2 descriptions, 2-3 sitelinks.

### The Verdict
Test both. Feed-only for efficiency; full-asset for growth. Many accounts find feed-only delivers higher ROAS.

---

## AUDIENCE SIGNALS

### Best Practices (Ezra/Brett)
- **ALWAYS use past purchasers audiences** -- has huge impact.
- Adding bottom-of-funnel audiences helps smart bidding create better converter avatars.
- Use combination of: customer email lists + all converters/purchasers from GA4 and Google Ads.

### Audience signals are SIGNALS, not targeting
- They guide the algorithm but don't restrict it.
- The algorithm can (and will) reach beyond your signals when it finds opportunities.

---

## CUSTOMER BIDDING OPTIONS (Ezra/Brett)

1. **Default:** Bid equally for new and returning customers.
2. **New Customer Only Mode** (growth campaigns): Only bids on new customers.
   - Define past buyers with up to 10 audiences (email list + converters lists).
   - If goal can't be met with new customers only, WILL bid on returning.
   - Takes longer to learn (up to 6 weeks).
3. **New Customer Value Mode** (NOT recommended): Bids higher on new, still bids on returning.
   - Artificially inflates conversion value.

---

## BRAND EXCLUSION (PPC Hub -- Critical)

- **Exclude brand traffic from PMax campaigns.**
- Create separate branded fallback campaigns.
- Brand traffic inflates PMax ROAS, hiding real non-brand performance.
- Use scripts to auto-exclude non-branded terms from branded shopping campaigns.

---

## PMAX OPTIMIZATION LEVERS (PPC Hub)

Despite the black box nature, you have 10 levers:

1. **Negative keyword optimization** (now available in PMax).
2. **Offer optimization** (the offer behind your ads).
3. **Bid/budget adjustments** (follow 20% rule, 10% increments).
4. **Final URL Expansion** (on/off + page feeds).
5. **Asset optimization** (using performance quadrants -- see below).
6. **Product feed optimization** (titles, images, descriptions).
7. **Audience signal / search theme optimization.**
8. **Value Rules optimization.**
9. **New Customer Acquisition Goals.**
10. **Unlock hidden insights via scripts** (channel reporting).

### Asset Performance Quadrants (PPC Hub)
| | High Impression Share | Low Impression Share |
|---|---|---|
| **High Conversions/Impression** | Winners (scale) | Hidden Gems (increase exposure) |
| **Low Conversions/Impression** | Silent Killers (remove FIRST!) | Underperformers (replace) |

Silent Killers are the priority -- actively hurting performance because Google shows them frequently.

### Asset Group Reporting Script (Mike Rhodes)
- No native asset group reporting in Google Ads.
- Script creates Google Sheet with: channels per asset group, impressions per asset group, detailed performance data.
- Must-have for all PMax campaigns.

---

## FIRE & ICE STRUCTURE (PPC Hub -- Lead Gen)

Standard PMax for lead gen has 3 problems: pushes same assets to all networks, optimizes for same conversion across all networks, can't control bids per network.

### Solution: Two-Campaign Structure
- **FIRE Campaign** (Hot/Bottom of Funnel): Search-heavy, direct CTAs (book demo, get quote), optimize for macro conversions.
- **ICE Campaign** (Cold/Top of Funnel): Prospecting via Display/YouTube/Discovery, soft CTAs (white paper, checklist), optimize for micro conversions.

**Key Principle:** Match offer to channel temperature. Hot CTAs on cold channels will fail.

---

## PERFORMANCE-BASED SEGMENTATION (PPC Hub)

### Labelizer Tools
Automatically label products based on performance:
- **Heroes:** Top performers -> bid aggressively.
- **Sidekicks:** Decent performers -> maintain.
- **Villains:** Poor performers -> reduce bids or exclude.
- **Zombies:** Zero/minimal data -> test carefully.

Tools: Producthero Labelizer, ProfitMetrics Shopping Booster, Channable, Flowboost.

---

## PMAX SCALING (Shri)

### Prerequisites
- Running minimum 14-30 days.
- No changes in past 2-3 days.

### Scaling Decision Framework
1. Check ROAS for last 14 days -> must be above break-even.
2. Check ROAS for last 30 days -> compare to 14-day (should be improving).
3. Check ROAS for last 7 days (grain of salt) -> confirms trend.
4. Check if budget is being spent fully.

### Scaling Methods
- **Budget increase** (when fully spent + profitable): 10-30%, wait 7-14 days.
- **Lower Target ROAS** (when budget NOT fully spent): small increments, wait 7 days.
- **Add more PMax campaigns** (per collection, per country, assets vs no-assets).

### Key Rule
After scaling, wait 7 days minimum before any other changes. ROAS will naturally decrease slightly when scaling (expected).
