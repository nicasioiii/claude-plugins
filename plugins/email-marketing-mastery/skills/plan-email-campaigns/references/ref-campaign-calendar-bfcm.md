# Reference: Campaign Calendar & BFCM Playbook

## CAMPAIGN FREQUENCY DECISION FRAMEWORK

### Starting Frequency Decision Tree
```
List size < 5,000?
  YES -> 1 campaign/week max. Focus on list growth.
  NO -> Continue

Open rates consistently above 30%?
  YES -> Add 1 campaign/week. Recheck after 4 weeks.
  NO -> Continue

Open rates 20-30%?
  YES -> Maintain current frequency. Test subject lines + segments.
  NO -> Continue

Open rates below 20%?
  YES -> Reduce frequency OR tighten segment. Check deliverability.
```

### Scaling Logic (E02)
- Each additional campaign has diminishing per-email revenue
- 1/week = $2K per email; 2/week = $1,500 per email but $3K total
- As long as TOTAL revenue increases AND open rates stay above 20%, keep adding
- When total revenue plateaus or open rates drop below 20%, pull back

### Frequency by Season
| Period | Recommended Frequency | Notes |
|--------|----------------------|-------|
| January-March | 1-2/week | Post-holiday recovery, list cleanup |
| April-June | 2-3/week | Spring campaigns, graduation, wedding |
| July-September | 2-3/week | Summer sales, back-to-school |
| October (pre-BFCM) | 2-3/week | Testing cadence, warming segments |
| November (BFCM) | 5-14/week | Peak sending. Boosters, daily sends, multi-send days |
| December | 3-5/week tapering | Delivery cutoffs, then scale back post-ship date |

---

## OPTIMAL SEND DAY AND TIME

### Finding Your Best Send Day (E02)
1. Form hypothesis about customer behavior (thesis-based testing)
   - Fitness brand: Monday motivation, Sunday meal prep
   - Alcohol brand: Thursday/Friday pre-weekend
   - General ecom: Thursday is cross-the-board best for conversions
2. Test hypothesis over 4-8 weeks
3. Once optimal days are found, make them consistent (uniform planning)

### Finding Your Best Send Time (E02)
1. Open Klaviyo's open-by-hour curve on sent campaigns
2. Identify primary and secondary peaks
3. Schedule campaigns at identified peak times
4. Re-evaluate quarterly as audience behavior shifts

### Contrarian Timing Strategy (E03)
- When "best time" studies are published, everyone sends at those times
- For ecom, send when others are NOT sending -- evenings and weekends
- 70%+ opens are on mobile; people browse phones during evening TV time
- Test evening sends (7-9 PM) and weekend morning sends

### Synthesized Approach
- Use Klaviyo data for YOUR specific audience peaks
- Test contrarian evening/weekend sends against peak-time sends
- Once you find what works, make it consistent and predictable

---

## UNIFORM PLANNING METHODOLOGY

### The System
- Choose 1-3 fixed send days per week
- Same days every week (e.g., every Tuesday and Thursday)
- Stick to the schedule to train subscriber opening habits
- Plan campaigns 1 week to 1 month in advance

### Team Workflow (E02)
| Step | Who | Time |
|------|-----|------|
| Create task with campaign idea + date + deadline | Marketing manager / founder | Planning day |
| Write copy | Copywriter | <30 min per email, <1 day turnaround |
| Design creative | Graphic designer | 20 min - 1 hour (excl. revisions) |
| Upload and schedule | Email manager | <10 minutes |
| **Buffer:** Leave 2-3 days minimum before send | | Ideal: 1 week in advance |

### Speed Over Perfection (E02)
- Past the first two screens, only ~5% of openers see the rest
- Turnaround time above all -- better to send on schedule with a good-enough email than to delay for perfect
- Subject lines above content -- invest time in opens, not body copy polish

---

## BOOSTER / DOUBLE-DOWN DETAILED PROTOCOL

### Why It Works (E02)
1. Different people check inboxes at different times (70% at 8 AM, 30% at 5 PM)
2. Different people resonate with different subject line styles
3. Estimated: boosters capture an additional 15-25% of potential opens

### Subject Line Style Switching
| Original Style | Booster Style |
|---------------|---------------|
| "30% off for Labor Day" (direct) | "Something special for you this weekend" (curiosity) |
| "MEMORIAL DAY SALE" (caps, urgent) | "we left a gift for you" (lowercase, personal) |
| Discount-forward | Content/story-forward angle |
| Short (under 40 chars) | Longer, conversational |

### Booster Revenue Benchmarks (E02)
- One client generated $18,300 additional revenue from a single booster email on the welcome series
- Test with 100-300 booster sends initially; expected conversion rate 1-3%
- Works best for high-AOV stores where customers delay purchasing decisions

### Gap Frequency Rules
- Minimum 6-week gap between booster cycles
- Maximum 5 consecutive days of boosting (kills sender reputation beyond that)
- Ideal: 6-9 weeks between uses for maximum impact

---

