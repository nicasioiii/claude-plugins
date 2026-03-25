---
name: Write Email
description: Write a complete email with subject line, preview text, and full copy. Asks business type, email purpose, audience, and tone, then produces a ready-to-send email using write-email-copy and write-subject-lines skills.
---

# /write-email -- Complete Email Generator

## INTAKE QUESTIONS (Ask All Before Writing)

### Question 1: Business Type & Context
**What type of business is this email for?**

| Choice | Copy Context |
|--------|-------------|
| A) Ecommerce / DTC brand | Table Method structure, designed/modular format, product-focused |
| B) Creator / Coach / Info-product | Personality-driven, story-based, plain text preferred |
| C) Newsletter / Media | Content-first, value-driven, habit-forming |
| D) Service business / Agency | Professional but warm, expertise-led |

### Question 2: Email Purpose
**What is the goal of this email?**

| Choice | Skill Focus |
|--------|------------|
| A) Sell a product (campaign/promo) | `write-email-copy` -- PAS or UPPER framework |
| B) Tell a story that leads to a pitch | `write-email-copy` -- Story angle + soft sell |
| C) Pure value / content (no direct sell) | `write-email-copy` -- Four Lenses approach |
| D) Announcement (new product, feature, event) | `write-email-copy` -- Oprah angle or direct |
| E) Cart close / final urgency | `write-email-copy` -- Rocky Balboa or Caveman Invite |
| F) Welcome / onboarding email | Route to `write-welcome-sequence` or `ecom-flows` |
| G) Launch sequence email | Route to `write-launch-sequence` |

### Question 3: Audience Awareness Level
**Where is your audience on the awareness spectrum?**
- **Unaware:** Do not know they have a problem
- **Problem-aware:** Know the problem, not the solution
- **Solution-aware:** Know solutions exist, have not chosen one
- **Product-aware:** Know your product, have not decided
- **Most-aware:** Ready to buy, need a push

### Question 4: Product/Offer Details
**Describe what you are selling or promoting:**
- Product/service name and what it does
- Price point (or range)
- Key differentiator vs. alternatives
- Current offer/discount (if any)

### Question 5: Tone & Voice
**What voice should this email use?**
- Brand name and any voice guidelines
- Founder name (if personality-driven)
- Tone preference: professional, casual, funny, edgy, warm, authoritative
- Any existing emails to reference for style?

---

## GENERATION PROCESS

### For Ecom Campaign Email (Choice 1A)
1. Load `write-email-copy` SKILL.md
2. Use the Table Method (8-row structure)
3. Select framework based on awareness level:
   - Unaware/Problem-aware: PAS or AIDA (emotional lead)
   - Solution-aware/Product-aware: UPPER or Problem-Solution Quick Template
   - Most-aware: Direct offer with urgency
4. Fill using Speed Writing (reverse order)
5. Load `write-subject-lines` SKILL.md
6. Generate subject line using question-forming principle
7. Write preview text to complete the curiosity gap
8. Output: Subject + Preview + Full 8-row email structure

### For Story-Based Sales Email (Choice 1B)
1. Load `write-email-copy` SKILL.md
2. Select an email angle from the nine proven angles (ref-copy-angles.md):
   - Pick based on what fits the product and available story
   - Default to Micro Story or Two Types if unsure
3. Apply storytelling principles (Sitcom Secret, exaggeration, non-linear)
4. Use TIMER framework to select the currency to target
5. Soft sell in the transition from story to pitch
6. Include PS with CTA for skimmers
7. Load `write-subject-lines` SKILL.md
8. Generate subject line aiming for double-whammy curiosity
9. Output: Subject + Preview + Story email with embedded pitch

### For Content/Value Email (Choice 1C)
1. Load `write-email-copy` SKILL.md
2. Select a lens from the Four Lenses:
   - Aspirational: inspiring story or transformation
   - Insightful: connect dots, reveal blind spot
   - Actionable: tactical step-by-step
   - Analytical: data/research breakdown
3. Keep to one topic, one idea
4. Apply Sam Bennett writing rules (3:1 you/I ratio, eliminate filler)
5. Include soft CTA (link to product/content/resource)
6. Load `write-subject-lines` SKILL.md
7. Generate subject line balancing self-interest and curiosity
8. Output: Subject + Preview + Value email with soft CTA

### For Announcement Email (Choice 1D)
1. Load `write-email-copy` SKILL.md
2. Use Oprah angle for fun announcements or direct lead for serious ones
3. Lead with the news, add personality
4. Below-fold: supporting details, social proof, or related products
5. Clear CTA for desired action
6. Load `write-subject-lines` SKILL.md
7. Generate subject line -- direct + brackets approach often works best
8. Output: Subject + Preview + Announcement email

### For Cart Close / Urgency Email (Choice 1E)
1. Load `write-email-copy` SKILL.md
2. Choose angle:
   - Rocky Balboa: aspirational + pop culture + deadline
   - Caveman Invite: stripped-down direct offer
   - Schoolgirl Screech: pure excitement (no claims)
3. Include deadline prominently
4. Handle final objections or add "two paths" close
5. Load `write-subject-lines` SKILL.md
6. Put deadline info IN the subject line
7. Output: Subject + Preview + Cart-close email

---

## OUTPUT FORMAT

Every output must include:

1. **Subject line** (primary) + 2 A/B test variations
2. **Preview text** that complements the subject line
3. **Full email copy** using the appropriate framework
4. **Awareness level label** confirming audience match
5. **Framework used** (AIDA, PAS, UPPER, angle name, etc.)
6. **Suggested A/B test** for the next send (what to test and why)

### For Ecom Emails, Also Include:
- Above-fold and below-fold content separated
- Module suggestions (banner, reviews, UGC, countdown, etc.)
- CTA button text

### For Creator/Story Emails, Also Include:
- PS section with CTA
- Suggested email angle name
- TIMER currency targeted
- Four Lenses perspective used
