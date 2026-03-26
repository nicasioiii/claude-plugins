---
name: Quality Inspection
description: >
  MANDATORY TRIGGERS: quality inspection, AQL, AQL 2.5, defect classification, defect rate,
  product inspection, pre-shipment inspection, PSI, third-party inspector, failed inspection,
  corrective action, quality control, QC, inspection checklist, packaging optimization,
  FBA packaging, manufacturer warranty, product defects, rework, inspection cost.
  FOR: Pre-shipment and post-arrival quality inspection -- AQL 2.5 standard, third-party
  inspectors, failed inspection 9-step action plans, defect classification, manufacturer
  warranties, variation-level packaging optimization, and inspection clause contracts.
  Synthesizes Gretta van Riel (defect benchmarks, horror stories, warranty contracts),
  Jason Wong (first-order inspection, rework costs, second arrival inspection), Matt Clark
  (AQL 2.5, defect classifications, failed inspection action plan, corrective action report),
  and Tomer Rabinovich/Kevin King (packaging size optimization for FBA fees).
  Do NOT use for: product development iteration (use product-development), supplier
  relationship management (use sourcing-suppliers), logistics/freight (use operations-systems).
---

# Quality Inspection

## Quick Navigation
- **AQL 2.5 standard & defect types** -> See Section: AQL 2.5 Standard
- **Failed inspection 9-step plan** -> ref-quality-inspection-standards.md
- **Packaging optimization for FBA** -> ref-quality-inspection-standards.md
- **Horror stories & lessons** -> See Section: Quality Horror Stories
- **Corrective action report template** -> ref-quality-inspection-standards.md

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| How does AQL 2.5 work exactly? Sampling tables? | ref-quality-inspection-standards.md |
| My inspection failed -- what do I do? | ref-quality-inspection-standards.md |
| Help me write a corrective action report | ref-quality-inspection-standards.md |
| Optimize packaging size for FBA fees | ref-quality-inspection-standards.md |
| What should my inspection contract clause say? | ref-quality-inspection-standards.md |

---

## Cross-References

| Topic | Primary Skill | Go To |
|---|---|---|
| Product specification sheets | product-development | `skills/product-development/SKILL.md` |
| Supplier evaluation and negotiation | sourcing-suppliers | `skills/sourcing-suppliers/SKILL.md` |
| Shopify store setup after inventory clears | shopify-store-setup | `skills/shopify-store-setup/SKILL.md` |
| Amazon listing after inventory at FBA | amazon-listing-optimization | `skills/amazon-listing-optimization/SKILL.md` |
| Pricing and unit economics | pricing-unit-economics | `skills/pricing-unit-economics/SKILL.md` |
| FBA fee optimization via packaging | pricing-unit-economics | `skills/pricing-unit-economics/SKILL.md` |

---

## Core Principle: Inspect EVERY Order

All instructors agree: inspection is non-negotiable.

- **Gretta:** Inspect every new order OR every 3 months
- **Jason:** Inform supplier upfront that you will inspect first order; first inspection costs on you; rework costs on supplier
- **Matt Clark:** Inspect EVERY order before it leaves the factory. Include inspection clause in Pro Forma Invoice.

**Inspection clause for Pro Forma Invoice (Matt Clark):**
> "Balance will be paid and shipment approved subject to approval of product quality inspection."

---

## AQL 2.5 Standard (Matt Clark)

**AQL = Acceptance Quality Limit of 2.5% defect rate or less.**

This is the industry standard for consumer product quality inspection.

### Defect Classifications

| Classification | Definition | Acceptance |
|---|---|---|
| **Critical** | Dangerous to user; safety hazard | Accept NONE (zero tolerance) |
| **Major** | Missing parts/components; product doesn't function as intended | Very low threshold |
| **Minor** | Cosmetic flaws; scratches, slight color variations | Higher threshold per AQL table |

### Inspection Cost
$100-$400 per inspection (third-party inspector visit to factory).

### Key Requirements
1. Inspect EVERY order before it leaves the factory
2. Use **external** inspection companies (NOT factory self-inspection)
3. Inspector takes random sample based on lot size and AQL table
4. Creates defect rate report with photos
5. Freight forwarder may offer inspection service as well

---

## Normal Defect Rate Benchmarks

| Source | Benchmark |
|---|---|
| Gretta van Riel | 2-5% of total order is normal |
| Matt Clark | AQL 2.5 (2.5% or less is acceptable) |
| Industry standard | 2.5% for consumer products |

If defect rate exceeds AQL threshold: do NOT ship. Trigger the failed inspection action plan.

---

## Third-Party Inspection Process

### Pre-Shipment Inspection (PSI)
1. Schedule inspector visit when production is 80-100% complete
2. Inspector draws random sample based on lot size
3. Checks against your spec sheet and approved pre-production sample
4. Classifies every defect found (critical, major, minor)
5. Produces detailed report with photos
6. Issues PASS or FAIL verdict based on AQL 2.5

