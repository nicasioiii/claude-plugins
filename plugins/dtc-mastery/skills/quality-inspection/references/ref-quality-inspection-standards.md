---
name: Quality Inspection Standards Reference
description: >
  Deep reference for AQL 2.5 sampling tables, detailed defect classification guides,
  corrective action report templates, packaging optimization specifics, inspection contract
  clauses, and third-party inspector selection criteria. Load when user needs exact sampling
  numbers, report templates, or detailed inspection procedures.
---

# Quality Inspection Standards -- Deep Reference

## AQL 2.5 Sampling Table

### General Inspection Level II (Normal)

| Lot Size | Sample Size | Accept (max defects) | Reject (if defects reach) |
|---|---|---|---|
| 2-8 | 2 | 0 | 1 |
| 9-15 | 3 | 0 | 1 |
| 16-25 | 5 | 0 | 1 |
| 26-50 | 8 | 0 | 1 |
| 51-90 | 13 | 1 | 2 |
| 91-150 | 20 | 1 | 2 |
| 151-280 | 32 | 2 | 3 |
| 281-500 | 50 | 3 | 4 |
| 501-1,200 | 80 | 5 | 6 |
| 1,201-3,200 | 125 | 7 | 8 |
| 3,201-10,000 | 200 | 10 | 11 |
| 10,001-35,000 | 315 | 14 | 15 |

### How to Use
1. Determine your lot (order) size
2. Find corresponding sample size
3. Inspector draws that many random units from production
4. Classify every defect found (critical, major, minor)
5. Compare defect count against Accept/Reject thresholds
6. Critical defects: ZERO tolerance regardless of sample size

---

## Detailed Defect Classification Guide

### Critical Defects (Zero Tolerance)
- Safety hazards (sharp edges, toxic materials, electrical faults)
- Choking hazards in children's products
- Structural failures that could cause injury
- Contamination (foreign objects in food/cosmetics)
- Non-compliance with mandatory safety standards
- **Action:** Reject entire lot. Do not ship under any circumstances.

### Major Defects
- Missing components or parts
- Product does not function as intended
- Significant color mismatch from approved sample
- Incorrect labeling or missing required labels
- Packaging that fails to protect product
- Wrong dimensions outside tolerance
- **Action:** Reject lot or require rework. Do not ship without resolution.

### Minor Defects
- Small cosmetic scratches or marks
- Slight color variations within acceptable range
- Minor packaging imperfections (small dents, slight misalignment)
- Thread ends not trimmed (textiles)
- Slight print misregistration
- **Action:** Accept within AQL threshold. Document for future improvement.

---

## Corrective Action Report Template

### Section 1: Problem Identification
| Field | Content |
|---|---|
| Product | [Product name and SKU] |
| Order number | [PO number] |
| Inspection date | [Date] |
| Inspector | [Third-party company name] |
| Lot size | [Total units] |
| Sample size | [Units inspected] |
| Defect rate | [Percentage] |
| Verdict | [PASS/FAIL] |

