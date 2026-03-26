---
name: Setup Amazon PPC
description: Amazon PPC campaign setup wizard covering campaign structure, placement strategy, bid optimization framework, and Search Query Performance analysis. Activates amazon-ppc-advertising.
---

# Amazon PPC Campaign Setup Wizard

## Step 1: Gather Campaign Details

Ask the user:
1. **ASIN(s):** Which product(s) are you advertising?
2. **Listing status:** Is the listing optimized? Reviews count? (If <10, route to /optimize-listing first)
3. **Budget:** Daily PPC budget available?
4. **Target ACOS:** What is your target ACOS? (If unsure, we'll calculate break-even)
5. **Current campaigns:** Do you have any existing PPC campaigns running?
6. **Competitors:** Top 3 competitor ASINs?
7. **Keywords:** Do you have keyword research done? Top keywords?

## Step 2: Campaign Architecture

Load `skills/amazon-ppc-advertising/SKILL.md` and `skills/amazon-ppc-advertising/references/amazon-ppc-advertising-ref.md`.

Generate campaign structure:
- **Sponsored Products:** Auto, broad, phrase, exact campaigns
- **Sponsored Brands:** Headline search, video, store spotlight
- **Sponsored Display:** Retargeting, audience targeting, product targeting

Include naming convention, budget allocation, and bid strategy per campaign.

## Step 3: Keyword Strategy

Provide:
- Seed keyword list from listing and competitor analysis
- Match type strategy (broad discovery -> exact scaling)
- Negative keyword starter list
- Search Query Performance (SQP) analysis framework

## Step 4: Placement & Bid Optimization

Output:
- Placement modifier recommendations (Top of Search, Product Pages)
- Bid optimization rules and adjustment schedule
- Day-parting recommendations if applicable
- Campaign optimization cadence (daily, weekly, monthly tasks)

## Step 5: Output PPC Launch Plan

Present:
- Complete campaign structure with naming, budgets, and bids
- Week 1-4 optimization roadmap
- KPI targets: ACOS, TACOS, impression share, conversion rate
- Scaling criteria -- when to increase budget
- Integration with pricing-unit-economics for break-even ACOS validation
