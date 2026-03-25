# Email Marketing Mastery v1.0.0 -- Routing & Operations

## Plugin Overview

Complete email marketing knowledge engine for ecommerce (DTC/Shopify/Klaviyo) and creator/newsletter businesses. Built from 6 extraction files covering expert-level training across 6 courses. Provides end-to-end guidance from program strategy through flow architecture, list growth, campaign planning, email copywriting, subject lines, launch sequences, welcome sequences, newsletter content, deliverability, segmentation, and newsletter monetization.

---

## Ambiguous Request Decision Tree

When a user's request could match multiple skills, use this decision tree:

```
Is the user asking about OVERALL EMAIL STRATEGY or AUDITING?
  YES -> email-strategy
  NO -> Continue

Is the user asking about AUTOMATED FLOWS (ecom)?
  YES -> ecom-flows
  NO -> Continue

Is the user asking about CAMPAIGNS, CALENDAR, or BFCM?
  YES -> plan-email-campaigns
  NO -> Continue

Is the user asking about GROWING their list or POP-UPS?
  YES -> list-growth-forms
  NO -> Continue

Is the user asking about a LAUNCH SEQUENCE?
  YES -> write-launch-sequence
  NO -> Continue

Is the user asking about a WELCOME SEQUENCE?
  YES -> Ecom? -> ecom-flows
       -> Creator/service? -> write-welcome-sequence
  NO -> Continue

Is the user asking about WRITING EMAIL COPY or BODY CONTENT?
  YES -> write-email-copy
  NO -> Continue

Is the user asking about SUBJECT LINES or PREVIEW TEXT?
  YES -> write-subject-lines
  NO -> Continue

Is the user asking about DELIVERABILITY or SPAM issues?
  YES -> fix-deliverability
  NO -> Continue

Is the user asking about SEGMENTATION or LIST MANAGEMENT?
  YES -> segmentation-list-health
  NO -> Continue

Is the user asking about NEWSLETTER CONTENT or WRITING?
  YES -> write-newsletter-content
  NO -> Continue

Is the user asking about NEWSLETTER MONETIZATION or SPONSORSHIPS?
  YES -> monetize-newsletter
  NO -> Ask clarifying questions
```

---

## Skill Routing Table (All 12 Skills)

### Layer 1: STRATEGY
| Skill | Display Name | Use When |
|---|---|---|
| `email-strategy` | Email Program Strategy | Revenue targets, KPIs, benchmarks, campaign calendar, frequency rules, audit, team workflow, ecom vs creator strategy |

### Layer 2: LIST GROWTH
| Skill | Display Name | Use When |
|---|---|---|
| `list-growth-forms` | Grow Email List | Pop-up forms, offer types, behavior settings, paid acquisition funnels, newsletter growth, organic growth, recommendation networks |

### Layer 3: FLOWS (Automated)
| Skill | Display Name | Use When |
|---|---|---|
| `ecom-flows` | Build Ecommerce Flows | Welcome, abandon checkout/cart/browse/site, post-purchase, winback, upsell, sunset, VIP, back-in-stock, replenishment, date-triggered, holiday flows |
| `write-welcome-sequence` | Write Welcome Sequences | Creator/service/info-product welcome sequences, lead magnet delivery, story-based selling (NOT ecom welcome) |

### Layer 4: CAMPAIGNS (Manual)
| Skill | Display Name | Use When |
|---|---|---|
| `plan-email-campaigns` | Plan Email Campaigns | Campaign types, calendar, booster/double-down, BFCM playbook, send frequency, segment selection |
| `write-launch-sequence` | Write Launch Sequences | Product/course launch emails, cart open/close, objection busters, pre-launch seeding, affiliate launches |

### Layer 5: CONTENT & COPY
| Skill | Display Name | Use When |
|---|---|---|
| `write-email-copy` | Write Email Copy | AIDA, PAS, table method, angle layering, Life Force Eight, speed writing, UPPER framework |
| `write-subject-lines` | Write Subject Lines | Curiosity gaps, double-whammy, self-interest vs curiosity, preview text, A/B testing methodology |
| `write-newsletter-content` | Write Newsletter Content | IV content framework, newsletter-as-meal, habit-forming sections, writing craft, content operations |

### Layer 6: OPTIMIZATION
| Skill | Display Name | Use When |
|---|---|---|
| `segmentation-list-health` | Segment & Manage List | Engaged/unengaged/VIP segments, list cleanup, iOS 15 adaptation, predictive analytics, churn prevention |
| `fix-deliverability` | Fix Deliverability | DMARC/DKIM/SPF, GlockApps, Warmup Inbox, IP warm-up, sender reputation repair, ESP migration |

### Layer 7: MONETIZATION
| Skill | Display Name | Use When |
|---|---|---|
| `monetize-newsletter` | Monetize Newsletter | Sponsorships, subscriber economics, flywheels, local newsletters, B2B monetization |

---

