---
name: Design Critique
description: "Systematic critique methodology, Shift Nudge critique patterns, typography/color/layout/spacing fixes, before/after examples, portfolio review, design taste development, design workflow checklist. FOR: design review, critique, design audit, what's wrong with my design, improve design, feedback, portfolio review, design taste, common design mistakes, before/after, iteration, design checklist, visual harmony. MANDATORY TRIGGERS: design review, critique, what's wrong, improve design, audit website, feedback, portfolio review, design taste, design eye, design mistakes, design checklist, visual harmony, iterate. Do NOT use for animation specifics -- use webflow-animations. Do NOT use for Webflow build issues -- use webflow-build. Do NOT use for Figma component setup -- use design-systems."
---

# Design Critique

Systematic design review methodology synthesized from Shift Nudge's Critique Vault (273+ video reviews, 1000+ critique patterns), Flux Academy's design taste framework, and Flux/Ran Segall's design workflow checklist. This skill teaches you how to identify problems, categorize them, and provide actionable fixes -- plus how to develop your design eye over time.

---

## WHEN TO USE THIS SKILL

- Reviewing your own designs before client handoff
- Giving peer feedback to other designers
- Analyzing competitor or reference websites
- Improving existing websites or apps
- Preparing designs for client review
- Building a design portfolio (structure and presentation)
- Developing design taste and visual judgment
- Running a systematic design audit with checklist

---

## THREE-PHASE CRITIQUE PROCESS

### Phase 1: Holistic Assessment (5 minutes)

Look at the entire design without analysis. Record gut reactions:
- Does it feel professional and polished?
- Does it feel trustworthy and credible?
- Is navigation obvious?
- Is there a clear visual hierarchy?

**Do not analyze yet.** First impressions reveal what users will feel.

### Phase 2: Systematic Analysis (15-20 minutes)

Work through each category using the decision tree below. Rate each area 1-5.

### Phase 3: Synthesis & Recommendations (10 minutes)

Prioritize 3-5 highest-impact fixes. Map each to a specific problem from systematic review.

---

## DECISION TREE: BIGGEST PROBLEM FIRST

```
Looking at the design...

1. Can you read the text easily?
   NO -> TYPOGRAPHY AUDIT (size, weight, line height, contrast)
   YES -> continue

2. Does color feel intentional?
   NO -> COLOR AUDIT (contrast, consistency, semantic meaning)
   YES -> continue

3. Does everything feel well-spaced?
   NO -> SPACING AUDIT (padding, gaps, breathing room)
   YES -> continue

4. Are similar components styled the same?
   NO -> COMPONENT AUDIT (buttons, cards, inputs consistency)
   YES -> continue

5. Is the most important thing visually dominant?
   NO -> HIERARCHY AUDIT (focal point, emphasis, visual weight)
   YES -> Design is solid; look for micro-refinements
```

---

## TYPOGRAPHY AUDIT

### Critical Checks

| Check | Target | Common Failure |
|-------|--------|----------------|
| Font sizes | 3-4 max per screen [MDS Rule of Four] | 5+ sizes destroying hierarchy |
| Font weights | Headlines heavier than body | Body heavier than headlines |
| Line height | 150%+ for body copy | Tight line height (<125%) = unreadable |
| Character width | 45-75 chars per line (sweet spot: 55-65) | >80 chars = eye fatigue |
| Contrast | 4.5:1 minimum (AA); 7.0:1 preferred (AAA) | Light gray on white = fails |

### Extending Hierarchy Without Adding Sizes [MDS]

When you've hit your size limit, differentiate with:
- **Color change:** Same size, different color = different meaning
- **Weight change:** Same size, different weight = different meaning
- **Position change:** Same size, different position = different meaning
- **Decoration:** Underline or background color for interactive signaling

### Common Typography Mistakes (from Critique Vault)

1. **5+ font sizes** -- Consolidate to 3-4 max; use weight/color for further hierarchy
2. **Light text on light background** -- Test contrast; aim for 7.0:1
3. **Inconsistent line heights** -- Standardize: titles 100-120%, body 150-160%
4. **No weight hierarchy** -- Headlines bold/semi-bold, body regular
5. **Orphan words** -- Single word on new line; reflow or expand container
6. **Body text heavier than titles** -- Clear weight gradient from headlines down

For detailed critique patterns with before/after examples, read `references/02-common-mistakes-vault.md`.

---

## COLOR & CONTRAST AUDIT

### Critical Checks

| Check | Target | Common Failure |
|-------|--------|----------------|
| Contrast ratio | 4.5:1 body text; 3.0:1 large text | Brand color + white text = only 3.0 |
| Text color consistency | Max 2-3 text colors throughout | Different grays per page |
| Semantic meaning | Red = error, green = success, blue = info | Green "delete" button |
| Neutral palette | 2-3 grays defined | 6+ arbitrary shades of gray |
| 60-30-10 rule | 60% dominant, 30% secondary, 10% accent | Colors competing equally |

### Common Color Mistakes (from Critique Vault)

