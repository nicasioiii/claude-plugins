---
name: Google Scaling Methods
description: GTC scaling (budget + bid), standalone campaign scaling, PMax scaling methods, Search scaling, Shopping scaling prerequisites, and scaling decision framework.
---

# Google Scaling Methods

## SHOPPING: GTC SCALING (Shri)

### Prerequisites
- Entire campaign must be profitable in last 7-14 days (not just one product).
- Product must be PROFITABLE, not just getting sales.
- Minimum 3-5 sales in last 7 days.
- Do NOT try to scale unprofitable products into profitability -- almost never works.

### Budget Scaling Rules
| Current Budget | Increase Amount | Frequency |
|---|---|---|
| Below $100/day | $10-$15 maximum | Every 7 days |
| Above $100/day | 20% | Every 7 days |
| Q4 / time-constrained | Same amounts | Every 3-4 days |

### Bid Scaling (Special Cases Only)
- Only increase bid if campaign ROAS > 6x OR budget is not fully spent.
- Increase by $0.01 to $0.03 at a time -- NEVER large bid changes.
- Expect ROAS to drop with bid increases.
- Higher bids don't rank higher -- they open up broader search queries.

### Additional GTC Scaling Levers
- Add more retargeting audiences (observation mode).
- Add more products in same niche/category as the winner.
- One change at a time, 7-14 day wait between changes.
- Exception: Adding products can be done alongside budget/bid changes.

---

## SHOPPING: STANDALONE CAMPAIGN SCALING (Shri -- Preferred Method)

### Why This Is Preferred
Isolates the winning product with its own budget, bid, and priority. More control over scaling the specific winner without affecting the testing campaign.

### Setup Steps
1. Copy/paste the original campaign (GTC or Smart Shopping).
2. Exclude ALL products in the duplicated campaign.
3. Include ONLY the winning product (via Item ID subdivision).
4. Set campaign priority to **HIGH** (vs Medium for GTC).
5. Increase bid by $0.01 to $0.15 above original campaign's average CPC.
6. Budget: Start at $50/day.

### Campaign Priority System
| Campaign Type | Priority |
|---|---|
| General Testing Campaigns | Medium or Low |
| Standalone Scaling Campaigns | HIGH |

When standalone (HIGH) exhausts its budget -> GTC (MEDIUM) takes over for that product. Creates a tiered bidding system automatically.

### Bid Strategy Options
- Maximize Clicks (with bid limit slightly above original CPC).
- Manual CPC with Enhanced CPC (check box if 10+ sales for that product).

### Smart Shopping Standalone Variant
- Create smart shopping campaign for individual winning product.
- Start with Enhanced CPC.
- After 50 sales total -> switch to Target ROAS.
- Set Target ROAS slightly below actual (e.g., actual 6.71x -> set 500%).
- This often causes conversion value to skyrocket.

---

## PMAX SCALING (Shri)

### Prerequisites
- PMax running minimum 14-30 days.
- No changes made in past 2-3 days.

### Scaling Decision Framework
1. Check ROAS for last 14 days -> must be above break-even.
2. Check ROAS for last 30 days -> compare to 14-day (should be improving or stable).
3. Check ROAS for last 7 days (grain of salt) -> confirms recent trend.
4. Check if budget is being spent fully.

### Method A: Budget Increase
**When:** Budget is fully spent + campaign is profitable.
- Increase budget by 10-30%.
- Example: $100/day -> $110-$130/day.
- Wait 7-14 days before next change.

### Method B: Lower Target ROAS
**When:** Budget is NOT fully spent (campaign is restricting itself).
- Lower target ROAS by small increments (e.g., 210% -> 200%).
- Removes restrictions so campaign can find more audience.
- Wait 7 days before next change.

### Method C: Add More PMax Campaigns
- Per collection (segment product catalog).
- Per country (geographic expansion).
- Assets vs no-assets testing (feed-only vs full-asset).
- Each new campaign needs its own 14-30 day learning period.

### Key Rule
After any scaling change, wait 7 days minimum before additional changes. ROAS will naturally decrease slightly when scaling budget (expected and acceptable if still above break-even).

---

## SEARCH SCALING (Ezra/Brett + PPC Hub)

### Bidding Progression for Scale
1. Start with Enhanced CPC or Max Conversions.
2. After 30 conversions in 30 days: switch to Target CPA or Target ROAS.
3. Set initial target at current performance level.
4. Optimize: max 20% change per week (recommended 10%, 1-2x/week).

### Budget Scaling
- High-volume accounts ($100K+/month): adjust weekly.
- Lower-volume accounts: monthly adjustments.
- Follow the 20% rule for budget changes.

### Scaling Within Limited Budgets (PPC Hub)
If hitting efficiency targets but budget-limited:
1. Lower target CPA to reduce CPCs.
2. More clicks within same budget.
3. If CVR holds, more conversions at lower CPA.
4. Then advocate for more budget with proven results.

Case study: Target CPA 3 EUR -> lowered to 2.25 EUR -> CPCs decreased -> more clicks in same budget -> explosion in conversions when budget increased.

---

## YOUTUBE SCALING (Ezra/Brett)

### Portfolio Approach
Don't judge YouTube by direct ROAS alone. YouTube's 50% direct ROAS drives 27%+ growth in non-YouTube campaign revenue.

### Budget Allocation for Scale
| Channel | % of Total Google Budget |
|---|---|
| Search | 10-30% |
| Shopping / PMax | 30-65% |
| Remarketing | 10-20% |
| YouTube & Display TOF | 10-50% |

### The Halo Effect at Scale
- Starting YouTube caused brand searches to more than DOUBLE (automotive case study).
- Pausing YouTube for 2 weeks halved Amazon brand search volume (hair care case study).
- Portfolio ROAS of 200% translates to ~330-400% MER.

---

## GOOGLE SCALING BENCHMARKS

| Metric | Threshold |
|---|---|
| Minimum sales before scaling (Shopping) | 3-5 in last 7 days |
| PMax minimum run time before scaling | 14-30 days |
| Smart bidding conversion threshold | 30 conversions in 30 days |
| YouTube smart bidding threshold | 15-20 conversions in 30 days |
| Maximum budget change per week | 20% (10% recommended) |
| Maximum bid change (Shopping) | $0.01-$0.03 per change |
| Target ROAS switch threshold (Smart Shopping) | 50+ sales for that campaign |
| Wait time between scaling changes | 7 days minimum |
| Budget scaling rate (Shopping GTC) | 10-30% every 7 days |

---

## COMMON GOOGLE SCALING MISTAKES

1. **Scaling before 3-5 profitable sales in last 7 days** -- insufficient data.
2. **Increasing Shopping bid by more than $0.03** -- disrupts learning.
3. **Budget jumps >30%** -- throws campaign into learning mode.
4. **Increasing bid when ROAS < 6x** -- unless budget is not fully spent.
5. **Not waiting 7 days between changes** -- learning periods stack.
6. **Trying to scale unprofitable products** -- almost impossible.
7. **Making multiple changes on same day** -- can't isolate what worked/failed.
8. **Touching PMax within first 2-6 weeks** -- kills learning.
9. **Not checking search impression share** -- may have room to scale with existing campaigns before adding new ones.
10. **Ignoring feed optimization before scaling** -- product titles are the #1 lever for Shopping reach.
