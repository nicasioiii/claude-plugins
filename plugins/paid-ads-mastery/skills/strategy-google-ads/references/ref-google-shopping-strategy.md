---
name: Google Shopping Campaign Strategy
description: Shopping fundamentals (wallet-out traffic), campaign architecture (high bid + low bid testing), optimization frequency (7-14 days only), product and keyword optimization, CTR targets, and standalone campaign scaling.
---

# Google Shopping Campaign Strategy

## SHOPPING FUNDAMENTALS

### Why Shopping Ads Work
- Largest comparison shopping engine outside Amazon.
- "Wallet out traffic" -- shoppers see image, price, title, reviews BEFORE clicking.
- No explicit keyword targeting -- Google decides when to show based on feed, landing page, and bids.
- Conversions happen at the item ID level -- Google stores conversion history with item IDs.
- NEVER change item IDs once set (loses all conversion history).

### Product Feed: The Foundation
Product titles are THE most important attribute:
- Front-load keywords (Google weights beginning words more heavily).
- 150 characters max, but only 50-70 show in the ad.
- Include: brand, color, size, gender, product type.
- DO NOT include: promotions, "best", extra non-specific qualifiers.

-> For detailed feed setup, see setup-google-ads skill.

---

## CAMPAIGN ARCHITECTURE: HIGH BID + LOW BID (Shri)

### Campaign 1: General Testing -- HIGH BID
| Setting | Value |
|---|---|
| Bidding | Maximize Clicks |
| Max CPC Bid Limit | $0.40 - $0.50 (sweet spot: $0.43-$0.46) |
| Daily Budget | $25 minimum |
| Campaign Priority | Medium |
| Networks | Search Network ONLY (uncheck YouTube/Gmail/Discover) |
| Location | United States only, "Presence: People in or regularly in" |
| Warm-up period | 1-4 weeks for new accounts |

### Campaign 2: General Testing -- LOW BID
| Setting | Value |
|---|---|
| Same as above EXCEPT: | |
| Max CPC Bid Limit | $0.10 (10 cents) |
| Daily Budget | $25 (will only spend $5-10/day due to low bid) |

**Key insight:** The low bid campaign may be your most profitable. Low bid = Google only finds highest-quality traffic within that bid limit. Products that don't perform at $0.40-$0.50 often perform well at $0.10.

### Bidding Strategy Rationale
- Do NOT start with Target ROAS -- new accounts lack data.
- Maximize Clicks preferred over Manual CPC -- gets data faster, CPC decreases as algorithm learns.
- Manual CPC bid ranges are usually the same regardless of product cost ($0.40 works for $50 AND $500 products).

---

## OPTIMIZATION FREQUENCY

### The Cardinal Rule: Every 7-14 Days ONLY
- Each optimization restarts the campaign learning phase.
- Expect results to tank for 2-3 days after any optimization.
- Look at data for last 7-14 day window matching your cycle.
- DO NOT TOUCH campaigns for first 2-3 weeks regardless of results.

---

## PRODUCT OPTIMIZATION

### Step 1: Rank by Cost (Highest Spend First)
**Filters:** Impressions >= 500, Product Status = Ready to Serve.

**Exclude products that spent 1.5x to 3x profit margin with no/insufficient sales:**
- Example: $30 profit margin -> exclude after $45-$90 spent with zero sales.
- Go through entire list one by one, highest spend first.

### Step 2: Rank by Low CTR
| CTR Level | Action |
|---|---|
| Zero clicks + 500+ impressions | EXCLUDE immediately |
| CTR < 0.10% + zero sales | EXCLUDE (or try fixing image/price/title) |
| CTR 0.10% - 0.25% + zero sales | Try fixing: image first (7-14 day wait), then pricing, then keywords |
| Products WITH sales | DO NOT change anything (sales > CTR always) |

### Campaign CTR Target
- **Overall campaign CTR target: 1% or above.**
- Below 1% = quality score drops -> CPC increases -> unprofitability spiral.

---

## KEYWORD / SEARCH TERM OPTIMIZATION

