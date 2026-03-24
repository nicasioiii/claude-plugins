---
name: Meta Scaling Methods
description: Bell Theory, Daily Loop Theory (detection + 5 ways to break), hot pockets as scaling mechanism, Crazy Method as amplifier, 20% rule at high budgets, vertical/horizontal/nuke/manual bid/sniper/surge/CBO/Advantage Shopping scaling, multi-country expansion.
---

# Meta Scaling Methods

## BELL THEORY (Konstantinos)

### How Every Ad Works
Every ad follows a bell curve: performance rises, hits a soft spot (peak), then declines as budget increases.

### The Soft Spot
The maximum ROAS for that ad at a given budget level. Pushing budget past the soft spot = declining ROAS. Each bell has a ceiling.

### The Scaling Hack
Duplicate the campaign at a higher starting budget. The new bell curve has a HIGHER soft spot.
- Example: Campaign peaked at $40/day. Duplicate at $40 -> new soft spot may be at $80/day.
- Multiple campaigns at their respective soft spots = higher total spend with maintained ROAS.
- You cannot infinitely scale one campaign -- use multiple campaigns at their peaks.

---

## DAILY LOOP THEORY (Konstantinos)

### Core Insight
If the algorithm doesn't want you to scale, adding more campaigns/budget redistributes the SAME number of sales across more campaigns. You spend more for identical total results.

### Discovery
Netherlands account: 1 campaign = 8 sales. 2 campaigns = 4+4 (same total, double the spend). With many campaigns, cannibalization is harder to spot.

### Detection Method
Compare TOTAL account-level sales/revenue across periods with different campaign counts. If total stays flat while campaigns multiply, you are in a daily loop.

### 5 Ways to Break the Daily Loop
1. **New creatives with different ANGLES** -- creates different hot pockets that reach untapped audiences.
2. **Different products or offers** -- gives the algorithm new conversion data to work with.
3. **Testing new countries** -- entirely new audience pools.
4. **Promotions to inflate account data** -- temporary data boost that carries over to post-promo performance.
5. **Improving AOV, conversion rate, or offer strength** -- makes each conversion more valuable, breaking the value ceiling.

Simply duplicating the same creatives in more campaigns = spending more for the same results. The loop can only be broken with genuinely new inputs.

---

## HOT POCKETS AS SCALING MECHANISM

### Why Hot Pockets Matter for Scaling
Each ad creates a hot pocket (cluster of similar people). One campaign = one hot pocket = limited scaling ceiling. Multiple campaigns with different creative angles = multiple hot pockets = higher ceiling.

### Proof
$1.7M spent on single broad ad set over 6 months only reached ~20M unique people out of 150M potential with 8.5 frequency. Even massive spend targets a LIMITED pocket.

### How to Create New Hot Pockets
Different creative angles for the same product target different hot pockets:
- Lifestyle angle -> young adults.
- Specs/performance angle -> enthusiasts.
- Aesthetics angle -> style-conscious buyers.
- Practicality angle -> utilitarian buyers.
- Each sustains its own campaign and budget allocation.

### Crazy Method as Hot Pocket Amplifier
The Crazy Method (identical ad sets in CBO) finds different hot pockets from the same targeting through random initial result variance. Only use with something already working. Do NOT run 6+ Crazy Method campaigns with identical creatives (collapses the system).

---

## VERTICAL SCALING (Deividas)

### Safe: 20% Budget Increase Every 48 Hours
- Conservative, minimal risk of learning phase disruption.
- Best for: budgets above $200/day on proven campaigns.
- Cap: ~$1K-$3K/day per ad set before diminishing returns.

### Aggressive: Up to 70% Every 24 Hours
- Faster, more risk.
- Learning phase may not reset even at 70% (updated from old 20% rule).
- Best for: strong performers where speed matters more than stability.

