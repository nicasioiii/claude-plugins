---
name: Amazon PPC Advertising
description: >
  MANDATORY TRIGGERS: amazon ppc, amazon ads, sponsored products, sponsored
  brands, sponsored display, DSP, demand side platform, ACOS, TACOS, bid
  optimization, placement strategy, top of search, search query performance,
  SQPR, keyword harvesting, campaign structure, amazon advertising, broad match
  modifier, negative keywords, PPC campaign, /setup-amazon-ppc, ppc placement,
  ranking formula ppc, GMV max amazon.
  FOR: Amazon-specific advertising -- Sponsored Products/Brands/Display campaign
  structure, PPC placement strategy, bid optimization framework, Search Query
  Performance Report analysis, DSP funnel with 60/20/20 budget split, broad match
  modifiers, keyword harvesting, ChatGPT PPC tools, ranking formula mechanics,
  and traffic-stealing tactics.
  Synthesized from Kevin King summits (Brandon Young -- ranking formula and
  placement strategy; Brian Johnson -- SQPR analysis; Ritu Java -- ChatGPT PPC
  tools; Kevin King -- broad match modifiers, steal traffic; Vanessa Hung/Tim
  Jordan -- DSP audience building) and Incrementum Digital Amazon Advertising
  Academy (campaign types, bid optimization, ACOS/TACOS) and Liran Hirschkorn
  (DSP funnel 60/20/20 budget split).
  Do NOT use for: Facebook/Google/TikTok ad platforms (-> paid-ads-mastery),
  listing copy optimization (-> amazon-listing-optimization), TikTok Shop GMV Max
  ads (-> tiktok-shop-setup).
---

# Amazon PPC Advertising

## Quick Navigation
- **Campaign types, bid optimization, ACOS/TACOS, DSP details** -> references/amazon-ppc-advertising-ref.md
- **Ranking formula, placement strategy, SQPR, ChatGPT tools** -> See frameworks below

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| What campaign types should I run? Auto vs manual? | amazon-ppc-advertising-ref.md |
| How do I optimize bids? What is ACOS/TACOS? | amazon-ppc-advertising-ref.md |
| Should I use DSP? What budget split? When does DSP make sense? | amazon-ppc-advertising-ref.md |
| How do I set up Sponsored Brands or Sponsored Display? | amazon-ppc-advertising-ref.md |
| ChatGPT tools for PPC? Google Sheets automation? | amazon-ppc-advertising-ref.md |
| How do I steal traffic from new launches? Broad match modifiers? | amazon-ppc-advertising-ref.md |

---

## Cross-References

| Situation | Route To |
|---|---|
| PPC running, need ACOS/TACOS break-even validation | pricing-unit-economics |
| Listing needs optimization before PPC will convert | amazon-listing-optimization |
| Want to drive external traffic to Amazon listing | external-traffic-list-building |
| Want to run Facebook/Google/TikTok ads (not Amazon PPC) | paid-ads-mastery (external plugin) |
| Listing live with 10+ reviews, ready for PPC | This skill (start here) |

**Prerequisite:** Listing must be live with 10+ reviews before scaling PPC budget (Vong). Otherwise you are "throwing money into a fire pit."

---

## Ranking Formula: Performance x Relevancy (Brandon Young)

This is the foundation of all Amazon PPC strategy.

**Ranking Score = Performance x Relevancy**

- **Performance** = CTR x CVR x revenue generated on that keyword
- **Relevancy** = 0 to 1 score based on keyword match type + keyword location in listing

**Example:** If relevancy = 0.25, a performance score of 1,000 becomes 250 -- drops you from page 1 to page 2-3.

**Three-step SOP:**
1. Fix conversion rate (listing optimization -- see amazon-listing-optimization)
2. Fix indexing (backend keywords, flat file completeness)
3. Make spend decisions based on TRIANGULATED data (organic rank + impression rank + conversion rate)

