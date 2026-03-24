---
name: Google Ads Campaign Strategy
description: >
  MANDATORY TRIGGERS: Google Ads strategy, Search campaign, Shopping campaign,
  Performance Max, PMax, YouTube ads strategy, Display ads, Discovery ads,
  Google bidding, Target CPA, Target ROAS, Quality Score, keyword strategy,
  full-funnel Google, demand capture, demand generation, Google campaign structure,
  broad match, exact match, phrase match, RSA, asset groups, feed-only PMax.
  FOR: All Google campaign architecture decisions including Search, Shopping, PMax,
  YouTube, Display, and Discovery campaign structure, bidding strategy progression,
  full-funnel framework (4 pillars), Quality Score optimization, keyword strategy,
  and demand capture vs demand generation framework.
  Do NOT use for: Meta campaign structure (use strategy-meta-ads), Google account
  or tracking setup (use setup-google-ads), YouTube ad scripting (use create-video-ads),
  Google RSA/PMax asset creation (use create-google-assets), day-to-day optimization
  (use optimize-google), TikTok strategy (use strategy-tiktok-ads).
---

# Google Ads Campaign Strategy

## Quick Navigation
- **Search campaigns** -> ref-google-search-strategy.md
- **Shopping campaigns** -> ref-google-shopping-strategy.md
- **Performance Max** -> ref-google-pmax-strategy.md
- **YouTube ads** -> ref-google-youtube-strategy.md
- **Full-funnel / budget allocation** -> ref-google-full-funnel.md

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| Search campaign setup, keywords, match types, Quality Score | ref-google-search-strategy.md |
| Shopping campaign architecture, high bid / low bid, product optimization | ref-google-shopping-strategy.md |
| PMax setup, feed-only vs full-asset, audience signals, Fire & Ice | ref-google-pmax-strategy.md |
| YouTube campaign types, bidding, creative requirements | ref-google-youtube-strategy.md |
| Budget allocation, 4 pillars, demand capture vs generation, full funnel | ref-google-full-funnel.md |

---

## INSTRUCTOR DISAGREEMENT NOTICES

### Disagreement 1: Consolidation

| Position | Advocate | Core Argument |
|---|---|---|
| **Strong consolidation** | PPC Hub | Case study: 19 -> 4 campaigns = +253% conversions, -60% CPA. Feeds more data to smart bidding. Golden rule: consolidate unless there's a good reason. |
| **Granular separation** | Shri | Uses high bid + low bid testing campaigns, standalone campaigns for winners, collection-based PMax. More control over individual product performance. |
| **Balanced** | Ezra/Brett | Full-funnel framework with distinct campaign types per pillar. Not hyper-consolidated but not fragmented. |

**Resolution:** Consolidate by default. Segment only when there is a clear reason: different bid targets, budget isolation, reporting requirements, or unique business insights Google doesn't have.

### Disagreement 2: Broad Match

| Position | Advocate | Core Argument |
|---|---|---|
| **Broad match = new standard** | PPC Hub | Used in 75%+ of accounts. More signals (landing page, keywords, user history, location). Must pair with smart bidding + challenging targets. |
| **Exact match only** | Shri | Maximum control. Exact match [brackets] for Search. $0.05 CPC bids. Only Search for winning products. |
| **Start phrase+exact, add broad** | Ezra/Brett | Start with phrase + exact, then incorporate broad for expansion. |

**Resolution:** Depends on data volume and budget. High-volume accounts with strong data: broad + smart bidding. Low-budget or new: start phrase + exact. Exact-only works for budget-constrained winners.

### Disagreement 3: PMax Feed-Only vs Full-Asset

| Position | Advocate | Core Argument |
|---|---|---|
| **Test both** | Shri & PPC Hub | Feed-only often outperforms. Test feed-only vs full-asset to compare. |
| **Full-asset with signals** | Ezra/Brett | Lean toward full-asset with proper audience signals. Growth campaigns need assets for YouTube/Display. |

**Resolution:** Efficiency campaigns: test feed-only first (highest ROAS). Growth campaigns: full-asset required to access non-Shopping channels.

---

## THE FOUR PILLARS OF GOOGLE ADS (Ezra/Brett)

You need at least 3 of 4 for stable, predictable growth. Ideally all 4.

