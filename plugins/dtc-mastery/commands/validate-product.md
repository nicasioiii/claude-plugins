---
name: Validate Product
description: Guided product scoring against all frameworks (PSSP, PRIME, 4-criteria, TikTokability). Outputs viability scorecard with go/no-go recommendation. Activates product-ideation.
---

# Product Validation Wizard

## Step 1: Gather Product Details

Ask the user these questions before proceeding. Do not skip any.

### Required Inputs
1. **Product description:** What is the product? What does it do?
2. **Problem it solves:** What pain point does it address?
3. **Target customer:** Who is the ideal buyer? Age, interests, behaviors?
4. **Approximate price point:** What would you sell it for?
5. **Target platforms:** Shopify DTC, Amazon, TikTok Shop, or multi-platform?
6. **Estimated landed cost:** What do you expect it to cost per unit delivered?
7. **Current demand signals:** Have you seen this selling well anywhere? Google Trends? Amazon BSR?

## Step 2: Score Against All Frameworks

Load `skills/product-ideation/SKILL.md` and `skills/product-ideation/references/ref-product-ideation-frameworks.md`.

### PSSP Clarity (0-10)
Score the Problem -> Stat -> Solution -> Product chain. Is it clear, compelling, and marketable?

### Clark 4-Criteria (0-4)
- Big market potential (0 or 1)
- Good demand -- BSR < 10,000 for 2+ products (0 or 1)
- Ability to differentiate (0 or 1)
- High profit potential -- 4x landed cost (0 or 1)

### PRIME Check (0-5)
- Positioning potential (0 or 1)
- Reviews mined for improvement opportunities (0 or 1)
- In-demand verified by data (0 or 1)
- Margins at 30%+ (0 or 1)
- Easy to make and ship (0 or 1)

### TikTokability (0-5)
- Demonstrable in short video (0 or 1)
- Unique visual attributes (0 or 1)
- Serves a passionate niche (0 or 1)
- Problem-solution in <10 seconds (0 or 1)
- Impulse-buy optimized under $50 (0 or 1)

## Step 3: Output Viability Scorecard

Present a table with all scores, weighted total, and recommendation:

- **GO** (70%+): Strong across frameworks, no critical fails. Proceed to brand-strategy.
- **CONDITIONAL GO** (50-69%): One framework fails but others pass. List specific fixes needed.
- **NO-GO** (<50%): Multiple critical fails. Recommend pivoting with specific guidance.

Include: specific strengths, specific weaknesses, anti-pattern warnings, and next steps.
