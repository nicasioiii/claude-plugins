---
name: QC Checklists & Inspection Templates
description: |
  Pre-shipment inspection checklist, AQL sampling table, defect classification guide, inspection communication templates in simple English, failed inspection escalation procedure, Matt Clark's quality inspection process, Jason Wong's stress testing protocol, and corrective action report template.
---

# QC Checklists & Inspection Templates

## PRE-SHIPMENT INSPECTION CHECKLIST

Use this checklist for every pre-shipment inspection. Send to your inspector along with golden sample photos and spec sheet.

### A. Quantity Verification
- [ ] Total units match purchase order
- [ ] Units per carton match specification
- [ ] Number of cartons matches calculation
- [ ] Carton markings match instructions

### B. Visual Inspection (Random Sample per AQL 2.5)
- [ ] Product matches golden sample photos
- [ ] Color matches Pantone specification
- [ ] No visible scratches, dents, or marks on product
- [ ] No visible scratches, dents, or marks on packaging
- [ ] Labels are correct and properly placed
- [ ] Barcodes scan correctly
- [ ] Print quality is clear and aligned

### C. Dimensional Check
- [ ] Product dimensions match spec sheet (length, width, height)
- [ ] Product weight within acceptable range
- [ ] Packaging dimensions match spec sheet

### D. Functional Testing
- [ ] Product performs primary function correctly
- [ ] All moving parts operate smoothly
- [ ] Electronic components work (if applicable)
- [ ] Zippers/closures/buttons function properly
- [ ] Assembly/disassembly works as designed

### E. Packaging and Labeling
- [ ] Correct packaging type used (poly bag, box, etc.)
- [ ] Required labels present (country of origin, care labels, warnings)
- [ ] Barcode/UPC correct and scannable
- [ ] Certifications/compliance marks present where required
- [ ] Product inserts included (if applicable)

### F. Carton and Shipping Preparation
- [ ] Master carton weight matches specification
- [ ] Carton dimensions match specification
- [ ] Inner packaging provides adequate protection
- [ ] Carton markings include all required information
- [ ] Packing list matches actual contents

---

## AQL SAMPLING TABLE (DETAILED)

### General Inspection Level II (Standard)

| Lot Size | Sample Size | AQL 1.0 (Accept/Reject) | AQL 2.5 (Accept/Reject) | AQL 4.0 (Accept/Reject) |
|---|---|---|---|---|
| 2-8 | 2 | 0/1 | 0/1 | 0/1 |
| 9-15 | 3 | 0/1 | 0/1 | 0/1 |
| 16-25 | 5 | 0/1 | 0/1 | 1/2 |
| 26-50 | 8 | 0/1 | 0/1 | 1/2 |
| 51-90 | 13 | 0/1 | 1/2 | 1/2 |
| 91-150 | 20 | 0/1 | 1/2 | 2/3 |
| 151-280 | 32 | 1/2 | 2/3 | 3/4 |
| 281-500 | 50 | 1/2 | 3/4 | 5/6 |
| 501-1200 | 80 | 2/3 | 5/6 | 7/8 |
| 1201-3200 | 125 | 3/4 | 7/8 | 10/11 |
| 3201-10000 | 200 | 5/6 | 10/11 | 14/15 |

**How to read:** For a 500-unit lot at AQL 2.5, inspect 50 units. If 3 or fewer defects are found, ACCEPT. If 4 or more defects are found, REJECT.

### Which AQL Level to Use
- **AQL 1.0:** Use for critical safety components or premium products
- **AQL 2.5:** Standard for most consumer products (recommended default)
- **AQL 4.0:** Use for minor/cosmetic defects only

---

## DEFECT CLASSIFICATION GUIDE

### Critical Defects (ZERO Tolerance)
| Defect Type | Examples |
|---|---|
| Safety hazard | Sharp edges, exposed wires, toxic materials, choking hazard |
| Regulatory non-compliance | Missing safety labels, banned substances, wrong voltage |
| Complete non-function | Product does not work at all |
| Wrong product | Different product than ordered |

**Rule: ANY critical defect = automatic lot rejection, regardless of AQL calculation.**

### Major Defects (AQL 2.5 Standard)
| Defect Type | Examples |
|---|---|
| Missing parts | Missing component, accessory, or hardware |
| Wrong specification | Wrong color, wrong size, wrong material |
| Significant function issue | Works but not as intended (switch intermittent, seal leaks) |
| Packaging failure | Packaging does not protect product adequately |
| Label error | Wrong text, missing required information |

### Minor Defects (AQL 4.0 Typical)
| Defect Type | Examples |
|---|---|
| Cosmetic imperfection | Small scratch not visible in normal use |
| Slight color variation | Within acceptable Pantone tolerance |
| Minor packaging issue | Crease in box, slightly off-center label |
| Thread loose end | Visible but does not affect function |

---

## INSPECTION COMMUNICATION TEMPLATES

Write inspection criteria in simple English. Your inspector may not be fluent.

### Template: General Product Inspection Brief

