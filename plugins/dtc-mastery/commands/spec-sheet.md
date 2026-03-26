---
name: Spec Sheet
description: Complete product specification sheet from a product concept, including materials, dimensions, packaging requirements, and sampling plan. Activates product-development.
---

# Spec Sheet Generator

## Step 1: Gather Product Details

Ask the user:
1. **Product:** What is the product?
2. **Materials:** What materials should it be made of? (If unsure, provide options)
3. **Dimensions:** Approximate size and weight?
4. **Features:** What are the key functional and aesthetic features?
5. **Target price:** What retail price are you targeting?
6. **Target market:** US, EU, both? (affects compliance requirements)
7. **Packaging:** Any packaging preferences? (standard box, premium, eco-friendly?)
8. **Competitor references:** Any existing products to reference?

## Step 2: Generate Specification Sheet

Load `skills/product-development/SKILL.md` and `skills/product-development/references/ref-product-development-processes.md`.

Output complete spec sheet with all Golzari template fields:
- Header (brand, product, code, season)
- Materials breakdown per component
- Color specifications (Pantone guidance)
- Dimensions and tolerances
- Feature requirements
- Labeling and hangtag specs
- Packaging specifications
- Competitor reference images to include
- Quote request section

## Step 3: Sampling Plan

Output 3-stage sampling timeline with specific milestones and sign-off criteria.

## Step 4: Compliance Check

Flag regulatory requirements. Recommend compliance consultant if in regulated category.

## Step 5: Next Steps

Direct to /find-supplier for the 10-3-1 method.
