---
name: Meta/Facebook Ads Campaign Strategy
description: >
  MANDATORY TRIGGERS: Meta ads, Facebook ads, Instagram ads, CBO, ABO, ASC,
  Advantage Shopping, Crazy Method, Blender Method, Stacked Lookalike, hot pockets,
  pixel training, Meta campaign structure, Meta budget, Meta targeting, retargeting,
  cost cap, bid cap, Meta scaling, campaign architecture, ad set structure.
  FOR: Planning Meta/Facebook/Instagram campaign structure, choosing campaign types
  (CBO vs ABO vs ASC), selecting methods (Crazy/Blender/Stacked LLA), budget sizing,
  targeting progression, retargeting design, and cost cap / bid cap implementation.
  Do NOT use for: Google Ads campaigns (use strategy-google-ads), Meta Pixel or CAPI
  setup (use setup-meta-tracking), ad copy or video creation (use create-ad-copy or
  create-video-ads), TikTok strategy (use strategy-tiktok-ads), day-to-day
  optimization or diagnostics (use optimize-meta).
---

# Meta/Facebook Ads Campaign Strategy

## Quick Navigation
- **Campaign type selection** -> Campaign Type Decision Tree below
- **Methods (Crazy/Blender/LLA)** -> ref-meta-campaign-methods.md
- **Budget & targeting rules** -> ref-meta-budget-targeting.md
- **Scaling logic** -> ref-meta-scaling-logic.md
- **Cost caps & bid caps** -> ref-meta-cost-caps.md
- **Retargeting design** -> ref-meta-retargeting.md

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| Which method should I use? CBO vs ABO vs ASC? | ref-meta-campaign-methods.md |
| How much budget? How many ad sets? What targeting? | ref-meta-budget-targeting.md |
| How do I scale? Bell Theory? Daily Loop? Hot pockets? | ref-meta-scaling-logic.md |
| Cost cap or bid cap? How to set them? | ref-meta-cost-caps.md |
| Retargeting setup? Should I exclude past buyers? | ref-meta-retargeting.md |

---

## INSTRUCTOR DISAGREEMENT NOTICES

This skill synthesizes three strategic philosophies that sometimes conflict. When advising users, present both positions and the resolution.

### Disagreement 1: Consolidation vs Multi-Campaign

| Position | Advocate | Core Argument |
|---|---|---|
| **Anti-consolidation** | Konstantinos | One campaign = one hot pocket = capped scaling. Proof: $1.7M spend on single broad ad set only reached 20M of 150M potential. Multiple campaigns with different angles = multiple hot pockets. |
| **Pro-consolidation** | Deividas | Fewer campaigns, algorithm-driven. Ultimate goal = few campaigns with most spend on top 10% of ads. Advantage Shopping lets you upload new creatives without resetting learning phase. |
| **Pro-broad** | Seth/ACA | Target as broadly as possible. Narrow targeting drives UP costs. Creative becomes the targeting. |

**Resolution:** Use multi-campaign approaches when actively scaling or exploring new audiences/angles. Consolidate proven winners into fewer campaigns for maintenance efficiency. New accounts should start with structured testing (Konstantinos approach), then consolidate winners (Deividas approach) as the account matures.

### Disagreement 2: Testing on Broad vs Interests

| Position | Advocate | Core Argument |
|---|---|---|
| **Avoid broad for testing** | Deividas | Too much randomness with new creatives. Test on interests sized 15-25M first. Broad only works with enough data or a home-run product. |
| **Train pixels from interests to broad** | Konstantinos | Follow the lowest-CPM path: small interests -> normal interests -> LLAs -> stacked LLAs -> broad. CPM is the compass. |
| **Target as broadly as possible** | Seth/ACA | Algorithm finds the right people. Narrow targeting drives up costs and excludes potential buyers. |

**Resolution:** Broad works with seasoned pixels and strong creative. Interests are better for new pixel/product testing. Follow Konstantinos's training path for new accounts; graduate to broad (Deividas/ACA approach) once pixel has 100+ purchase events.

### Disagreement 3: The 20% Scaling Rule

| Position | Advocate | Core Argument |
|---|---|---|
| **Irrelevant at small budgets** | Konstantinos | $10 -> $12 is meaningless. Only matters at $500+/day. Learning phase is largely gamification. |
| **Up to 70% OK** | Deividas | Budget increase up to 70% won't reset learning phase. Assets that exit learning phase perform better long-term. |

**Resolution:** Both agree the old strict 20% rule is outdated. At small budgets (<$200/day), increase freely. At $500+/day, use 20% increments for safety. Alternatively, duplicate at higher budget to start a new bell curve.

---

## CAMPAIGN TYPE DECISION TREE

