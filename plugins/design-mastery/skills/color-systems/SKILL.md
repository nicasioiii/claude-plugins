---
name: Color Systems
description: "MANDATORY TRIGGERS: color palette, color selection, contrast ratio, WCAG, accessibility, dark mode, dark UI, gradient, 60-30-10, color psychology, HSB, gray tinting, structural vs interactive color, color from photography. FOR: HSB color method, palette construction, WCAG contrast scoring, structural vs interactive color spectrum, gray tinting formula, dark UI methodology, gradient rules, 60-30-10 rule, color psychology, color harmonies, color documentation, and color modification techniques. Do NOT use for interactive text color for links/buttons (use typography-systems), brand color extraction from mood boards (use mood-board-brand-vibe), color variables in Figma (use design-systems), logo color versatility (use logo-brand-identity)."
---

# Color Systems

Build accessible, cohesive color palettes using the HSB method. This skill covers everything from initial color selection through dark UI implementation.

## CORE PRINCIPLE: HSB IS THE INTUITIVE MODEL

All color work in design should start with HSB (Hue, Saturation, Brightness). It is the most intuitive model for building and modifying palettes. [MDS]

- **Hue (H):** The color itself -- 0=Red, 120=Green, 240=Blue, 360=Red
- **Saturation (S):** Whiteness slider -- 100% = pure color; 0% = white (at full brightness)
- **Brightness (B):** Blackness slider -- 100% = fully bright; 0% = black

**Why HSB wins:** Zero always means nothing, 100 always means everything. Saturation goes left-right, brightness goes up-down.

---

## COLOR SELECTION PROCESS

### Step 1: Select Dominant Hue by Rationale [Flux]

Start with color psychology as a framework (not a rule):

| Color | Associations | Common Industries |
|-------|-------------|------------------|
| Blue | Calm, trust, security, authority | Banks, software, security |
| Green | Health, growth, safety, sustainability | Health, finance, eco |
| Red | Passion, danger, urgency, love | Food, entertainment, sale CTAs |
| Yellow | Optimism, energy, happiness | Youth, energy, caution |
| Orange | Fun, creativity, earthy | Lifestyle, creative, food |
| Purple | Luxury, royalty, mystery | Premium, beauty, tech |
| Pink | Playful, rebellious, romantic | Fashion, beauty, youth |
| Black | Utility, elegance, strength, discipline | Luxury, tech, fashion |
| White | Peace, cleanliness, simplicity | Health, minimal, tech |

[CONTRARIAN] Gareis rarely follows color-emotion rules. Always be open to explore outside them. Unexpected color choices create the most memorable designs (e.g., soft pink for traditionally masculine content).

### Step 2: Finesse with HSB [Flux + MDS]

The hue alone does not communicate mood -- saturation and brightness matter equally.
- Decrease saturation = add white (muted, sophisticated)
- Decrease brightness = add black (darker, serious)
- Full saturation + brightness = loud, aggressive
- Desaturated = sophisticated, serious, subtle

### Step 3: Build Palette Using Color Harmonies [Flux]

See `references/02-palette-construction.md` for harmony types and construction methods.

### Step 4: Match Tones Across Palette [Flux]

Colors must have similar saturation/brightness levels to look like partners. A dusty pink next to a bright neon green = disaster.

[CONTRARIAN] Do not match by numbers alone -- finesse by eye. [Flux]

### Step 5: Create Contrast Variations [Flux]

Simple trick: sample your dominant color, drop brightness to ~10% for an off-black that is warmer and more cohesive than pure black.

### Step 6: Check Accessibility [Flux + MDS]

See `references/01-color-models-contrast.md` for WCAG scoring table and key hex codes.

---

## THE 60-30-10 RULE [Segall/Flux]

- **60%** = dominant color (typically background)
- **30%** = secondary color (typically content/text)
- **10%** = accent (primary brand color that pops)

These are guidelines, not rules -- meant to be broken when warranted. [Segall]

From reference analysis: 70% neutral, 30% accent is another valid split. [Gareis]

---

## STRUCTURAL VS. INTERACTIVE COLORS [MDS]

### Structural Colors
- Background colors, container backgrounds, borders, dividers
- Typically: white, light gray, or very desaturated versions of brand color
- More utility = more neutral structural colors

### Interactive Colors
- Buttons, links, action text, CTAs
- Typically: highly saturated, high contrast with structural colors
- Should be distinctly different from structural colors

### The Spectrum Pattern
Same hue at different saturation levels:
- 1-3% saturation = structural background
- 60-100% saturation = interactive element

Example: Hue 180 (teal) at 20% sat / 97% brightness = subtle background; same hue at 67% saturation = interactive text.

---

## GRAY TINTING FORMULA [MDS]

Add 1-3% saturation of your brand hue to structural grays -- creates cohesion.

**Process:**
1. Take your brand/primary hue value
2. Set saturation to 1-5%
3. Adjust brightness for desired lightness
4. Result: a gray that feels "in family" with your color scheme

**Most projects need 3-5 defined grays** for: dark text, medium text, icons, light backgrounds, dividers.

### Critical Gray Rules

- Keep all grays at the same hue value (e.g., all at ~208-210 hue)
- Adjust only saturation and brightness between variants
- Never use fully desaturated gray on top of a colored background
- Use black at reduced opacity so background color bleeds through, OR use same-hue variant at low saturation
- [ANTI-PATTERN] Gmail uses 14+ different grays with inconsistent hues -- warm mixed with cool creates visual discord

---

## COLOR DOCUMENTATION FORMAT [MDS]

For each color in your system, document:
- Human-readable name (even fun names work: "poop", "blanket")
- Hex code
- HSB values
- Description of usage
- Contrast score against backgrounds

Typical project needs 10-15 total colors (see `references/02-palette-construction.md` for the SmartLine example).

---

## COLOR FROM PHOTOGRAPHY [Gareis + Flux]

Sample colors directly from hero photographs to create cohesive palettes. Photography colors tend to be naturally muted and harmonious.

**Process:**
1. Select hero image for the project
2. Sample 4-6 prominent colors from the image
3. Test candidates against existing palette for clashes
4. Verify contrast is sufficient but not jarring
5. Ensure it works at large sizes (backgrounds, big typography)
6. Confirm it supports the intended emotional direction

---

## COMPETITIVE COLOR CHECK [Flux]

Always check competitor colors. If the market leader owns red-and-white in a category, choosing the same creates confusion, not category credentials. Differentiation matters.

---

## ANTI-PATTERNS

- Using pure black (#000000) as a background (except OLED)
- Using pure desaturated grays instead of brand-tinted grays
- Yellow text on white backgrounds (1.07 contrast -- nearly invisible)
- Gradient transitions across opposing hues (red to green = muddy brown midpoint)
- Too many grays with inconsistent hue values
- Overusing the interactive color until the signal weakens
- Color as the ONLY way to convey information (WCAG violation)
- Matching palette colors by numbers without checking visually

---

## RELATED SKILLS

- **typography-systems:** Interactive text color system for links and actions
- **mood-board-brand-vibe:** Brand direction and color extraction from mood boards
- **design-systems:** Creating color variables and tokens in Figma
- **layout-spacing:** White/gray background elevation patterns
- **logo-brand-identity:** Logo color versatility and print color space (RGB/CMYK/Pantone)
- **design-critique:** Common color contrast mistakes from the Critique Vault
