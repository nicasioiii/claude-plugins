---
name: Type System
description: Design a complete typographic scale and hierarchy for a project. Walks through font selection, sizing with the Rule of Four, weight hierarchy, line-height, tracking, and text style definition.
skill: typography-systems
---

# /type-system

You are helping the user design a complete typography system. Follow this workflow:

## Step 1: Understand Context

Ask the user:
1. **What type of project?** (marketing site, app, dashboard, e-commerce, editorial)
2. **What mood/personality?** (modern, classic, bold, elegant, playful, serious)
3. **System or custom fonts?** (platform-native feel vs. brand differentiation)
4. **How much text content?** (minimal marketing copy vs. long-form vs. data-heavy)
5. **Any existing brand fonts or guidelines?**

## Step 2: Font Selection

Using the font selection process from typography-systems:
1. Match mood to font classification (serif, sans, display, script, mono)
2. Recommend 1-2 specific fonts with reasoning for each
3. Verify the font has enough weight variations for hierarchy needs
4. Check legibility: x-height, counter spaces, stroke contrast
5. Note tracking adjustments needed (most fonts need -2% to -3% for body)

Reference `02-font-classification-pairing.md` for specific font recommendations, industry pairings, and pairing strategies.

## Step 3: Build Type Scale (Rule of Four)

Apply the Rule of Four -- limit to 3-4 distinct sizes maximum:
- Use headline multiples of body size (1.5x, 2x, 3x, 4x)
- Snap to the nearest 8px grid value
- Define each style with the 5 Properties: size, weight, line-height, tracking, color

Reference `01-type-scale-values.md` for specific values and ranges.

## Step 4: Define Weight Hierarchy

Set weight rules:
- Headlines: Semi-bold to Black (600-900)
- Body: Regular (400); bold only for emphasis
- Metadata/captions: Regular to Medium (400-500)
- Ensure at least 2-3 weight steps between headline and body
- Never force-bold a font without a dedicated bold weight

## Step 5: Set Line-Height and Tracking

| Element | Line Height | Tracking |
|---------|-------------|----------|
| Hero titles | 75-100% | -3% to -5% |
| Section titles | 100-120% | -2% to -3% |
| Body copy | 130-175% (start at 150%) | -1% to -3% |
| All-caps labels | 120%+ | +5% to +80% |

## Step 6: Verify Body Copy Width

Check that body text stays within:
- Minimum: 45 characters per line
- Sweet spot: 55-65 characters
- Maximum: 75 characters per line

## Step 7: Document the System

Output a Text Style System template:

```
TEXT STYLE SYSTEM
Display:     [font] / [size]px / [weight] / [line-height]% / [tracking]
Heading 1:   [font] / [size]px / [weight] / [line-height]% / [tracking]
Heading 2:   [font] / [size]px / [weight] / [line-height]% / [tracking]
Body:        [font] / [size]px / [weight] / [line-height]% / [tracking]
Body Small:  [font] / [size]px / [weight] / [line-height]% / [tracking]
Caption:     [font] / [size]px / [weight] / [line-height]% / [tracking]
Label:       [font] / [size]px / [weight] / [line-height]% / [tracking]
```

## Step 8: Recommend Next Steps

- If color is not defined → recommend `/color-palette`
- If spacing is not defined → recommend `/layout-grid`
- If ready for Figma → recommend setting up text styles in `/design-system`

## Skills Activated

- **typography-systems** (primary)
- Cross-references: color-systems, layout-spacing, design-systems
