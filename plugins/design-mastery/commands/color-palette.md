---
name: Color Palette
description: Build an accessible, cohesive color system. Walks through hue selection, HSB construction, contrast checking, structural vs interactive spectrum, and gray tinting.
skill: color-systems
---

# /color-palette

You are helping the user build a color system. Follow this workflow:

## Step 1: Understand Context

Ask the user:
1. **What industry/brand personality?** (use color psychology as starting framework)
2. **Any existing brand colors?** (hex codes, brand guidelines)
3. **Light UI, dark UI, or both?**
4. **What competitors should we differentiate from?**

## Step 2: Select Dominant Hue

Using the color selection process from color-systems:
1. Match industry/personality to hue using psychology table
2. Finesse with HSB -- adjust saturation and brightness for appropriate tone
3. Check against competitor colors for differentiation

## Step 3: Build the Palette

1. Choose color harmony type (analogous, complementary, monochromatic, etc.)
2. Match tones across all palette colors (similar saturation/brightness levels)
3. Build the structural-interactive spectrum from the brand hue
4. Create 3-5 brand-tinted grays using the gray tinting formula
5. Define primary and secondary interactive colors

Reference `02-palette-construction.md` for the full spectrum pattern and SmartLine example.

## Step 4: Check Accessibility

Verify all text-on-background combinations against WCAG:
- Body text: 4.5:1 minimum (AA)
- Large text: 3.0:1 minimum (AA Large)
- Long-form reading: aim for 7.0:1 (AAA)

Reference `01-color-models-contrast.md` for key hex codes and boundary values.

## Step 5: Document the System

For each color, provide:
- Human-readable name
- Hex code and HSB values
- Usage description
- Contrast score against backgrounds

## Step 6: Dark UI (if needed)

If the project requires dark mode, reference `03-dark-ui-gradients.md`:
- Use off-black backgrounds (#161416 range), not pure black
- Apply tinted darks technique
- Reduce saturation on supporting elements
- Nail typography and layout BEFORE fine-tuning colors

## Step 7: Recommend Next Steps

- If typography is not defined → recommend `/typography`
- If spacing is not defined → recommend `/layout-grid`
- If ready for Figma → recommend creating color variables in design-systems
