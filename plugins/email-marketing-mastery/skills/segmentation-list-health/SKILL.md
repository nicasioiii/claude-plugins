---
name: Segment & Manage List
description: >
  MANDATORY TRIGGERS: segment, segmentation, engaged segment, unengaged segment,
  VIP segment, list cleanup, list hygiene, list health, sunset unengaged, exclusion
  segment, traffic source segment, microlist, iOS 15, predictive analytics, churn
  prevention, LTV upselling, email list management, Klaviyo segments, suppress,
  unsubscribe rate, spam rate, list size, billing optimization, Facebook lookalike,
  engagement tiers, 30-day engaged, 90-day engaged, 180-day engaged.
  FOR: Building and managing email segments -- engaged/unengaged/VIP/exclusion segments,
  list cleanup protocols, traffic source segmentation, predictive analytics for churn,
  iOS 15+ adaptation strategies, microlist strategy, segment split testing, and
  list health monitoring.
  Do NOT use for: deliverability protocols and authentication (use fix-deliverability),
  flow architecture (use ecom-flows), campaign planning (use plan-email-campaigns or
  email-strategy), pop-up forms (use list-growth-forms).
---

# Segment & Manage List

## Quick Navigation
- **Segment definitions (engaged, unengaged, VIP, exclusions)** -> ref-segmentation-framework.md
- **List cleanup protocols and billing** -> ref-list-management.md
- **iOS 15 adaptation** -> ref-segmentation-framework.md
- **Predictive analytics and LTV** -> ref-list-management.md

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| How do I define my engaged segment? Unengaged? VIP? | ref-segmentation-framework.md |
| What segments should I exclude from campaigns? | ref-segmentation-framework.md |
| How do I adapt segments for iOS 15? | ref-segmentation-framework.md |
| What is a microlist? Segment split testing? | ref-segmentation-framework.md |
| When should I clean my list? How does it affect billing? | ref-list-management.md |
| How do I use predictive analytics for churn prevention? | ref-list-management.md |
| What negative segments should I monitor? | ref-list-management.md |

---

## Cross-References

| Topic | Primary Skill | Go To |
|---|---|---|
| Sunset unengaged flow (triggered by segment) | ecom-flows | `skills/ecom-flows/SKILL.md` |
| Deliverability repair (related to list health) | fix-deliverability | `skills/fix-deliverability/SKILL.md` |
| Campaign targeting (uses these segments) | email-strategy | `skills/email-strategy/SKILL.md` |
| Pop-up forms (acquisition source tracking) | list-growth-forms | `skills/list-growth-forms/SKILL.md` |
| BFCM segment strategy | email-strategy | `skills/email-strategy/SKILL.md` |

---

## Core Segment Architecture (E03 + E02 Synthesized)

### The 5 Essential Segments Every Ecom Brand Needs

```
1. ENGAGED (baseline for campaign sends)
   -> OR logic: opened OR clicked OR ordered OR active on site OR new profile

2. UNENGAGED (candidates for sunset flow)
   -> AND logic: NOT opened AND NOT clicked AND NOT ordered AND NOT visited

3. VIP (highest-value customers)
   -> OR logic: 3+ orders OR revenue > 5x AOV

4. EXCLUSION (recent purchasers)
   -> Ordered in last 7-14 days -- exclude from promotional campaigns

5. CHRONIC UNENGAGED (candidates for removal)
   -> Double the unengaged windows: 180-day non-engagement
```

### Why Logic Gates Matter
- **Engaged uses OR:** Any single signal of life keeps them in the engaged pool
- **Unengaged uses AND:** All signals must be dead before declaring unengaged
- This prevents false positives in both directions

---

## Segmentation Impact (E03)

- Klaviyo data: ~50% decrease in unsubscribe rate when using segmentation properly
- Microlists produce 20%+ conversion rates, 70% open rates
- Proper segmentation enables frequency scaling (more campaigns to tighter segments)
- Without segmentation: impossible to maintain deliverability at higher send volumes

---

## Segment Tightening Strategy

Start broad, tighten as needed:

```
Level 1: 180-day engaged (broadest -- default starting point)
Level 2: 120-day engaged (tighter)
Level 3: 90-day engaged (standard for established brands)
Level 4: 60-day engaged (tight -- for high-frequency senders)
Level 5: 30-day engaged (tightest -- for daily senders or deliverability repair)
```

**When to tighten:** Open rates dropping below 20% on current segment
**When to loosen:** Open rates consistently above 30% and you want more revenue reach

---

## CONTRARIAN INSIGHT: Don't Segment Out Buyers from Promotions (E06 -- Throssell)

Do not segment buyers out of sales emails about products they already own. Your emails should be interesting enough that people enjoy them regardless of purchase status. More importantly: by sending buyers sales emails, you re-sell them on actually USING the product they bought (most people never use products they buy). This keeps buyers engaged, reinforces purchase decisions, and maintains list-wide engagement metrics. Only segment out buyers when the discount in a subsequent send is higher than what they paid (to avoid buyer's remorse).
