---
name: Write Welcome Sequence
description: Design and write a complete welcome sequence tailored to business type. Routes to write-welcome-sequence for creator/service businesses or ecom-flows for ecommerce. Outputs full welcome sequence with email copy, timing, and conditional logic.
---

# Write Welcome Sequence Wizard

## Step 1: Determine Business Type

Ask the user this question FIRST -- it determines which skill to load.

**"What type of business is this welcome sequence for?"**
- A) **Ecommerce / DTC / Shopify** -- product-based, discount-driven, Klaviyo flows
- B) **Creator / Service / Info Product** -- personality-driven, relationship-focused, content + offers
- C) **Newsletter** -- content-first, subscriber onboarding, monetization via sponsorships or products
- D) **Not sure** -- ask clarifying questions about their business model

### Routing Logic
```
Ecommerce / DTC -> Load skill: ecom-flows
  Output: Klaviyo flow with triggers, filters, discount stacking, product blocks

Creator / Service / Info Product -> Load skill: write-welcome-sequence
  Output: Personality-driven sequence with split-path architecture

Newsletter -> Load skill: write-welcome-sequence (newsletter variant)
  Output: Content-focused onboarding with engagement hooks
```

**This command focuses on the Creator / Service / Info Product path.** For ecommerce, redirect the user to `/build-flow` with the welcome series type.

---

## Step 2: Gather Essential Information

### Required Inputs
1. **What lead magnet(s) do you have?** PDF, template, video, quiz, or newsletter-only signup?
2. **How many opt-in paths exist?** Single lead magnet, multiple lead magnets, or newsletter + lead magnets?
3. **What do you sell?** Courses, services, coaching, digital products, physical products, or a mix?
4. **Brand voice:** Funny/casual, professional, warm/personal, edgy/contrarian?
5. **ESP:** ConvertKit, Active Campaign, Klaviyo, Flodesk, or other?
6. **Current list size:** New list (0-500), growing (500-5,000), or established (5,000+)?
7. **Current email frequency:** How often do you email your list? (Or: this is new)

### Optional Inputs (Ask If Relevant)
- Do you have an active promotion or launch happening?
- Do you want a yes/no opt-in checkbox for newsletter emails?
- Do you have testimonials or case studies to feature?
- Do you plan to use a tripwire/upsell page after opt-in?

---

## Step 3: Design the Architecture

### Single Lead Magnet Path (Most Common)

```
WELCOME SEQUENCE ARCHITECTURE

Opt-In: [Lead Magnet Name]
  |
  Email 1 (Day 0): Deliver lead magnet + orientation
  |
  Email 2 (Day 1): Resell the lead magnet
  |
  Email 3 (Day 3): Get to know you / fun facts
  |
  Email 4 (Day 5): "I sell things" transparency
  |
  ---- START BROADCASTS (merge with regular emails) ----
  |
  Email 5 (Day 7): Story + soft sell
  Email 6 (Day 10): Testimonial + product pitch
  Email 7 (Day 14): Pure value / teaching
  Email 8 (Day 18): Mystery / curiosity
  Email 9 (Day 23): Myth-busting
  Email 10 (Day 30): Survey / bribe
```

### Multi-Path Architecture (Multiple Lead Magnets)

```
[Lead Magnet A]     [Lead Magnet B]     [Newsletter Only]
      |                   |                    |
  Deliver LM-A        Deliver LM-B        Welcome email
  Resell LM-A         Resell LM-B        Best content link
      \                   |                   /
       ------> MERGE AT EMAIL 3 <-----------
                     |
            Get to know you
            "I sell things"
            Ongoing sequence...
```

### With Second Chance Email

```
[Opt-In with Yes/No Checkbox]
      |              |
   [Yes]          [No]
      |              |
  Email 1         Email 1
  (Deliver)       (Deliver)
      |              |
      |         Second Chance Email
      |         "Is this it for us?"
      |              |
      |         [Clicks Yes] -> Merge into main sequence
      |         [No click] -> End
      |
  Email 2 (Resell)
  Email 3+ (Continue)
```

---

## Step 4: Generate the Welcome Sequence

**Load skill:** `write-welcome-sequence` for email-by-email templates.
**Load skill:** `write-email-copy` for copywriting frameworks.
**Load skill:** `write-subject-lines` for welcome sequence subject line formulas.

Output each email in this format:

```
WELCOME SEQUENCE: [Brand/Business Name]

EMAIL 1: Lead Magnet Delivery + Orientation
  Timing: Immediate
  Subject: "[Lead Magnet Name] is ready for you"
  Preview: "[Supporting text]"

  Structure:
  - Download link (top of email, no scrolling needed)
  - What to expect from future emails
  - "Since you signed up for [X], I'm guessing you're into [Y]"
  - CTA 1: Follow on Instagram
  - CTA 2: Whitelist / primary-list request
  - CTA 3: Reply and tell me [question]
  - Link to best content

  Conditional content:
  - [If lead magnet A]: "[Text for path A]"
  - [If newsletter only]: "[Text for newsletter path]"

---

EMAIL 2: Resell the Lead Magnet
  Timing: Day 1
  Subject: "[Curiosity + personality option]"
  ...

EMAIL 3: Get to Know You
  Timing: Day 3
  ...

[Continue for all emails in the sequence]
```

---

## Step 5: Configure Mechanics

### Timing Decision
| Business Stage | Cadence Recommendation |
|----------------|----------------------|
| New list, cautious | Conservative: Days 0, 2, 5, 8, then every 3-4 days |
| Established, testing | Moderate: Days 0, 1, 3, 5, then every 2-3 days |
| Confident, personality-driven | Aggressive: Days 0, 1, 2, 3, then overlap with broadcasts |

### Broadcast Integration
- After core sequence (4-8 emails), subscribers start receiving regular broadcasts
- Options: (a) Immediate merge, (b) Overlap period, (c) Wait until sequence completes
- Recommended: Start overlap at Email 4 for engaged audiences

### Conditional Content Setup
- Configure dynamic blocks for different opt-in paths
- Show different product offers to non-purchasers vs. existing customers
- Acknowledge active promotions for subscribers joining mid-launch

### Survey Setup
- 2-question, 90-second survey
- Question 1: Interest segmentation
- Question 2: Product ownership (for offer exclusion)
- Place survey CTA in at least 3 welcome emails for maximum submissions

---

## Step 6: Deliverables Summary

Generate a complete welcome sequence document including:

1. **Architecture diagram:** Visual flow showing paths, merges, and timing
2. **Email-by-email spec:** Subject line, preview text, structure, CTAs, conditional content
3. **Timing schedule:** Day-by-day cadence with broadcast merge point
4. **Mechanics checklist:**
   - [ ] Lead magnet delivery link configured
   - [ ] Tags/segments set up for each opt-in path
   - [ ] Conditional content blocks configured
   - [ ] Survey created and linked
   - [ ] Second chance email set up (if using yes/no checkbox)
   - [ ] Broadcast suppression configured for first 4 emails
   - [ ] Tripwire/upsell page set up (if applicable)
5. **Success metrics:** Target open rates, click rates, reply rates per email position

---

## Next Steps

| Need | Command / Skill |
|------|----------------|
| Write individual email body copy | `write-email-copy` skill |
| Generate subject line variants | `write-subject-lines` skill |
| Build an ecom welcome flow instead | `/build-flow` command or `ecom-flows` skill |
| Set up a launch sequence | `/write-launch` command |
| Grow the list that feeds this sequence | `/grow-list` command or `list-growth-forms` skill |
| Plan ongoing campaigns after welcome | `/plan-campaign` command |
