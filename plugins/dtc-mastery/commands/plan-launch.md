---
name: Plan Launch
description: Generate a platform-specific launch checklist and timeline. Covers DTC/Shopify (12-week), Amazon (honeymoon + Vine), and TikTok Shop (22-step). Activates 11-launch-reviews and cross-references 13-influencer-content for pre-launch content.
---

# Launch Strategy Planner

## Step 1: Gather Essential Information

Ask the user these questions before proceeding. Do not skip any.

### Required Inputs
1. **Platform(s):** Shopify/DTC, Amazon FBA, TikTok Shop, or multi-platform?
2. **Product:** What are you selling? Price point? Product category?
3. **Stage:** Pre-product (ideation), product ready (samples approved), inventory in hand, or already live (relaunch)?
4. **Budget:** Total available launch budget (including inventory, ads, tools)?
5. **Audience:** Do you have an existing email list, social following, or customer base? Sizes?
6. **Timeline:** When do you need to launch? Any hard deadlines (seasonal, event)?
7. **Resources:** Are you solo or do you have a team? Any experience with influencer outreach or paid ads?

### Optional Inputs (Ask If Relevant)
- Do you already have reviews on another platform you could import?
- Is this a seasonal product with a specific launch window?
- Do you have Brand Registry on Amazon?
- Are you already selling on one platform and expanding to another?

---

## Step 2: Platform Selection

Based on user input, select the appropriate launch framework.

**Load skill:** `11-launch-reviews` for all launch strategies.

| User Platform | Launch Framework | Key Timeline |
|---|---|---|
| Shopify / DTC only | Matt Clark 12-Week Launch | 12 weeks from start to full launch |
| Amazon FBA | Amazon Honeymoon + Vine Strategy | Optimize listing BEFORE launch; budget 2.5x inventory |
| TikTok Shop | 22-Step Launch Sequence | Sequential steps from registration through GMV Max |
| Multi-platform | Staggered Launch (strongest platform first) | Launch primary first, expand after 30-60 days |

---

## Step 3: Pre-Launch Checklist

For each platform, generate a tailored checklist.

### For DTC/Shopify:
**Load reference:** `skills/11-launch-reviews/ref-launch-checklists.md` for the 12-week checklist.

Key decision: Does user have social media skills and time?
- YES -> Recommend Gretta's audience-first approach (build following + waitlist before product)
- NO -> Recommend Matt's speed approach (12-week sprint with paid ads)

### For Amazon:
**Load reference:** `skills/11-launch-reviews/ref-launch-checklists.md` for cost breakdown.

Key decision: Does user have Brand Registry?
- YES -> Vine + Review Strategy + full launch playbook
- NO -> Apply for IP Accelerator; focus on listing optimization and PPC

### For TikTok Shop:
**Load reference:** `skills/11-launch-reviews/ref-launch-checklists.md` for 22-step sequence.
**Cross-reference:** `skills/10-tiktok-shop/SKILL.md` for setup details.

Key decision: Does user have existing Amazon reviews?
- YES -> Import reviews pipeline (Amazon -> Shopify -> TikTok via Yotpo)
- NO -> Focus on creator outreach volume to generate social proof

---

## Step 4: Launch Timeline Output

Generate a week-by-week (DTC) or step-by-step (Amazon/TikTok) plan.

```
LAUNCH PLAN

Platform: [Shopify / Amazon / TikTok Shop / Multi]
Launch Date Target: [date]
Total Budget: $[amount]

PRE-LAUNCH PHASE
- [Checklist items with dates]

SOFT LAUNCH PHASE
- [Checklist items with dates]

FULL LAUNCH PHASE
- [Checklist items with dates]

REVIEW STRATEGY
- [Platform-specific review generation plan]

POST-LAUNCH (Week 1-4)
- [Optimization and scaling steps]

BUDGET ALLOCATION
- Inventory: $[amount]
- Ads (month 1): $[amount]
- Tools: $[amount]
- Branding/images: $[amount]
- Influencer/creator: $[amount]
- Reserve: $[amount]
```

---

## Step 5: Review Strategy

Based on platform, recommend review generation approach.

| Platform | Primary Review Method | Secondary |
|---|---|---|
| Amazon | Vine + Request a Review button | Product inserts with QR code |
| Shopify | Email follow-up 3-5 days post-purchase | UGC incentive program |
| TikTok Shop | Import from Amazon via Yotpo pipeline | Creator content as social proof |

**Always warn about:** review compliance rules, geographic clustering risk, incentivized review prohibition.

---

## Step 6: Cross-Reference Recommendations

Based on the launch plan, recommend additional skills the user should review:

- **Listing optimization before Amazon launch:** `/optimize-listing` command
- **Influencer outreach for launch content:** `/influencer-outreach` command
- **Pricing and unit economics check:** `/price-product` command
- **Quality control before shipping:** `skills/05-quality-control/SKILL.md`
