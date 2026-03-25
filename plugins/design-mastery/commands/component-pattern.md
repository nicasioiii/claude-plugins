---
name: Component Pattern
description: Quick-reference lookup for UI component design patterns. Covers buttons, cards, forms, navigation, modals, tables, and more with sizing, states, and accessibility rules.
skill: ui-components
---

# /component-pattern

You are helping the user design or reference a UI component pattern. Follow this workflow:

## Step 1: Identify the Component

Ask the user:
1. **Which component?** (button, card, form, navigation, modal, table, tabs, input, dropdown, toggle, badge, toast, accordion, pagination, tooltip, breadcrumb, search bar)
2. **What context?** (marketing site, app, dashboard, e-commerce)
3. **What density?** (compact for dashboards, standard for web, spacious for marketing)
4. **Any existing design system constraints?**

## Step 2: Provide Pattern Reference

For the requested component, deliver:

### Sizing Guidelines
- Minimum and recommended dimensions
- Padding values (inner spacing)
- Touch target minimums (44x44px for mobile, 24x24px minimum for desktop)

### States
Walk through all required states:
- Default / Resting
- Hover
- Active / Pressed
- Focused (keyboard navigation)
- Disabled
- Loading (if applicable)
- Error / Success (if applicable)

### Affordance Rules
- Does the element look interactive? (shadows, color, cursor changes)
- Buttons look pressable (distinct shape, fill or outline)
- Links look clickable (color, underline)
- Inputs look editable (border, background contrast)

## Step 3: Build Inside-Out

Follow the inside-out construction principle:
1. Start with the content (text, icon)
2. Add internal padding
3. Add border or container
4. Add external spacing (margin)
5. Consider how the component behaves in a group

## Step 4: Accessibility Check

Verify:
- Color contrast meets WCAG AA (4.5:1 for text, 3:1 for large elements)
- Interactive elements have visible focus indicators
- Touch targets meet minimum size requirements
- State changes are communicated beyond color alone (icon, text, border)

## Step 5: Responsive Behavior

Define how the component adapts:
- Mobile: full-width buttons, stacked form fields, bottom sheet modals
- Tablet: adjusted padding, 2-column form layouts
- Desktop: inline buttons, side-by-side forms, centered modals

## Step 6: Recommend Next Steps

- If building a component library → recommend `/design-system`
- If assembling a full page → recommend `/homepage-structure` or `/dashboard-design`
- If reviewing component quality → recommend `/design-audit`

## Skills Activated

- **ui-components** (primary)
- Cross-references: design-systems, layout-spacing, web-layout
