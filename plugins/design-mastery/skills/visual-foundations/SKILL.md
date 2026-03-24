---
name: Visual Foundations
description: "Core design principles: typography, color, spacing, layout, hierarchy, grids, contrast, visual weight, alignment, proximity. MANDATORY TRIGGERS: typography rules, color theory, color contrast, spacing systems, layout patterns, grid systems, visual hierarchy, design principles, font sizes, color palettes, accessibility standards. Do NOT use for — use figma-workflows for file organization, ui-components for specific components, web-layout for page structure."
---

# Visual Foundations

Design fundamentals are timeless. Typography, color, layout, and hierarchy work the same way today as they did 20 years ago. Master these rules and every design project becomes easier.

---

## Core Mindset

Before learning the rules, adopt the right mindset:

**Master the fundamentals:** Typography, color, layout, hierarchy. These last longer than any tool or trend.

**Beginner's mind:** Stay curious about WHY design works, not just HOW to do it.

**Design is earned:** Watching videos is 20% effective. Actual practice builds skill. "Putting in the reps" is the only path.

**Constant learning:** Even experienced designers continuously learn. Never consider yourself "arrived."

---

## Typography: The Hierarchy System

Typography is how 80% of your interface communicates. Get this right and everything else feels easier.

### Rule of Four: Maximum 4 Type Sizes

Never use more than 4 different font sizes in a single design. Use 3-4 maximum.

**Hierarchy through size:**
- **H1 (Headline):** 48px or larger
- **H2 (Section header):** 32px
- **Body copy:** 16-18px (minimum safe size for reading)
- **Small/metadata:** 13-14px

**The ratio:** Each size step should be visually distinct. Aim for 1.5x ratio minimum.

**Web safe combinations:**
- 48px / 32px / 18px / 14px
- 40px / 28px / 16px / 13px
- 56px / 36px / 20px / 14px

**Mobile safe combinations:**
- 34px / 20px / 16px / 13px (iOS style)
- 32px / 18px / 16px / 14px

### Font Weight Strategy

**Critical rule:** Font MUST include actual weights. Never rely on browser-generated bold.

**Weight availability checklist:**
- Does your font have 400 (regular)? ✓ Required
- Does it have 600-700 (semi-bold/bold)? ✓ Required
- Light weights (100-300)? Only use for 60px+ headlines

**Apply weights:**
- **Headlines:** 600-700 (semi-bold or bold)
- **Body copy:** 400 (regular)
- **Metadata/secondary:** 400 (can be lighter color instead of lighter weight)

**Never do:** Light weight (100-200) on 16-18px body copy. Unreadable, strains eyes.

### Typography Hierarchy Rules

1. **Three text roles:**
   - **Title/Headline:** Bold, larger, commands attention
   - **Body copy:** Regular weight, readable, 16px minimum
   - **Metadata:** Smaller or lighter color

2. **Hierarchy is ranking importance, not semantic tags**
   - H1/H2/H3 are HTML. Visual importance is what matters.
   - Small text in generous space can outrank large text in cramped space

3. **Establish hierarchy through:**
   - Size (larger = more important)
   - Weight (bolder = more important)
   - Color (higher contrast = more important)
   - Positioning (top-left = natural entry point)
   - Negative space (isolated element = more important)

### Line Height & Readability

**Body copy width:** 45-75 characters wide (optimal readability)

**Line height:**
- **Body copy:** 150% (1.5x) is the default safe value
- **Range:** 125%-220% depending on typeface and context
- **Too tight (<125%):** Awkward, hard to follow line-to-line
- **Too loose (>200%):** Content feels disconnected

**Titles:** 100-120% line height (much tighter than body)
- **All caps titles:** Can go as low as 75-80% due to blockier letters

---

## Color: System & Contrast

### Color Selection Methods

**RGB** (0-255 per channel): Hard to visualize. Avoid unless pulling existing values.

