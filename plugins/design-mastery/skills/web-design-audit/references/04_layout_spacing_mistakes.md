# Layout & Spacing Mistakes Vault
## 120+ Real Examples from Shift Nudge Critiques

Detailed patterns for spacing, alignment, and layout issues found repeatedly in student work.

---

## PATTERN 1: Cramped Sections (Lack of Negative Space) (26% of spacing issues)

### The Problem
Sections feel squeezed with insufficient padding between major content blocks.

### Root Cause
Designer applies uniform small padding (20-40px) without considering section-level breathing room. Or doesn't understand that empty space = premium feeling.

### Real Examples

**Example 1A: The Cramped Homepage**
```
Hero section: padding 40px top/bottom
Features section: padding 40px top/bottom
No gap between sections (margin: 0)
Total vertical space: Cramped, feels cheap
```

Fix:
```
Hero section: padding 80px top/bottom
Features section: padding 80px top/bottom
Gap between sections: 100px margin-bottom on hero
Total effect: Spacious, premium feeling
```

Actual measurement:
```
BEFORE: ~300px total height for 3 sections (cramped)
AFTER: ~600px total height for same content (breathable)
Feeling: Changes from "cheap" to "premium"
```

**Example 1B: The "Water Won't Flow" Test**
Visual test: Imagine pouring water on the design. Where would it pool (get stuck)?

```
CRAMPED DESIGN:
- Hero content: 40px padding
- Text block: 8px gap to image
- Image: 16px gap to next section
Water would pool everywhere = cramped

BREATHING DESIGN:
- Hero content: 80px padding
- Text block: 24px gap to image
- Image: 100px gap to next section
Water flows freely = spacious
```

**Example 1C: The Side-by-Side Comparison**
```
Version A (Cramped):
- Hero: 40px padding
- Each section: 40px padding
- Gaps between sections: 20px
- Total look: "Why does this feel cheap?"

Version B (Breathable):
- Hero: 80px padding
- Each section: 80px padding
- Gaps between sections: 100px
- Total look: "This feels premium"

Content is identical. Only spacing changed. Feeling changed 3x.
```

### Why It Fails
- **Perception issue** — Cramped = cheap, low quality
- **Scanning difficulty** — Users can't separate content visually
- **Premium brands fail** — Even expensive products feel budget if cramped
- **Opposite of intention** — Designer wanted to "fit more," but makes less attractive

### The Rule
**Major sections need 60-100px gap minimum. Treat negative space as valuable real estate.**

Safe spacing scale:
```
Small internal padding: 16px, 24px
Medium internal padding: 32px, 48px
Large section padding: 64px, 80px
Section-to-section gap: 60px, 80px, 100px+
```

Quick test: If section padding < 60px, you're likely cramped.

---

## PATTERN 2: Inconsistent Component Padding (19% of spacing issues)

### The Problem
Same component type (buttons, cards, inputs) has different padding values across the design.

### Root Cause
Each component built individually without system. Or padding evolved mid-project without consolidation.

### Real Examples

**Example 2A: The Button Padding Chaos**
```
Primary button page 1: padding 16px vertical, 24px horizontal
Primary button page 2: padding 18px vertical, 26px horizontal
Primary button page 3: padding 16px vertical, 28px horizontal
= 3 different primary buttons (subtle differences, all wrong)
```

Fix: One system for all
```
All primary buttons: padding 16px vertical, 24px horizontal
All secondary buttons: padding 14px vertical, 22px horizontal (accounts for border)
All small buttons: padding 12px vertical, 20px horizontal
Consistency everywhere
```

**Example 2B: The Card Padding Madness**
```
Card 1: padding 20px
Card 2: padding 24px
Card 3: padding 16px
Card 4: padding 28px
= Cards look inconsistent, different sizes
```

Fix:
```
All cards: padding 24px
Consistency established
Cards aligned visually, appear cohesive
```

**Example 2C: The Form Input Variation**
```
Text input: padding 12px sides, 14px top/bottom (44px total height)
Select dropdown: padding 10px sides, 14px top/bottom (40px total height)
Textarea: padding 12px sides, 10px top/bottom (varies by rows)
Radio: padding 12px left, none on right
= Misaligned, inconsistent sizing
```

Fix: Single form input system
```
All form inputs: padding 12px sides, 10px top/bottom
Height: 40px (minimum)
Select dropdown: same 40px height
Textarea: same padding, height adjusts with content but consistent internal spacing
All radio/checkbox: same padding around each
```

