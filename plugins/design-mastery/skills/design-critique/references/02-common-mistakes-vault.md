# Common Mistakes Vault

Real critique patterns from Shift Nudge Critique Vault (273+ video reviews) organized by category. Each pattern includes the problem, root cause, and specific fix.

---

## TYPOGRAPHY MISTAKES (Most Frequent)

### Pattern T1: Five Different Title Sizes [MDS Critique Vault]

**Problem:** H1=56px, H2=48px, H3=36px, H4=28px, H5=18px (5 levels)
**Root cause:** Treating semantic HTML tags (H1-H5) as design sizes
**Fix:** Pick 3-4 sizes max. Use weight/color/spacing for further hierarchy, not size
**Example:** 48px (H1), 32px (H2), 16px (body) -- only 3 sizes, clear hierarchy

### Pattern T2: Body Text in Light Gray [MDS Critique Vault]

**Problem:** #999999 text on white background = 2.8:1 contrast (fails AA)
**Root cause:** "Light" gray looks trendy but fails accessibility
**Fix:** Use #757575 or darker for 4.5:1 minimum
**Test:** colorable.com -- #999999 on #FFFFFF = fails; #757575 on #FFFFFF = passes

### Pattern T3: No Visual Weight Hierarchy [MDS Critique Vault]

**Problem:** Title and body at same size, same weight, different color only
**Root cause:** Assuming color difference creates sufficient hierarchy
**Fix:** Use size AND weight: 32px bold title + 16px regular body
**Impact:** Clear, immediate hierarchy without effort

### Pattern T4: Tiny Text in Big Spaces [MDS Critique Vault]

**Problem:** 12px metadata floating in generous 200px of whitespace
**Root cause:** Padding applied uniformly regardless of content size
**Fix:** Large text needs large surrounding space; small text lives in tighter areas
**Principle:** Padding should scale proportionally with content size

### Pattern T5: Over-Reliance on Bold [MDS Critique Vault, 28 weight reviews]

**Problem:** Everything bold = nothing bold
**Root cause:** Using bold as default rather than intentional emphasis
**Fix:** Reserve bold for titles and key emphasis; body stays regular weight
**Rule:** If more than 30% of visible text is bold, emphasis is diluted

### Pattern T6: Inconsistent Line Heights [MDS Critique Vault, 66 font size reviews]

**Problem:** Same-size text with different line heights across sections
**Root cause:** Line height set per element instead of per text style
**Fix:** Define line height per size: titles 100-120%, body 150-160%

### Pattern T7: Title Sizes Too Similar to Body [MDS Critique Vault]

**Problem:** Title 20px, body 16px -- only 4px difference, no clear hierarchy
**Root cause:** Incremental size increases instead of dramatic contrast
**Fix:** Use multiples of body size for headlines (2x, 3x, 4x) [Flux]

---

## COLOR & CONTRAST MISTAKES (Common)

### Pattern C1: Insufficient Contrast on Accent Color [MDS Critique Vault]