**Hex** (#RRGGBB): Most portable—works everywhere. Use as standard format.
- #000000 = black
- #FFFFFF = white
- Shorthand: #000 = #000000

**HSL** (Hue, Saturation, Lightness): More intuitive than RGB. Slight inconsistency between Sketch/Figma.

**HSB** (Hue, Saturation, Brightness) ⭐ **DESIGNER FAVORITE:** Most intuitive. Consistent across Figma, Sketch, Adobe CC.

### Color Contrast: WCAG Accessibility Standards

**Contrast ratio scale (1-21):**
- **3.0:** AA Large (minimum for 18.5px bold or 24px regular only)
- **4.5:** AA (standard body text, accessible for all sizes)
- **7.0:** AAA (highest level, best for long reading and 20/80 vision)
- **21.0:** Black on white (maximum contrast)

**Vision requirements:**
- 20/20 vision: Can see at 3.0 contrast
- 20/40 vision: Requires 4.5 (1.5x sensitivity loss)
- 20/80 vision (legally blind): Requires 7.0

**Minimum standards:**
- Body copy: 4.5:1 ratio minimum (non-negotiable)
- Large text (18.5px bold+): 3.0 minimum
- Preferred: 7.0 for titles and long reading

**Testing:** Use colorable.com or Figma Contrast plugin

**Example: Black backgrounds**
- #666666 on #000000 = 3.0 (barely passing, not recommended)
- #757575 on #000000 = 4.5 (safe standard)
- #999999 on #000000 = 7.0+ (excellent)

### Color System Structure

**Primary color:** Brand color, most used, CTAs, key interactive elements

**Secondary color:** Complement to primary, less frequent use, alternative actions

**Neutral colors:** Grays for body text, backgrounds, dividers

**Interactive colors:** Buttons, links, hover states, active indicators

**Accessibility rule:** Never rely on color alone. Use color + pattern, color + text, color + icon.

---

## Layout & Spacing: The Box Model

### Everything is a Box

Every UI element = box with 4 edges.

**Box model components:**
1. **Content** - The actual element (text, image)
2. **Padding** - Space INSIDE the box (insulation)
3. **Border** - Optional outline
4. **Margin** - Space OUTSIDE the box (separation)

**Key distinction:**
- **Padding:** Inside, can have background color
- **Margin:** Outside, creates separation from other elements

### Grid Systems

**Desktop (1440px):**
- 12-column grid (flexible for 2, 3, 4, 6-column layouts)
- Margins: 24-64px (depends on breathing room desired)
- Gutters: 16-40px between columns

**Tablet (800px):**
- 6-column grid or 8-column
- Reduced margins: 32-40px
- Gutters: 16-32px

**Mobile (390px):**
- 1-column (stretch content)
- Margins: 16-24px
- Or 2-column for specific components

**Max-width technique (Desktop+):**
- Set max-width: 1312px (1440 - 64×2 margins)
- Center with auto margins
- Prevents awkward stretching on ultrawide displays

### Safe Spacing Values (8px Base)

Use multiples of 8px for consistency and scalability.

**Micro-spacing:** 4px, 8px (between elements, tight gaps)

**Small spacing:** 12px, 16px (padding, standard gaps)

**Medium spacing:** 24px, 32px (between sections, breathing room)

**Large spacing:** 40px, 60px, 80px+ (major content blocks)

### Negative Space: Design Oxygen

**Core principle:** "Negative space is premium. Without it, designs suffocate."

**Key insight:** More space = more luxury (airlines charge for extra legroom, not volume)

**Distribution:**
- More flexibility with **vertical** space (users can scroll)
- Limited **horizontal** space (fixed screen width)

**Application:**
- 20px minimum padding around contained text
- 16-24px between line items
- 60-100px+ between major sections
- Larger elements REQUIRE more breathing room

**Rule of thumb:** If an element feels cramped, it needs space. Step back and ask: "Would water flow smoothly through this design?"

### Alignment & Implicit Grid

**Explicit grid:** Visible column/row system

**Implicit grid:** Invisible spacing system based on consistent increments (8px, 12px, 16px, 24px)

**Alignment practices:**
- Left-align: Strong, clean verticals
- Right-align: Balance (opposite edge)
- Center: Only for special moments (headlines, cards)
- Avoid: Center-aligned long-form body copy (looks odd)

---

## Visual Hierarchy: Making Things Important

You establish visual hierarchy through:

1. **Size:** Larger commands attention
2. **Weight:** Bolder commands attention
3. **Color:** Higher contrast commands attention
4. **Position:** Top-left is natural entry point (Western reading pattern)
5. **Whitespace:** Isolated elements seem more important
6. **Proximity:** Grouped elements = related

**Hierarchy ranking:**
- **Primary (Most important):** Largest, darkest, boldest, isolated with space
- **Secondary (Supporting):** Medium size, supporting color, close proximity to primary
- **Tertiary (Supplementary):** Smallest, lighter color, grouped with secondary

---

## Design Principles in Practice

### Contrast
Create clear differences between similar elements. Example: Button vs. text link must be obviously different (color, size, weight, or style).

### Alignment
All elements snap to grid. No random placement. Creates order and professionalism.

### Proximity
Elements close together suggest relationship. Similar spacing suggests equality.

### Balance
Visual weight distributed evenly. Can be symmetrical (formal) or asymmetrical (dynamic).

### Consistency
Repeated patterns feel cohesive. Use consistent spacing, sizes, colors across the design.

---

## Quick Reference: Safe Values

### Typography Sizes
- Web: 48px / 32px / 24px / 18px / 16px / 14px / 13px
- iOS: 34px / 20px / 18px / 16px / 15px / 13px
- Minimum body: 16px (web), 15px (iOS)

### Spacing Scale
- **Micro:** 4, 6, 8px
- **Small:** 12, 16px
- **Medium:** 24, 32px
- **Large:** 40, 60, 80, 100px+

### Color Contrast
- Absolute minimum: 3.0 (large text only, 18.5px bold+)
- Recommended: 4.5 (all body text)
- Best practice: 7.0 (titles, long reading)
- Gold standard: #757575 on #000000 = 4.5

### Grid Systems
- **Desktop:** 12 columns, 1440px width, 64px margins, 24-40px gutters
- **Tablet:** 6-8 columns, 800px width, 40px margins
- **Mobile:** 1-4 columns (usually 1), 390px width, 24px margins

### Line Heights
- Body: 150% (1.5x)
- Titles: 100-120%
- All caps: 75-80%
- Range: 125%-220% depending on context

---

## When to Use References

Load these reference files when:

- **01-typography-reference.md** — Designing type system, setting font sizes, understanding readability rules
- **02-color-systems.md** — Creating color palette, understanding color theory, building accessible colors
- **03-spacing-metrics.md** — Establishing spacing system, padding/margins, responsive breakpoints

---

## Common Mistakes

1. **Too many font sizes:** 5+ different sizes destroy hierarchy
   - **Fix:** Limit to 3-4 maximum

2. **Poor contrast:** Text hard to read, fails accessibility
   - **Fix:** Test all colors. Minimum 4.5:1 ratio

3. **No breathing room:** Elements packed too tight
   - **Fix:** Add negative space. If cramped, add 25% more space

4. **Inconsistent spacing:** 8px here, 12px there, 15px there
   - **Fix:** Commit to spacing scale (8, 12, 16, 24, 32, etc.)

5. **No visual hierarchy:** Everything same size/weight/color
   - **Fix:** Make most important thing obvious through size, weight, or color

6. **Text too long without breaks:** No line height or spacing between paragraphs
   - **Fix:** Use 150% line height, add 16-24px gaps between sections

---

## After Learning Foundations: Next Steps

1. **Figma setup:** Move to `figma-workflows` to organize your design file
2. **Specific components:** Move to `ui-components` for button, card, form patterns
3. **Web layouts:** Move to `web-layout` for structuring full pages
4. **Design audit:** Move to `web-design-audit` to critique existing designs

These foundations apply to ALL of them.

---

## Cross-References

- **discovery-direction** — Determines what you're designing (brand, audience, goals)
- **figma-workflows** — How to organize these principles in your file
- **ui-components** — Applies these principles to specific components
- **web-layout** — Applies these principles at page scale
- **web-design-audit** — Uses these principles as critique checklist