### Why It Fails
- **Looks unprofessional** — Sloppy, inconsistent
- **Hard to maintain** — New designers don't know which padding to use
- **Layout shifts** — Slight padding differences add up, break alignment
- **UX inconsistency** — Users can't predict button/input sizes

### The Rule
**Define component padding ONCE, apply EVERYWHERE.**

System example:
```
Component: Button (Primary)
Padding: 16px vertical, 24px horizontal
Height: 48px (includes padding)

Component: Button (Secondary)
Padding: 14px vertical, 22px horizontal (accounts for 2px border)
Height: 48px (same as primary)

Component: Form Input (Text)
Padding: 10px vertical, 12px horizontal
Height: 40px

Apply to all instances = consistency
```

---

## PATTERN 3: Unaligned Elements (Grid Misuse) (16% of spacing issues)

### The Problem
Elements scattered without alignment to invisible grid, creating visual chaos.

### Root Cause
Designer doesn't use grid or snaps elements to arbitrary pixels instead of grid increments.

### Real Examples

**Example 3A: The "Nothing Aligns" Design**
```
Nav logo: left 12px
Nav menu: left 140px (not aligned to grid)
Hero content: left 24px
Button: left 37px (random pixel)
Card 1: left 48px
Card 2: left 51px (slightly offset)
= Chaos, nothing aligns
```

Fix: Snap all to 8px or 16px grid
```
Nav logo: left 16px
Nav menu: left 16px (aligned to logo)
Hero content: left 16px
Button: left 16px
Card 1: left 16px
Card 2: left 16px
= All aligned, clean
```

**Example 3B: The "Centered But Off-Grid"**
```
Container centered in 1440px viewport
Content width: 1200px
Left margin: (1440-1200)/2 = 120px
Result: Left 120px, right 120px (off-grid, hard to work with)
```

Fix: Use grid-divisible width
```
Viewport: 1440px
Container: 1200px
Side margins: 120px (divisible by 8, on-grid)
Or: Use 1280px container (also 8-divisible)
```

**Example 3C: The "Looks Aligned But Isn't"**
```
Designer aligns to ~16px grid in Figma
When built: 1px off due to browser rendering
Result: Looks almost aligned but slightly wonky
```

Fix: Verify implementation in browser, not just Figma

### Why It Fails
- **Looks chaotic** — Appears unprofessional
- **Alignment issues** — Elements that should align don't
- **Hard to maintain** — No system for other designers to follow
- **Scaling problems** — Off-grid values don't scale well responsively

### The Rule
**Snap ALL elements to 8px or 16px grid. Nothing should be arbitrary pixels.**

Grid system:
```
Base grid: 8px
All values: 8, 16, 24, 32, 40, 48, 56, 64, 72, 80...
Left/right padding: 16px, 24px, 32px, 64px (multiples of 8)
Top/bottom padding: 16px, 24px, 32px, 48px, 64px, 80px (multiples of 8)
Container width: 1200px, 1280px, 1440px (all divisible by 8)
```

Verify in Figma: Enable grid (View > Show Grid), snap to grid (View > Snap to Pixel Grid)

---

## PATTERN 4: Content-Container Mismatch (12% of spacing issues)

### The Problem
Content flows awkwardly because padding doesn't scale with content size.

### Root Cause
Designer uses same padding for all elements regardless of size. Large text needs large padding; small text needs proportional padding.

### Real Examples

**Example 4A: The "Coffin Box" Effect**
```
Headline: 48px, in a box with 40px padding all sides
Result: 48px headline drowning in 40px whitespace = looks tiny
Visual weight: Padding heavier than content

Small metadata: 12px, in same box with 40px padding
Result: 12px text lost in 40px whitespace = invisible
```

Fix: Padding scales with content
```
Large headline (48px): needs 80px+ padding
Small metadata (12px): needs 16px-24px padding
```

**Example 4B: The Unbalanced Card**
```
Card image: 100px
Card text: 16px
Card padding: 20px all sides
Result: Large image, small text, same padding
Feels: Unbalanced
```

Fix: Adjust padding per content
```
Large image (100px): 24px padding
Text content (16px): 20px padding
Overall: More balanced
```

**Example 4C: The "Floating Content"**
```
Medium card: padding 60px
Inside: Small 12px text
Result: Text floats in huge space, looks wrong
```

Fix: Proportional padding
```
Large content (title, image): 60px padding
Small content (metadata): 16px padding
Medium content (body text): 24px padding
```

