---
name: Inspect Order
description: Pre-shipment inspection checklist with AQL 2.5 sampling plan, defect classification, and failed-inspection contingency plan. Activates quality-inspection.
---

# Pre-Shipment Inspection Wizard

## Step 1: Gather Order Details

Ask the user:
1. **Product:** What product is being inspected?
2. **Order quantity:** How many units in this production run?
3. **Supplier:** Who manufactured the order? (name, location)
4. **Spec sheet:** Do you have a finalized spec sheet? (If not, route to /spec-sheet)
5. **Previous issues:** Have you had quality issues with this supplier or product before?
6. **Inspection type:** First order or repeat? (affects sampling severity)
7. **Destination market:** US, EU, or other? (affects compliance checks)

## Step 2: Generate AQL 2.5 Sampling Plan

Load `skills/quality-inspection/SKILL.md` and `skills/quality-inspection/references/ref-quality-inspection-standards.md`.

Calculate:
- Sample size based on order quantity and AQL 2.5 standard
- Critical, major, and minor defect acceptance numbers
- Inspection level recommendation (normal, tightened, or reduced)

## Step 3: Defect Classification Guide

Generate product-specific defect classification:
- **Critical defects** (0 tolerance): Safety hazards, regulatory non-compliance
- **Major defects** (AQL 2.5): Functional failures, significant cosmetic issues
- **Minor defects** (AQL 4.0): Cosmetic imperfections that don't affect function

## Step 4: Inspection Checklist

Output:
- Pre-inspection preparation checklist
- On-site inspection steps (packaging, labeling, function, cosmetic, measurement)
- Documentation requirements (photos, measurements, defect log)
- Third-party inspector recommendations and booking guidance

## Step 5: Failed Inspection Plan

Provide contingency framework:
- Rework vs. reject decision criteria
- Supplier communication templates for quality issues
- Cost recovery and re-inspection procedures
- Next steps: once passed, route to shopify-store-setup or amazon-listing-optimization
