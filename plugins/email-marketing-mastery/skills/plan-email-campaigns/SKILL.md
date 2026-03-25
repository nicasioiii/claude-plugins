---
name: Plan Email Campaigns
description: |
  MANDATORY TRIGGERS: plan email campaigns, campaign calendar, sale campaign, holiday campaign,
  BFCM campaign, content campaign, product launch campaign, review campaign, booster strategy,
  double-down strategy, campaign frequency, send times, send days, seasonal email marketing,
  promotional email schedule, campaign types, email schedule, campaign planning, email calendar.
  FOR: Campaign type selection (sales, announcement, holiday, content, product launch, review), campaign calendar architecture, send frequency rules, optimal send day/time selection, uniform planning, booster/double-down strategy (2-day and 4-day), BFCM timeline and escalating discount playbook, two-offer strategy, purchaser exclusion logic, holiday email strategy (invention vs. convention), mystery discount emails, extending sales, and campaign-to-segment matching.
  Do NOT use for: Writing email body copy (use write-email-copy), writing subject lines (use write-subject-lines), building automated flows like welcome/checkout/winback (use ecom-flows), launch sequences for info products or courses (use write-launch-sequence), deliverability troubleshooting (use fix-deliverability), segmentation architecture (use segmentation-list-health).
---

# Plan Email Campaigns

Plan and execute email campaigns -- sales, announcement, holiday, content, product launch, review campaigns. Includes campaign calendar, send frequency, segment selection, booster/double-down strategy, and BFCM playbook.

---

## SIX CAMPAIGN TYPES

### 1. Sales Campaign
- Highest revenue-generating campaign type; use sparingly to maintain impact
- Banner must convey offer without scrolling, within 3 seconds of opening
- If offer requires more than 7-10 words on the banner, it is too complicated
- Tiered discounts that require "mental gymnastics" increase friction and reduce conversion
- Mystery discount emails drive people to checkout to discover their code -- 50% more likely to buy (E02)
- 90% of people who see a well-designed banner click immediately if the offer is clear
- Keep sale campaigns brief -- below-the-banner content matters little when the offer is strong
- Promotion + urgency generally produces the highest conversion rate (E03)

### 2. Announcement Campaign
- Blends three purposes: offers, product launches, collection launches
- Two modes: **priming** (inform without CTA, optimize for awareness) or **selling** (educate + sell)
- Header banner (50% screen) vs. full banner (entire screen) -- use header when body content is equally important
- For product launches, use exclusivity language: "Early VIP Access" drove 40% open rate (E03)

### 3. Holiday Campaign
- **Invention holidays:** Made-up occasions to TEST new offers in 48-hour flash sales (E02)
- **Convention holidays:** Traditional holidays for bigger, extended sale periods
- Resource: nationaltoday.com/category/world for finding holidays
- If no fitting holiday exists, make one up (E02: "National Dog Bed Day")
- Structure: standard sales campaign with holiday theme; banner = occasion + offer

### 4. Content Campaign
- Most frequently sent campaign type (not every day has a sale)
- Two objectives: drive sales through educational content OR drive traffic for rapport
- Drive traffic to high-performing content on your site, NOT external blogs or YouTube
- Never link to external websites -- embed content on your site to capture pixel data (E02)
- Split one product's 3 benefits into 3 separate emails (E02: better readability, more emails, more conversions)

### 5. Review Campaign
- Feature customer reviews front and center
- Adds credibility and social validation from real buyers (E03)
- Select reviews that address specific objections (shipping time, results timeline)
- Blend reviews with UGC for maximum impact

### 6. Product Launch Campaign
- Announce new products to engaged/VIP audience first
- Drive scarcity: "Limited quantities available"
- Use exclusivity language for VIP early access
- For sustained launches (courses, info products), use the `write-launch-sequence` skill instead

---

## CAMPAIGN CALENDAR ARCHITECTURE

