---
name: Find Supplier
description: Supplier outreach plan with communication templates, evaluation criteria, negotiation scripts, and MOQ reduction strategy. Activates sourcing-suppliers.
---

# Supplier Outreach Wizard

## Step 1: Gather Product Details

Ask the user:
1. **Product:** What product do you need manufactured?
2. **Spec sheet:** Do you have a specification sheet ready? (If not, route to /spec-sheet first)
3. **Quantity:** How many units for first order?
4. **Budget:** What is your target per-unit cost?
5. **Timeline:** When do you need inventory ready?
6. **Preferences:** Domestic vs. China manufacturing? Any specific requirements?

## Step 2: Supplier Outreach Plan

Load `skills/sourcing-suppliers/SKILL.md` and `skills/sourcing-suppliers/references/ref-sourcing-suppliers-tactics.md`.

Generate:
- Alibaba search criteria (Gold 3+yr, Trade Assurance, product-specific)
- Customized initial outreach message
- 5-point audit scorecard for comparing responses
- Import record research strategy (if targeting specific competitors)

## Step 3: Negotiation Strategy

Provide:
- Customized price negotiation script
- MOQ reduction strategy (select from 9 tactics based on situation)
- Payment terms recommendation
- Timeline with milestones

## Step 4: Sample & Evaluation Plan

Output:
- Sample request checklist
- Evaluation scorecard template
- Stress test protocol
- Next steps: product-development (3-stage sampling) -> quality-inspection (PSI)