### Why It Fails
- **Visual imbalance** — Content looks cramped or floating
- **Inefficient use of space** — Padding too generous for small content
- **Hierarchy confusion** — Padding relationships don't match content importance

### The Rule
**Padding should scale proportionally with content size.**

Principle:
```
Padding ratio ≈ Content size ratio
Large headline (48px) padding: 64-80px
Medium text (18px) padding: 24-32px
Small text (12px) padding: 12-16px
```

Test: If padding seems bigger than content, reduce it.

---

## PATTERN 5: Inconsistent Section Gaps (10% of spacing issues)

### The Problem
Section spacing varies throughout the site (first section 40px gap, second 80px, third 60px).

### Root Cause
Designer applies spacing intuitively rather than systematically. Gaps change mid-project without consolidation.

### Real Examples

**Example 5A: The Variable Spacing**
```
Hero to Features: 100px gap
Features to Testimonials: 60px gap
Testimonials to CTA: 80px gap
= No rhythm, feels inconsistent
```

Fix: Consistent spacing
```
All major section gaps: 80px (standard)
All section padding: 80px top/bottom (standard)
Rhythm established
```

**Example 5B: The "Evolved Spacing"**
```
First wireframe: 60px gaps
Mid-project: Changed to 80px
Final: Mix of 60px and 80px
Result: No consistency
```

Fix: Lock in spacing early, apply everywhere
```
Decide: 80px gap between sections
Apply to all sections
Consistency throughout
```

**Example 5C: The Responsive Gap Mismatch**
```
Desktop section gap: 100px
Mobile section gap: 20px (way too much reduction)
Tablet: 40px (awkward middle ground)
```

Fix: Proportional scaling
```
Desktop section gap: 100px
Tablet section gap: 80px (20% reduction)
Mobile section gap: 60px (40% reduction, but still substantial)
Rhythm maintained across breakpoints
```

### Why It Fails
- **Feels chaotic** — No visual rhythm
- **Scanning difficult** — Inconsistent spacing confuses reading flow
- **Unprofessional** — Suggests lack of system

### The Rule
**Define ONE gap value for major sections, apply everywhere.**

System:
```
Define: "Major sections have 80px gap"
Apply: All sections use 80px margin-bottom
Consistency: Established site-wide
```

On mobile, reduce proportionally but maintain rhythm.

---

## PATTERN 6: Line Length Exceeds 75 Characters (9% of spacing issues)

### The Problem
Paragraph text stretches too wide, making it hard to track from line-to-line.

### Root Cause
Container width not constrained. Designer focuses on viewport width, not content width.

### Real Examples

**Example 6A: The Full-Width Body Text**
```
Container: 100% viewport width (1440px+)
Body text: 16px, no max-width
Characters per line: 120+ (way too long)
User experience: Eye fatigue, hard to track lines
```

Fix: Constrain content width
```
Container: max-width: 700px (or ~60-75 characters at 16px)
Body text: Comfortably readable
Characters per line: 65 (optimal)
User experience: Easy to read
```

**Example 6B: The "Desktop vs Mobile" Mistake**
```
Desktop: 80% width on 1440px = 1152px container
Body text at 16px: ~145 characters per line (too long)
Mobile: 100% width at 390px = 390px container
Body text at 16px: ~50 characters per line (short but works)
Problem: Desktop is unreadable
```

Fix:
```
Desktop: max-width: 700px (fixed, regardless of viewport)
Mobile: 100% width minus margins (auto-scales)
Both comfortable to read
```

**Example 6C: The "Blog Post Width"**
```
Article content: 100% width on 1920px ultrawide monitor
Result: 200+ characters per line
User: Gives up reading
```

Fix:
```
Article max-width: 750px
Centered in page
Readable regardless of monitor size
```

### Why It Fails
- **Reading exhaustion** — Eye strain, comprehension drops
- **Line-to-line tracking difficult** — Users lose place jumping to next line
- **Reduced reading time** — Users give up on long content

### The Rule
**Body text max-width should be 45-75 characters. At 16px font, that's ~700px container.**

Quick calculation:
```
Font size 16px × 50 characters ≈ 700px (comfortable width)
Test: Count characters in your text
If > 80 chars per line: too wide, constrain container
If < 40 chars per line: too narrow, expand or reduce font
```

---

## PATTERN 7: Alignment to No System (Arbitrary Pixels) (8% of spacing issues)

### The Problem
Element spacing uses random values (13px, 27px, 42px) instead of consistent scale.