### Frequency Rules
- **Starting point:** 4 campaigns/month (1/week)
- **Scale range:** 4-12 campaigns/month based on season and list response
- **Scaling trigger:** Consistent 30%+ open rates = add one campaign per week
- **Alternative scaling:** Broaden segment (90-day to 120-day to 150-day engaged)
- **Maximum floor:** Keep open rates above 20% -- below that damages sender reputation
- **Revenue math:** 1/week = $2K/email; 2/week = $1,500/email but $3K total (E02)
- **Recommended max:** 3/week in non-promotional periods (4 if pushing it)
- **Smaller brands:** Max 1-2/week; focus on cracking acquisition channels first

### Optimal Send Days
- Thursday is cross-the-board best performing day for purchase conversions (E02)
- Use "thesis-based testing" -- form hypothesis about customer behavior (e.g., alcohol brand = Thursday/Friday)
- [CONTRARIAN -- E03] Send when others are NOT sending (evenings, weekends) for less inbox competition
- Synthesize: test peak-time approach (E02) with contrarian timing (E03) -- both have data behind them

### Finding Optimal Send Time
- Use ESP open-by-hour curve on sent campaigns
- Identify secondary peaks (e.g., fitness brand peaks at 7 AM)
- 70%+ of opens are on mobile; people browse phones in the evening while watching TV (E03)
- Test sending at identified peak times in subsequent campaigns

### Uniform Planning Strategy
- Use predictable, consistent sending days to train customers to expect your emails
- If sending 2x/week: same 2 weekdays every week (e.g., every Sunday and Thursday)
- Stick to the schedule once optimal days are found
- Predictability builds habitual opening behavior

### Beyond 3-4 Campaigns/Week: Microlists
- Send targeted messaging to hyper-filtered segments (e.g., females in a specific US state)
- Microlists produce 20%+ conversion rates, 70% opens (E02)
- This is how top agencies generate impressive case study screenshots
- Use for: High-LTV customers, specific geography, ultra-tailored content

---

## BOOSTER / DOUBLE-DOWN STRATEGY

### What It Is
Send the same campaign to the same audience with a DIFFERENT subject line and preview text, EXCLUDING people who already opened the original (E02).

### Execution Checklist
1. Schedule original campaign normally (specific time, NOT recipient local timezone)
2. Create segment: opened campaign [campaign name/ID] at least once over all time
3. Clone original campaign, add "BOOSTER" to name
4. Exclude the opened-segment from recipients
5. Change subject line style (e.g., camel case to lowercase; direct offer to content angle)
6. Schedule at different time of day
7. MUST tick "determine recipients at send time" in Klaviyo (critical)

### Timing
- **Aggressive:** Same day, minimum 6-hour gap (original 8 AM, booster 7 PM)
- **Conservative:** ~30 hours later (full day for opens + hits different time of day)
- **Never:** Boost at exactly 24 hours (same time = same audience awake)

