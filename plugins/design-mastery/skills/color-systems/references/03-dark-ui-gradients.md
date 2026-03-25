---
name: Dark UI & Gradients
description: |
  When to Read: Designing dark mode interfaces, creating gradients, understanding color psychology for specific industries, or troubleshooting dark UI contrast issues.
  Cross-references: 01-color-models-contrast.md (contrast scoring for dark backgrounds), 02-palette-construction.md (gray construction methods), web-layout (dark section design).
---

# Dark UI & Gradients

## DARK UI -- THE HARDEST MODE [MDS]

### Core Principles

- All light UI principles apply to dark UI -- but mistakes are amplified
- Dividers, borders, and subtle elements show up FAR more dramatically on dark backgrounds
- **Never just reverse colors** -- it does not work (like inverting a photo)

### Background Color

[CONTRARIAN] Full black (#000000) usually does not work as a background -- exception: OLED displays where pixels physically turn off. [MDS]

**Use NOT pure black:**
- #161416 (slightly purple-tinted dark)
- #1A1A1C (neutral near-black)
- #1E1E20 (slightly lighter dark base)
- #0F0F11 (sidebar/deeper dark)

### Tinted Darks Technique [MDS]

Remove some green from hex code for subtle purple tint:
- #494949 (pure gray) vs. #494749 (purple-tinted) = richer, warmer feel
- Apply across all dark values for cohesion

### The Dark UI Process

1. **First:** Nail typography and layout on the dark background
2. **Then:** Nail negative space and visual hierarchy
3. **LAST:** Fine-tune colors, dividers, and subtle elements

Typography and layout first, color last -- even more important than with light UI.

### Dark UI Problems

- White text on pure black "vibrates" more than dark text on white
- Reduce vibration by using off-black backgrounds and slightly off-white text (#E0E0E0 range)
- Borders and dividers dominate on dark backgrounds -- use even MORE subtlety than light UI
- Saturated elements stand out more on dark backgrounds -- reduce saturation for supporting elements

### Twitter Dark Mode Critique [MDS]

- "Dim" mode: too much saturation in dividers -- they stand out more than intended
- "Lights Out" (full black): makes borders and bright icons dominate; white-on-black text vibrates harder
- Dark UI requires even MORE subtlety with dividers and borders than light UI

---

## GRADIENT RULES [MDS]

### Types

- **Linear gradients:** Most common for backgrounds, buttons, header bars
- **Radial gradients:** For spotlights, glows, atmospheric effects

### Color Proximity Rule

Keep gradient colors close on the hue wheel to avoid muddy transitions:
- **Safe zone:** Within 60-90 degrees on the hue wheel
- **Danger zone:** Opposing hues (red to green) create ugly brown/gray midpoints
- Blue to purple = safe and beautiful
- Orange to yellow = warm and cohesive
- Red to blue = acceptable but use carefully

### Gradient Usage

Gradients add depth, dimension, and visual interest. Use for:
- Hero section backgrounds
- Button hover states
- Card backgrounds
- Decorative elements
- Overlay effects on images

**Do not use gradients** as a substitute for a proper color palette. A gradient is an enhancement, not a foundation.

---

## COLOR PSYCHOLOGY REFERENCE TABLE

| Color | Primary Associations | Industries | Emotional Effect |
|-------|---------------------|-----------|-----------------|
| Red | Passion, urgency, danger, love | Food, entertainment, sales | Increases heart rate, creates urgency |
| Orange | Fun, creativity, warmth, earthy | Lifestyle, creative, food | Friendly, approachable, energetic |
| Yellow | Optimism, energy, happiness, caution | Youth brands, energy, construction | Attention-grabbing, cheerful |
| Green | Health, growth, safety, nature | Health, finance, eco, wellness | Calming, trustworthy, fresh |
| Blue | Calm, trust, security, authority | Banks, software, security, health | Most universally liked; professional |
| Purple | Luxury, royalty, mystery, creativity | Premium brands, beauty, tech | Sophisticated, imaginative |
| Pink | Playful, rebellious, romantic | Fashion, beauty, youth | Modern, bold when saturated |
| Brown | Earth, stability, warmth | Coffee, outdoor, organic | Natural, grounded |
| Black | Elegance, strength, discipline, utility | Luxury, tech, fashion | Powerful, sophisticated |
| White | Peace, cleanliness, simplicity | Health, minimal, tech | Clean, spacious |
| Gray | Neutral, professional, sophisticated | Corporate, tech, finance | Mature, balanced |

### Saturation Effect on Mood

- **High saturation** = energetic, playful, bold, youthful
- **Low saturation** = sophisticated, serious, subtle, premium
- Color wheel outer edge (saturated) = energetic designs
- Color wheel inner area (desaturated) = high-class/serious designs
- This applies to ALL hues [Gareis]

---

## COMPETITIVE COLOR DIFFERENTIATION [Flux]

### Process

1. Map the dominant colors of top 5-10 competitors
2. Identify the "owned" colors in your category (e.g., Coca-Cola owns red in soda)
3. Choose a color that differentiates while remaining appropriate for the category
4. Test your chosen color against competitor palettes -- would someone confuse your brand?

### When to Match Category Norms

- Financial services: blue/green is expected -- straying too far may reduce trust
- Health: green/blue/white communicate cleanliness
- Food: warm colors (red, orange, yellow) stimulate appetite

### When to Break Category Norms

- When the brand positioning is explicitly "different" or "disruptive"
- When the category is visually homogeneous (everyone uses blue -- stand out with orange)
- When the brand personality is strong enough to redefine expectations

---

## DARK UI ELEMENT-SPECIFIC GUIDANCE [MDS]

### Dark UI Text Colors

| Element | Color Recommendation | Notes |
|---------|---------------------|-------|
| Primary text | #E0E0E0 range (off-white) | Avoid pure #FFFFFF to reduce vibration |
| Secondary text | #A0A0A0 range | Clearly subordinate to primary |
| Disabled text | #606060 range | Must still be distinguishable |
| Links/interactive | Brand color at reduced saturation | Saturated colors pop more on dark |

### Dark UI Surface Layering

Use lighter shades of the base background to create elevation:
- Base background: #161416 - #1A1A1C
- Raised surface (cards): +2-4% brightness from base
- Higher elevation (modals): +4-8% brightness from base
- Sidebar/navigation: -2% brightness from base (darker)

### Dark UI Border and Divider Rules

- Borders and dividers dominate on dark backgrounds -- use even MORE subtlety than light UI
- Use semi-transparent white borders (rgba(255,255,255,0.08-0.12)) instead of solid gray
- Reduce border width from 1px to 0.5px if rendering allows
- Consider removing borders entirely and relying on surface elevation differences

### Dark UI Saturated Element Adjustment

- Saturated elements stand out more on dark backgrounds -- reduce saturation for supporting elements
- Keep full saturation only for primary interactive colors
- Desaturate status indicators (success, warning, error) by 10-20% compared to light UI versions
- Icons that were dark gray on light UI should become light gray, not pure white

---

## GRAY PALETTE CONSTRUCTION [MDS]

### The Cohesive Gray Method

Most projects need 3-5 defined grays for: dark text, medium text, icons, light backgrounds, dividers.

**The Rules:**
- Keep all grays at the same hue value (e.g., all at ~208-210 hue)
- Adjust only saturation and brightness between gray variants
- Result: all grays feel cohesive because they share the same color family

**The Brand-Tinted Gray Formula:**
1. Take your brand/primary hue
2. Set saturation to 1-5%
3. Vary brightness for different uses
4. Result: a gray that feels "in family" with your color scheme

[ANTI-PATTERN] Gmail uses 14+ different grays with inconsistent hues -- warm grays mixed with cool grays creates visual discord. Avoid this. [MDS]

---

## ELEVATION AND DEPTH WITH COLOR [MDS]

- White elements appear closest to the user (foreground); darker elements recede (background)
- Shadows reinforce this: elements with shadows float above elements without
- Without borders: very subtle background color difference may not be enough contrast -- borders help define edges
- Too dark a background = too much contrast, visual weight in wrong places