### Section 2: Defect Summary
| Defect | Classification | Count | % of Sample | Photo Reference |
|---|---|---|---|---|
| [Describe] | Critical/Major/Minor | [#] | [%] | [Photo #] |

### Section 3: Root Cause Analysis
For each defect type:
1. What went wrong?
2. At what stage of production did it occur?
3. Was it a material issue, process issue, or human error?
4. Was it caught by factory QC? If not, why?

### Section 4: Corrective Actions
| Action | Responsible Party | Deadline | Verification Method |
|---|---|---|---|
| [Specific fix] | Supplier/Buyer | [Date] | [How to verify] |

### Section 5: Prevention Measures
- Updated QC checkpoints for future production
- Additional inspection stages if needed
- Training requirements for factory workers
- Material source changes if applicable

### Section 6: Re-Inspection Plan
- Date of re-inspection
- Scope (full re-inspection or spot check)
- Pass/fail criteria
- Cost allocation (supplier bears rework + re-inspection costs)

---

## Packaging Optimization for FBA Fees (Tomer Rabinovich)

### FBA Size Tier Impact
| Tier | Max Dimensions (L x W x H) | Max Weight | Relative Fee |
|---|---|---|---|
| Small Standard | 15" x 12" x 0.75" | 1 lb | Lowest |
| Large Standard | 18" x 14" x 8" | 20 lb | Low |
| Small Oversize | 60" x 30" | 70 lb | Medium |
| Large Oversize | 108" max side | 150 lb | High |
| Special Oversize | 108"+ | 150 lb+ | Highest |

### Optimization Process
1. **Measure current packaging** -- length, width, height, weight (packaged)
2. **Identify current tier** -- which tier does it fall into?
3. **Calculate nearest tier boundary** -- how close are you to the next smaller tier?
4. **Redesign packaging** to fit within smaller tier:
   - Remove excess packaging material
   - Use more compact insert designs
   - Consider polybag instead of box if product allows
   - Reduce void fill
   - Test structural integrity at smaller size
5. **Verify with Amazon** -- use FBA calculator to confirm new tier and fees
6. **Calculate ROI:** (old fee - new fee) x monthly units = monthly savings

### Worked Example
- Product: Flashlight
- Before: Large Standard tier (box too big)
- After: Redesigned packaging to fit Small Standard
- Savings: $3.86 -> significant reduction per unit
- At 500 units/month = $600+/month additional profit

### Tools
- **Signify:** 3D rendering of optimized packaging designs
- **Amazon FBA Calculator:** Verify size tier and fee impact
- **Amazon Revenue Calculator:** Full P&L including new packaging costs

---

## Inspection Contract Clauses

### Pro Forma Invoice Clause (Matt Clark)
"Balance will be paid and shipment approved subject to approval of product quality inspection."

### Warranty Clause Template
"Manufacturer warrants that all products shall conform to the specifications, drawings, samples, and descriptions provided. Manufacturer shall be responsible for all costs associated with defective products, including but not limited to: rework, re-inspection, return shipping, replacement, and disposal. Warranty period: [12/24] months from date of delivery."

### Quality Standards Clause
"All products shall meet AQL 2.5 (Acceptance Quality Limit) per ANSI/ASQ Z1.4 sampling procedures. Critical defects: zero tolerance. Major defects: per AQL table. Minor defects: per AQL table. Inspector's report is final for acceptance/rejection determination."

### Rework Cost Allocation Clause (Jason Wong)
"First inspection costs shall be borne by Buyer. If inspection reveals defects exceeding AQL 2.5 thresholds, all costs for rework, re-inspection, and delayed shipment shall be borne by Manufacturer."

---

## Third-Party Inspector Selection Criteria

### Major Inspection Companies
| Company | Coverage | Pricing | Best For |
|---|---|---|---|
| QIMA (AsiaInspection) | Global, strong Asia | From $299/inspection | Most product types |
| SGS | Global, largest | Premium pricing | High-value products |
| Bureau Veritas | Global | Mid-range | Industrial products |
| TUV | Europe-focused | Premium | EU compliance |
| V-Trust | China-focused | Competitive | China-sourced products |

### Selection Criteria
1. Coverage in your manufacturing region
2. Experience with your product category
3. Reporting quality and detail level
4. Speed of scheduling and reporting
5. Cost relative to order value
6. Language capabilities
7. Digital reporting with photo documentation

### When to Inspect
| Scenario | Action |
|---|---|
| First order from new supplier | Always inspect (non-negotiable) |
| Repeat order, good history | Inspect every order OR every 3 months |
| Order value >$10,000 | Always inspect |
| Fragile or consumable product | Always inspect |
| Seasonal rush order | Always inspect (quality drops under time pressure) |

---

## Quality Drop Warning Signs

### Production Quality vs. Sample Quality
- Quality commonly drops from prototype/sample to batch production
- Causes: different workers, speed pressure, material substitution, batch variation
- Prevention: 3-stage sampling process (product-development skill) catches this early
- Always compare batch production against signed-off pre-production sample

### Red Flags During Production
- Supplier resists scheduling inspection
- Supplier rushes to ship before inspection date
- Supplier claims "our QC already checked"
- Multiple delays without clear explanation
- Sudden request for additional payment
- Communication becomes less responsive

### Post-Arrival Checks
- Open random cartons immediately upon arrival
- Compare against pre-production sample
- Check for shipping damage vs. manufacturing defects
- Document everything with photos
- If defects found: file claim within freight insurance window
