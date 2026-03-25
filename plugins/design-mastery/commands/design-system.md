---
name: Design System
description: Set up a Figma design system with tokens, components, variants, variables, and auto layout. Covers atomic design methodology and file organization.
skill: design-systems
---

# /design-system

You are helping the user set up a design system in Figma. Follow this workflow:

## Step 1: Understand Scope

Ask the user:
1. **What is the project?** (new product, existing redesign, multi-product system)
2. **How large is the system?** (single product vs. multi-brand)
3. **What foundations exist?** (type scale, color palette, spacing tokens -- or building from scratch?)
4. **Who will use the system?** (solo designer, team, developer handoff)
5. **What Figma plan?** (free vs. professional -- affects variable and library features)

## Step 2: Establish Foundations (Atomic Elements)

Set up the atomic design layers:

### Color Variables
- Create color styles for every palette color
- Organize by role: Primary, Secondary, Neutral, Semantic (success, warning, error, info)
- Set up light and dark mode variable collections if needed
- Use 1-3% brand hue tinting on grays for cohesion

### Text Styles
- Create Figma text styles matching the type scale
- Include: font family, size, weight, line-height, letter-spacing
- Name consistently: Display, H1, H2, H3, Body, Body Small, Caption, Label

### Spacing Tokens
- Define spacing variables on the 8px grid
- Name tokens semantically: space-xs (4), space-sm (8), space-md (16), space-lg (24), space-xl (32)

### Effect Styles
- Shadows (elevation levels)
- Border radius tokens
- Blur effects

## Step 3: Build Component Library

Follow the inside-out construction pattern:
1. **Atoms:** Icons, buttons, inputs, labels, badges
2. **Molecules:** Search bars (input + button), form fields (label + input + helper), card headers
3. **Organisms:** Navigation bars, card groups, form sections, hero blocks

For each component:
- Use auto layout for all spacing
- Create variants for size (sm, md, lg) and state (default, hover, active, disabled)
- Use component properties: boolean (show/hide icon), instance swap (icon options), text
- Set constraints for responsive resizing

## Step 4: Organize the File

Recommended page structure:
- Cover page (project name, version, last updated)
- Foundations (colors, typography, spacing, effects)
- Components (organized by type or atomic level)
- Patterns (common component combinations)
- Templates (full-page layouts)

## Step 5: Set Up for Handoff

- Enable Dev Mode annotations on key components
- Document component usage notes
- Specify spacing in tokens, not raw pixels
- Include interaction notes (hover states, transitions)

## Step 6: Recommend Next Steps

- If foundations are missing → recommend `/type-system`, `/color-palette`, `/layout-grid`
- If components need designing → recommend `/component-pattern`
- If building pages → recommend `/homepage-structure` or `/dashboard-design`

## Skills Activated

- **design-systems** (primary)
- Cross-references: typography-systems, color-systems, layout-spacing, ui-components
