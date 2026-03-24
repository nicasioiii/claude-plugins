---
name: UI Components
description: "Design reusable button, card, navigation, form, modal, and table patterns with proper states and accessibility. MANDATORY TRIGGERS: button design, card patterns, navigation design, form inputs, modals, accessibility, component states, hover states, disabled states. Do NOT use for page layouts — use web-layout instead. Do NOT use for entire dashboard layouts — use dashboard-systems instead."
---

# UI Components

## When You Need This Skill

Use this skill when:
- Designing a specific UI component (button, card, form field, navigation)
- Building a component library or design system
- Creating variations and states for interactive elements
- Ensuring components are accessible and keyboard-navigable
- Establishing hover, active, disabled, and loading states

**Do NOT use for:**
- Entire page layouts → see **web-layout**
- Full dashboard/app interfaces → see **dashboard-systems**
- Design fundamentals → see **visual-foundations**

---

## Component Anatomy: The Universal Structure

Every component has **three essential layers:**

1. **Structure** — How is it built? (container, padding, alignment)
2. **States** — What are all possible states? (default, hover, active, disabled, loading, error)
3. **Variants** — What size/style options exist? (primary/secondary, sizes, colors)

### State Definitions (Required for All Components)

| State | Visual Change | When Used | Accessibility |
|-------|---------------|-----------|----------------|
| **Default** | Base appearance | Component loads | Visible, focusable |
| **Hover** | Color/scale/shadow change | Mouse cursor enters (desktop only) | N/A |
| **Active** | Pressed/selected appearance | User clicks/selects | Visible focus ring |
| **Focus** | Outline/ring around element | Keyboard navigation | **REQUIRED** — 3px min outline |
| **Disabled** | Reduced opacity/grayed | Element unavailable | Can fail contrast (intentional de-emphasis) |
| **Loading** | Spinner/skeleton | Async operation in progress | Brief description: "Loading..." |
| **Error** | Red border/text + message | Validation fails | 4.5:1 contrast on error color |

---

## Button Patterns

Primary, secondary, and tertiary buttons with state definitions, sizing guidelines, and sizing variations.

For complete button patterns including primary/secondary/tertiary styles, size variations, and touch targets, read `references/component-patterns.md`.

---

## Card Components

Image cards, feature cards, and testimonial cards with spacing, hover states, and responsive grid layouts.

For complete card patterns including structure, spacing, hover states, and grid layouts, read `references/component-patterns.md`.

---

## Navigation Components

Desktop horizontal navigation and mobile hamburger menu with sizing, states, dropdown menus, and animation timings.

For complete navigation patterns including desktop/mobile structures, dropdown styling, and animations, read `references/component-patterns.md`.

---

## Form Input Patterns

Text inputs, checkboxes, radio buttons, and select dropdowns with states, sizing, and accessibility requirements.

For complete form patterns including input states, checkbox/radio styling, dropdown menus, and label requirements, read `references/component-patterns.md`.

---

## Modal / Dialog Patterns

Modal structure, sizing, animations, and backdrop interactions.

For complete modal patterns including sizing, title styling, button placement, and animations, read `references/component-patterns.md`.

---

## Table Components

Data table structure, styling, interactions, and responsive behavior.

For complete table patterns including header styling, row interactions, sorting, selection, and responsive layouts, read `references/component-patterns.md`.

**Pagination:**
```
Showing 1-10 of 247 items
[← Prev] [1] [2] [3] ... [25] [Next →]
```

- Items per page: 10-25 default
- Page selector: Centered or right-aligned
- Button states: Disabled on first/last page

---

## Accessibility Requirements (Non-Negotiable)

### Keyboard Navigation
- [ ] All interactive elements focusable (buttons, links, inputs)
- [ ] Tab order logical (left-to-right, top-to-bottom)
- [ ] Focus ring visible (3px, high contrast, 2-3px offset)
- [ ] Enter/Space triggers buttons
- [ ] Escape closes modals/dropdowns