### The 20% Rule Context
- Konstantinos: Only matters at $500+/day. At small budgets ($10-$50), 20% is meaningless.
- Deividas: Up to 70% won't reset learning. Assets outside learning phase perform better long-term.
- Both agree: The old strict 20% rule is outdated.

---

## HORIZONTAL / NUKE SCALING (Deividas)

### Method
Duplicate winning creative into 25-100 ad sets at $25-50 each. Kill non-performers fast (after 1x CPA spend with no sale).

### Characteristics
- Faster scaling than vertical.
- Less stable (many ad sets will die quickly).
- Hits different audience pockets within the same broad targeting.
- Requires active monitoring and fast kill decisions.

---

## MANUAL BID SCALING (Deividas)

### Standard Approach
Test cost caps, bid caps, ROAS value optimization. Start at average CPA, increase by 20% per ad set. Create multiple ad sets at different bid levels.

### Sniper Variant
Very low manual bid = only spend ~40-50% of budget. Captures cheapest audience pockets. Highly efficient but limited volume.

### Surge Variant
One ad set, very high budget. Opposite of nuke -- shotgun approach. Let the algorithm spend freely on a single high-budget ad set.

---

## CBO CONSOLIDATION SCALING (Deividas)

Push all winners into CBO campaigns for automated scaling. The algorithm allocates budget to the best performers.

### The Consolidation End Goal
Few campaigns, most spend on top 10% of ads. Test in ABO -> push winners to CBO/Advantage Shopping -> maintain by continuously testing + refreshing creatives.

### Downscaling Protocol
When killing an ad set in CBO: reduce CBO budget by the amount that ad set was spending. When performance drops: test LESS, not more. Focus on consolidating what works.

---

## ADVANTAGE SHOPPING SCALING (Deividas)

Evergreen scaling campaign. Continuously add winning creatives. Uploading new creatives does NOT reset learning phase (unlike CBO/ABO). Best for big markets; can have frequency issues in small markets.

---

## MULTI-COUNTRY EXPANSION (Konstantinos)

### Rules
- Test one country at a time to isolate results.
- Smaller countries may require different approaches (broader works faster).
- Canada is often tested as expansion from US campaigns.
- Each country may need its own creative testing and optimization cycle.
- In smaller countries, ASC may work even with new pixels due to limited audience pool.

---

## ATTACK PERIODS / PROMOTIONS (Konstantinos)

### The Strategy
Run promotions during bad periods to inflate data within the platform. The inflated results from promo period CARRY OVER to improve post-promo performance.

### Black Friday Playbook
1. Build evergreen campaigns BEFORE Black Friday (weeks/months in advance).
2. Run promo campaigns ALONGSIDE evergreen during Black Friday.
3. Evergreen campaigns get inflated by Black Friday data spillover.
4. After closing promo campaigns, evergreen campaigns perform better.

**Critical mistake:** Running ONLY promo campaigns during Black Friday, then having nothing after.

---

## WHEN TO SCALE (Decision Criteria)

### Meta (Deividas)
- Above-average ROAS for 3-5 consecutive days (NOT just one good day).
- Never judge by single day.
- Only scale based on ROAS/CPA -- never based on CTR improvements alone.

### Prerequisites
- Creative pipeline ready (need fuel for multiple hot pockets).
- Unit economics validated (scaling losses = bigger losses).
- Tracking correlation established (know what Ads Manager numbers mean in real terms).

---

## WHEN YOU CANNOT SCALE

If lowering budget = good ROAS and increasing budget = bad ROAS:

| Root Cause | Solution |
|---|---|
| Weak offer | Create irresistible offer (see ref-scaling-prerequisites.md) |
| Bad/limited creatives | New angles and iterations (see test-creative) |
| Low AOV | Upsells, cross-sells, bundles |
| Poor conversion rate | Fix website/landing page (CRO) |
| Too much competition | Differentiate offer or find less competitive markets |
| Product-market limitations | Accept ceiling or expand product line |

"Facebook is just an amplifier of reality." If the product can't scale in reality, Facebook can't force it.