1. **Google Search** -- Reaches shoppers at learn/do/buy moments.
2. **Google Shopping / PMax** -- The workhorse. Up to 60%+ of ad spend for e-commerce.
3. **Remarketing** (YouTube, Display, Discovery) -- Re-engage the 95-99% who don't purchase.
4. **Top of Funnel** (YouTube primarily) -- Needed for stable/rapid growth.

---

## DEMAND CAPTURE vs DEMAND GENERATION

| | Demand Capture | Demand Generation |
|---|---|---|
| Audience | Active shoppers already searching | People unaware your product exists |
| Channels | Search + Shopping | YouTube + Display + Discovery |
| Best for | Auto parts, appliances, known categories | Novel products, impulse, fashion |
| Strength | High ROAS, low CAC | Scale & rapid growth |

Almost ALL businesses need BOTH.

---

## 9 PILLARS SUCCESS FORMULA (PPC Hub)

All 9 must be in place. Failing at ANY one causes failure:

1. **Irresistible Offer** -- without it, campaigns are useless.
2. **High-Converting Landing Page** -- without it, traffic leaks.
3. **Solid Unit Economics** -- without them, unscalable.
4. **Realistic Goals & KPIs** -- without them, aimless.
5. **Proper Conversion Tracking** -- without it, blind.
6. **Solid Campaign Structure** -- without it, fragmented data.
7. **Right Targeting** -- without it, inaccurate.
8. **Compelling Creatives** -- without them, unremarkable.
9. **Optimized Bids & Budgets** -- without them, inefficient.

Never think about tactics (6-9) before foundations (1-4).

---

## BIDDING STRATEGY PROGRESSION (All Campaign Types)

### Phase 1: Launch
Enhanced CPC or Max Conversions / Max Conversion Value.
If Max Conversions: set initial budget 33-50% lower (can overspend 2-3x).

### Phase 2: The 30/30 Threshold
After 30 conversions in 30 days: switch to Target CPA or Target ROAS.
YouTube: 15-20 conversions sufficient.

### Phase 3: Optimize Gradually
Set initial target at current performance. Max 20% change per week (10% recommended).

### Target CPA vs Target ROAS
- **Target CPA:** High LTV, repeat purchases, new customer volume, no dollar value on conversions.
- **Target ROAS:** Per-transaction profitability, low LTV, varying AOV.

---

## QUALITY SCORE QUICK REFERENCE

### Three Components (1-10 Scale)
1. **Expected CTR** (most weight) -- are people clicking?
2. **Ad Relevance** -- does ad match query intent?
3. **Landing Page Experience** -- speed, relevance, content alignment.

### Targets
- Goal: 7+ out of 10.
- Below 5: definitely paying too much.
- Higher QS = higher rank AND potentially lower CPC.

### CPC Formula
Actual CPC = (Ad Rank of person below you / Your Quality Score) + $0.01.

### Fix Sequence (PPC Hub -- 3-Phase Sequential)
1. **Ad Relevance** first (structural fix, 7-14 days).
2. **Expected CTR** second (competitiveness fix, 7-21 days).
3. **Landing Page** third (post-click fix, 14-30 days).

Priority Score = (10 - QS) x Impressions. Work on highest-priority first.

---

## CROSS-REFERENCES

| Condition | Go To |
|---|---|
| Merchant Center or conversion tracking issues | setup-google-ads |
| Scaling Shopping or PMax | scale-campaigns |
| RSA headlines, PMax assets, YouTube scripts | create-google-assets |
| Day-to-day optimization | optimize-google |
| Meta campaign structure | strategy-meta-ads |
| Cross-channel allocation | strategy-cross-channel |

---

## ANTI-PATTERNS

1. **Skipping conversion tracking** -- nothing works without it.
2. **Using GA4 conversions instead of native Google Ads code** -- smart bidding fails.
3. **Target CPA/ROAS too far from current performance** -- campaign dies.
4. **Bid changes >20% per week** -- resets learning.
5. **Running only 1 of 4 pillars** -- unstable growth.
6. **Judging YouTube by direct ROAS alone** -- misses halo effect.
7. **Skipping remarketing** -- 95-99% don't buy first visit.
8. **Not giving PMax 2-6 weeks** -- premature optimization kills it.
9. **Changing item IDs** -- loses all conversion history.
10. **15 RSA headlines** -- data poverty. Use 6-8.
11. **Hot CTAs on cold channels** -- match offer to channel temperature.
12. **Fighting the algorithm** -- device segmentation, match-type ad groups are outdated.