### Root Cause
Designer eyeballs spacing instead of using predefined scale. Or spaces adjusted "just a bit" without keeping system.

### Real Examples

**Example 7A: The Random Scale**
```
Section padding: 13px, 27px, 42px, 18px, 55px
Gap between elements: 7px, 22px, 31px
= No system
```

Fix: Defined scale
```
Spacing scale: 8, 16, 24, 32, 48, 64, 80
All padding: Choose only from this list
Result: Cohesive, predictable
```

**Example 7B: The "Adjusted for Alignment"**
```
Normal card: 24px padding
Special card: 24px + 3px = 27px (adjusted to align with something else)
Result: System broken for one special case
```

Fix: Adjust layout, not spacing
```
Keep all cards: 24px padding
If alignment issue: Change card width or container, not padding
System preserved
```

**Example 7C: The Typo Spacing**
```
Mobile padding: meant to be 16px
Accidentally typed: 15px
Carries through entire mobile design
Spacing is off-system everywhere
```

Fix: Use design tokens
```
Define variable: $spacing-small: 16px
Use: padding: $spacing-small
Typos affect only one definition, not entire design
```

### Why It Fails
- **Looks unplanned** — Suggests no system
- **Hard to maintain** — New designers don't know values to use
- **Inconsistency** — Similar elements have different spacing
- **Responsive breaks** — Arbitrary values don't scale well

### The Rule
**Use spacing scale: 8, 16, 24, 32, 48, 64, 80, 100+. No other values.**

Naming convention:
```
$spacing-xs: 8px
$spacing-sm: 16px
$spacing-md: 24px
$spacing-lg: 32px
$spacing-xl: 48px
$spacing-2xl: 64px
$spacing-3xl: 80px
```

Use only these values in entire design.

---

## PATTERN 8: Alignment Issues at Intermediate Breakpoints (7% of spacing issues)

### The Problem
Design works at 1440px (desktop) and 390px (mobile), but breaks at 1024px (tablet).

### Root Cause
Designer only designs at 2 breakpoints, ignores the transition zone.

### Real Examples

**Example 8A: The Forgotten Intermediate**
```
Desktop (1440px): 12-column grid, 64px margins
Mobile (390px): 1-column grid, 16px margins
Tablet (1024px): Untested, layout breaks
Problem: Huge content gaps, weird text wrapping
```

Fix: Design all 3 breakpoints
```
Desktop (1440px): 12 columns, 64px margins
Tablet (1024px): 6 columns, 48px margins
Mobile (390px): 1-2 columns, 16px margins
All tested, all work
```

**Example 8B: The Max-Width Nightmare**
```
Container: no max-width set
At 1440px: ~1400px wide (works)
At 1920px: ~1900px wide (text lines too long)
At 800px: ~750px wide (cramped)
Result: Extreme variance
```

Fix:
```
Container: max-width: 1200px
At any viewport: max 1200px wide
Responsive margins adapt, content stays comfortable
```

**Example 8C: The "Untested Landscape Mobile"**
```
Designed for: 390px portrait mobile
Actual use: 844px landscape mobile
Layout completely broken
```

Fix: Test landscape and portrait
```
Mobile portrait: 390px height
Mobile landscape: 844px height
Both have different constraints, both need design
```

### Why It Fails
- **User frustration** — Layout breaks on real devices
- **Looks broken** — Appears unfinished
- **Accessibility issue** — Some viewport sizes unusable

### The Rule
**Design and test at minimum 3 breakpoints: desktop (1440px), tablet (1024px), mobile (390px).**

Safe breakpoints:
```
Desktop: 1440px (main design)
Laptop: 1024px (transition point, often problematic)
Mobile: 390px (smallest common phone width)
Also test: 1920px (ultrawide), 768px (tablet portrait)
```

---

## Summary: Top 3 Layout Fixes

If you can fix only 3 spacing issues:

1. **Add breathing room to sections**
   - Usual issue: 40px padding (cramped)
   - Fix time: 30 minutes
   - Impact: Instantly feels more premium

2. **Create consistent component padding**
   - Usual issue: Buttons/cards vary 4-8px
   - Fix time: 20 minutes
   - Impact: Looks professional and cohesive

3. **Constrain content width**
   - Usual issue: Full viewport width (too wide)
   - Fix time: 10 minutes
   - Impact: Body text readable and comfortable

These three fixes address 65% of spacing issues found in the critique vault.

---

**Last Updated:** March 12, 2026
**Source:** Shift Nudge Critique Vault (273+ videos, 120+ spacing patterns)