[CONTRARIAN -- Young] Optimizing purely for ACOS/TACOS sacrifices long-term keyword ranks. Track organic rank alongside ad metrics.

---

## PPC Placement Strategy (Brandon Young)

**Step 1:** Pull placement report from Amazon (top of search vs rest of search vs product detail pages).

**Example analysis:**
| Placement | CPC | CVR | Verdict |
|---|---|---|---|
| Top of Search | $1.72 | 17% | High cost but strong conversion |
| Rest of Search | $0.72 | 6% | Low cost but poor conversion |
| Product Detail Pages | $0.72 | 6% | Low cost but poor conversion |

**Key insight:** Low-converting placements HURT organic ranking because conversion rate is a key ranking factor.

**Strategy:** Set base bid to $0.60, then:
- Top of Search modifier: +300%
- Rest of Search modifier: 0%
- Product Detail Pages modifier: 0%

**Result:** Effective bids = $1.80 TOS, $0.60 ROS, $0.60 PDP

**Warning:** Over-reducing bids causes impression drops. Start at 60% reduction from current and test incrementally.

---

## Search Query Performance Report (Brian Johnson)

**Access:** Brand Analytics > Search Query Performance > ASIN report

**Three key metrics:**
1. ASIN impression share %
2. Relative click rate (ASIN clicks / total clicks)
3. Relative conversion rate

**Formula:** (ASIN purchase count / ASIN click count) minus (total purchase count / total click count)

- **Positive result** = you have competitive advantage on that keyword -- lean into it with ad spend
- **Negative result** = fix product/listing or stop investing in that keyword

**Tool:** DeepM.ai tracks 30+ search rank factors for competitive positioning.

---

## Broad Match Modifiers (Kevin King)

Add `+` sign before each word in broad campaigns to force those words in customer query.

**Example:** `+basketball +shoes` prevents Amazon showing ads for "sneakers" or "running shoes."

**Why:** Prevents burning cash on irrelevant synonym matches that broad match normally allows.

---

## Steal Traffic from New Launches (Kevin King)

1. Use X-Ray creation date field to find products launched in last 10-90 days
2. These products have heavy PPC spend but low/no reviews
3. Target them with product-targeting campaigns
4. If you have better reviews or lower price, you get high conversion rate on their traffic

---

## DSP Overview: 60/20/20 Budget Framework (Liran Hirschkorn)

**Budget allocation:**
- **60% Bottom of Funnel** (retargeting + retention): Best ROAS. Target viewers who did not purchase, add-to-cart abandonments, past purchasers of consumables (60-180 day lapsed).
- **20% Middle of Funnel** (consideration): Target competitor ASIN viewers/purchasers; cross-sell own product catalog.
- **20% Top of Funnel** (brand awareness): Amazon lifestyle/in-market audiences; OTT streaming TV ads.

**When DSP makes sense:** Already spending $25K-$50K+/month on Amazon search ads, selling consumable products, or selling higher-price products >$100-$200 (longer research period = retargeting opportunity).

**When DSP does NOT make sense:** Small ad budget, low-price impulse purchases (<$10-$15), new sellers not yet maximizing Sponsored Products.

[CONTRARIAN -- Hirschkorn] DSP view-through attribution can be inflated. Retargeting may show 10x ROAS but true ROAS is 4-5x due to people who would have purchased anyway. Some cannibalization is inherent.

---

## /setup-amazon-ppc Command Output

When user runs `/setup-amazon-ppc`, deliver:
1. **Campaign structure recommendation** -- which campaign types to launch and in what order
2. **Placement strategy** with bid modifiers for TOS, ROS, PDP
3. **Keyword harvesting plan** (auto discovery > manual exact/broad/phrase)
4. **Bid optimization framework** with ACOS/TACOS targets based on their margins
5. **SQPR analysis guide** -- how to pull and interpret the report
6. **DSP readiness assessment** -- whether DSP makes sense for their situation
7. **Negative keyword strategy** including broad match modifier setup