```
INSPECTION BRIEF
Product: [Name]
Order Number: [PO#]
Factory: [Name, Address]
Inspection Date: [Date]
Inspector: [Assigned by Qima/service]

GOLDEN SAMPLE REFERENCE:
[Attach 4-6 photos of approved sample from all angles]

CHECK THESE ITEMS:
1. Color must match photo. No dark spots. No light spots.
2. [Feature] must work. Test 10 times. Must work every time.
3. Weight must be between [X] and [Y] grams.
4. Size must be [X] cm long, [Y] cm wide. Tolerance: +/- 2mm.
5. No scratches on [surface]. Hold under bright light to check.
6. Label must say [exact text]. Must be straight. No wrinkles.
7. Box must close properly. No tears. No dents.
8. Barcode must scan with phone. Try 3 different units.

DEFECT CATEGORIES:
- CRITICAL (reject ALL): [list specific critical defects]
- MAJOR (AQL 2.5): [list specific major defects]
- MINOR (AQL 4.0): [list specific minor defects]

TAKE PHOTOS OF:
- Every defect found (close-up)
- Overall product appearance (front, back, sides)
- Packaging (open and closed)
- Labels and barcodes
- Carton markings
```

---

## FAILED INSPECTION ESCALATION PROCEDURE

```
Step 1: RECEIVE REPORT
  |
  v
Step 2: CLASSIFY FAILURE
  |---> Critical defects found? --> REJECT LOT. Demand rework at supplier cost
  |---> Major defects > AQL? --> Continue to Step 3
  |---> Minor only? --> Consider accepting with discount
  |
  v
Step 3: CONTACT SUPPLIER (within 24 hours)
  - Share inspection report with photos
  - Request supplier's explanation
  - Request root cause analysis
  |
  v
Step 4: NEGOTIATE RESOLUTION
  |---> Option A: Supplier reworks defective units (most common)
  |---> Option B: Sort good units, ship only those
  |---> Option C: Discount on 70% balance payment
  |---> Option D: Reject entire lot (last resort)
  |
  v
Step 5: CORRECTIVE ACTION REPORT
  - Document root cause
  - Document solution implemented
  - Update spec sheet if ambiguity caused issue
  |
  v
Step 6: RE-INSPECT (at supplier's cost)
  - Same criteria, same AQL level
  - Must pass before any shipment authorized
  |
  v
Step 7: AUTHORIZE SHIPMENT
  - Pay 70% balance
  - Notify freight forwarder to pick up
```

---

## MATT CLARK'S QUALITY INSPECTION PROCESS

### Cost and Standards
- Cost: $100-$400 depending on company and inspection level
- Industry standard: AQL 2.5 (Acceptance Quality Limit)
- AQL 2.5 = maximum 2.5% defect rate acceptable

### Trade Assurance Integration
- Always filter for Trade Assurance suppliers on Alibaba
- Inspection specifics MUST be written into Trade Assurance agreement
- Example: if you want max 2% defect rate, write it into the agreement
- Without written specifics, Trade Assurance does not cover quality claims

---

## JASON WONG'S SAMPLE STRESS TESTING PROTOCOL

Before approving any sample for production:

1. **Drop test:** Drop from table height (3 feet) onto hard floor. Repeat 3 times, different orientations each time. Document any damage.
2. **Scratch test:** Use coin, keys, fingernail on visible surfaces. Note any marks that remain.
3. **Color test:** Rub vigorously with damp white cloth. Check for color transfer. Expose to direct sunlight for 48 hours. Check for fading.
4. **Functional test:** Use the product as intended 20+ times. Note any degradation.
5. **Failure test:** Push beyond intended use until something breaks. Document WHERE it fails and HOW.
6. **Water test:** If product may get wet in normal use, test water resistance.
7. **Weight test:** Load to maximum intended capacity. Check for structural deformation.
8. **Packaging test:** Ship sample to yourself via normal courier. Check if packaging protected it during transit.

Document all results with photos and measurements. This becomes your quality baseline.

---

## CORRECTIVE ACTION REPORT TEMPLATE

### Section 1: Problem Description
- Inspection date and location
- Order/PO number
- Total units inspected
- Defect types found (with photos)
- Defect count per category (critical, major, minor)
- AQL result (pass/fail)

### Section 2: Root Cause Analysis
- Manufacturing process step where defect occurred
- Was it material issue, machine issue, operator issue, or design issue?
- Was this defect present in pre-production sample? (If no, what changed?)

### Section 3: Corrective Actions
- Specific changes supplier will implement
- Timeline for implementation
- Person responsible at supplier
- Updated spec sheet or quality checklist (if applicable)

### Section 4: Verification Plan
- Re-inspection date
- Additional checks to be added for this defect type
- Ongoing monitoring frequency

### Section 5: Financial Impact
- Units rejected or requiring rework
- Cost of rework (supplier's responsibility)
- Cost of re-inspection
- Shipping delays and associated costs
- Customer impact (if any units already shipped)
