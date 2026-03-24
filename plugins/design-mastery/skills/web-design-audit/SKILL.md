---
name: Web Design Audit
description: "Systematic design critique methodology, 1000+ real critique patterns from Shift Nudge, typography/color/layout/spacing fixes, before/after examples. MANDATORY TRIGGERS: design review, critique, what's wrong, improve design, audit website, feedback. Do NOT use for animation specifics — use animation-interactions instead. Do NOT use for build — use webflow-implementation instead."
---

## Web Design Audit

A systematic approach to reviewing and critiquing digital designs using proven methodology from 1000+ real design critiques. This skill teaches you how to identify problems, categorize them, and provide actionable fixes.

## When You Need This Skill

- Reviewing your own designs before handoff
- Giving peer feedback to other designers
- Analyzing competitor or reference websites
- Improving existing websites or apps
- Preparing designs for client feedback
- Learning what makes designs effective

## Core Audit Methodology

### Three-Phase Critique Process

**Phase 1: Holistic Assessment (5 minutes)**
Look at the entire design without analysis. Does it feel:
- Professional and polished?
- Trustworthy and credible?
- Easy to navigate?
- Visually appealing?

Take notes on your gut reaction before diving into details.

**Phase 2: Systematic Analysis (15-20 minutes)**
Work through each category systematically using the checklists below. Rate each area 1-5 (1 = major issues, 5 = excellent).

**Phase 3: Synthesis & Recommendations (10 minutes)**
Prioritize 3-5 highest-impact fixes. Map them to specific problems from your systematic review.

---

## Typography Audit Checklist

### Critical Questions

- [ ] **Font sizes:** Are there 4 or fewer distinct sizes? ✓ = 1 size, ❌ = 6+ sizes
  - Measure: H1, H2, H3, body, small text — count unique values
  - Problem: Too many sizes = destroyed hierarchy
  - Fix: Consolidate to 3-4 sizes max

- [ ] **Font weights:** Do headlines use heavier weight than body?
  - Check: Headline weight > body weight
  - Problem: Body text heavier than headlines = hierarchy failure
  - Fix: Ensure clear weight differentiation

- [ ] **Line height:** Does body text have 150%+ line height?
  - Measure: Body copy line height (should be 125%-220%, sweet spot 150%)
  - Problem: Tight line height (< 125%) = readability suffers
  - Fix: Increase to 150%-160% for comfortable reading

- [ ] **Character width:** Does body copy fit 45-75 characters per line?
  - Count: Characters from start to end of line
  - Problem: Too wide (> 80 chars) = eye fatigue, too narrow (< 40) = awkward breaks
  - Fix: Constrain with max-width or adjust container width

- [ ] **Color contrast:** Does text pass 4.5:1 minimum contrast ratio?
  - Test: Use colorable.com or Figma contrast plugin
  - Problem: Light gray on white = unreadable, especially for vision-impaired
  - Fix: Darken text or lighten background to reach 4.5:1+ (aim for 7.0 for excellence)

### Real Critique Patterns (From 1000+ Reviews)

**Typography Pattern #1: "Five Different Title Sizes"**
- **Problem:** H1=56px, H2=48px, H3=36px, H4=28px, H5=18px (5 levels!)
- **Root cause:** Designer treating semantic HTML tags (H1-H5) as design sizes
- **Fix:** Pick 3-4 sizes max. Use weight/color/spacing for further hierarchy, not size
- **Example:** 48px (H1), 32px (H2), 16px (body) — only 3 sizes, clear hierarchy

**Typography Pattern #2: "Body Text in Light Gray"**
- **Problem:** #999999 text on white background = 2.8:1 contrast (fails AA)
- **Root cause:** "Light" gray looks trendy but fails accessibility
- **Fix:** Use #757575 or darker for 4.5:1 minimum
- **Test:** colorable.com — #999999 on #FFFFFF = fails; #757575 on #FFFFFF = passes

**Typography Pattern #3: "No Visual Weight Hierarchy"**
- **Problem:** Title and body at same size, same weight, different color only
- **Root cause:** Assuming color difference creates hierarchy
- **Fix:** Use size OR weight (preferably both): 32px bold title + 16px regular body
- **Impact:** Clear, immediate hierarchy without effort

**Typography Pattern #4: "Tiny Text in Big Spaces"**
- **Problem:** 12px metadata text floating in generous 200px² of whitespace
- **Root cause:** Padding applied uniformly; no relationship between text size and breathing room
- **Fix:** Reduce padding for small text, increase for large text
- **Principle:** Large text needs large surrounding space; small text can live in tighter areas

