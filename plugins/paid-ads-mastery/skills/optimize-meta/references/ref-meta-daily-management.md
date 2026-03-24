---
title: Meta Daily Campaign Management
skill: optimize-meta
usage: Load when user asks about daily optimization routines, the 24-48 hour boost, when to add creatives to working campaigns, downscaling protocol, or engagement management.
---

# Meta Daily Campaign Management

## CBO Optimization Loop (Daily Process)

### Morning Check (15 Minutes)
1. **Spend vs. budget:** Is today's spend tracking to daily budget? Meta may vary day-to-day but respects weekly total (7x daily budget).
2. **Rolling 7-day ROAS:** Compare to break-even ROAS. Is the trend up, flat, or down?
3. **CPA trend:** Is cost per acquisition stable? Slight daily variation is normal.
4. **Creative performance:** Which creatives received the most spend? Are they the ones performing best?
5. **Comments check:** Scan high-spend ads for negative comments. Hide immediately.

### Evening Check (10 Minutes)
1. **Daily spend pacing:** Did the campaign over/under-spend? Significant over-spend may indicate Meta found cheap conversions (good) or is burning budget on junk (check CPA).
2. **Checkout-to-purchase lag:** If checkouts showed up today but purchases did not, delayed reporting is likely the cause. Wait 24-72 hours before reacting.
3. **Flag any anomalies:** Sudden CPM spikes, creative that stopped spending, or unusual geographic shifts.

### Weekly Review (Monday Morning, 30 Minutes)
1. Pull 7-day rolling averages for all active campaigns
2. Identify winners and losers by campaign, ad set, and creative
3. Compare to previous 7-day period
4. Document learnings in testing tracker
5. Plan this week's creative launches

---

## The 24-48 Hour Boost

### What It Is
- New campaigns receive a performance boost in the first 24-48 hours
- Meta gives "low-hanging fruit" sales to kickstart the optimization chain
- This is by design -- Meta wants the campaign to succeed so you spend more

### How to Interpret It
- **Trained pixel:** The boost transitions smoothly into sustained performance
- **Untrained pixel:** Performance often drops sharply after the boost period
- **Never declare a winner based on Day 1-2 performance.** Wait until Day 4-5 for true signal.

### Relaunch Strategy
- When a campaign dies after the boost: turn it off, duplicate it, launch next day at 6 AM
- This gets a fresh 24-48 hour boost
- **Warning:** Overusing relaunches causes diminishing returns
  - Each relaunch holds for shorter periods: 4 days -> 2 days -> 1 day -> stops working
  - Meta's algorithm catches on to repeated relaunches

---

## When to Add New Creatives to Working Campaigns

### Default Answer: DO NOT.

**Case study proof:** ASC campaign went from 5.4 ROAS to ~2 ROAS after adding new creatives. Adding new ads to a working campaign disturbs the dominant ad's balance. New ads may not take significant budget, but they disrupt the optimization.

### What to Do Instead
- Put new creatives in their OWN new campaign
- Ads that do not perform in a working campaign can perform perfectly in their own campaign with their own budget allocation

### Two Exceptions
1. **Campaign is dying anyway** -- worst case you close it, so try new creatives of the SAME angle
2. **Seasonal transition** -- swap Black Friday ads for Christmas ads in same campaign (same hot pocket, different offer)

---

## Working with Rolling Averages

### The Right Way to Evaluate Performance

| Timeframe | Use For |
|---|---|
| **24-hour** | Anomaly detection only. Never optimize based on this. |
| **3-day** | Early signal for new campaigns (after boost period). |
| **7-day** | Primary optimization timeframe. Standard for weekly decisions. |
| **14-day** | Strategic decisions (scaling up/down, killing campaigns). |
| **30-day** | Business-level evaluation. Account health assessment. |

### Handling Day-to-Day Variance
- A campaign with 5 ROAS one day and 0.5 ROAS the next is NORMAL
- If the 7-day average is above break-even, the campaign is working
- Do not panic-close on bad days
- Do not over-celebrate on good days
- "The average over time is what matters"

