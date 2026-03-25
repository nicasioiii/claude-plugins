---
name: Layout Grid
description: Set up a grid system, spacing tokens, and responsive breakpoints for a project. Walks through grid selection, spacing scale, density level, pacing, and breakpoint strategy.
skill: layout-spacing
---

# /layout-grid

You are helping the user set up a layout grid and spacing system. Follow this workflow:

## Step 1: Understand Context

Ask the user:
1. **What type of project?** (marketing site, app, dashboard, e-commerce)
2. **What density level?** (marketing = low density, dashboard = high density)
3. **What breakpoints are needed?** (standard 3: desktop/tablet/mobile, or more?)
4. **8px grid or 4pt grid preference?**
5. **Any existing design system or spacing tokens?**

## Step 2: Select Grid Type

Based on content type, recommend a grid approach:
- **Column grid (12-column):** Best for text-heavy content and general web
- **Modular grid:** Best for data-heavy interfaces and diverse content
- **Hierarchical grid:** Best for editorial layouts with varied content types
- **Simple column grid (fewer columns):** Best for focused, minimal layouts

12-column grids offer factors of 1, 2, 3, 4, 6, 12 for maximum flexibility. You do not need to fill every column -- empty columns create intentional white space.

## Step 3: Define Spacing Scale

Build a spacing token scale on the 8px grid:

| Token | Value | Use Case |
|-------|-------|----------|
| xs | 4px | Icon-to-label gap, tight grouping |
| sm | 8px | Related elements within a component |
| md | 16px | Component internal padding |
| lg | 24px | Between components, card padding |
| xl | 32-40px | Between sections on dense layouts |
| 2xl | 48-64px | Section padding on marketing pages |
| 3xl | 80-120px | Major section divisions |

## Step 4: Configure Responsive Breakpoints

| Breakpoint | Width | Columns | Margins | Gaps |
|-----------|-------|---------|---------|------|
| Desktop | 1440px | 12 | 24-64px | 24-40px |
| Tablet | 810px | 6 | max 32px | max 32px |
| Mobile | 390px | 4 or 2 | 24px | 24px |

Define what changes at each breakpoint:
- Column count reduction
- Typography size adjustments
- Spacing scale reductions
- Navigation pattern changes (hamburger, bottom nav)
- Component stacking behavior

## Step 5: Set Density Level

| Density | Section Padding | Element Gaps | Type Scale | Best For |
|---------|----------------|-------------|------------|---------|
| Low | 80-120px | 24-48px | Larger | Marketing, portfolio |
| Medium | 40-64px | 16-24px | Standard | General web, e-commerce |
| High | 16-32px | 4-12px | Smaller | Dashboard, admin, SaaS |

## Step 6: Plan Pacing Strategy

- Alternate between dense and open sections for visual rhythm
- Create "wow moments" between quieter content sections
- Vary alignment direction through the page
- Ensure breathing room after data-heavy sections
- Think of websites like movies -- each scroll panel is part of a cinematic story

## Step 7: Document the System

Output a grid specification:
- Grid type and column count per breakpoint
- Gutter and margin values
- Spacing token scale with names and pixel values
- Density rules per area/section type
- Breakpoint behavior notes

## Step 8: Recommend Next Steps

- If typography is not defined → recommend `/type-system`
- If color is not defined → recommend `/color-palette`
- If page structure is needed → recommend `/homepage-structure`
- If ready to build → recommend `/webflow-build`

## Skills Activated

- **layout-spacing** (primary)
- Cross-references: typography-systems, web-layout, webflow-build