### Color & Contrast
- [ ] Text: 4.5:1 minimum (WCAG AA)
- [ ] Large text (18.5px+ bold or 24px+): 3:1 minimum
- [ ] Button/control states distinguishable (not color alone)
- [ ] Test with colorblind simulator

### Semantic HTML (Developer Concern)
- [ ] Buttons use `<button>` not `<div>`
- [ ] Links use `<a>` with href
- [ ] Form fields have `<label>` connected via `for` attribute
- [ ] ARIA attributes for custom components

### Microcopy
- [ ] Error messages: Clear, actionable, red color (4.5:1 contrast)
- [ ] Success messages: Positive language, green color
- [ ] Loading: Brief, honest ("Saving...", "Loading...")
- [ ] Help text: Positioned below input, 12px gray

---

## Common Component Mistakes

### ❌ Mistake: Hover states only on desktop
**Fix:** Provide focus states for keyboard users. Hover should also trigger focus ring.

### ❌ Mistake: Disabled buttons with failed contrast
**Fix:** Disabled buttons CAN fail contrast, but use visual difference (opacity, gray color).

### ❌ Mistake: No focus ring on buttons
**Fix:** Always include 3px outline on focus (offset 2-3px), high contrast.

### ❌ Mistake: Placeholder text as label
**Fix:** Use permanent label above input. Placeholder disappears when typing.

### ❌ Mistake: Modal without close button
**Fix:** Always include X button or Escape key support.

### ❌ Mistake: Ambiguous button labels
**Fix:** Use specific labels ("Delete Account", not "Confirm"). No icon-only buttons without labels.

---

## When to Read Reference Files

| Need | Reference |
|------|-----------|
| Detailed button sizing, states, and variations | **button-patterns.md** |
| Card layout grid systems, image ratios, hover effects | **card-components.md** |
| Navigation desktop/mobile patterns, dropdowns, hamburger menu | **navigation-patterns.md** |
| Form inputs, validation states, error handling | **form-inputs.md** |
| Modal dialogs, popovers, sheets, backdrop behavior | **modals-overlays.md** |
| Tables, data grids, sorting, pagination, responsive table design | **data-display.md** |

---

## Cross-Skill References

- **visual-foundations** → For color contrast, typography sizing, spacing values
- **web-layout** → To see components in full page context
- **dashboard-systems** → For dense component layouts and data-heavy UIs
- **web-design-audit** → To review existing component quality
- **figma-workflows** → For building component libraries in Figma

---

## Quick Decision Tree

**What component do I need?**

```
Are you designing a clickable element?
├─ YES → Button (see button-patterns.md)
└─ NO →

Are you displaying an image + text together?
├─ YES → Card Component (see card-components.md)
└─ NO →

Is it a navigation element?
├─ YES → Navigation (see navigation-patterns.md)
└─ NO →

Is the user entering data?
├─ YES → Form Input (see form-inputs.md)
└─ NO →

Is content displayed in a layer over other content?
├─ YES → Modal/Overlay (see modals-overlays.md)
└─ NO →

Is it tabular data?
└─ YES → Table (see data-display.md)
```

---

## Component Checklist

Before finalizing any component:

- [ ] All states defined (default, hover, active, focus, disabled, loading, error)
- [ ] Sizing follows 8px grid (all values divisible by 8 or 4)
- [ ] Focus ring visible and high contrast (3px, 2-3px offset)
- [ ] Color contrast tested (4.5:1 minimum for text)
- [ ] Touch targets minimum 44×44px (48px recommended)
- [ ] Labels clear and associated with inputs
- [ ] Error messages actionable
- [ ] Hover state doesn't break accessibility
- [ ] Works on keyboard navigation (Tab, Enter, Escape)
- [ ] Mobile responsive variant designed
- [ ] Hover and focus states don't repeat
- [ ] Used consistently across design system