---

## Color & Contrast Audit Checklist

### Critical Questions

- [ ] **Contrast testing:** Have all text colors been tested against their backgrounds?
  - Method: colorable.com, enter hex codes
  - Required minimum: 4.5:1 for body text
  - Preferred: 7.0:1 for body text + titles
  - Problem: Brand color (bright orange) + white text = only 3.0 contrast
  - Fix: Darken text or use different background color

- [ ] **Color consistency:** Are text colors consistent throughout (same dark gray for all body)?
  - Check: Should be max 2-3 text colors (primary dark, secondary medium, accent)
  - Problem: Different grays for body text across pages = incoherent brand
  - Fix: Create 2-3 text color styles; use consistently

- [ ] **Semantic color usage:** Do colors carry meaning accurately?
  - Error states: Red? Success: Green? Warning: Orange?
  - Problem: Green button with "delete" = confusing, contradicts expectation
  - Fix: Align color meaning (danger=red, success=green, info=blue)

- [ ] **Neutral palette:** Does the design use 2-3 neutral grays?
  - Count unique grays for backgrounds, borders, disabled states
  - Problem: 6+ shades of gray = confusion, looks unplanned
  - Fix: Define 3 grays: light (backgrounds), medium (borders), dark (text)

### Real Critique Patterns (From 1000+ Reviews)