1. **Insufficient contrast** -- Gray text on white fails accessibility; test with colorable.com
2. **Too many colors** -- Stick to 60-30-10 rule
3. **Brand color as text** -- If brand color is bright, use as background with dark text, not as text color
4. **Too many grays** -- Lock in 3: light (backgrounds), medium (borders), dark (text)
5. **Inaccessible disabled states** -- Use 4.5:1 minimum if communicating; or make obviously grayed

For detailed color patterns, read `references/02-common-mistakes-vault.md`.

---

## LAYOUT & SPACING AUDIT

### Critical Checks

| Check | Target | Common Failure |
|-------|--------|----------------|
| Alignment | All elements on invisible grid | Random positioning |
| Section spacing | 60-100px between major sections minimum | 20px padding = cramped |
| Vertical rhythm | Consistent spacing between sections | 40px, 80px, 20px = inconsistent |
| Hierarchy through spacing | Most important content most isolated | Primary elements crammed with secondary |
| Component padding | Consistent across same-type components | Button #1: 16px, Button #2: 20px |

### Spacing Relationship Scale [MDS]

| Relationship | Spacing |
|-------------|---------|
| Related elements | 4-8px apart |
| Loosely related | 12-16px |
| Section breaks | 24-40px |
| Major divisions | 48-80px+ |
| Component internal padding | 12-20px |
| Module margin from screen edge | 16-20px (mobile), 40-60px (desktop) |

### Common Spacing Mistakes (from Critique Vault)

1. **Coffin box effect** -- Small content in large box with uniform padding; padding should scale with content size
2. **Missing breathing room between sections** -- Add 80-100px margin between major sections
3. **Unequal horizontal/vertical padding** -- Cards with 40px top/bottom but 12px sides
4. **Grid misalignment** -- Container width not divisible by grid (use 1440px or 1200px)
5. **Arbitrary margins** -- Random spacing (13px, 27px) instead of system (8, 16, 24, 32)

---

## COMPONENT CONSISTENCY AUDIT

### Critical Checks

- All buttons (primary, secondary, sizes) styled consistently
- All cards follow the same internal structure
- All form inputs: same height, padding, border style
- All icons consistently sized
- Hover, active, disabled states defined and consistent

### Common Component Mistakes (from Critique Vault)

1. **Multiple button styles for same action** -- Define once; only color/weight vary
2. **Card heights inconsistent** -- Set fixed height with truncation for variable content
3. **Form input chaos** -- Text 44px, select 36px, textarea 40px -- standardize all at same height
4. **Mixed icon sizes** -- Lock in one or two sizes; use consistently
5. **Border radius inconsistency** -- Some 4px, others 8px; establish one system value

---

## HIERARCHY VERIFICATION

### The Squint Test

Squint at the design until it blurs. Can you still identify:
1. The most important element (headline, hero image, CTA)?
2. The primary action (main button)?
3. The grouping of content sections?

If everything blurs into equal visual weight, hierarchy has failed.

### Hierarchy Through Multiple Properties [MDS + Flux]

**Weak hierarchy:** Only size differs (48px, 42px, 36px, 16px -- all same weight and color)

**Strong hierarchy:** Size + weight + color all differentiate levels:
- H1: 48px bold #000
- H2: 32px semi-bold #333
- H3: 24px regular #666
- Body: 16px regular #999

**Principle [Flux]:** Seven tools for establishing hierarchy -- order, spacing/isolation, alignment shift, value/weight, color, scale, enclosure/notation. Use 2-3 per hierarchy level for dramatic contrast.

---

## DESIGN WORKFLOW CHECKLIST [Flux]

For any design project, verify before handoff:

**Layout:**
- [ ] Clear hierarchy established
- [ ] Focal point identified and intentionally placed
- [ ] Related elements grouped; unrelated elements separated
- [ ] Deliberate alignment throughout (no random placement)
- [ ] Visual balance achieved (symmetric or asymmetric)
- [ ] Scale variation creates interest (big-medium-small)
- [ ] Adequate white space for breathing room
- [ ] Sequential scroll experience considered

**Typography:**
- [ ] Body copy: legible font, 130% leading, 7-15 word line length, left-aligned
- [ ] Headlines: dramatic size contrast (multiples), 100% leading, optical kerning
- [ ] Font pairing: max 3 typefaces, distinct but complementary
- [ ] Single emphasis method per instance (no bold+italic+underline)
- [ ] Proper typographic details (real italics, proper quotes)

**Color:**
- [ ] Dominant hue selected by rationale (psychology + associations)
- [ ] Saturation/brightness finessed for appropriate tone
- [ ] Palette tones matched across colors
- [ ] Contrast checked for accessibility (4.5:1 minimum body text)
- [ ] Competitor colors considered for differentiation

**Imagery:**
- [ ] High quality, relevant photographs
- [ ] Consistent photography/illustration style
- [ ] Crops are intentional
- [ ] Images support hierarchy (not compete with it)

