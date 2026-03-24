---
name: Meta Cost Caps & Bid Caps
description: Cost cap vs bid cap philosophy, discover during good periods, implementation with dual ABO campaigns, value optimization for ASC.
---

# Meta Cost Caps & Bid Caps

## CORE PHILOSOPHY (Konstantinos)

### Set Caps During GOOD Periods, Not Bad Periods
- Bad periods = inflated CPMs from bad advertisers flooding the auction.
- Don't chase bad advertisers' inflated CPMs by raising your caps.
- Set caps based on what works during good periods, then hold steady during bad periods.

### Cost Caps and Bid Caps Are "Next Level"
- Master CBO/ASC optimization first.
- They are difficult because every account behaves differently.
- Requires experimentation specific to each account.

---

## BID CAPS VS COST CAPS

### Bid Cap
- **More strict:** "Give me this or nothing."
- Delivery is closer to the number you set.
- If no conversions can be found at your bid level, spend will be $0.
- Better for precise cost control when you have reliable historical data.

### Cost Cap
- **More flexible:** If you set $48, it might deliver at $58-60 sometimes but averages out.
- Allows more spending flexibility while maintaining average efficiency.
- Better for accounts that need volume with some cost protection.

### Both Are Volatile
- Require experimentation on each account.
- Results vary by account, product, country, and season.
- Start conservative, then increase gradually.

---

## IMPLEMENTATION: DUAL ABO APPROACH

### Setup
Run two ABO campaigns simultaneously:

**Campaign 1: Cost Cap ABO**
- Budget at ad set level.
- Set cost cap at your target CPA.
- More flexible delivery -- will sometimes exceed cap but averages out.

**Campaign 2: Bid Cap ABO**
- Budget at ad set level.
- Set bid cap at your target CPA.
- Stricter -- closer to exact number but may not spend full budget.

### Why Run Both
- Different accounts respond differently to each type.
- Running both simultaneously lets you compare performance.
- One typically outperforms the other on any given account.
- Keep the winner, optimize the other, or run both if both profitable.

---

## VALUE OPTIMIZATION FOR ASC

### How It Works
- Works well with Advantage Shopping (ASC) campaigns.
- Optimizes for conversion VALUE, not just conversion count.
- Prioritizes higher-AOV purchases.

### When to Use
- Products with varying price points.
- Want to maximize revenue, not just purchase count.
- Account has enough purchase data for value-based optimization.

---

## COST CAP SCALING PROGRESSION

### Starting Point
1. Set cost cap at your current average CPA.
2. Run for 5-7 days to validate.
3. If profitable and spending full budget:
   - Increase cost cap by 10-20% to unlock more volume.
   - Each increase trades some efficiency for more spend.

### If Not Spending
- Cost cap may be too low for current market conditions.
- Check if this is a "bad period" (seasonal CPM inflation) before raising.
- Small increase ($2-5) may unlock spending without significant efficiency loss.

### Manual Bid Scaling (Deividas Method)
- Start at average CPA.
- Increase by 20% per ad set.
- Create multiple ad sets at different bid levels.
- Sniper variant: Very low manual bid = only spend ~40-50% of budget, captures cheapest audience pockets.

---

## WHEN NOT TO USE COST CAPS / BID CAPS

### Skip If:
- Account is brand new (insufficient data to set meaningful caps).
- You don't know your break-even CPA (flying blind).
- You haven't mastered standard CBO/ASC optimization.
- You're in a "bad period" and trying to force results (will just prevent spending).

### Cost Caps Cannot Fix:
- Bad creatives (no amount of bid optimization helps).
- Weak offers (the product/offer must convert first).
- Untrained pixels (not enough data for meaningful cap-based optimization).
- Fundamental business problems (low margins, low AOV).

---

## KEY BENCHMARKS FOR CAP SETTING

| Metric | How to Use |
|---|---|
| Break-even CPA | Absolute maximum for your cost cap |
| Target CPA | Start your cost cap here (typically 70-80% of break-even) |
| Historical average CPA | Baseline for initial cap setting |
| Good-period average CPA | Best reference -- set caps from this number |
| Bad-period average CPA | Ignore -- don't chase inflated costs |

### Reporting Correlation Method
- Find the correlation between Ads Manager CPA and real (bank) CPA.
- If Ads Manager shows $25 CPA when real CPA is $20, set cost cap based on Ads Manager number ($25), not real number.
- Optimize campaigns based on Ads Manager numbers; evaluate BUSINESS based on real numbers.

---

## ADVANCED IMPLEMENTATION EXAMPLES

### Example 1: E-Commerce Brand ($50 AOV, 60% Margin)
- Break-even CPA = $30
- Target CPA = $22 (73% of break-even)
- Cost cap starting point: $22
- Bid cap starting point: $22
- Run both simultaneously for 7 days
- If cost cap spends full budget at $24 avg CPA: profitable, keep running
- If bid cap delivers at $21 CPA but only spends 40% of budget: consider raising to $25

### Example 2: High-AOV Product ($200 AOV, 45% Margin)
- Break-even CPA = $90
- Target CPA = $65 (72% of break-even)
- Longer evaluation window needed (10-14 days) due to lower volume
- Cost cap preferred over bid cap for high-AOV (fewer conversions = less data for strict bid cap)

### Example 3: Lead Gen ($150 CPL Target)
- Set cost cap at $150 CPL
- Bid cap at $150 CPL
- Lead gen typically responds better to cost caps (more volume flexibility)
- Kill threshold: 2x target CPL with zero qualified leads

---

## EDGE CASES AND TROUBLESHOOTING

### Cap Suddenly Stops Spending
1. Check if CPM environment changed (seasonal spike, competitor surge)
2. Review if creative fatigue set in (frequency climbing)
3. Check for auction overlap with other campaigns eating the same audience
4. Try raising cap by $3-5 increments rather than large jumps

### Cap Overspending Significantly
1. Cost cap averaging out over a longer window than expected
2. Switch to bid cap for tighter control
3. Reduce daily budget to limit total overspend exposure
4. Check if a hot pocket shift moved you into a more expensive audience segment

### Running Caps Alongside Standard CBO
- Keep standard CBO campaigns running as your baseline
- Layer cost cap and bid cap campaigns on top for incremental volume
- Do not shut down working CBO campaigns to "switch" to caps
- Caps are additive scaling tools, not replacements for working campaigns

### Seasonal Adjustment Protocol
1. **Pre-peak (2-4 weeks before):** Set caps at your current good-period CPA
2. **During peak (Black Friday, holidays):** Allow 15-25% higher caps due to elevated CPMs
3. **Post-peak cooldown:** Return to pre-peak cap levels immediately
4. **Bad months (January, slow seasons):** Hold steady -- do not chase rising CPMs by raising caps
