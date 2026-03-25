---
name: Email Program Strategy
description: >
  MANDATORY TRIGGERS: email strategy, email marketing strategy, revenue attribution,
  email channel benchmarks, email vs other channels, campaign calendar, send frequency,
  email frequency rules, ecom email strategy, creator email strategy, email program audit,
  email implementation roadmap, email KPIs, email reporting, team workflow, email metrics,
  open rate benchmarks, click rate benchmarks, email revenue split, flow vs campaign split.
  FOR: Building an email marketing strategy from scratch -- revenue targets, channel
  benchmarks, implementation roadmap, audit frameworks, team workflow, campaign calendars,
  frequency scaling rules, metric interrelations, and reporting cadence. Covers both
  ecommerce (DTC/Shopify/Klaviyo) and creator/newsletter business models.
  Do NOT use for: specific flow architecture (use ecom-flows), specific campaign copywriting
  (use write-email-copy), deliverability diagnosis (use fix-deliverability), segmentation
  rules (use segmentation-list-health), pop-up forms (use list-growth-forms).
---

# Email Program Strategy

## Quick Navigation
- **Revenue benchmarks & attribution** -> ref-email-program-benchmarks.md
- **Implementation roadmap & calendar** -> ref-email-program-roadmap.md
- **Ecom vs creator strategy differences** -> See business model section below
- **KPIs & reporting** -> ref-email-program-benchmarks.md

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| What % of revenue should come from email? Flow vs campaign split? | ref-email-program-benchmarks.md |
| What KPIs should I track? How do metrics relate to each other? | ref-email-program-benchmarks.md |
| Where do I start? What order do I build things in? | ref-email-program-roadmap.md |
| How many campaigns per week? When should I send? | ref-email-program-roadmap.md |
| How do I plan a campaign calendar? Team workflow? | ref-email-program-roadmap.md |

---

## Cross-References

| Topic | Primary Skill | Go To |
|---|---|---|
| Building specific automated flows | ecom-flows | `skills/ecom-flows/SKILL.md` |
| Pop-up forms and list capture | list-growth-forms | `skills/list-growth-forms/SKILL.md` |
| Segment definitions and list cleanup | segmentation-list-health | `skills/segmentation-list-health/SKILL.md` |
| Email copy frameworks (AIDA, PAS) | write-email-copy | `skills/write-email-copy/SKILL.md` |
| Subject line craft and A/B testing | write-subject-lines | `skills/write-subject-lines/SKILL.md` |
| Deliverability repair | fix-deliverability | `skills/fix-deliverability/SKILL.md` |
| Newsletter growth and monetization | monetize-newsletter | `skills/monetize-newsletter/SKILL.md` |

---

## INSTRUCTOR DISAGREEMENT NOTICES

### Disagreement 1: Email Volume Philosophy

| Position | Advocate | Core Argument |
|---|---|---|
| **Volume drives revenue** | Throssell (E06), McGarry (E05) | Daily emailers build stronger relationships; media companies prove more emails = more revenue. Double frequency = quadruple revenue for ad-supported newsletters. |
| **Quality over quantity** | Boyan (E02) | Oversending leads to high churn, spam rates, and destroyed sender reputation. "The more I send the more I make" is a dangerous myth. Only send when you have something worth sending. |

**Resolution:** Both are correct for different business models. Newsletter/media businesses benefit from high frequency (daily or near-daily). Ecommerce brands should start conservative (1-2/week) and scale based on engagement metrics. The guardrail: maintain 20%+ open rates. If open rates drop below 20%, reduce frequency or tighten segments before adding more sends.

### Disagreement 2: Aesthetic vs Plain Text Emails

| Position | Advocate | Core Argument |
|---|---|---|
| **Plain text converts better** | MuteSix (E03), Boyan (E02) | Plain text bypasses spam filters, has higher deliverability, feels personal. "Highest conversion rates from plain text emails." Multi-seven-figure brands with terrible-looking emails convert well. |
| **Designed emails are essential** | E03 (also) | Designed emails convey offers immediately via banner. Visual products (fashion, jewelry) need imagery. Professional brands need branded emails. |

**Resolution:** Use 80/20 or 90/10 designed-to-plain ratio for ecommerce. Use plain text for founder letters, thank you emails, repeat buyer flows, and as pattern breakers during heavy promotional periods. Creators should lean toward plain text as default. Always test.

---

## Business Model Decision Tree

```
What type of email business are you building?

ECOMMERCE (DTC / Shopify / Klaviyo):
  -> Revenue target: 20-50% of total revenue from email
  -> Split: roughly even between flows and campaigns
  -> Priority order: deliverability > flows > campaigns > segmentation
  -> Frequency: 4-12 emails/month, scale based on engagement
  -> Key metric: revenue per recipient

CREATOR / INFO PRODUCT / SERVICE:
  -> Revenue target: direct product sales + sponsorships + affiliate
  -> Priority: welcome sequence > regular content > launches > monetization
  -> Frequency: 1-7x per week depending on audience tolerance
  -> Key metric: reply rate, trust signals, launch revenue

NEWSLETTER / MEDIA:
  -> Revenue target: CPA < LTV = self-funding growth
  -> Priority: content quality > growth > monetization flywheel
  -> Frequency: daily or near-daily
  -> Key metric: open rate (60%+ for top performers), revenue per employee
```

---

## Core Philosophy (Synthesized Across All Instructors)

### The Seven Rules of Ecom Email Copy (E02 -- Boyan)
1. Keep it simple -- simple sticks and wins
2. Only a small portion reads past the banner
3. Focus on communicating the offer
4. Sell the click, not the product
5. Understand customer journey stage
6. Subject lines above content -- easier to double open rate than CTR
7. Turnaround time above all -- speed over perfection

### The Trust-First Approach (E05 -- Jay Clouse)
- Prioritize maximizing trust over maximizing attention
- Inverse relationship: easier attention = less valuable attention
- Personal emails convert higher than branded emails
- Email sits at the sweet spot: moderate difficulty, high value

### Owned vs Rented Audience (E05 -- McGarry + Clouse)
- Social media = rented land. Email = owned distribution
- Email is the one open-source internet identifier
- Strategy: use discovery platforms to build relationship platforms
- Pick ONE discovery platform + ONE relationship platform to start

---

## Metric Interrelations Framework (E02)

Understanding what drives each metric prevents misdiagnosis:

- **Open rate** is driven by: subject line, preview text, sender name, segmentation, send time, deliverability
- **Click rate** is driven by: offer quality, messaging clarity (3-second rule)
- **Conversion rate** is driven by: click intent + landing page quality
- **Deliverability** is driven by: sender reputation (volume + spam rates + bounce rates + content weight)
- **Spam/churn rate** is driven by: send frequency and content relevance to segment

**Critical distinction:** There are two click rate calculations. Use clicks/opens (not clicks/sends) for optimization decisions.

---

## SMS Companion Channel (Overview)

SMS is referenced across E02 and E03 as a companion channel to email:
- Use for transactional messages, flash sales, and time-sensitive promotions
- Never replace email strategy with SMS -- email remains the primary channel
- SMS has higher open rates but lower tolerance for volume
- Best for: abandoned checkout reminders, shipping updates, flash sale alerts
- Detailed SMS strategy is outside this plugin's scope