**Visual Harmony [Flux]:**
- [ ] Everything belongs in the same "world" (World Test)
- [ ] Consistent element system (shapes, styles, patterns)
- [ ] Fonts, colors, imagery, layout all point in same direction
- [ ] No anachronisms (modern element in retro design or vice versa)

---

## DEVELOPING DESIGN TASTE [Flux]

### Five Methods to Improve Your Design Eye

1. **Improve your visual diet** -- quality in = quality out. Upgrade from social media scrolling to design books, magazines, quality blogs
2. **Gather stylistic references** -- collect visuals that resonate (even if you don't know why). Patterns will emerge
3. **Learn the language** -- vocabulary lets you precisely identify what's happening (hierarchy, focal point, tracking, leading, tones)
4. **Play art director** -- describe, then analyze good and bad work. Ask: how could this be improved?
5. **Find your influences' influences** -- trace back: Beirut led to Vignelli; Saville led to Tschichold. [CONTRARIAN] Old masters contain depth not found in endless scrolling

### Visual Harmony Framework (The World Test) [Flux]

Think like a TV production designer. Everything must look like it belongs in the same world.

**Three steps:**
1. Define the era, mood, aesthetic territory
2. Establish consistent elements and reuse them (if using triangles, don't randomly introduce circles)
3. Analyze cross-element compatibility -- do fonts work with images? Does palette match photography style?

### Creativity Process [Flux] [CONTRARIAN]

Big ideas are NOT inside the computer. Don't scroll feeds hoping for inspiration.

**Process:**
1. Research the brief thoroughly
2. Write your idea in words first -- before touching software
3. Sketch rough, small, fast on paper
4. Verbs lead to graphic approaches; adjectives lead to decorative styles

### Anti-Trend Philosophy [Gareis] [CONTRARIAN]

"Design trends are shit." Focus on principles that endure (hierarchy, typography, contrast, spacing) rather than current visual fashions. Trends date your work; principles make it timeless.

---

## PORTFOLIO REVIEW FRAMEWORK [Flux]

### Portfolio Structure (One-Pager)

| Section | Purpose |
|---------|---------|
| 1. Navigation | Name/logo + links |
| 2. Hero | Photo + headline + CTA (answer in 3 seconds: what do you do? why care? next step?) |
| 3. Work showcase | 2-4 projects with exceptional hero images |
| 4. Process/services/values | Pick ONE angle; keep brief |
| 5. Testimonials | What it's LIKE working with you |
| 6. About | Who you are, background, skills |
| 7. Contact CTA | Clear next step |
| 8. Footer | Links, social |

### Portfolio Hero Messaging [Flux]

Three headline templates:
1. **Client-goal:** "Helping [client type] achieve [their goal]"
2. **Belief-based:** "[What you do] for [who] who believe [shared value]"
3. **Differentiation:** "[What you do] + [how it's different]"

Headline specs: 9-14 words ideal. Subheading expands with one sentence.

### Showcasing Work [Flux] [CONTRARIAN]

Do NOT create lengthy case studies with process images. Most clients judge quality in 1-2 seconds from the visual. Focus on making one hero image per project look exceptional.

**Mockup approaches:**
- Scene generator mockups (custom PSD with device mockups, color-matched backgrounds)
- Simple elevated screenshots (complementary background sampled from project, subtle shadow, slight rotation)

### Conceptual Projects [Flux] [CONTRARIAN]

High-quality concept work showing the work you WANT to attract is better than real but uninspiring client projects. Treat with same professionalism as paid work. Your portfolio is your most powerful filter.

For detailed portfolio and taste guidance, read `references/03-developing-taste.md`.

---

## CROSS-CUTTING PRINCIPLES [MDS]

### The Iteration Loop
Design > Review > Adjust > Repeat. Never ship first draft. Make copies before major changes. Zoom out for composition, zoom to 100% for readability. Check on actual device.

### The Restraint Principle
Fewer font sizes, fewer colors, fewer grays = cleaner design. Constraints force creative use of weight, color, position.

### The System-Building Process
1. Explore freely (messy, unnamed)
2. Find something that works
3. Abstract patterns into components/styles
4. Define the system (document sizes, colors, spacing)
5. Apply consistently
6. Revise as needed

### The Presentation Principle
If you can't explain WHY every color/size/weight exists, the system isn't complete. "This works because..." is infinitely more compelling than "I think this looks good."

---

## WHEN TO READ REFERENCES

| Reference File | Read When |
|---------------|-----------|
| `01-critique-methodology.md` | Running a full design audit; need systematic process |
| `02-common-mistakes-vault.md` | Looking up specific mistake patterns; need before/after fixes |
| `03-developing-taste.md` | Improving design eye; portfolio building; creativity process |

---

## RELATED SKILLS

- **typography-systems:** For deep typography rules when audit reveals type issues
- **color-systems:** For color theory and palette construction when audit reveals color issues
- **layout-spacing:** For grid systems and spacing values when audit reveals layout issues
- **ui-components:** For component patterns when audit reveals consistency issues
- **web-layout:** For page structure when audit reveals structural issues
- **logo-brand-identity:** When reviewing logo designs specifically
