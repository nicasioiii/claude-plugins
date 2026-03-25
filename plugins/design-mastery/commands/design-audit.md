---
name: Design Audit
description: Systematic design review checklist covering typography, color, spacing, layout, hierarchy, and accessibility. Based on Shift Nudge critique patterns.
skill: design-critique
---

# /design-audit

You are conducting a systematic design review. Follow this checklist workflow:

## Step 1: Gather Context

Ask the user:
1. **What am I reviewing?** (screenshot, Figma link, live URL, wireframe)
2. **What stage is this?** (early exploration, mid-refinement, pre-launch)
3. **What type of design?** (marketing site, app, dashboard, e-commerce, landing page)
4. **Any specific concerns?** (or full audit)

## Step 2: Typography Audit

Check for these common issues (from 273+ Shift Nudge critique reviews):

### Font Size (66 critique patterns)
- [ ] Are there 4 or fewer distinct font sizes? (Rule of Four)
- [ ] Is the size contrast between heading and body dramatic enough? (2x+ multiples)
- [ ] Is metadata clearly subordinate to body text?
- [ ] Are line-heights appropriate? (100% titles, 150% body)

### Font Weight (28 critique patterns)
- [ ] Is there sufficient weight contrast between hierarchy levels?
- [ ] Are light/hairline weights avoided at small sizes?
- [ ] Is weight used for interactive signaling? (bold = active/primary)

### General Typography
- [ ] Body copy width within 45-75 characters per line?
- [ ] Tracking appropriate? (negative on headlines, neutral on body)
- [ ] Consistent text styles throughout?

## Step 3: Color Audit

- [ ] All text passes WCAG AA contrast (4.5:1 body, 3:1 large)?
- [ ] Body text on white no lighter than #767676?
- [ ] Interactive colors distinct from structural colors?
- [ ] No yellow text on white backgrounds?
- [ ] Gray palette uses consistent hue tinting (not mixed warm/cool)?
- [ ] Color count is restrained (palette is intentional, not accumulated)?

## Step 4: Spacing & Layout Audit

- [ ] Consistent spacing scale throughout (8px grid)?
- [ ] Related elements are closer than unrelated elements (proximity principle)?
- [ ] Section padding is consistent and appropriate for density level?
- [ ] Elements are properly aligned to grid?
- [ ] Negative space is used intentionally (not just leftover)?

## Step 5: Hierarchy Audit (48 critique patterns)

- [ ] Clear reading order: what is first, second, third?
- [ ] Single focal point per section (not everything competing)?
- [ ] Lower-priority elements are clearly subordinate?
- [ ] Visual weight distributed intentionally (size + weight + color + position)?

## Step 6: Component Audit

- [ ] All interactive elements look interactive (affordance)?
- [ ] Button hierarchy is clear (primary vs. secondary vs. tertiary)?
- [ ] Form inputs have proper states (default, focus, error, disabled)?
- [ ] Touch targets meet 44px minimum on mobile?

## Step 7: Responsive Audit

- [ ] Layout works at desktop, tablet, and mobile widths?
- [ ] Navigation adapts appropriately?
- [ ] Images are optimized and do not overflow containers?
- [ ] Text remains readable at all breakpoints?

## Step 8: Deliver Findings

Categorize issues by severity:
- **Critical:** Accessibility failures, broken layouts, unreadable text
- **Major:** Hierarchy confusion, inconsistent spacing, poor contrast
- **Minor:** Tracking adjustments, alignment tweaks, weight refinements

For each issue, provide:
1. What the problem is
2. Where it occurs
3. How to fix it (reference specific skill if applicable)

## Step 9: Recommend Next Steps

- Route fixes to the appropriate skill:
  - Typography issues → `/type-system`
  - Color issues → `/color-palette`
  - Spacing issues → `/layout-grid`
  - Component issues → `/component-pattern`
  - Responsive issues → `/responsive-check`

## Skills Activated

- **design-critique** (primary)
- Cross-references: all other skills as needed for specific fixes
