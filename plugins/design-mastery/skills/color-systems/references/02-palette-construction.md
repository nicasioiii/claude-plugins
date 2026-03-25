---
name: Palette Construction & Color Spectrum
description: |
  When to Read: Building a color palette from scratch, applying the 60-30-10 rule, defining structural vs interactive colors, or creating a documented color system.
  Cross-references: 01-color-models-contrast.md (contrast checking), 03-dark-ui-gradients.md (dark mode palettes), color-systems SKILL.md (overall process).
---

# Palette Construction & Color Spectrum

## COLOR HARMONY TYPES [Flux + Gareis]

| Harmony | Description | Best For |
|---------|------------|---------|
| Analogous | Neighboring colors on wheel | Harmonious, low-contrast palettes |
| Monochromatic | Same hue, different sat/brightness | Elegant, cohesive, safe |
| Complementary | Opposite on wheel | High impact, bold contrast |
| Split-complementary | Just off opposite | More nuanced than complementary |
| Triadic | Three equidistant points | Vibrant, balanced variety |

### Tone Matching Rule

Colors must have similar saturation/brightness levels to look like partners.

- Dusty pink + bright neon green = disaster
- Dusty pink + muted sage = cohesive
- [CONTRARIAN] Do not match by numbers alone -- finesse by eye [Flux]

---

## THE STRUCTURAL-INTERACTIVE SPECTRUM [MDS]

### Building the Full Spectrum

From one brand hue, create your entire color system:

```
STRUCTURAL (low sat)          →          INTERACTIVE (high sat)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
1-3% sat     5-20% sat      30-50% sat     60-100% sat
Backgrounds  Tinted grays   Muted accents  Buttons/links/CTAs
```

### Wireframe Palette (Minimal)

Only 5-6 colors needed for a complete wireframe:
- White (primary background)
- Light gray (secondary background)
- Medium gray (icons, metadata)
- Dark gray/near-black (primary text)
- One blue (interactive elements)

---

## COMPLETE COLOR SYSTEM EXAMPLE [MDS -- GoDaddy SmartLine]

13 total colors for an entire application:

| # | Name | Hex | Usage | Contrast |
|---|------|-----|-------|----------|
| 1 | Standard white | #FFFFFF | Primary background | -- |
| 2 | Light gray | ~#F5F5F5 | Secondary interactive element BGs | -- |
| 3 | Lighter accent gray | ~#BFBFBF | Placeholder text, large display values | May fail at small sizes |
| 4 | Darker accent gray | ~#8C8C8C | Standalone icons, elements needing weight | AA Large |
| 5 | AA Large gray | ~#767676 | 18pt regular / 14pt bold helper text | 3.0:1 (AA Large) |
| 6 | AA gray | ~#595959 | Text under 18pt, body copy | 4.5:1 (AA) |
| 7 | Primary dark | #2B2B2B | Primary text AND primary CTA color | 7.0+ |
| 8 | Error light | ~#FFF0F0 | Error state background | -- |
| 9 | Error dark | ~#CC0000 | Error/missed call text | AA on light BG |
| 10 | Teal AA Large | ~#009B9B | Interactive text (large) | 3.0:1 |
| 11 | Teal AA | ~#008080 | Interactive text (standard) | 4.5:1 |
| 12 | Teal light | ~#E0F5F5 | Interactive element background | -- |
| 13 | Teal dark | ~#006666 | Interactive emphasis | 4.5+ |

**Type sizes for entire app:** Only 4 sizes -- 20pt (occasional), 18pt, 16pt, 14pt.

---

## PRIMARY AND SECONDARY INTERACTIVE COLORS [MDS]

- **Primary color:** Most important interactive -- main CTAs, brand recognition
- **Secondary color:** Less important actions (cancel, secondary nav, helper links)
- Sometimes brand color serves as secondary (text links) while dark/black serves as primary CTA
- Define clear rules: "Green is for creating/manipulating content; structural brown is for loading more of existing content"

---

## GRAY CONSTRUCTION METHODS [MDS]

### Method 1: Brand-Tinted Grays

1. Take brand/primary hue value
2. Set saturation to 1-5%
3. Adjust brightness for desired lightness

### Method 2: Opacity-Based Grays

Use black at reduced opacity so background color bleeds through:
- 90% opacity black on colored BG = dark text with color undertone
- 50% opacity black = medium element
- 20% opacity black = subtle divider/border

### Method 3: Same-Hue Family [MDS -- Twitter Example]

Keep all grays at same hue value (e.g., all at ~208-210 hue). Adjust only saturation and brightness between variants. Result: all grays feel cohesive.

**Pinterest mastery:** Only 3 core grays -- dark text (#333), medium for icons/metadata, light for backgrounds.

---

## COLOR AMOUNT AND PERCEPTION [MDS]

### Simultaneous Contrast

The same color appears different depending on surrounding colors:
- Same gray looks different on white vs. black backgrounds
- A red CTA looks different on green vs. white vs. black backgrounds

### Modification Rule

When adjusting colors, account for how the surrounding environment changes perception. Always evaluate colors in context, not in isolation.

---

## COLOR NAMING CONVENTIONS [Segall]

Name colors semantically, not by hex value:
- `gray-bg` not `#F5F5F5`
- `gray-mid` not `#757575`
- `brand-primary` not `#0066CC`

After defining, walk through the design to verify no sections look broken from consolidation.

---

## WHITE/LIGHT-GRAY ELEVATION SYSTEM [MDS]

### The Pattern

Light gray background (#F5F5F5 range) + white modules sitting "on top" creates visual elevation without drop shadows.

### Options

| Approach | When |
|----------|------|
| White on light gray, no border | Minimal, clean |
| White on light gray + thin border (0.5-1px) | More definition |
| White on light gray + subtle shadow | Modern elevation |

### Balancing Act

- Too dark a background = too much contrast in wrong places
- Too many borders = cluttered
- Sweet spot: barely-visible gray background + white cards + optional ultra-thin border
- For high-density information, white modules on gray >> all-white (avoids heavy border usage)