### When to Use
- Promotional periods (Black Friday, Christmas, 4th of July, Easter, Valentine's)
- Exceptionally high-performing campaigns (200%+ of average revenue)
- Minimum 6-week gap between uses; ideal 6-9 weeks between booster cycles
- Maximum 5 consecutive days of double-down (kills sender reputation beyond that) (E02)

### When NOT to Boost
- Original campaign open rate below 15% (deliverability issue -- fix that first)
- [CONTRARIAN -- E02] Only boost WINNERS, never underperformers. Boosting losers is "like giving raises to underperforming employees."

### Two-Day Double Down (Flash Sales)
- Day 1: 2 emails (AM launch + PM booster)
- Day 2: 2 emails (AM + PM booster with heavy urgency/scarcity + countdown timer)

### Four-Day Double Down (Major Promotions)
- Day 0: Prime email (non-sales: "something big is coming, watch your inbox")
- Day 1: 2 emails (launch AM + booster PM)
- Day 2: 2 emails (offer + product benefits emphasis)
- Day 3: 2 emails (social proof, reviews, UGC)
- Day 4: 2 emails (urgency, countdown timers, final push)

### Extending a Sale
Frame as "sale was so successful we're extending 24 hours so nobody misses out" -- but only extend ONCE. Repeated extensions destroy trust (E02).

---

## BFCM PLAYBOOK

See `ref-campaign-calendar-bfcm.md` for the complete BFCM timeline, escalating discount framework, purchaser exclusion logic, countdown timer tactics, and post-BFCM December strategy.

Key principles:
- Start preparation September-October
- Test segmentation and cadence: which segments tolerate multiple emails/day?
- Escalating discounts from early bird through Cyber Monday
- ALWAYS exclude purchasers from subsequent sends at higher discount tiers (E03)
- [CONTRARIAN -- E03] Do not worry about over-sending during BFCM -- everyone expects high volume
- [NUANCE -- E02] Aggressive but with guardrails: max 5 consecutive days of double-down
- Pop-up messaging must match email messaging when discounts change
- Post-BFCM: work backwards from guaranteed Christmas delivery date

---

## DISCOUNT STRATEGY

### Tiering (Work Backwards from Maximum)
- Reserve highest discount for highest-traffic period (BFCM)
- Use lower discounts (15-20%) for secondary holidays
- In automations, start lower and increase as user moves deeper without converting (E03)

### Tiered Discounting (AOV Booster)
- Buy 1 item: 10% off / Buy 2 items: 15% off / Buy 3 items: 20% off
- Lifts AOV, overall conversion rate, and total sales (E03)

### Non-Discount Alternatives
- Giveaways, BOGO, free gift with purchase, Spend X Save X
- Use segmented offers: VIPs get free gift, engaged get spend-save (E03)

---

## CAMPAIGN MIX STRATEGY

### Weekly Email Mix (By Throssell -- E06)
Structure a weekly broadcast rhythm:
- Majority of emails: soft sell (story + link to offer)
- Sprinkle in pure value, entertainment, and engagement
- At intervals, run short sales (3-7 day promotions) with harder selling
- Disguise sales pitches as entertainment for multi-send-per-day periods
- Save your ammunition: do not throw every element (guarantee, price, bonuses) in the first email. Distribute objection handling over the promotion window (E06)

### Plain Text as Pattern Breaker
- After 3-4 designed emails during heavy promos, deploy one plain text email
- Plain text nearly doubled open rates for a brand with 10% open rates (E02)
- Use 80/20 or 90/10 designed-to-plain ratio overall
- Plain text is a strategic weapon, not the default

---

## INSTRUCTOR DISAGREEMENTS (RESOLVED)

| Topic | E02 (Ecom School) | E03 (MuteSix) | Synthesis |
|-------|-------------------|---------------|-----------|
| Send time | Find peak open times via Klaviyo curves | Send when others are NOT sending (evenings/weekends) | Test both -- peak-time data plus contrarian timing |
| BFCM frequency | Max 5 consecutive days of double-down | "Don't worry about over-sending during BFCM" | Aggressive but with guardrails per E02 |
| Subject line importance | Subject line is THE most important variable | Subject line still #1 for A/B testing | Both agree; E06 nuances that sender name matters more for daily loyal readers |

---

## CROSS-REFERENCES

| Need | Skill |
|------|-------|
| Writing the actual email body copy | `write-email-copy` |
| Crafting subject lines + A/B testing | `write-subject-lines` |
| Launch sequence for info product/course | `write-launch-sequence` |
| Campaign segment selection | `segmentation-list-health` |
| Welcome/abandon/post-purchase flows | `ecom-flows` |
| Deliverability issues during campaigns | `fix-deliverability` |
| Newsletter content creation | `write-newsletter-content` |
| Overall email program strategy | `strategy-email-program` |
