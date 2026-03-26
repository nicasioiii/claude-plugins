---
name: Optimize Amazon Listing
description: Audit an Amazon listing against A9 ranking factors, semantic relevance, image optimization, Rufus/Cosmo readiness, and conversion best practices. Outputs scored report with prioritized actions. Uses amazon-listing-optimization skill.
---

# /optimize-listing -- Amazon Listing Optimization Workflow

## INTAKE QUESTIONS (Ask All Before Auditing)

### Question 1: Listing Status
**What's the current state of your listing?**

| Choice | Audit Focus |
|--------|------------|
| A) Brand new listing (not yet live) | Full build guidance; pre-launch optimization |
| B) Live listing, underperforming | Diagnostic audit; identify ranking blockers |
| C) Live listing, want to improve rankings | Optimization audit; competitive analysis |
| D) Listing was ranking, dropped | Troubleshooting audit; identify what changed |

### Question 2: Product Details
Please provide:
- **ASIN** (if live) or product description
- **Main target keyword** (what customers search to find this product)
- **Current title, bullets, and backend search terms** (if available)
- **Number of reviews and average rating**
- **Current organic rank for main keyword** (if known)

### Question 3: PPC Context
- Are you running PPC campaigns on this product?
- Approximate daily PPC spend?
- Current ACOS/TACOS?

---

## AUDIT FRAMEWORK

### Section 1: Title Analysis
**Check against A9 ranking formula (Brandon Young):**
- [ ] Brand name present at beginning of title
- [ ] Highest-volume keyword in first 80 characters
- [ ] Title reads naturally (not keyword-stuffed)
- [ ] Under 200 characters including spaces
- [ ] Check title density for main keyword (Bradley Sutton method)

**Score: ___/5**

### Section 2: Bullet Points Analysis
**Check against Melisa Vong structure:**
- [ ] All 5 bullets used
- [ ] Total under 1,000 characters combined
- [ ] Format: BENEFIT IN CAPS + description
- [ ] Keywords woven naturally into benefits
- [ ] Pain points and multi-use applications addressed
- [ ] Emotional OR logical selling (appropriate to persona)

**Score: ___/5**

### Section 3: Backend Search Terms
- [ ] Within 250-byte limit
- [ ] No duplication of title/bullet keywords
- [ ] Processed through Frankenstein (no duplicate words)
- [ ] Semantic relevance maintained (no off-topic keywords)
- [ ] Spanish language keywords included (if applicable)
- [ ] Misspellings and alternate names included

**Score: ___/5**

### Section 4: Semantic Relevance (Leo Sgovio)
- [ ] Run ChatGPT semantic relevance audit on keyword list
- [ ] No trendy but irrelevant keywords diluting relevance
- [ ] Central topic clearly defined
- [ ] All keywords cluster around central topic
- [ ] Branded and non-commercial keywords removed

**Score: ___/5**

### Section 5: Image Optimization
- [ ] All 7-9 image slots filled
- [ ] Main image: white background, high resolution
- [ ] Lifestyle image showing product in use
- [ ] Infographic with key benefits
- [ ] One topic per image (cognitive load principle)
- [ ] Target keywords in image text
- [ ] Image metadata set (filename, Photoshop metadata)
- [ ] Addresses #1 customer concern

**Score: ___/5**

### Section 6: Rufus/Cosmo Readiness (Vanessa Hung)
- [ ] Check Rufus-prompted questions on listing
- [ ] Check Rufus questions on competitor listings
- [ ] Feed listing + questions into ChatGPT for scorecard
- [ ] All scores 3+ (fix anything below 3)
- [ ] Images communicate product functionality to AI

**Score: ___/5**

### Section 7: Listing Simplicity (Matt Kostan)
- [ ] One clear message per image
- [ ] Not overwhelming with feature count
- [ ] Primary benefit immediately obvious
- [ ] #1 customer concern addressed prominently

**Score: ___/5**

### Section 8: Conversion Signals
- [ ] 10+ reviews (minimum before scaling PPC)
- [ ] Price competitive (within range of top 15 competitors)
- [ ] A+ Content active (if Brand Registry)
- [ ] Variations set up correctly (if applicable)

**Score: ___/5**

---

## OUTPUT FORMAT

### Listing Health Score: ___/40

| Score Range | Assessment |
|---|---|
| 35-40 | Excellent -- focus on PPC scaling |
| 28-34 | Good -- fix priority items before increasing spend |
| 20-27 | Needs work -- significant optimization needed before PPC ROI |
| Below 20 | Major rebuild -- fix listing before spending on ads |

### Priority Action List
1. **Critical fixes** (blocking ranking/conversion)
2. **High-impact improvements** (will noticeably improve performance)
3. **Optimization tweaks** (incremental gains)

### Specific Recommendations
- Rewritten title suggestion (if needed)
- Bullet point rewrites (if needed)
- Backend keyword optimization suggestions
- Image strategy recommendations
- Rufus/Cosmo content gaps to fill

---

## SKILLS ACTIVATED
- Primary: `amazon-listing-optimization`
- Supporting: `amazon-ppc-advertising` (for PPC-listing interaction)
- Reference: `ref-amazon-seo-tools.md` (for tool recommendations)
