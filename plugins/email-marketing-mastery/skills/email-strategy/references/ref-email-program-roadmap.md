---
name: Email Program Roadmap & Campaign Calendar
description: >
  When to Read: User asks about implementation priority order, where to start with email,
  campaign calendar planning, send frequency rules, scaling frequency, team workflow,
  optimal send times, or audit checklists.
  Cross-references: ref-email-program-benchmarks.md for target KPIs,
  ecom-flows SKILL.md for flow build order, segmentation-list-health for segment setup.
---

# Email Program Roadmap & Campaign Calendar

## Implementation Priority Order (E02 -- Boyan)

Build email programs in this exact sequence:

1. **Check deliverability** -- before anything else
2. **Revive deliverability if dead** -- use fix-deliverability skill protocols
3. **Build out all flows in recommended order** (highest revenue to lowest):
   - Welcome series (9-15% of email revenue)
   - Abandon checkout (8-12% of email revenue)
   - Abandon cart (if separate from checkout)
   - Browse abandonment (2-5% of email revenue)
   - Site abandonment
   - Post-purchase thank you
   - Customer winback
   - Upsell/cross-sell
   - Sunset unengaged
4. **Monitor metrics** -- establish baselines
5. **Send test campaigns to narrow segment** (start with 15-30 day engaged, NOT 90)
6. **Expand segment** as open rates stay high
7. **Scale up frequency**
8. **Test and repeat cycle**

---

## Campaign Calendar Framework (E02 + E03)

### Frequency Rules

| Send Volume | When Appropriate | Guardrails |
|---|---|---|
| 4/month (1/week) | Starting out, building consistency | Minimum for any brand |
| 8/month (2/week) | Growing brands with 30%+ open rates | Use consistent days (e.g., Sunday + Thursday) |
| 12/month (3/week) | Established brands with strong engagement | Recommended max for non-promo periods |
| 16/month (4/week) | Pushing it -- only with proven segments | Mix campaign types aggressively |
| Daily | Newsletter/media businesses only | Requires dedicated content system |

### Scaling Logic (E02)
- Consistent 30%+ open rates = increase weekly volume by one
- OR broaden targeting segment (90-day engaged to 120-day, 150-day, etc.)
- Keep open rates above 20% consistently -- 10% range hurts sender reputation
- Revenue has diminishing returns: 1 email/week = $2K/email; 2 emails/week = $1,500/email but $3K total
- As long as total revenue increases AND open rates stay above 20%, add campaigns

### Beyond 3-4 Campaigns/Week: Microlists (E02)
- Send targeted messaging to hyper-filtered segments
- Examples: females in specific US state, high-LTV customers, specific geography
- Microlists produce 20%+ conversion rates, 70% opens
- This is how agencies get impressive case study screenshots

### Uniform Planning Strategy (E02)
- Use predictable, consistent sending days to train customers to open
- If sending 2x/week: same 2 weekdays every week (e.g., Sunday + Thursday)
- Stick to the schedule once optimal days are found
- Thursday is cross-the-board best performing day for purchase conversions (E02)

---

## Finding Optimal Send Time

### E02 Approach: Data-Driven
- Use Klaviyo's open-by-hour curve on sent campaigns
- Identify secondary peaks (e.g., fitness brand peaks at 7 AM)
- Test sending at peak times in subsequent campaigns
- Use "thesis-based testing" for days: form hypothesis about customer behavior

### E03 Approach: Contrarian Timing
- "Send times aren't as important as they used to be"
- When studies publish "best time to send," everyone sends then -- making it irrelevant
- **For ecommerce: send when everybody else is NOT sending**
- Recommended: weekends and evenings/nighttime
- Theory: 70%+ of email opens are on mobile; people browse phones in evening while watching TV

### Resolution
Test both approaches. Start with E02's data-driven method to find your audience's engagement peaks. Then test E03's contrarian approach (evenings, weekends) against those peaks. Let the data decide for your specific audience.

---

## Campaign Type Mix (E02 + E03)

### Six Campaign Types (E02 -- Boyan)

| Type | Frequency | Purpose |
|---|---|---|
| **Sales** | Sparingly -- highest revenue per send | Banner conveys offer in 3 seconds. If offer needs >7-10 words, it's too complex |
| **Announcement** | As needed | Prime list for upcoming event OR sell something launched |
| **Holiday** | Calendar-driven | Invention holidays (made up) vs. Convention holidays (traditional) |
| **Content** | Most frequently sent | Drive sales through education OR drive traffic for rapport |
| **Product Launch** | As products launch | Exclusivity language + scarcity. Send to engaged/VIP first |
| **Review** | Periodically | Feature customer reviews for social proof and credibility |