## BFCM COMPLETE PLAYBOOK

### Pre-BFCM Preparation (Start September-October)

#### Technical Checks
- Check ESP plan limits (send volume, traffic caps on popup tools)
- Ensure all tracking pixels are functioning
- Verify inventory levels match projected demand
- Test discount types: percentage vs. dollar amount vs. free gift vs. tiered

#### Strategic Preparation
- Test segmentation and cadence: which segments tolerate multiple emails/day?
- Align messaging across ALL channels (email, paid ads, site banners)
- Plan campaign calendar at least 1 month in advance
- Build BFCM-specific popup with "notify me first when deals drop" messaging

#### Deliverability Prep
- Run IP warm-up if needed (see `fix-deliverability` skill)
- Clean unengaged subscribers before peak season
- Start broadening send segments in October to warm wider list

### BFCM Email Cadence (E03)

| Period | Timing | Discount | Emails/Day |
|--------|--------|----------|------------|
| Early Bird / Pre-BF | Mon before BF (or 2 weeks out) | Lowest tier (15%) | 1/day |
| Black Friday | BF day | Higher tier (20%) | 2 emails |
| Extended BF | Sat-Sun after BF | Same as BF | 1/day |
| Cyber Monday | CM day | Highest tier (25-30%) | 2 emails |
| Extended CM | Through end of November | Same or slightly lower | 1/day |

### Escalating Discount Framework
- Start lower, escalate through the week
- Each tier is a "new" opportunity for fence-sitters
- Critical: EXCLUDE purchasers from subsequent sends at higher tiers (E03)
- Someone who bought at 15% off must NEVER see the 20% offer

### Purchaser Exclusion Logic (E03)
```
For each BFCM campaign:
  Exclude: Placed order during [current BFCM period] = 1+ times
  Result: Purchasers at Tier 1 never see Tier 2+
  Why: Prevents cancel-and-reorder behavior + resentment
```

### Two-Offer Strategy (E02)
- Offer A for early buyers (first 48 hours)
- Offer B introduces new incentive for holdouts (days 3-5)
- Never show Offer B to people who already purchased via Offer A

### BFCM Countdown Timer Tactics (E03)
- Use countdown timer tools (Motion Mail, countdownmail.com)
- Option A: Accurate countdown to actual sale end date
- Option B: Daily reset timer (resets every 24 hours for ongoing urgency)
- Place in emails AND on-site (JustUno)

### BFCM-Specific Popup Strategy (E03)
- Separate BFCM popup: "Give us your email, we'll notify you first when deals drop"
- Pop-up discount MUST match email discount -- update popup every time discount changes
- Trigger BFCM-specific welcome flow for new popup subscribers
- Repurpose campaign emails as triggered automations for new subscribers during BFCM

### BFCM Key Benchmarks (E03 -- Klaviyo Data)
- 48% of BFCM sales came from existing customers (active Q1 previous year to Q3 current)
- 70% of first-time BFCM purchasers did NOT buy again (retention opportunity)
- Customers who clicked email before Q4 had 17% higher AOV
- 89% of BFCM sales came from customers who had opened an email
- Holiday sales increased 19% YoY; acquisition costs rose 25%

---

## POST-BFCM / DECEMBER STRATEGY

### Delivery Cutoff Campaign Series
- Work backwards from guaranteed Christmas delivery date
- Different cutoff dates for standard vs. expedited vs. overnight
- Campaign messaging: "Order by X date to receive by Christmas"

### Post-Shipping-Cutoff
- Do NOT stop emailing -- scale back significantly but stay relevant
- Christmas Eve: send personalized text-only email from founder (holiday wishes)
- Christmas content: brand personality, gratitude, behind-the-scenes

### January Strategy
- "New year, new you" -- critical for wellness/fitness brands
- "Post-Q4 BFCM hangover" is real -- automation revenue bridges the gap
- Focus on content campaigns and list re-engagement
- Light promotional cadence with fresh spring collection or clearance

---

## WEEKLY EMAIL BROADCAST RHYTHM (Throssell -- E06)

### Structure for Creator/Personality Lists
- 90% of emails: soft sell (story + link to offer)
- Sprinkle pure value, entertainment, and engagement
- At regular intervals: short 3-7 day promotions with harder selling
- During promotions: 1-2 emails per day, mixing salesy with value-based
- Final day of promotion: 3-8 emails if they are entertaining (E06: 8 on last day, list begged for MORE)
- Sales are back-loaded: expect 1/3 to 1/2 of sales in the final 24 hours

### Save Your Ammunition (E06)
- Do not throw every element into the first email of a promotion
- Distribute: guarantee, price, bonuses, payment plan, testimonials over the promotion window
- As people become ready, they buy. For holdouts, introduce new elements progressively.

### Disguise Pitches as Entertainment (E06)
- When sending multiple sales emails in a day, wrap each in a different creative frame
- Example: Each email written in the "voice" of a different copywriter
- People read the same pitch multiple times when it is entertainingly packaged
