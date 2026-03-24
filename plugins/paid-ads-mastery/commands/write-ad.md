---
name: Write Ad
description: Generate ad copy, video scripts, AI ad scripts, or Google assets. Asks platform, product, audience, awareness level, and format, then produces ready-to-use creative using the appropriate skill.
---

# /write-ad -- Ad Copy & Creative Generator

## INTAKE QUESTIONS (Ask All Before Writing)

### Question 1: Platform & Format
**What platform and format do you need?**

| Choice | Skill Activated |
|--------|----------------|
| A) Meta/Facebook/Instagram -- **static ad copy** | `create-ad-copy` |
| B) Meta/Facebook/Instagram -- **video script** | `create-video-ads` |
| C) Meta/Facebook/Instagram -- **AI-generated video** | `create-ai-ads` |
| D) Google -- **RSA headlines/descriptions** | `create-google-assets` |
| E) Google -- **Shopping product titles** | `create-google-assets` |
| F) Google -- **YouTube ad script** | `create-google-assets` |
| G) Google -- **PMax asset group** | `create-google-assets` |
| H) TikTok -- **video ad** | `create-video-ads` + `strategy-tiktok-ads` |

### Question 2: Product/Service
**Describe your product/service in 2-3 sentences. Include:**
- What it does
- Price point (or range)
- Key differentiator vs. competitors

### Question 3: Target Audience
**Who is this ad targeting?**
- Age range, gender (if relevant)
- Primary pain point or desire
- What they've tried before that didn't work

### Question 4: Awareness Level
**Where is your audience on the awareness spectrum?**
- **Unaware:** Don't know they have a problem
- **Problem-aware:** Know the problem, not the solution
- **Solution-aware:** Know solutions exist, haven't chosen one
- **Product-aware:** Know your product, haven't decided
- **Most-aware:** Ready to buy, need a push

### Question 5: Creative Context
**Any additional context?**
- Existing winning ads to reference?
- Specific angles to test?
- Seasonal/promotional element?
- Tone preference? (humor, serious, educational, aspirational)

---

## GENERATION PROCESS

### For Static Ad Copy (Choice A)
1. Load `create-ad-copy` SKILL.md
2. Select copy template based on awareness level:
   - Unaware/Problem-aware: Long-form or bullet template
   - Solution-aware/Product-aware: Bullet or short-form template
   - Most-aware: Short-form template
3. Apply emotional sandwich framework (emotional > logical > emotional)
4. Select 1-2 persuasion principles from ref-copy-psychology
5. Write hook text using condensing technique
6. Generate: Primary text + Headline + Description
7. Include 3 headline variations for testing

### For Video Scripts (Choice B)
1. Load `create-video-ads` SKILL.md
2. Select video framework based on product/audience:
   - Older audience + complex product: Mini VSL
   - Standard DR: Single-Creator UGC
   - Social proof heavy: UGC Mashup
   - Visual product: Non-Narrated UGC
3. Select script framework based on awareness level
4. Write full script with visual directions and timing
5. Include 3 hook variations
6. Add demographic-appropriate pacing notes

### For AI Video Ads (Choice C)
1. Load `create-ai-ads` SKILL.md
2. Write script using appropriate template (clone, UGC-style, or seasonal)
3. Break into 8-second segments for Google Flow
4. Include Whisk scene descriptions for each segment
5. Add visual direction notes for each scene
6. Include editing notes for CapCut assembly

### For Google RSA (Choice D)
1. Load `create-google-assets` SKILL.md
2. Extract 6 message angles from product info
3. Write 6-8 headlines using the 7 types framework
4. Write 2-3 descriptions (80-90 chars each)
5. All headlines 25-30 characters
6. Include DKI for relevance anchor headline

### For Shopping Titles (Choice E)
1. Load `create-google-assets` ref-google-shopping-titles
2. Identify search terms and rank by volume
3. Apply left-to-right importance rule
4. Generate title (70-100 chars sweet spot)
5. Write original product description (100-200 words)

### For YouTube Scripts (Choice F)
1. Load `create-google-assets` ref-google-youtube-scripts
2. Apply 7 must-have elements framework
3. Write 1.5-3 minute script with all elements
4. Include The One Thing golden thread throughout
5. Hook in first 5 seconds (before skip button)

### For PMax Assets (Choice G)
1. Load `create-google-assets` ref-google-pmax-assets
2. Generate: 5 headlines + 5 long headlines + 5 descriptions
3. Include image direction notes
4. Include video concept brief
5. Ensure assets work across all PMax placements

---

## OUTPUT FORMAT

Every output must include:

1. **The creative itself** (copy, script, or assets)
2. **3 variations** of the hook/headline for testing
3. **Awareness level label** (confirms the audience match)
4. **Recommended testing approach** (from test-creative skill)
5. **Cross-reference note** if research-creative should be run first