### Second Inspection Upon Arrival (Jason Wong)
- Even after factory PSI passes, inspect again upon arrival at your warehouse/3PL
- Factory conditions vs. shipping conditions can reveal new defects
- Especially important for fragile or temperature-sensitive products

### Finding Third-Party Inspectors
- QIMA (formerly AsiaInspection) -- major global provider
- SGS -- largest inspection company worldwide
- Bureau Veritas
- Your freight forwarder may offer inspection services
- Search Alibaba for "[product category] inspection service"

---

## Failed Inspection 9-Step Action Plan (Matt Clark)

1. **Understand the nature of the problem** -- What went wrong? How widespread?
2. **Get pictures from inspector** -- Document everything visually
3. **Go over results with BOTH inspector AND supplier** -- Three-way review
4. **Request complete inspection of entire order** -- Full count, not just sample
5. **Choose from options:**
   - Refuse goods entirely
   - Insist on discount for acceptable defects
   - Rework goods (fix defects at factory)
   - Sort defects and ship only good units
6. **NEVER "ship the goods outright"** without resolution
7. **Create Corrective Action Report:**
   - Identify problems
   - Identify root causes
   - Provide solutions
   - Document all actions taken
8. **Re-inspect before shipment** -- Verify rework is complete and acceptable
9. **Implement corrective measures for future orders** -- SOPs to prevent recurrence

---

## Manufacturer Warranty & Contracts

### Gretta's Approach
- Get manufacturer warranty in contract (e.g., The Fifth has 1-year guarantee from manufacturer)
- Manufacturer pays for defects within warranty period
- Basic manufacturing contract via LegalZoom or lawyer

### Jason's Approach
- Inform supplier upfront about inspection on first order
- First inspection costs on buyer
- Rework inspection costs on supplier
- Rework cost allocation: supplier bears cost of fixing defects in production

### Contract Essentials
- Inspection clause in Pro Forma Invoice
- Warranty period and terms
- Defect cost allocation
- Rework timeline expectations
- Quality standards reference (AQL 2.5)
- Photo documentation requirements

---

## Quality Horror Stories -- Lessons Learned

### SkinnyMeTea Metal Bolts Disaster (Gretta)
- Ordered $1M worth of tea from Chinese manufacturer
- Arrived with metal bolts inside the tea
- Entire batch unusable
- $14,000 just to dispose of the product
- Total cost: well over $1M
- 3 months supply chain delay
- **Lesson:** Always use third-party inspection, especially for consumables

### Drop Bottle Breakage (Gretta)
- Thick glass bottles = breakable during shipping
- Some customers on 3rd replacement bottle with 6 shipments
- Each shipment costs $20 on a $40 product
- **Lesson:** Packaging must be stress-tested for transit durability

### General Quality Drop (Gretta)
- Quality can drop from prototype to batch production
- Always verify batch production against approved prototype
- The 3-stage sampling process (product-development skill) catches this early

---

## Packaging Size Optimization for FBA (Tomer Rabinovich, Kevin King Summit)

### Why It Matters
- Reducing from Large Standard to Small Standard size tier saves significant FBA fees
- Example: flashlight product went from $386 fulfillment to dramatically less
- Savings of $600/month profit on single product

### Process
1. Check current FBA size tier for your product
2. Identify the next smaller tier threshold (dimensions + weight)
3. Redesign packaging to fit within smaller tier
4. Use Signify for 3D rendering of optimized packaging
5. Calculate savings: current FBA fee - new FBA fee = monthly savings x units = annual impact

### FBA Size Tier Boundaries (check current Amazon rates)
- Small Standard: longest side 15", median 12", shortest 0.75", weight 1 lb
- Large Standard: longest side 18", median 14", shortest 8", weight 20 lb
- Every fraction of an inch matters at tier boundaries

---

## The /inspect-order Command

When the user runs `/inspect-order`, execute this guided process:

### Step 1: Gather Order Details
Ask: What product? Order quantity? Where is it being manufactured? Do you have a signed-off pre-production sample? First order or repeat? What was the last defect rate?

### Step 2: Generate Inspection Checklist
Output customized checklist including:
- AQL 2.5 sampling plan for the lot size
- Product-specific inspection points (based on product type)
- Spec sheet verification points
- Packaging inspection points
- Defect classification guide for this product

### Step 3: Inspector Brief
Generate a brief to send to the third-party inspector:
- Product description and spec sheet reference
- Critical quality points to check
- Approved sample reference (photos)
- Acceptable vs. unacceptable defect examples

### Step 4: Contingency Plan
Provide the 9-step failed inspection action plan with product-specific guidance:
- What constitutes a critical vs. major vs. minor defect for this product
- Rework feasibility assessment
- Cost allocation framework
- Re-inspection requirements

### Step 5: Next Steps
- If PASS: proceed to shipify-store-setup or amazon-listing-optimization
- If FAIL: execute action plan, then re-inspect
- Document corrective actions for future orders