**Color Pattern #1: "Insufficient Contrast on Accent Color"**
- **Problem:** Bright orange primary color (#FF6B35) + white text = 3.1:1 contrast (fails AA)
- **Root cause:** Brand color is vibrant, not high contrast
- **Fix:** Dark text on orange background = 5.2:1 (passes). OR use orange only for backgrounds, not text
- **Rule:** If brand color is bright, use it as background with dark text, not light text on white

**Color Pattern #2: "Too Many Grays"**
- **Problem:** #999999, #888888, #777777, #666666, #AAAAAA used throughout
- **Root cause:** Designer picked grays arbitrarily without system
- **Fix:** Lock in 3: #999999 (light), #666666 (medium), #333333 (dark). Use only these
- **Impact:** Looks more intentional and cohesive

**Color Pattern #3: "Green Success Button, Red Cancel"**
- **Problem:** ✓ Green (success) button, ✗ Red (danger) button in same form
- **Root cause:** Reversed expectations — red usually means "stop" or "delete"
- **Fix:** Green = confirm, Red = delete/cancel. Make meaning obvious through color
- **Principle:** Color psychology matters for UX

**Color Pattern #4: "Inaccessible Disabled State"**
- **Problem:** Disabled input at #CCCCCC on white = 2.1:1 (fails even as decorative element)
- **Root cause:** Designer made disabled state too light to indicate "off"
- **Fix:** Disabled state should be #A6A6A6 (4.5:1) if it needs to communicate. Or truly invisible (no contrast needed)
- **Rule:** Disabled states can skip contrast IF they're obviously disabled (much lighter/grayed)

---

## Layout & Spacing Audit Checklist

### Critical Questions

- [ ] **Alignment:** Are all elements aligned to invisible grid?
  - Check: Select multiple elements; do left edges align? Content horizontally centered?
  - Problem: Random positioning = chaotic, unprofessional
  - Fix: Snap all elements to 8px or 16px grid

- [ ] **Negative space:** Does the design feel cramped or breathable?
  - Visual test: Pour water on design — would it flow smoothly?
  - Problem: 20px padding top/bottom between sections = cramped
  - Fix: Increase to 60-80px+ between major sections
  - Principle: More space = premium feeling

- [ ] **Vertical rhythm:** Do sections have consistent spacing?
  - Measure: Top padding of one section should match bottom padding of previous
  - Problem: First section 40px padding, second 80px, third 20px = inconsistent
  - Fix: Establish spacing scale (e.g., all sections: 80px top/bottom)

- [ ] **Hierarchy through spacing:** Is the most important content most isolated?
  - Check: Primary CTA should have generous surrounding space
  - Problem: Important elements crammed together with secondary content
  - Fix: Give primary elements breathing room; nest secondary items closer

- [ ] **Component spacing consistency:** Do buttons, cards, inputs use consistent padding?
  - Measure: Button padding (16px vert × 24px horiz everywhere?)
  - Problem: Button #1 has 16px padding, Button #2 has 20px = inconsistency
  - Fix: Define padding rules once, apply everywhere

### Real Critique Patterns (From 1000+ Reviews)

**Spacing Pattern #1: "Coffin Box Effect"**
- **Problem:** Small content in large box with 40px padding all sides
- **Root cause:** Padding applied uniformly without considering content size
- **Fix:** Padding should scale: 64px for large content (H1), 16px for small metadata
- **Principle:** Padding ratio = content size ratio

**Spacing Pattern #2: "Missing Breathing Room Between Sections"**
- **Problem:** Hero section (padding: 40px), then immediately Features section (no gap)
- **Root cause:** Designer only set internal padding, forgot inter-section margins
- **Fix:** Add 80-100px margin-bottom to hero OR margin-top to features section
- **Rule:** 60-100px gap between major sections minimum

**Spacing Pattern #3: "Unequal Horizontal/Vertical Padding"**
- **Problem:** Card has 40px padding top/bottom, 12px left/right
- **Root cause:** Designer focused on desktop width, ignored vertical balance
- **Fix:** More balanced: 24px all sides, or 32px top/bottom + 24px left/right
- **Principle:** Padding should feel intentional, not accidental

**Spacing Pattern #4: "Grid Misalignment"**
- **Problem:** Elements snap to 8px grid on desktop, but center column offset by 3px
- **Root cause:** Container width not divisible by grid (e.g., 1441px width, 8px grid doesn't divide evenly)
- **Fix:** Use 1440px width or 1200px — clean grid multiples
- **Test:** Check component alignment in Figma; should snap without remainder

---

## Component Consistency Audit

### Critical Questions

- [ ] **Button styling:** Are all buttons (primary, secondary, sizes) styled consistently?
  - Check: Primary buttons have consistent bg color, text color, padding, border radius
  - Problem: "Sign up" button is 48px tall, "Download" button is 36px tall (arbitrary)
  - Fix: Define button sizes: small (32px), medium (40px), large (48px); use consistently

- [ ] **Card patterns:** Do all cards follow the same internal structure?
  - Pattern: Image > title > description > CTA (same order everywhere)
  - Problem: Some cards have image at top, others on left; inconsistent
  - Fix: Pick one pattern; apply to all cards

- [ ] **Form inputs:** Do all text inputs have same height, padding, border style?
  - Measure: Height (should be 40-44px), padding (12px sides), border (1px)
  - Problem: Login form inputs 44px tall, contact form inputs 36px tall = inconsistent
  - Fix: Lock in one size for all inputs

- [ ] **Icon sizing:** Are icons (social, UI) consistently sized?
  - Problem: Social icons in footer 20px, in header 24px, in sidebar 18px
  - Fix: Pick one size (20px, 24px) and use everywhere (or scale by area, but consistently)

### Real Critique Patterns (From 1000+ Reviews)

**Component Pattern #1: "Two Button Styles (Actually Three)"**
- **Problem:** Primary button (bg: blue, radius: 4px), Secondary button (bg: white, radius: 4px), CTA button (bg: blue, radius: 8px)
- **Root cause:** Designer evolved button style mid-project, didn't update throughout
- **Fix:** Define once: Primary (blue, 4px), Secondary (white, 4px), Loading state (blue, 4px, spinner)
- **System:** All buttons same border-radius; only color/weight vary

**Component Pattern #2: "Card Heights Inconsistent"**
- **Problem:** Product cards auto-height with variable descriptions (card 1 = 240px, card 2 = 180px, card 3 = 310px)
- **Root cause:** Content-driven heights; no fixed card system
- **Fix:** Set fixed card height (280px) with 3-line max description; truncate excess
- **Principle:** Cards should look cohesive even with variable content

**Component Pattern #3: "Form Input Chaos"**
- **Problem:** Text input 44px tall, select dropdown 36px, textarea 40px (all different!)
- **Root cause:** Each component built independently
- **Fix:** All form elements 40px height minimum (or standardize on 44px)
- **Benefit:** Inputs aligned horizontally without weird gaps

---

## Hierarchy Verification

### Critical Questions

- [ ] **Visual importance order:** Can you instantly identify the most important element?
  - First glance: Is it the headline? Hero image? CTA button? Or equally confusing?
  - Problem: Multiple large headlines at similar size = no clear focal point
  - Fix: Make the single most important element visually dominant

- [ ] **Primary action visibility:** Can users instantly see the primary CTA?
  - Check: Is primary button bigger, bolder, more prominent than secondary options?
  - Problem: "Sign up" and "Learn more" buttons same size/color = unclear
  - Fix: Primary button larger, darker, more color contrast

- [ ] **Secondary content de-emphasized:** Is supporting info visually lighter?
  - Examples: Metadata (dates, read time) should be smaller, lighter gray, less prominent
  - Problem: Small metadata text same size/weight as content headlines
  - Fix: Use 12-14px for metadata, much lighter gray (#999999 range)

### Real Critique Patterns

**Hierarchy Pattern #1: "Equal Visual Weight Throughout"**
- **Problem:** H1 (48px, #333), H2 (42px, #333), H3 (36px, #333), body (16px, #333) — only size differs
- **Root cause:** Designer relied solely on size; no weight or color variation
- **Fix:** H1 (48px bold #000), H2 (32px semi-bold #333), H3 (24px regular #666), body (16px regular #999)
- **Impact:** Hierarchy becomes crystal clear

**Hierarchy Pattern #2: "CTA Button Lost Among Navigation**
- **Problem:** Primary CTA "Buy now" (40px button, blue) surrounded by navigation links (18px text, blue)
- **Root cause:** Button not visually dominant enough
- **Fix:** Make button 48px, darker blue, add shadow for depth; navigation links stay at 16px, lighter color
- **Principle:** Primary action should be 1.5-2x visual weight of secondary actions

---

## Common Mistakes by Category

### Typography Mistakes (Most Frequent)

1. **5+ font sizes** — Consolidate to 3-4 max
2. **Light text on light background** — Test contrast, aim for 7.0:1
3. **Inconsistent line heights** — Standardize: titles 100-120%, body 150-160%
4. **No weight hierarchy** — Make headlines bold/semi-bold, body regular
5. **Orphan words** — Single word on new line due to narrow width; reflow or expand container

### Color Mistakes (Common)

1. **Insufficient contrast** — Gray text on white fails accessibility; test ratio
2. **Too many colors** — Stick to 60-30-10 rule (60% dominant, 30% secondary, 10% accent)
3. **Disabled states too subtle** — Use 4.5:1 minimum or make obviously grayed out
4. **No semantic meaning** — Success states not green, errors not red = confusing
5. **Brand color as primary text** — Bright brand color + white text fails contrast; use on backgrounds instead

### Spacing Mistakes (Very Common)

1. **Cramped sections** — 20-40px padding between sections feels cheap; increase to 60-100px
2. **Inconsistent padding** — Card #1 has 20px padding, Card #2 has 24px; lock it in
3. **Missing breathing room for large text** — 48px headline needs 80px+ surrounding space, not 40px
4. **Arbitrary margins** — Random spacing (13px, 27px, 42px) instead of system (8, 16, 24, 32...)
5. **Unequal horizontal/vertical padding** — Button text feels cramped; balance padding on all sides

### Layout Mistakes (Structural)

1. **No clear focal point** — Important content not visually dominant
2. **Unaligned elements** — Items scattered, not on grid = chaotic
3. **Inconsistent column grid** — Desktop 12 columns, tablet inconsistent → layout breaks
4. **Full-width text too long** — Line length exceeds 75 characters; constrain container width
5. **Mobile = desktop shrunk** — Content hidden or made unreadable; redesign for mobile instead

### Component Mistakes (Consistency)

1. **Multiple button styles for same action** — Primary button changes style page-to-page
2. **Inconsistent form input heights** — Text input 44px, select 36px; standardize
3. **Cards with auto-heights** — Variable descriptions make card heights uneven; truncate with max-lines
4. **Icons in multiple sizes** — Social icons 20px in one place, 32px elsewhere
5. **Border radius inconsistency** — Some components 4px, others 8px, no system

---

## Real Before/After Examples

### Example 1: Poor Typography → Excellent Typography

**Before:**
- 6 font sizes: 56px, 48px, 42px, 36px, 20px, 14px
- All same weight (regular)
- Body text: #999999 gray on white (2.8:1 contrast, fails)
- Line height: 100% for body (unreadable)
- Character width: 120 characters per line (eye fatigue)

**After:**
- 3 font sizes: 48px (H1), 32px (H2), 16px (body)
- Weight hierarchy: bold H1, semi-bold H2, regular body
- Body text: #333333 on white (8.5:1 contrast, AAA pass)
- Line height: 150% for body (comfortable reading)
- Character width: 65 characters per line (optimal)

**Impact:** Clear hierarchy, readable, professional

---

### Example 2: Cramped Layout → Breathable Layout

**Before:**
- Hero section: 40px padding top/bottom
- Features section: 40px padding top/bottom
- No gap between sections
- All content feels squeezed together

**After:**
- Hero section: 80px padding top/bottom
- Gap between sections: 100px (margin-bottom on hero)
- Features section: 80px padding top/bottom
- Content feels spacious, premium

**Impact:** Same content, but feels 3x more luxurious

---

### Example 3: Inconsistent Components → Cohesive System

**Before:**
- Primary buttons: 40px height, 16px padding horiz, 6px border-radius, blue bg
- Secondary buttons: 36px height, 12px padding horiz, 2px border-radius, white bg
- Form inputs: 44px height (text), 36px height (select), 40px height (textarea)

**After:**
- All buttons: 40px height, 16px padding horiz, 4px border-radius; color varies
- All form inputs: 40px height, 12px padding horiz, 4px border-radius
- Single system applied everywhere

**Impact:** Cohesive, predictable, professional

---

## Contrarian Insights (When Rules Can Break)

**Rule: 4 sizes max**
Exception: Complex content system (blog, docs) might use 5-6 sizes intentionally. OK if justified.

**Rule: Light/thin fonts only at scale (60px+)**
Exception: Designer uses light font at 24px intentionally for aesthetic. Risk: readability suffers; test with users.

**Rule: Contrast minimum 4.5:1**
Exception: Decorative elements (not functional) can use 3:1 or lower. Example: watermark text.

**Rule: Padding should scale with content size**
Exception: Some designs use consistent padding everywhere. OK if intentional, but watch for "coffin box" effect.

---

## Decision Tree: "What's the Biggest Problem Here?"

```
Looking at design...

1. Does it look like it uses color intentionally?
   → NO → Check COLOR AUDIT → contrast, consistency, semantic meaning
   → YES → Continue

2. Can you read the text easily?
   → NO → Check TYPOGRAPHY AUDIT → size, weight, line height, contrast
   → YES → Continue

3. Does everything feel well-spaced?
   → NO → Check SPACING AUDIT → padding, gaps, breathing room
   → YES → Continue

4. Are all similar components styled the same?
   → NO → Check COMPONENT AUDIT → buttons, cards, inputs, consistency
   → YES → Continue

5. Is the most important thing visually dominant?
   → NO → Check HIERARCHY AUDIT → focal point, emphasis, visual weight
   → YES → Design is solid; look for micro-refinements
```

---

## Quick Reference Metrics

### Typography Standards
| Element | Desktop | Mobile | Check |
|---------|---------|--------|-------|
| H1 | 48-96px | 32-48px | 4:1 ratio min |
| H2 | 32-48px | 28-32px | Clear from H1 |
| H3 | 24-32px | 20-24px | Clear from H2 |
| Body | 16-18px | 14-16px | NEVER below 14px |
| Small | 12-14px | 12-13px | Metadata only |
| **Line Height** | 100-150% (titles) | 150-160% (body) | Body must be 150%+ |

### Spacing Scale
- Micro: 4px, 8px
- Small: 12px, 16px
- Medium: 24px, 32px
- Large: 40px, 60px, 80px, 100px+

### Contrast Ratios
- **Minimum (AA):** 4.5:1 (all body text)
- **Preferred (AAA):** 7.0:1 (optimal for long reading)
- **Large text only:** 3.0:1 (18.5px bold+)
- **Test tool:** colorable.com

---

## When to Use This Skill

**Use this skill when:**
- Reviewing your own design before client handoff
- Giving feedback on peer designs
- Analyzing what makes competitor websites work
- Improving an existing website
- Learning systematic critique methodology

**Don't use this skill when:**
- Designing animations/micro-interactions → use **animation-interactions**
- Building in Webflow → use **webflow-implementation**
- Creating new component designs → use **ui-components**
- Structuring a page layout → use **web-layout**

---

## Cross-References

**Related skills to deepen your audit:**
- **visual-foundations** — Understand WHY the rules work (principles behind spacing, contrast, hierarchy)
- **ui-components** — See best patterns for buttons, cards, forms you're auditing
- **web-layout** — Understand section structure and responsive behavior

**Reference files for specific mistake categories:**
- **02_typography_mistakes_vault.md** — Deep catalog of 1000+ real typography errors from Shift Nudge critiques
- **03_color_contrast_mistakes.md** — Comprehensive color accessibility patterns
- **04_layout_spacing_mistakes.md** — Real spacing issues and their fixes

---

**Last Updated:** March 12, 2026
**Source:** Shift Nudge Critique Vault (273+ videos, 1000+ critique patterns), Interface Design Course
**Status:** Extraction complete, ready for use
