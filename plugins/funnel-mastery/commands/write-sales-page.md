---
name: Write Sales Page
description: Generate complete sales page copy using the 10-step structure or high-ticket format. Asks product, audience, awareness level, and page type, then produces ready-to-use sales page copy section by section.
---

# /write-sales-page -- Sales Page Copy Generator

## INTAKE QUESTIONS (Ask All Before Writing)

### Question 1: Page Type
**What type of sales page do you need?**

| Choice | Structure Used |
|--------|---------------|
| A) **Low-ticket / standard product** ($1-$500) | 10-Step Perfect Sales Page (Gusten) |
| B) **High-ticket application** ($5,000+) | High-Ticket Structure (Katie/Floyd) |
| C) **Not sure** -- help me decide | Ask price point + fulfillment model, then route |

### Question 2: Product/Service
**Describe your product/service:**
- What it does (the transformation, not the features)
- Price point (or price range / package options)
- Key differentiator vs. competitors
- Is there an existing unique mechanism (UMP/UMS)? If so, describe it.

### Question 3: Target Audience
**Who is this page targeting?**
- Specific person description (not just demographics -- include psychographics)
- Primary pain point or desire
- What they've tried before that didn't work
- Any specific language or phrases they use

### Question 4: Awareness Level
**Where is your audience on the awareness spectrum?**
- **Problem-aware:** Know the problem, don't know solutions exist (needs full 10-step long-form)
- **Solution-aware:** Know solutions exist, haven't chosen one (needs medium-length with differentiation)
- **Product-aware:** Know your product category, deciding between options (shorter, comparison-heavy)
- **Most-aware:** Ready to buy, need a push (short page, urgency-focused)

### Question 5: Assets Available
**What do you already have?**
- Testimonials or case studies? (How many, how specific?)
- Guarantee details?
- Social proof data? (Customer count, ratings, media mentions)
- Comparison data vs. competitors?
- Existing research document or Brief 2.0?

---

## GENERATION PROCESS

### For Low-Ticket / Standard (Choice A)

1. Load `sales-page-copy` SKILL.md
2. Load `sales-page-copy/references/sales-page-sections.md`
3. If no mechanism exists, suggest completing `market-research` first (note this, but proceed with what's available)
4. Write each of the 10 steps in order:

**Step 1: Big Promise / Headline**
- Write pre-headline targeting specific audience
- Write main headline using [Outcome] + [Timeframe] + "Without" [Objection] formula
- Include above-the-fold element suggestions (logo bar, ratings, CTA placement)

**Step 2: Empathy Section**
- Write stakes statement
- Write connection/shared experience
- Write pain points list using THEIR language
- Write support bridge

**Step 3: Opportunity / New Solution**
- Write "what you've tried" acknowledgment
- Introduce the new method/vehicle
- Write before/after gap-and-bridge content

**Step 4: USP / Comparison**
- Write comparison table (old way vs. new way or us vs. competitors)
- Write differentiation statement

**Step 5: Benefits**
- Write Feature -> Benefit -> Impact chains for top 5-7 features
- Ensure every chain ends at emotional impact

**Step 6: Offer Stack**
- Write offer stack with individual values for each component
- Write price anchoring (total value vs. investment)
- Include "Smart People Buy More" push if multiple packages

**Step 7: Social Proof**
- Write social proof placement recommendations
- Draft testimonial placement strategy (sprinkled, not clumped)
- Write proof elements for each page section

**Step 8: Risk Reversal**
- Write guarantee copy
- Include payment plan framing if applicable

**Step 9: Authority**
- Write transformation story (not bio)
- Include epiphany moment

**Step 10: Urgency / Scarcity**
- Write urgency mechanism copy
- Write What/When/Why close
- Write FAQ section (5-6 questions)

### For High-Ticket Application (Choice B)

1. Load `sales-page-copy` SKILL.md
2. Load `sales-page-copy/references/sales-page-sections.md` (High-Ticket section)
3. Write each section:

**Section 1: Promo Banner** -- Current offer or deadline

**Section 2: Tagline** -- One statement answering: How long? What? What benefit? How different?

**Section 3: Heart Section** -- Mission, story, genuine belief. Written from conviction, not sales.

**Section 4: Who It's For** -- Clear avatar description that self-selects the right person

**Section 5: Authority Proof** -- Specific results, named clients, revenue/transformations

**Section 6: What's Inside** -- Focus on WHY the support helps, not what information is covered. Frame as coaching/transformation, NOT more content.

**Application CTA** -- "Apply to work with us" framing, not "Buy now"

---

## OUTPUT FORMAT

Every output must include:

1. **Complete sales page copy** -- section by section, clearly labeled
2. **Headline variations** -- 3 alternative headlines for testing
3. **Awareness level confirmation** -- which level the copy was written for
4. **Social proof placement map** -- where to insert testimonials throughout
5. **CTA button text** -- recommended button copy for each CTA placement
6. **Cross-reference notes:**
   - If no mechanism was provided: "Consider running `market-research` to develop a UMP/UMS for stronger differentiation"
   - If testing is planned: "Use `funnel-cro` frameworks for split testing headlines and sections"
   - If this is part of a larger funnel: "Ensure this page connects to your `funnel-architecture` flow"