### When Averages Break Down
- External events (holidays, competitor launches, news events) can skew averages
- Exclude Black Friday / major promotion days from rolling average calculations
- If 7-day average drops below break-even for the first time, extend to 14-day before killing

---

## Delayed Reporting (Post-iOS)

### Reporting Delays by Region
| Market | Typical Delay |
|---|---|
| United States | Up to 72 hours |
| Europe | 24-48 hours |
| Smaller countries | ~24 hours |

### Why Delays Happen
- Meta needs to identify WHO purchased (not just that a purchase occurred)
- The optimization event (whatever you optimize for) always has delayed reporting
- Checkout events report immediately (Meta does not need to ID "who" for non-optimization events)

### The Checkout-to-Purchase Ratio
- Use existing campaign data to establish your ratio
- Example: If historical ratio is 3:1 (3 checkouts per purchase), and new campaign shows 6 checkouts / 0 purchases -- wait 48 hours for delayed reported sales
- This ratio is your early indicator of campaign health before purchase data arrives

### Statistical Modeling
- Meta uses statistical modeling to fill in missing/partial conversion data
- They inflate reported events slightly to feed the optimization engine
- This is GOOD for optimization even if reporting is not 100% accurate
- Focus on correlation between Ads Manager numbers and actual bank results

---

## Engagement Management Protocol

### Why Comments Matter for Budget Allocation
- Facebook uses engagement to determine initial budget allocation between creatives
- High engagement (even negative) = more budget from the algorithm
- The algorithm CANNOT distinguish good engagement from bad engagement

### Comment Management SOP

**Daily (for high-spend creatives):**
1. Check all comments on active ads
2. **Hide** negative comments immediately (do not delete -- hiding is invisible to the commenter)
3. Respond publicly to questions and objections (turns negatives into sales opportunities)
4. Document recurring objections -- these become hooks for future ads

**When to Escalate:**
- Comments mentioning lawsuits, scams, or health risks = URGENT hide + review ad compliance
- Comment threads devolving into arguments = hide the triggering comment
- Competitors posting links in comments = hide + report

### Budget Hierarchy by Creative Type
Facebook allocates more budget to high-engagement formats:
1. Catalog/Dynamic ads (always win -- carousel format, auto-play)
2. Video post IDs (auto-play = easy engagement)
3. Carousel post IDs (swipeable = engagement)
4. Image post IDs (existing engagement helps)
5. Single image (hardest to get initial engagement)

**Never mix different creative types in the same campaign.** Catalog + video = catalog takes all budget. Video + image = video takes all budget. This is not a quality judgment -- it is an engagement-based allocation issue.

---

## Downscaling Protocol

### When to Downscale
- 7-day rolling ROAS below break-even
- CPA trending up for 5+ consecutive days with no improvement signal
- Seasonal downturn approaching (post-holiday, summer lulls)

### How to Downscale Safely
1. **When killing an ad set in CBO:** Reduce CBO budget by the amount that ad set was spending
2. **When pausing a campaign:** Do not reduce budget on remaining campaigns to "compensate" -- let them run at their current level
3. **Reduce testing percentage:** During downturns, shift from 50/50 concept/iteration to 20/80

### The Counter-Intuitive Rule
**When ad account underperforms: test LESS, not more.**
- Common mistake: media buyers panic and launch MORE tests during downturns
- More campaigns during a downturn = more spend for the same total results (daily loop effect)
- Focus on consolidating what works rather than fragmenting budget

---

## Automated Rules

### Expert Position: Skepticism
- Automated rules cannot account for delayed reporting, daily loops, or hot pocket dynamics
- A rule that kills a campaign at $50 CPA might kill it before delayed purchases report in
- Manual optimization based on understanding the algorithm beats automated rules

### If You Must Use Rules
- Only use for safety nets (e.g., pause if spend exceeds 3x CPA with zero conversions)
- Never use for optimization decisions (scaling, audience changes, bid adjustments)
- Always check rule-triggered actions within 2 hours