**Step 1: Assess pixel maturity and country size.**

### New Pixel + Small Country (Switzerland, Greece, NL, etc.)
-> Start with ASC (broad). May work immediately due to limited audience pool.
-> Fallback: CBO with 3-5 interests if ASC fails.

### New Pixel + Large Country (US, UK, DE, FR)
-> CBO with small interests (2-3M) to start training.
-> Progress: interests -> LLAs (at ~100 purchases) -> stacked LLAs -> broad.
-> Use relaunches (duplicate + restart) when campaigns die after 24-48hr boost.

### Seasoned Pixel (consistent sales, stable CPMs)
-> ASC broad + CBO Crazy Method broad + CBO Crazy Method with stacked LLAs.
-> Multiple campaigns with different angles for multiple hot pockets.

### Struggling / Problematic Pixel
-> Blender Method (LLAs + interests combined) run as Crazy Method.
-> Last resort approach when interests alone AND LLAs alone underperform.

### Lead Generation (Local Business)
-> CBO Crazy Method with broad + demographic filters.
-> Screening questions in lead forms to filter quality.

---

## CORE STRATEGIC PRINCIPLES

### The Optimization Chain
Everything in Meta ads serves one purpose: feeding consistent sales data back to the algorithm so it finds more buyers. More data = better optimization = cheaper results over time.

### Know Your Numbers First
- **Break-even ROAS** = 1 / Profit Margin (decimal). Example: 62.5% margin -> 1.6 ROAS break-even.
- **Budget sizing rule:** Daily budget / Average CPP = number of ad sets. Example: $100 / $30 CPP = 3-4 ad sets.
- If margin is 10%, you need 10x ROAS -- nearly impossible for low-AOV products.

### Key Diagnostic Metrics (Priority Order)
1. Cost per unique click (creative quality)
2. Conversion rate (website/offer quality)
3. CPM (pixel training / targeting quality)
4. Cost per purchase (overall efficiency)
5. AOV (business model / upsell indicator)

### Always Optimize for Purchase Events
- Optimizing for add-to-cart delivers add-to-cart people, not buyers.
- Exception: Very small countries where audience pool is too limited.

### Creative Type Separation (Mandatory)
Never mix creative types in one campaign:
- Catalog/dynamic ads always steal budget from video/image.
- Video takes budget from image.
- Put each type in its own campaign.

---

## HOT POCKETS THEORY (Key Scaling Concept)

A "hot pocket" = a cluster of similar people formed around initial purchasers. The algorithm locks onto characteristics of early buyers and targets similar people.

**Critical insight:** Hot pockets form at the AD level, not the ad set level. Different ads within the same ad set produce different hot pockets.

**Why this matters for strategy:**
- One campaign with one angle = one hot pocket = scaling ceiling.
- Multiple campaigns with different creative angles = multiple hot pockets = higher ceiling.
- Creatives ARE targeting: a video showing parents attracts parents; a video showing athletes attracts athletes.

**How to create different hot pockets:**
- Use different angles for the same product (lifestyle, specs, aesthetics, practicality).
- Each angle targets a different customer segment.
- Each sustains its own campaign and budget.

---

## CROSS-REFERENCES

| Condition | Go To |
|---|---|
| Pixel maturity unknown or account is new | setup-meta-tracking |
| User asks about scaling budgets or breaking daily loops | scale-campaigns |
| Need ad copy or video scripts | create-ad-copy or create-video-ads |
| Day-to-day optimization or diagnostics | optimize-meta |
| Creative testing methodology | test-creative |
| Google campaign structure | strategy-google-ads |
| TikTok-specific strategy | strategy-tiktok-ads |

---

## ANTI-PATTERNS (Never Do These)

1. **One-campaign consolidation for scaling** -- limits to one hot pocket, caps ceiling.
2. **Mixing creative types in one campaign** -- catalog/video/image compete unfairly for budget.
3. **Adding new creatives to working campaigns** -- disrupts dominant ad balance. Put new creatives in new campaigns.
4. **Running traffic/engagement campaigns for e-commerce** -- targets non-buyers at $2-3 CPMs.
5. **Following Meta rep strategy advice** -- they are salespeople pushing consolidation and awareness.
6. **Excluding past customers** -- removes best optimization data from the chain.
7. **Launching ads late in the day** -- wastes the 24-48hr boost on dead hours. Launch at 6AM local.
8. **Mixing audience sizes in one CBO** -- broad (150M) takes all budget from small interest (3M).
9. **Running 6+ identical Crazy Methods with same creatives** -- same hot pocket collapses.
10. **Optimizing based on third-party app data** -- Facebook can only optimize on what IT sees.
