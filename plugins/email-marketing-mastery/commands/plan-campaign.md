---
name: Plan Campaign
description: Plan a specific campaign or campaign series (sale, holiday, BFCM, content, product launch, review) with calendar, segments, booster strategy, and subject line options. Activates plan-email-campaigns and write-subject-lines.
---

# Plan Campaign Wizard

## Step 1: Gather Essential Information

Ask the user these questions before proceeding. Do not skip any.

### Required Inputs
1. **Campaign type:** Sales, announcement, holiday, content, product launch, review, or BFCM?
2. **Business type:** Ecommerce/DTC, creator/service, newsletter, or info product?
3. **Product/offer:** What are you promoting? Price point? Discount level?
4. **List size:** How many subscribers? What is your engaged segment size?
5. **Current send frequency:** How many campaigns per week are you currently sending?
6. **Timeline:** When does this campaign need to go out? How many days does the sale/event run?
7. **ESP:** Klaviyo, ConvertKit, Active Campaign, or other?
8. **Past performance:** What are your typical open rates and click rates?

### Optional Inputs (Ask If Relevant)
- Do you have a specific segment in mind or should we determine targeting?
- Is this a standalone campaign or part of a series?
- Do you want to use a booster/double-down strategy?
- Is this during BFCM or another peak period?

---

## Step 2: Campaign Type Selection

Based on user input, load the appropriate campaign framework.

**Load skill:** `plan-email-campaigns` for campaign type details.

| User Intent | Campaign Type | Key Characteristics |
|-------------|---------------|---------------------|
| Discount/sale/promo | Sales Campaign | Banner-first, offer clarity, 3-second rule |
| New product or collection | Announcement Campaign | Priming > Selling, exclusivity language |
| Seasonal/holiday event | Holiday Campaign | Invention vs. convention, flash sale testing |
| Education/blog/content | Content Campaign | Value-first, drive to on-site content |
| Social proof/reviews | Review Campaign | Customer voices, objection-specific selection |
| New product to existing customers | Product Launch | VIP early access, scarcity language |
| Black Friday / Cyber Monday | BFCM Playbook | Escalating discounts, purchaser exclusion |

---

## Step 3: Campaign Calendar

### Single Campaign Output

```
CAMPAIGN BRIEF

Campaign Name: [name]
Type: [sales / announcement / holiday / content / product launch / review]
Send Date(s): [specific dates]
Send Time: [time with timezone]

Target Segment: [engaged 90-day / VIP / specific microlist]
Exclusion Segment: [recent purchasers / opted-out / etc.]

Offer: [discount / freebie / content / announcement]
Banner Copy: [7-10 words max]
Primary CTA: [Shop Now / Learn More / Read More]

Subject Line Options:
  A: [direct/specific approach]
  B: [curiosity/emotional approach]
Preview Text Options:
  A: [supporting the subject line]
  B: [contrasting angle]

Below-Fold Strategy: [product recs / testimonials / founder message / bestsellers]

Booster Planned: [Yes/No]
  If Yes:
    Booster Time: [6+ hours after original]
    Booster Subject Line: [different style from original]
    Exclude: [opened original campaign]
```

### Campaign Series Output (Multi-Day)

For multi-day campaigns (sales events, BFCM), generate a day-by-day calendar:

```
CAMPAIGN SERIES CALENDAR

Day 0: Prime email (no CTA, awareness only)
Day 1: Launch email AM + Booster PM
Day 2: [Type] email AM + Booster PM
Day 3: [Type] email AM + Booster PM
Day 4: Last chance AM + Final push PM
```

**Load skill:** `write-subject-lines` for subject line generation and A/B testing methodology.

---

## Step 4: Segment Strategy

### Segment Selection Decision Tree

```
Is this a general promotion?
  YES -> Use core engaged segment (180-day OR logic)
  NO -> Continue

Is this for VIPs only?
  YES -> Use VIP segment (3+ orders OR 5x AOV)
  NO -> Continue

Is this a winback/re-engagement?
  YES -> Use 90-120 day no-purchase segment
  NO -> Continue

Is this a microlist campaign?
  YES -> Use hyper-filtered segment (geography, purchase history, etc.)
  NO -> Use core engaged segment
```

### Exclusion Segments (Always Apply)
- Recent purchasers (7-14 day window) for sales campaigns
- Active in relevant flow (avoid flow/campaign collision)
- For BFCM: exclude purchasers from higher-tier discount sends

---

## Step 5: Booster / Double-Down Decision

### When to Recommend Booster
- Campaign is a promotional/sales type
- List size is 5,000+
- Original expected open rate is 25%+
- It has been 6+ weeks since last booster was used

### When NOT to Recommend Booster
- Content/educational campaign (low urgency)
- List size under 5,000 (insufficient volume for meaningful impact)
- Currently in a booster cycle (max 5 consecutive days)
- Open rates are trending below 15%

### Booster Configuration
- Time gap: 6-30 hours after original
- Subject line: opposite style from original
- "Determine recipients at send time" MUST be enabled
- Exclude: segment who opened original campaign

---

## Step 6: Deliverables Summary

Generate a complete campaign brief document including:

1. **Campaign overview:** Type, dates, offer
2. **Segment targeting:** Include and exclude segments
3. **Email structure:** Banner direction, above/below fold strategy
4. **Subject line options:** 2-4 variants with A/B test recommendation
5. **Booster plan:** If applicable, with timing and subject line variant
6. **Calendar view:** Day-by-day breakdown for multi-day campaigns
7. **Success metrics:** Target open rate, click rate, revenue benchmark
8. **Post-campaign:** When to analyze, what to optimize

---

## Next Steps

| Need | Command / Skill |
|------|----------------|
| Write the actual email copy | `/write-email` command or `write-email-copy` skill |
| Write subject lines with A/B variants | `write-subject-lines` skill |
| Build automated flows to support campaign | `/build-flow` command or `ecom-flows` skill |
| Full BFCM multi-week planning | `plan-email-campaigns` skill > ref-campaign-calendar-bfcm.md |
| Launch sequence for info product | `/write-launch` command |
| Diagnose deliverability before sending | `/fix-deliverability` command |
