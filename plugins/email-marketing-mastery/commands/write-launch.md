---
name: Write Launch Sequence
description: Plan and write a complete launch sequence for a product, course, or promotion. Outputs full sequence with pre-launch, cart-open, mid-cart, and cart-close emails. Activates write-launch-sequence, write-email-copy, and write-subject-lines.
---

# Write Launch Sequence Wizard

## Step 1: Gather Essential Information

Ask the user these questions before proceeding. Do not skip any.

### Required Inputs
1. **What are you launching?** Product, course, service, membership, or affiliate promotion?
2. **Price point:** What does it cost? Is there a payment plan?
3. **Launch window:** How many days is the cart open? What are the exact open/close dates and times?
4. **List size:** How many subscribers?
5. **Pre-launch runway:** How far in advance can we start seeding? (Ideal: 1-4 weeks)
6. **Your offer/bonuses:** What bonuses are included? Any fast-action bonus?
7. **Your relationship to the product:** Is this YOUR product, or are you an affiliate?
8. **Brand voice:** Personality-driven? Professional? Casual? Humorous?

### Optional Inputs (Ask If Relevant)
- Do you have a webinar or free content as part of the funnel?
- Have you launched this before? What worked / did not work?
- Are competitors launching the same product? (Affiliate scenario)
- Do you want soft opt-out functionality?
- What objections do you expect from your audience?

---

## Step 2: Determine Launch Scale

Based on inputs, recommend the appropriate launch intensity.

**Load skill:** `write-launch-sequence` for the Lazy Launch framework.

| List Size | Launch Type | Pre-Launch | Cart-Open | Cart-Close Day | Total Emails |
|-----------|------------|------------|-----------|----------------|-------------|
| Under 2,000 | Lean Launch | 2-3 emails (1 week) | 3-4 emails | 1-2 emails | 6-9 |
| 2,000-10,000 | Standard Launch | 4-6 emails (2 weeks) | 5-7 emails | 2-4 emails | 11-17 |
| 10,000+ | All-In Launch | 6-10 emails (3-4 weeks) | 8-10 emails | 3-6 emails | 17-26 |

---

## Step 3: Build the Launch Sequence

### Phase 1: Pre-Launch / Seeding Emails

Select from these templates based on launch type and product:

| Email Type | Use When | Key Element |
|------------|----------|-------------|
| Sneak Peek | Always (required) | Behind-the-scenes, interest list CTA |
| Enviable Lifestyle | Product delivers aspirational results | Paint picture of transformation |
| Education / Catch the Wave | Market trend supports purchase | Stats, timeliness, FOMO |
| Personal Journey | You have a before/after story | Vulnerability, relatability |
| Contrast | You can contrast struggle vs. success | Us-vs-them, exclusivity |
| Webinar Promo | Launching with a live event | Event urgency, limited replay |

**Load skill:** `write-email-copy` for copywriting frameworks to apply within each email.

### Phase 2: Cart Pre-Open Email
- Required for all launches with a fast-action bonus
- Full bonus description (only time to detail everything)
- "Keep an eye on your inbox. I'll be here at [hour]."

### Phase 3: Cart-Open Emails
- **Cart Open Announcement** (required): Link near top, benefits, bonuses, fast-action deadline
- **Fast Action Bonus Reminder** (if applicable): Countdown, social proof, screenshots

### Phase 4: Mid-Cart Emails

Select objection busters based on anticipated audience concerns:

| Objection | Email Type | When to Include |
|-----------|-----------|-----------------|
| "It won't work for me" | Self-deprecation story | Always |
| "This is for suckers" | Skeptic validation | High-price products, saturated markets |
| "Can't afford it" | Investment framing | Products over $200 |
| "I'm not ready" | "No one's ever ready" | Courses, programs |
| "I've tried everything" | "This time is different" | Competitive markets |

Also include:
- Future Pacing email (paint the "after" picture)
- FAQ email (or sprinkle FAQs through PS sections)
- Testimonial / Social Proof email (at least 1)
- Catch-Up / "What Even Is This?" email

### Phase 5: Cart-Close Emails
- **Closing Tomorrow** (required): Story + urgency
- **Closing Today - Morning** (required): Last day + bonus details
- **One More Hour** (required): Schedule 70 minutes before close. Short, empowering, urgent.
- **Additional final-day emails** (optional): Aspirational close, last-call with deadline in subject line

**Load skill:** `write-subject-lines` for launch-specific subject line formulas.

---

## Step 4: Configure Launch Mechanics

### Soft Opt-Out
```
Recommend if: Launch is 5+ days or 10+ emails
Placement: Top of every email once promotion frequency increases
Language: "Not interested in [product]? Click here to skip these emails."
Mechanics: Tag-based suppression in ESP
```

### Fast-Action Bonus
```
Type: [Live Q&A / Limited spots / Time-limited / Digital bonus]
Deadline: [X hours after cart open]
Reminders: In every email during the bonus window
```

### Pre-Launch Segmentation (Optional)
```
Send "5 Kinds of People" email 1-2 weeks before launch:
1. Not interested (suppress)
2. Looking to [achieve result] (target)
3. Already curious (highest intent)
4. Already bought / not buying but like emails (no special treatment)
5. Fun wildcard option (personality moment)
```

---

## Step 5: Generate the Sequence

Output a complete email sequence as a numbered list:

```
LAUNCH SEQUENCE: [Product Name]
Launch Window: [Date range]
Total Emails: [count]

PRE-LAUNCH (Weeks 1-2)
  Email 1 - Day -14: Sneak Peek
    Subject A: [option]
    Subject B: [option]
    Preview: [text]
    Purpose: [brief]
    Key elements: [checklist]

  Email 2 - Day -10: [Type]
    ...

CART PRE-OPEN
  Email X - Day -1: Ready to Pounce
    ...

CART OPEN (Days 1-2)
  Email X - Day 1 AM: Cart Open!
    ...
  Email X - Day 1 PM: Fast Action Reminder
    ...

MID-CART (Days 2-5)
  Email X - Day 2: Objection Buster #1
    ...
  Email X - Day 3: [Type]
    ...

CART CLOSE (Final Day)
  Email X - Day 7 AM: Last Day
    ...
  Email X - Day 7 PM (-70 min): Final Hour
    ...
```

---

## Step 6: Post-Launch Planning

### Immediate (Day After Close)
- Send thank-you email to buyers
- Review sales data: which emails drove the most conversions?
- Note which objection busters generated the most replies

### One Week Later
- Analyze full sequence performance
- Identify top-performing emails for future launches
- Save best performers as templates

### For Next Launch
- Add top performers to your launch template library
- Address objections you heard but did not cover
- Adjust volume based on unsubscribe feedback

---

## Next Steps

| Need | Command / Skill |
|------|----------------|
| Write the individual email body copy | `write-email-copy` skill |
| Generate subject line options | `write-subject-lines` skill |
| Set up a welcome sequence post-launch | `/write-welcome` command |
| Plan ongoing campaigns after the launch | `/plan-campaign` command |
| Fix deliverability before the launch | `/fix-deliverability` command |