### Filters
- Impressions >= 300.
- Added/Excluded = None.

### Process
1. Rank by cost -- exclude keywords that spent 1.5x-3x profit margin with zero sales.
2. Aggressive method: Exclude any keyword that spent $20+ without a sale.
3. One product can have hundreds of keywords -- don't have budget to test each one.

---

## SHOPPING BIDDING PROGRESSION (Ezra/Brett)

1. **Start:** Manual CPC with Enhanced option (ECPC), optimize for conversion value.
2. **Alternative start:** Maximize Clicks if struggling for traffic (use briefly).
3. **Goal:** Target ROAS (only channel with direct Target ROAS option).
4. **Switch:** After 30 conversions in 30 days.
5. Set initial ROAS target at current performance, then optimize over time.

### Important Bid Mechanics
- Higher bids DON'T rank higher -- they open up broader search queries.
- Lower bids narrow/focus targeting.
- $0.40 bid can sell both $50 and $500 products.

---

## STANDALONE CAMPAIGN SCALING (Shri -- Preferred Method)

### When to Scale
- Product must be PROFITABLE (not just getting sales).
- Minimum 3-5 sales in last 7 days.
- Do NOT try to scale unprofitable products into profitability.

### Setup
1. Copy/paste the original campaign (GTC or Smart Shopping).
2. Exclude ALL products in the duplicated campaign.
3. Include ONLY the winning product (via Item ID subdivision).
4. Set campaign priority to HIGH (vs Medium for GTC).
5. Increase bid by $0.01 to $0.15 above original campaign's average CPC.
6. Budget: Start at $50/day.

### Campaign Priority System
| Campaign Type | Priority |
|---|---|
| General Testing Campaigns | Medium or Low |
| Standalone Scaling Campaigns | HIGH |

When standalone (HIGH) exhausts its budget -> GTC (MEDIUM) takes over for that product.

---

## GTC SCALING (Shri)

### Requirements
Entire campaign must be profitable in last 7-14 days (not just the product).

### Budget Scaling Rules
| Current Budget | Increase Amount | Frequency |
|---|---|---|
| Below $100/day | $10-$15 max | Every 7 days |
| Above $100/day | 20% | Every 7 days |
| Q4 / time-constrained | Same amounts | Every 3-4 days |

### Bid Scaling (Special Cases Only)
- Only increase bid if campaign ROAS > 6x OR budget not fully spent.
- Increase by $0.01 to $0.03 at a time -- NEVER large bid changes.
- Expect ROAS to drop with bid increases.

### Additional GTC Scaling
- Add more retargeting audiences.
- Add more products in same niche/category as the winner.
- One change at a time, 7-14 day wait between changes.

---

## RETARGETING VIA SHOPPING ADS (Shri)

### Audiences to Create
| Audience | Bid Adjustment |
|---|---|
| All Visitors (max window) | +40-80% (sweet spot: 50%) |
| Cart Abandoners (90-180 days) | +80-150% (highest intent) |
| Purchasers (150+ days) | Start at 0%, monitor |
| Similar to All Visitors | +0-5% (low trust) |

### Setup
- Use OBSERVATION mode (not Targeting) -- targets warm alongside cold.
- Build ALL audiences from the start so they accumulate data.

### Performance Benchmarks (Shri)
| Audience | ROAS |
|---|---|
| Cart Abandoners | 10.49x |
| All Visitors | 6.01x |
| Similar to All Visitors | 2.68x |
| Purchasers | 1.67x |

Cart abandoners consistently outperform purchasers for retargeting.

---

## IMAGE SELECTION STRATEGY (Shri)

### Rule 1: Do the OPPOSITE of Competitors
- If majority are lifestyle images -> use white background.
- If majority are white background -> use lifestyle image.
- Count top 5-10 listings to determine which type has fewer.

### Rule 2: Find a Unique Variant
- If everyone sells black/gray -> find blue, green, purple, orange.
- Different color/design = instant visual standout.

### Real-World Proof
Sold a product at $150 when Amazon/eBay sold at $100, purely because of a lifestyle image vs their white background images.
