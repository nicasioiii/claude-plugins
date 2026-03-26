---
name: Price Product
description: Pricing and unit economics calculator covering landed cost, markup validation, break-even ROAS, RPV targets, and tariff optimization. Activates pricing-unit-economics.
---

# Pricing & Unit Economics Calculator

## Step 1: Gather Cost Details

Ask the user:
1. **Product cost (FOB):** What does the manufacturer charge per unit?
2. **Shipping method:** Sea freight, air freight, or courier? (estimated per-unit cost)
3. **Duties & tariffs:** Do you know the HTS code or duty rate? Country of origin?
4. **Packaging cost:** Per-unit packaging and labeling cost?
5. **Selling platforms:** Shopify, Amazon, TikTok Shop, or combination?
6. **Target retail price:** What price point are you considering?
7. **Advertising budget:** Estimated ad spend as % of revenue?

## Step 2: Calculate Landed Cost

Load `skills/pricing-unit-economics/SKILL.md` and `skills/pricing-unit-economics/references/pricing-unit-economics-ref.md`.

Build complete landed cost breakdown:
- Product cost (FOB)
- Freight (per unit)
- Duties and tariffs
- Customs brokerage
- Last-mile / prep fees
- Platform fees (by channel)
- Total landed cost per unit

## Step 3: Markup Validation

Apply pricing rules per channel:
- **Shopify DTC:** 4x landed cost target (minimum 3x)
- **Amazon:** One-third rule (selling price / 3 = product cost ceiling)
- **TikTok Shop:** Can price higher than Amazon (bots can't see TikTok prices)

Flag any channel where margins are below threshold.

## Step 4: Break-Even Analysis

Calculate:
- Break-even ROAS per channel
- RPV (Revenue Per Visitor) targets
- Cash conversion cycle estimate
- Monthly break-even unit volume

## Step 5: Output Pricing Report

Present:
- Landed cost waterfall chart
- Per-channel pricing recommendation with margin analysis
- Break-even ROAS and RPV targets
- Tariff optimization opportunities (if applicable)
- Sensitivity analysis: impact of 10% cost increase or price decrease
- Budget allocation guidelines by channel
- Next steps: route to launch-strategy or platform setup commands
