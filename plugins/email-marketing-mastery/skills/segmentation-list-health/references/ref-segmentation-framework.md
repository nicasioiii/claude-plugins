---
name: Segmentation Framework
description: >
  When to Read: User asks about segment definitions, engaged/unengaged/VIP segments,
  exclusion segments, traffic source segments, microlist strategy, segment split testing,
  or iOS 15 adaptation for engagement tracking.
  Cross-references: ref-list-management.md for cleanup protocols,
  ecom-flows for sunset flow triggered by unengaged segment.
---

# Segmentation Framework

## Core Engaged Segment (E03 -- Baseline for Campaign Sends)

**Definition (OR logic -- any of these):**
- Opened email at least once in last 180 days
- Clicked email at least once in last 180 days
- Placed order at least once in last 180 days
- Active on website in last 90 days (shorter window -- lower signal)
- Profile created in last 90 days (give new subscribers a chance)

"This segment tends to be a general engaged list that you can send on the regular without facing deliverability issues." -- E03

**To tighten:** Shorten windows (90 days, 60 days, 30 days) for hyper-engaged targeting.

---

## Unengaged Segment (E03)

**Definition (AND logic -- all of these):**
- Has NOT opened in last 90 days
- Has NOT clicked in last 90 days
- Has NEVER placed an order
- Has NOT visited site in 30-60 days

This segment feeds the sunset unengaged flow.

---

## Chronic Unengaged Segment (E03)

**Definition:**
- Double the windows: not opened/clicked in last 180 days
- Never visited site
- Never purchased

These are candidates for list removal/cleanup. Keeping them harms deliverability and increases Klaviyo billing costs.

---

## Unengaged Segment for Sunset Flow (E02 -- Boyan)

**Definition (AND logic):**
- Opened 0 emails in last 90 days (sweet spot: 90-120 days; never less than 60)
- Clicked 0 emails in last 90 days
- Received at least 15 emails (adjust based on send frequency)
- NOT already suppressed
- Active on site 0 times in last 45 days (higher-interest metric, shorter window)

---

## VIP Segment (E03)

**Definition (OR logic):**
- Ordered 3+ times
- Total revenue over $X (usually ~5x AOV; if AOV is $50-100, VIP threshold = $500+)

**VIP Treatment:**
- First access to new product launches
- Highest discounts / exclusive offers
- Most engaged subscribers -- keep them happy
- Use for: reviews, refer-a-friend, early access
- Separate VIP flows vs normal customer flows

---

## Exclusion Segments (E03)

### Recent Purchasers
- Exclude people who ordered in last 7-14 days from promotional campaigns
- "You'll get a lot of angry customers if you send them promo after they just bought"
- Especially important during BFCM (prevents cancel-and-reorder-at-discount)

### BFCM-Specific Exclusions
- Anyone who bought during November stops receiving sale emails
- People who convert during Black Month never see bigger Black Week offers
- Create Black Friday opt-out list pre-November (opt-out preferred over opt-in)

---

## Traffic Source Segments (E03)

- Segment by acquisition source: Facebook, Google Ads, organic, referral
- Target differently based on how they found the brand
- Trigger different pop-ups and messaging per traffic source
- Useful for: measuring acquisition channel quality, tailoring welcome content

---

## Microlist Strategy (E02)

For advanced segmentation beyond 3-4 campaigns/week:
- Send targeted messaging to hyper-filtered segments
- Examples: females in specific US state, high-LTV customers, specific geography
- Microlists produce 20%+ conversion rates, 70% open rates
- This is how agencies produce impressive case study metrics

---

## Segment Split Testing (E02)

### Methodology
- Send 2-4 campaigns to new segment
- Compare average revenue per campaign vs old segment
- **Primary metric: total revenue generated** (NOT open rate or click rate -- these will naturally be lower for broader segments)
- Test segments that don't rely on open/click metrics (preparation for iOS 15+)

---

## iOS 15+ Engaged Segment (E02)

### The Problem
iOS 15 Mail Privacy Protection pre-loads email images, falsely inflating open rates for Apple Mail users. Open-rate-based segments become unreliable.

### iOS 15 Adapted Segment (E02)
Replace open-rate conditions with behavioral signals:
- Active on site (any activity)
- Placed order (any time)
- Viewed product (any time)
- Checkout started (any time)

All over all time -- these are real engagement signals not affected by mail privacy.

### Recommendation
Build both traditional and iOS 15 segments. Compare performance. Gradually shift campaign targeting toward behavioral segments.

---

## BFCM Segment Strategy (E02 + E03 Synthesized)

### Segments to Target During BFCM

| Segment | When to Use | Notes |
|---|---|---|
| Highly engaged (90-120 day) | Most BFCM sends | Extend slightly if consistent 25%+ opens |
| BF opt-in list | All BF emails | From pre-BF capture popup |
| Existing customers | Targeted offers | Different messaging than prospects |
| Winback opportunities | BF as re-engagement | "We miss you" + BF deal |
| VIP / high-value repeat | Early access, best offers | First to know, best discount |
| Whole list | Limited use ONLY | Announcement email, BF itself, CM only |

### Three Tactics to Avoid High Unsub/Spam (E02)
1. **BF opt-out list (preferred):** Pre-November email giving choice to opt out. Opt-out > opt-in because non-clickers may still want BF content
2. **Boost campaigns tactically:** Only boost highest-impact campaigns (announcement, BF, CM)
3. **Exclude recent purchasers:** Anyone who bought during November stops receiving sale emails

---

## Facebook Lookalike Sync (E03)

- Sync high-engagement and VIP segments to Facebook for lookalike targeting
- Exclude low-performing segments from Facebook audiences
- Creates feedback loop: email engagement data improves paid acquisition targeting
- High-value email segments make excellent seed audiences for lookalikes
