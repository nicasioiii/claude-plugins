---
name: Write VSL
description: Generate a complete VSL (video sales letter) script. Asks product, audience, awareness level, length preference, and mechanism status, then produces a ready-to-use VSL script with structure annotations and hook variations.
---

# /write-vsl -- VSL Script Generator

## INTAKE QUESTIONS (Ask All Before Writing)

### Question 1: VSL Format & Length
**What format and length do you need?**

| Choice | Format | Typical Use Case |
|--------|--------|-----------------|
| A) **Short VSL** (1-8 min) | One of 8 mini-VSL structures | In-feed ads, high-awareness markets, quick pitches |
| B) **Medium VSL** (8-20 min) | Compressed classic outline | Most common format today; Meta in-feed or landing page |
| C) **Long VSL** (20-60+ min) | Full classic outline expanded | Low-awareness markets, unknown brands, high-ticket |
| D) **Not sure** -- help me decide | Use 15-factor scoring | Ask follow-up questions to determine |

### Question 2: Placement
**Where will this VSL live?**

| Choice | Impact on Structure |
|--------|-------------------|
| A) **In-feed** (running as Meta/TikTok ad) | Native content feel; hooks tested against same body; delayed product reveal |
| B) **On-page** (landing page after click-through) | Classic outline; stronger lead with curiosity loops; viewer has some intent |

### Question 3: Product/Service
**Describe your product/service:**
- What it does (the transformation)
- Price point (and package options if multiple)
- Key differentiator vs. competitors
- Product type: supplement, info product, SaaS, coaching, physical product, etc.

### Question 4: Target Audience
**Who is this VSL targeting?**
- Specific audience description (demographics + psychographics)
- Primary pain point or desire
- What they've tried before that failed
- Their awareness level:
  - **Problem-aware:** Know the problem, don't know solutions exist
  - **Solution-aware:** Know solutions exist, haven't chosen one
  - **Product-aware:** Know your product category, comparing options

### Question 5: Unique Mechanism
**Do you have a UMP/UMS (Unique Mechanism)?**

| Status | Action |
|--------|--------|
| **Yes, fully developed** | Provide UMP + UMS + nickname if available |
| **Partially developed** | Provide what you have; we'll refine it |
| **No mechanism yet** | We'll develop one as part of the script (load unique-mechanism.md) |

### Question 6: Supporting Assets
**What do you already have?**
- Testimonials or case studies?
- Background/discovery story for the spokesperson?
- Research brief or Brief 2.0 completed?
- Specific hooks or big ideas to test?
- Guarantee details?
- Bonuses to include?

---

## GENERATION PROCESS

### For Short VSL (Choice A)

1. Load `vsl-sales-copy` SKILL.md
2. Load `vsl-sales-copy/references/vsl-structures.md` (Short VSL section)
3. If no mechanism exists, load `vsl-sales-copy/references/unique-mechanism.md` and develop one
4. Select the best short structure based on product type:

| Product Type | Recommended Structure |
|---|---|
| Supplement / Health / Skincare | Structure 1 (Problem -> Mechanism -> Solution) or Structure 7 (Contrarian + Expert) |
| Business opportunity / Coaching | Structure 2 (BizOpp Contrarian) or Structure 8 (SPG BizOpp) |
| Personal transformation / Info product | Structure 3 (Personal Discovery -> Solution) or Structure 5 (Secret Reveal) |
| Premium / Expert-positioned brand | Structure 4 (Authority/Affinity) |
| Emotional / Pain-relief product | Structure 6 (Emotional Story) |

5. Write the complete script with:
   - Time markers for each section
   - Visual direction notes (what the viewer sees)
   - 3 alternative hooks for testing
   - CTA copy

### For Medium VSL (Choice B)

1. Load `vsl-sales-copy` SKILL.md
2. Load `vsl-sales-copy/references/vsl-structures.md` (Medium VSL section)
3. If no mechanism exists, load unique-mechanism.md and develop one
4. Apply compression strategy:
   - Merge Lead + Background into one section (90 seconds max)
   - Keep UMP/UMS tight (3-4 minutes combined)
   - Shorten product buildup (skip extended trial-and-tribulation)
   - Close can still be the longest section
5. Write the complete script with:
   - Section labels and time estimates
   - 3 alternative hooks (for testing against same body)
   - CTA copy at each CTA point
   - Visual/slide direction notes

### For Long VSL (Choice C)

1. Load `vsl-sales-copy` SKILL.md
2. Load `vsl-sales-copy/references/vsl-structures.md` (Full classic outline)
3. Load `vsl-sales-copy/references/unique-mechanism.md`
4. Write the full 8-section script:

**I. Hook/Microlead** -- Attention-grabbing opening, pain relation, solution promise

**II. Lead** -- Open loops, tease mechanism, fascinations, broad testimonials, qualifiers, address skepticism

**III. Background Story** -- Credibility, shared struggle, trigger event, search for answers

**IV. UMP** -- The real cause revealed, surprising/counterintuitive, backed by proof, summarized

**V. UMS** -- The real solution (macro), logical connection to UMP, proof at micro level

**VI. Product Buildup + Reveal** -- Out-of-box solutions are flawed, innovator creates new solution, trial and tribulation, breakthrough, product born

**VII. Close** -- Product details, alternatives dismissed, value building, testimonials, usage clarity, scarcity, price justification, first CTA (crescendo), bonuses, guarantee, second CTA, crossroads close, urgency, third CTA

**VIII. FAQ** -- Tone shift to friendly, clear confusion, final CTA

5. Include time estimates per section
6. Include 3 alternative hooks
7. Include visual/production direction notes

### Mechanism Development (When No UMP/UMS Exists)

If the user has no mechanism:
1. Load `vsl-sales-copy/references/unique-mechanism.md`
2. Use the 3-step AI ideation process:
   - Step 1: Generate 5-8 UMP/UMS pairs based on product and audience info
   - Step 2: Evaluate and rank by connection potential, logical coherence, and differentiation
   - Step 3: Expand the top mechanism into full narrative + nickname
3. Integrate the developed mechanism into the VSL script

---

## OUTPUT FORMAT

Every output must include:

1. **Complete VSL script** -- section by section with clear labels
2. **Time estimates** -- approximate duration for each section and total
3. **3 hook variations** -- alternative openings for testing
4. **Structure annotation** -- which structure was used and why
5. **Visual direction notes** -- what the viewer should see at key moments
6. **CTA copy** -- exact wording for each call to action in the script
7. **Mechanism summary** -- UMP + UMS in 2-3 sentences (for reference)
8. **Cross-reference notes:**
   - If no research was done: "Consider running `market-research` for deeper audience insights and stronger mechanism validation"
   - If advertorial is needed upstream: "Use `advertorial-copy` to build a pre-sell page that warms traffic before this VSL"
   - If this is in-feed: "Test multiple hooks against the same body -- the winning hook can drive 60%+ of all conversions"
   - If upsells follow: "Connect to `upsell-downsell-strategy` for post-purchase flow design"