## Cross-Reference Map with Trigger Conditions

| Source Skill | References | Trigger Condition |
|---|---|---|
| `email-strategy` | `ecom-flows` | User needs specific flow architecture |
| `email-strategy` | `segmentation-list-health` | User needs segment definitions for targeting |
| `email-strategy` | `fix-deliverability` | Open rates suggest deliverability problems |
| `list-growth-forms` | `ecom-flows` | Form-to-flow connection setup |
| `list-growth-forms` | `monetize-newsletter` | Newsletter growth tied to monetization strategy |
| `ecom-flows` | `write-email-copy` | User needs body copy for flow emails |
| `ecom-flows` | `segmentation-list-health` | Flow filters reference segment definitions |
| `ecom-flows` | `list-growth-forms` | Welcome flow connected to pop-up forms |
| `plan-email-campaigns` | `write-subject-lines` | Every campaign needs subject line strategy |
| `plan-email-campaigns` | `segmentation-list-health` | Campaign targeting uses segments |
| `plan-email-campaigns` | `ecom-flows` | BFCM flows complement BFCM campaigns |
| `write-launch-sequence` | `write-email-copy` | Launch emails need copy frameworks |
| `write-launch-sequence` | `write-subject-lines` | Launch emails need subject line craft |
| `write-email-copy` | `write-subject-lines` | Always -- subject line + body work together |
| `write-newsletter-content` | `monetize-newsletter` | Content strategy tied to monetization |
| `segmentation-list-health` | `fix-deliverability` | List health issues may indicate deliverability problems |
| `segmentation-list-health` | `ecom-flows` | Sunset flow triggered by unengaged segment |
| `fix-deliverability` | `segmentation-list-health` | Warm-up requires tight segment targeting |

---

## Slash Command Table

| Command | Description | Skills Activated |
|---|---|---|
| `/audit-email` | Comprehensive audit of an existing email program -- flows, campaigns, segmentation, deliverability, KPIs. Outputs scored report with prioritized actions | email-strategy, segmentation-list-health, fix-deliverability |
| `/build-flow` | Design a specific automated flow with triggers, filters, timing, content briefs, and conditional splits. Outputs complete flow blueprint | ecom-flows |
| `/plan-campaign` | Plan a campaign or series (sale, holiday, BFCM, content) with calendar, segments, booster strategy | plan-email-campaigns, write-subject-lines |
| `/write-email` | Write a specific email with subject line, preview text, and full copy | write-email-copy, write-subject-lines |
| `/write-launch` | Plan and write a complete launch sequence for a product, course, or promotion | write-launch-sequence, write-email-copy, write-subject-lines |
| `/write-welcome` | Design and write a complete welcome sequence tailored to business type (ecom or creator) | write-welcome-sequence OR ecom-flows |
| `/grow-list` | Design a list growth strategy including pop-up optimization, paid acquisition funnels, and organic growth | list-growth-forms, segmentation-list-health |
| `/fix-deliverability` | Diagnose and create a recovery plan for deliverability issues | fix-deliverability, segmentation-list-health |

---

## Cross-Plugin Boundaries

| Topic | This Plugin Handles | Delegate To |
|---|---|---|
| Cold email outreach | Nothing | `cold-outbound-mastery` |
| Landing page CRO | Email drives to page | `cro-copywriting-mastery` (page optimization) |
| Ad copy for list growth | Funnel concept only | `paid-ads-mastery` (ad creative) |
| Sales calls from email leads | Nothing | `sales-negotiation-mastery` |
| Social media content | Nothing | Out of scope |

---

## Instructor Source Map

| Instructor | Primary Skills |
|---|---|
| Chase Dimond (E01) | write-email-copy, ecom-flows |
| Boyan / Ecom Email School (E02) | ecom-flows, plan-email-campaigns, fix-deliverability, email-strategy |
| MuteSix team (E03) | ecom-flows, segmentation-list-health, fix-deliverability, list-growth-forms |
| Laura Belgray (E04) | write-launch-sequence, write-welcome-sequence |
| Matt McGarry / Sam Bennett (E05) | write-newsletter-content, list-growth-forms, monetize-newsletter |
| Daniel Throssell / Emails That Crush (E06) | write-email-copy, write-subject-lines, write-newsletter-content |

---

## Implementation Notes

- **Decision Tree First:** Use routing tables above to determine which skill(s) to invoke.
- **Cross-Reference When Needed:** Acknowledge when multiple skills contribute.
- **SKILL.md First, Then References:** Start with SKILL.md for high-level guidance, then reference files for deep specifics.
- **Ask Clarifying Questions:** If business type is unclear (ecom vs creator vs newsletter), ask before routing.
- **Instructor Disagreements:** When instructors disagree, present both positions and the resolution. Never silently pick one side.
- **Business Model Context:** If the user has provided their business type, use that to filter advice (ecom flows are irrelevant for newsletter operators, launch sequences are irrelevant for DTC brands).
