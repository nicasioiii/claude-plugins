---
name: Color Models & Contrast Reference
description: |
  When to Read: Checking WCAG contrast requirements, looking up color model differences, finding key hex codes for contrast, or verifying accessibility compliance.
  Cross-references: color-systems SKILL.md (selection process), 02-palette-construction.md (building palettes), typography-systems (text contrast requirements).
---

# Color Models & Contrast Reference

## COLOR MODEL COMPARISON [MDS]

| Model | Format | Best For | Notes |
|-------|--------|---------|-------|
| **HSB** | H: 0-360, S: 0-100%, B: 0-100% | **Design work (preferred)** | Most intuitive; S=whiteness, B=blackness |
| **HSL** | H: 0-360, S: 0-100%, L: 0-100% | Finding muddy/desaturated variants | 50% L = pure color; S pulls toward gray |
| **RGB** | R: 0-255, G: 0-255, B: 0-255 | Code handoff | Not intuitive for design |
| **Hex** | #RRGGBB (6 digits) | Universal sharing | Shorthand: #000, #fff, #f00 |

### HSB Deep Dive (Preferred Model) [MDS]

- **Hue (H):** The color itself -- 0=Red, 120=Green, 240=Blue, 360=Red again
- **Saturation (S):** Whiteness slider -- 100% = pure color; 0% = white (at full brightness)
- **Brightness (B):** Blackness slider -- 100% = fully bright; 0% = black
- **Why HSB wins:** Saturation always goes left-right; Brightness always goes up-down; zero=nothing, 100=everything -- simple mental model

### HSB vs HSL Saturation Difference

- **HSB saturation** pulls toward white -- like reducing opacity on a white background
- **HSL saturation** pulls toward muddy/gray -- useful for finding richer secondary color variants
- HSL advantage: changing saturation produces muddier, more nuanced colors good for secondary palettes

### Hex Code Shorthand

- `#000` = `#000000` (black)
- `#fff` = `#ffffff` (white)
- `#f00` = `#ff0000` (red)

---

## STRUCTURAL VS. INTERACTIVE COLORS [MDS]

Understanding the structural-interactive spectrum is essential for applying contrast correctly:

**Structural Colors:**
- Background colors, container backgrounds, borders, dividers
- Typically: white, light gray, or very desaturated versions of brand color
- More utility = more neutral structural colors (leave room for user-generated content)

**Interactive Colors:**
- Buttons, links, action text, CTAs
- Typically: highly saturated, high contrast with structural colors
- Should be distinctly different from structural colors

**The Spectrum Pattern:**
- Same hue at different saturation levels: 1-3% saturation = structural background; 60-100% = interactive
- Example: Hue 180 (teal) at 20% saturation/97% lightness = subtle background; same hue at 67% saturation = interactive text

**Tinting Structural Grays:**
- Add 1-3% saturation of your brand hue to structural grays -- creates cohesion
- `#F5F5F5` (pure gray) vs. adding 1-2% saturation at brand hue = warmer, more intentional feel

**Color Perception Rules:**
- Surrounding colors affect perception -- the same gray looks different on white vs. black backgrounds
- Simultaneous contrast illusion: identical colors appear different when surrounded by different values
- Never use fully desaturated gray on top of a colored background -- use the same hue variant at low saturation, or use black at reduced opacity so background color bleeds through

---

## WCAG CONTRAST SCORING TABLE [MDS]

| Score | Level | Minimum Font Size | Use Case |
|-------|-------|-------------------|---------|
| 3.0:1 | AA Large | 18.5px bold / 24px regular | Large titles, big UI elements |
| 4.5:1 | AA | Any size | **Sweet spot** -- body copy, standard UI text |
| 7.0:1 | AAA | Any size | Best for long-form reading |
| 21.0:1 | Maximum | N/A | Black on white (theoretical max) |

### Practical Contrast Guidance

| Rule | Value | Notes |
|------|-------|-------|
| Body text on white (minimum) | #767676 | Approximately AA (4.5:1) -- lightest gray for body copy on white |
| Body text on white (recommended) | #595959 | AAA level for comfortable reading |
| Body text on black (minimum) | #757575 | Approximately AA (4.5:1) |
| Titles + body (blog posts) | 7.0:1+ | Aim for AAA on long-form content |

### Per-Color Contrast with White

Fully saturated hues have varying contrast with white:
- Dark Blue: ~8.0+ (excellent)
- Red: ~4.0 (borderline AA)
- Yellow: ~1.07 (nearly invisible -- NEVER use yellow text on white)

---

## KEY HEX CODES FOR DESIGN [MDS]

### Contrast Boundary Values

| Hex | On White | On Black | Use |
|-----|----------|----------|-----|
| #000000 | 21.0 (max) | -- | Pure black text |
| #2C2C2C | -- | 1.5 (fail) | Too similar to black BG |
| #595959 | ~7.0 (AAA) | -- | Recommended body on white |
| #666666 | -- | 3.0 (AA Large) | Body text on dark BG |
| #757575 | -- | 4.5 (AA) | Lightest body on dark BG |
| #767676 | ~4.5 (AA) | -- | Lightest body on white BG |
| #FFFFFF | -- | 21.0 (max) | Pure white text |

### Common Dark UI Background Values

| Hex | Description |
|-----|------------|
| #161416 | Slightly purple-tinted dark (recommended) |
| #1A1A1C | Neutral near-black |
| #1E1E20 | Slightly lighter dark base |
| #0F0F11 | Sidebar/deeper dark |

### Accessibility Checker Tools

- **Coolors.co** -- generate palettes + check contrast
- **colorcontrast.cc** -- interactive slider for testing ratios
- **Adobe Color** -- contrast checker + colorblind safety
- **Figma plugin "Contrast"** -- in-design accessibility checking
- **Tailwind CSS color generator** -- input hex, get shade/tint scale

---

## CONTRAST EXCEPTIONS [MDS]

[CONTRARIAN] Failing contrast is acceptable when:
- Text is extremely large (60pt+)
- Surrounding context provides additional information (labels, icons, cursor position)
- The element is decorative rather than critical for understanding
- Placeholder text in input fields (expected to be lighter)

These exceptions should be documented and intentional, never accidental.

---

## COLOR DOCUMENTATION FORMAT [MDS]

Per-Color Documentation (GoDaddy SmartLine example -- 13 total colors):

| Attribute | Format |
|-----------|--------|
| Color name | Human-readable (even fun names work) |
| Hex code | Standard 6-digit hex |
| HSB values | Hue, Saturation, Brightness |
| Usage description | When and where to use |
| Contrast score | Against primary backgrounds |

### GoDaddy SmartLine System Example

1. Standard white -- primary background
2. Light gray -- secondary interactive element backgrounds
3. Lighter accent gray -- placeholder text, large single-field values
4. Darker accent gray -- standalone icons, elements needing more weight
5. AA Large gray -- 18pt regular / 14pt bold helper text
6. AA gray -- text under 18pt, body copy
7. Primary dark (#2B2B2B) -- primary text AND primary CTA color
8-9. Accent red pair -- error/missed call: light red background + dark red text
10-13. Teal pair for interactive text: AA Large + AA version + light teal background