### Campaign Type Mix Rules
- Never send only promotional emails -- mix types
- Content campaigns are the most frequently sent (not every day has a sale)
- Use invention holidays to TEST new offers in 48-hour flash sales
- Split one product's 3 benefits into 3 separate emails for better readability and more sends
- Drive traffic to high-performing content, NOT SEO blog articles

---

## BFCM / Holiday Strategy Overview

### Timeline Architecture (E02)
1. **Black Month** (Nov 1 onward): Announcement email + 2x weekly campaigns
2. **Black Week** (Monday before BF): Daily campaigns; launch main offer
3. **Black Friday**: 2 campaigns same day (AM + PM)
4. **Black Friday Weekend**: Daily campaigns
5. **Cyber Monday**: 2 campaigns (AM + PM)
6. **Cyber Monday Extended**: Daily campaigns

### Two-Offer Strategy (E02)
- Black Month offer: evergreen/welcome offer (converts non-price-elastic customers first)
- Black Week offer: the heavy hitter (best-performing offer)
- People who convert during Black Month never see the bigger Black Week offer (excluded)
- Maximizes margin: no extra discount for people who would convert without it

### BFCM Cadence (E03)

| Period | Timing | Discount | Emails/Day |
|---|---|---|---|
| Early Bird / Pre-BF | Monday before BF (or 2 weeks before) | Lowest tier (15%) | 1/day |
| Black Friday | BF day | Higher tier (20%) | 2 emails |
| Extended BF | Sat-Sun after BF | Same as BF | 1/day |
| Cyber Monday | CM day | Highest tier (25-30%) | 2 emails |
| Extended CM | Through end of November | Same or slightly lower | 1/day |

### Critical BFCM Tactics
- Escalating discounts: start lower, escalate through the week
- **Exclude purchasers from subsequent sends** so someone who bought at 15% never sees 20%
- Create BF opt-out list (preferred over opt-in) pre-November
- Use countdown timers (24-hour reset or accurate countdown)
- BFCM-specific popup: "Give us your email, we'll notify you first when deals drop"
- Pop-up messaging must match email messaging -- change popup every time discount changes
- Revenue will spike; open rates WILL decrease deeper into Black Month (expected)
- This strategy is for ONCE a year only; maybe twice max

### Post-BFCM Strategy
- Work backwards from guaranteed Christmas delivery date
- Campaign messaging: "Order by X date to receive by Christmas"
- Do NOT stop emailing after shipping cutoff -- scale back, stay relevant
- Christmas Eve: personalized plain text from founder
- January: "new year, new you" -- especially for wellness/fitness brands

---

## Team Workflow & Timelines (E02)

### Production Pipeline
1. Marketing manager/founder creates task with campaign idea, date, deadline
2. Copywriter writes copy (<30 min per email, <1 day turnaround)
3. Graphic designer designs (20 min to 1 hour, excluding revisions)
4. Upload and schedule (<10 min for skilled person)
5. Leave 2-3 days minimum before send time; ideal: 1 week to 1 month in advance

### Speed Rules
- Speed > perfection
- Past the first two screens, only ~5% of openers see the rest
- Brands doing <$500K-$1M/month should not worry about tiny details
- Give graphics team creative control -- minimal revisions
- Use lossy compression on all JPEGs to keep emails lightweight

### Brief Format for Design Team (E02)
```
Campaign name: [name]
Date & time: [date/time]
Sender name: [name]
Subject line: [subject]
Preview text: [preview]
Content:
  Banner: "[banner copy]"
  CTA: "[button text]"
  Reviews: "[paste reviews]"
  Authority: "As Seen On. [LOGO] [LOGO] [LOGO]"
  CTA: "[button text]"
```

---

## Audit Checklist for Existing Programs

### Quick Audit (15 minutes)
1. What % of revenue comes from email? (target: 20-50%)
2. What is the flow vs campaign revenue split? (target: roughly even)
3. Are all core flows live? (welcome, abandon checkout, post-purchase, winback, sunset)
4. What is the campaign frequency? (minimum 4/month)
5. What is the average open rate on engaged segments? (target: 25%+)
6. Is the unsubscribe rate below 0.4%?
7. Is the spam rate below 0.2%?

### Deep Audit (1-2 hours)
1. All quick audit items above
2. Review each flow: trigger logic, timing, email count, offer strategy
3. Review segmentation: engaged vs unengaged definition, VIP segment
4. Review deliverability: authentication (SPF/DKIM/DMARC), Google Postmaster
5. Review pop-up: offer type, behavior settings, mobile vs desktop
6. Review campaign mix: are all 6 types represented?
7. Review A/B testing: is subject line testing happening on every campaign?
8. Review list hygiene: when was last cleanup? Are sunset flows active?