**Problem:** Bright orange (#FF6B35) + white text = 3.1:1 (fails AA)
**Root cause:** Brand color is vibrant, not high contrast
**Fix:** Dark text on orange background = 5.2:1 (passes). OR use orange only for backgrounds
**Rule:** If brand color is bright, use it as background with dark text

### Pattern C2: Too Many Grays [MDS Critique Vault]

**Problem:** #999, #888, #777, #666, #AAA used throughout
**Root cause:** Grays picked arbitrarily without system
**Fix:** Lock in 3: #999 (light), #666 (medium), #333 (dark). Use only these
**Impact:** Looks more intentional and cohesive

### Pattern C3: Semantic Color Mismatch [MDS Critique Vault]

**Problem:** Green "Delete" button or red "Confirm" button
**Root cause:** Reversed expectations from color psychology
**Fix:** Green = confirm/success, Red = delete/danger/cancel
**Principle:** Color psychology matters for UX -- align color with expected meaning

### Pattern C4: Inaccessible Disabled States [MDS Critique Vault]

**Problem:** Disabled input at #CCCCCC on white = 2.1:1
**Root cause:** Made disabled state too light to indicate "off"
**Fix:** Disabled at #A6A6A6 (4.5:1) if needs to communicate. Or make visually obvious

### Pattern C5: Brand Color Used as Body Text

**Problem:** Bright blue brand color used for paragraph text
**Root cause:** Brand consistency taken too far -- brand color isn't always readable
**Fix:** Use brand color for accents, buttons, highlights. Body text stays dark neutral

---

## SPACING & LAYOUT MISTAKES (Very Common)

### Pattern S1: Coffin Box Effect [MDS Critique Vault]

**Problem:** Small content in large box with 40px padding all sides
**Root cause:** Uniform padding regardless of content size
**Fix:** Padding ratio = content size ratio. 64px for large content, 16px for metadata
**Principle:** Large text needs large surrounding space; small text needs less

### Pattern S2: Missing Section Breathing Room [MDS Critique Vault]

**Problem:** Hero section, then immediately features section with no gap
**Root cause:** Only set internal padding, forgot inter-section margins
**Fix:** 80-100px margin between major sections minimum
**Rule:** 60-100px gap between major sections

### Pattern S3: Unequal Padding [MDS Critique Vault]

**Problem:** Card has 40px top/bottom, 12px left/right
**Root cause:** Focused on one axis, ignored the other
**Fix:** More balanced: 24px all sides, or 32px vertical + 24px horizontal
**Principle:** Padding should feel intentional, not accidental

### Pattern S4: Grid Misalignment [MDS Critique Vault]

**Problem:** Center column offset by 3px from grid
**Root cause:** Container width not divisible by grid (1441px on 8px grid)
**Fix:** Use clean grid widths: 1440px, 1200px, 960px
**Test:** All components should snap to grid without remainder

### Pattern S5: Arbitrary Margins

**Problem:** Spacing values of 13px, 27px, 42px throughout
**Root cause:** Eyeballing instead of using spacing scale
**Fix:** Use system: 4, 8, 12, 16, 24, 32, 48, 64, 80, 100

---

## COMPONENT MISTAKES (Consistency)

### Pattern K1: Multiple Button Styles [MDS Critique Vault]

**Problem:** Primary (blue, 4px radius), Secondary (white, 4px radius), CTA (blue, 8px radius)
**Root cause:** Style evolved mid-project, not updated throughout
**Fix:** Define once: all buttons same border-radius; only color/weight vary

### Pattern K2: Inconsistent Card Heights [MDS Critique Vault]

**Problem:** Cards at 240px, 180px, 310px heights due to variable descriptions
**Root cause:** Content-driven heights, no fixed system
**Fix:** Set fixed/min card height with 3-line max description; truncate excess
**Principle:** Cards should look cohesive even with variable content

### Pattern K3: Form Input Chaos [MDS Critique Vault]

**Problem:** Text input 44px, select 36px, textarea 40px (all different)
**Root cause:** Each component built independently
**Fix:** All form elements same height minimum (standardize on 40px or 44px)
**Benefit:** Inputs aligned horizontally without gaps

### Pattern K4: Mixed Icon Sizes

**Problem:** Social icons 20px in footer, 24px in header, 18px in sidebar
**Root cause:** Icons sized per context instead of per system
**Fix:** Pick one or two sizes and use consistently everywhere

---

## HIERARCHY MISTAKES

### Pattern H1: Equal Visual Weight Throughout [MDS Critique Vault]

**Problem:** H1 (48px #333), H2 (42px #333), H3 (36px #333) -- only size differs
**Root cause:** Relied solely on size for hierarchy; no weight or color variation
**Fix:** H1 (48px bold #000), H2 (32px semi-bold #333), H3 (24px regular #666), body (16px regular #999)

### Pattern H2: CTA Button Lost Among Navigation [MDS Critique Vault]

**Problem:** "Buy now" 40px button surrounded by 18px blue navigation links
**Root cause:** Button not visually dominant enough
**Fix:** Button 48px, darker shade, add shadow; navigation stays 16px, lighter color
**Principle:** Primary action 1.5-2x visual weight of secondary actions

### Pattern H3: Flat Hierarchy -- Everything Competing [MDS Critique Vault, 48 reviews]

**Problem:** All elements at same visual level; no clear focal point
**Root cause:** Over-designing lower-priority elements
**Fix:** Identify the ONE most important element per screen; make it visually dominant
**Rule:** Consider what the user wants to accomplish on each screen

---

## QUICK REFERENCE: CONTRAST RATIOS

| Background | Lightest Passing Gray (AA) | For |
|------------|--------------------------|-----|
| White (#FFF) | ~#767676 | Body text minimum |
| White (#FFF) | ~#595959 | AAA body text |
| Black (#000) | ~#757575 | Body text minimum |

### Common Dark UI Background Values [MDS]

- Not pure black: #161416, #1A1A1C, #1E1E20
- Sidebar darker: ~#0F0F11
- Card on dark: lighter shade of same background hue
