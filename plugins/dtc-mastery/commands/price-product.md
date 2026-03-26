---
name: Price Product
description: Calculate unit economics, markup, break-even CPA, and recommended pricing. Runs the user through all instructor pricing frameworks and outputs a complete financial picture. Activates 12-pricing-finance.
---

# Pricing & Unit Economics Calculator

## Step 1: Gather Cost Information

Ask the user these questions before proceeding. Do not skip any.

### Required Inputs
1. **Product cost (per unit):** What does the manufacturer charge per unit? (Include any MOQ context)
2. **Packaging cost (per unit):** Packaging, labels, inserts?
3. **Shipping to warehouse (per unit):** Freight cost allocated per unit (ocean, air, or domestic)?
4. **Fulfillment cost (per unit):** 3PL pick-and-pack, or Amazon FBA fees, or self-ship cost?
5. **Platform fees:** Which platform(s)? (Shopify transaction fees, Amazon referral + FBA, TikTok referral)
6. **Primary acquisition channel:** Paid ads (Facebook, Google), organic/influencer, Amazon PPC, TikTok creators, or mixed?
7. **Target retail price (if known):** Do you have a price in mind, or should we calculate from costs?

### Optional Inputs (Ask If Relevant)
- Do you plan to sell wholesale? If so, what wholesale discount (typically 50%)?
- Do you have repeat purchase / subscription data?
- What is your current or expected AOV (including bundles)?
- What is your monthly ad budget?
- Are you selling on multiple platforms with different pricing?

---

## Step 2: Calculate Landed Cost

**Load skill:** `12-pricing-finance` for all formulas and frameworks.

```
UNIT COST BREAKDOWN

Product cost (manufacturer):     $[___]
Packaging (per unit):            $[___]
Shipping/freight (per unit):     $[___]
Fulfillment/pick-pack:           $[___]
Transaction fees (estimated):    $[___]
Other variable costs:            $[___]
─────────────────────────────────
TOTAL LANDED COST PER UNIT:      $[___]
```

---

## Step 3: Apply Markup Rules

Calculate pricing using ALL four instructor frameworks, then recommend.

```
MARKUP ANALYSIS

Gretta's 2.5x (organic/influencer brands):
  $[landed] x 2.5 = $[price]

Matt's 4x (paid-ads DTC brands):
  $[landed] x 4 = $[price]

Jason's 5x (conservative default):
  $[landed] x 5 = $[price]

Melisa's 30%+ after fees (Amazon):
  Retail price needed for 30% profit after fees = $[price]
  (Account for [X]% referral fee + $[X] FBA fee)
```

**Recommend** the appropriate framework based on primary acquisition channel:
- Paid ads primary -> Matt's 4x minimum
- Organic/influencer primary -> Gretta's 2.5x minimum
- Amazon primary -> Melisa's 30%+ after fees
- Uncertain -> Jason's 5x (safest default)

**Flag dollar margin warning:** If dollar margin is below $15, recommend bundles or multi-packs to increase AOV.

---

## Step 4: Calculate Break-Even CPA

```
PROFITABILITY ANALYSIS

Retail price:                    $[___]
Landed cost:                     $[___]
Platform fees:                   $[___]
Gross profit per unit:           $[___]
Gross margin:                    [___]%

Break-Even CPA (day-one):       $[gross profit]
  (Maximum ad spend per customer to break even on first purchase)

Target CPA (healthy):           $[gross profit x 0.5]
  (50% of gross profit allows reinvestment)
```

### If User Has Repeat Purchase Data
```
LTV-BASED CPA ANALYSIS

Month 1 AOV:                     $[___]
Estimated repeat rate:           [___]%
6-month cumulative LTV:          $[___]
12-month cumulative LTV:         $[___]
LTV gross profit:                $[___]

6-month break-even CPA:          $[6-mo LTV x margin]
12-month break-even CPA:         $[12-mo LTV x margin]

LTV:CAC ratio at target CPA:    [___]:1
  (Target: 3:1 or higher)
```

---

## Step 5: Wholesale Viability Check

If user plans to sell wholesale:

```
WHOLESALE ANALYSIS

Retail price:                    $[___]
Wholesale price (50% discount):  $[retail / 2]
Landed cost:                     $[___]
Wholesale margin:                $[wholesale - landed]
Wholesale margin %:              [___]%

Verdict: [VIABLE / TIGHT / NOT VIABLE]
  (Need positive margin after wholesale discount)
  (Gretta minimum: 2.5x to accommodate 50% wholesale)
```

---

## Step 6: Complete Financial Summary

Output the final pricing recommendation:

```
PRICING RECOMMENDATION

Recommended retail price:        $[___]
Pricing framework used:          [Gretta 2.5x / Matt 4x / Jason 5x / Melisa 30%+]
Reasoning:                       [Based on primary channel and margin needs]

Per-unit economics:
  Revenue:                       $[___]
  - Landed cost:                 $[___]
  - Platform fees:               $[___]
  - Estimated ad cost/unit:      $[___]
  = Net profit per unit:         $[___]
  = Net margin:                  [___]%

Break-even CPA:                  $[___]
Target CPA:                      $[___]
Monthly break-even volume:       [___] units
  (at target ad spend of $[___]/month)

Gross margin:                    [___]%
  Target: 30% minimum, 60% ideal

WARNINGS:
- [Flag if margin below 30%]
- [Flag if dollar margin below $15 for paid ads]
- [Flag if wholesale margin negative]
- [Recommend bundles if AOV too low for paid acquisition]
```

---

## Step 7: Action Items

Based on the analysis, recommend next steps:

- If margins are healthy: proceed to launch planning (`/plan-launch`)
- If margins are tight: recommend cost reduction tactics (negotiate supplier, lighter packaging, sea freight)
- If margins are insufficient: recommend product repositioning (bundles, premium version, different target price)
- If selling multi-platform: calculate separate unit economics for each platform
- Cross-reference: `skills/03-sourcing-suppliers/SKILL.md` for supplier negotiation to reduce costs
