---
name: Webflow Implementation
description: "Build responsive websites in Webflow: layout (flexbox, grid, positioning), responsive design, CMS, animations, naming conventions, client handoff, performance optimization. Includes 38-step build checklist, exact spacing/typography values, component patterns, and performance best practices. MANDATORY TRIGGERS: Webflow, build, implementation, layout, flexbox, grid, responsive, CMS, client handoff. Do NOT use for design — use web-layout or ui-components instead. Do NOT use for animations — use animation-interactions instead."
---

## Webflow Implementation

Build responsive, performant websites in Webflow. This skill covers the complete workflow from design to live site.

## Core Principle: Content Flows

**The fundamental rule of web design:** Content flows downward (vertical). Everything starts in normal document flow.

**Document flow = block stacking**
- Elements stack vertically by default
- Each element takes full width available
- Content below gets pushed down
- To change: Use display property (flex, grid, positioning)

---

## Display Properties (The Three You Need)

### Block (Default)
```
display: block
- Elements stack vertically
- Full width available
- Respects margins
- Use: Text, paragraphs, sections
```

### Flex (One-Dimensional Layout)
```
display: flex
- Direction: row (horizontal) or column (vertical)
- Alignment: main-axis + cross-axis
- Gap: equal spacing between items
- Use: Navigation, button groups, inline layouts
- Benefit: Responsive without media queries
```

**Flex example:**
```
Nav: display flex, flex-direction row
  → Logo (flex: 0 0 auto)
  → Menu items (flex: 1)
  → CTA button (flex: 0 0 auto)
Spacing: gap: 32px
```

### Grid (Two-Dimensional Layout)
```
display: grid
- Columns + Rows defined
- Column span: elements span multiple columns
- Row span: elements span multiple rows
- Gap: spacing between cells
- Use: Cards, masonry, complex layouts
- Critical: Each grid cell holds ONE element
```

**Grid example:**
```
4-column card grid:
  4 cards × 1 column width each = fills grid
  Gap: 24px
Responsive:
  Desktop: 4 columns
  Tablet: 2 columns
  Mobile: 1 column
```

---

## Positioning (Where Things Sit)

### Static (Default)
```
position: static
- Normal document flow
- Z-index ignored
- Use: Most elements
```

### Relative
```
position: relative
- Offset from normal position
- Still takes space in flow
- Z-index works
- Use: Small adjustments while maintaining flow
```

### Absolute
```
position: absolute
- Removed from flow (doesn't take space)
- Position relative to nearest positioned ancestor
- CRITICAL: Parent must have position: relative
- Z-index works
- Use: Layered designs, overlays, floating elements
```

**Example:**
```
Container (position: relative)
  └── Overlay image (position: absolute)
      ├── top: 20px
      ├── left: -50px
      ├── z-index: 10
      (floats over content)
```

### Fixed
```
position: fixed
- Removed from flow
- Position relative to viewport
- Stays in place while scrolling
- Z-index works
- Use: Sticky nav, floating buttons
- Caveat: Mobile issues (check carefully)
```

### Sticky
```
position: sticky
- Stays in flow until scroll reaches it
- Then sticks to viewport
- CRITICAL: Must have top/left value (e.g., top: 0)
- Z-index works
- Use: Table headers, section markers, while-scrolling animations
```

---

## Responsive Design Strategy (Mobile-First)

### Webflow Breakpoints (Standard)

```
Mobile:    480px and below (default, start here)
Tablet:    768px and above
Laptop:    1024px and above
Desktop:   1440px and above
Ultra:     1920px and above
```

**Strategy:**
1. Design mobile layout first (simplest, most constrained)
2. Add breakpoint rules as viewport expands
3. Each breakpoint inherits larger breakpoint's styles
4. Only override what changes at each size

### Responsive Pattern: Flex Column → Row

```
Mobile (default):
  display: flex, flex-direction: column
  Items stack vertically
  width: 100%

Tablet (768px+):
  display: flex, flex-direction: row
  Items sit side-by-side
  width: 50% each

Desktop (1024px+):
  width: 33.33% each
  3 items per row
```

### Responsive Pattern: Grid Changes

```
Mobile:
  grid-template-columns: 1fr (1 column)
  Cards: full width

Tablet:
  grid-template-columns: 1fr 1fr (2 columns)
  Cards: half width

Desktop:
  grid-template-columns: 1fr 1fr 1fr 1fr (4 columns)
  Cards: quarter width
```

---

## Container Pattern (Essential)

**Pattern:**
```
Section (width: 100%, padding: 0)
└── Container (max-width: 1200px, margin: 0 auto, padding: 64px)
    └── Content
```

**Benefits:**
- Section: Full viewport width (background extends edge-to-edge)
- Container: Content constrained to readable width
- Margin auto: Centers horizontally
- Padding: Internal spacing

**Spacing Values by Breakpoint:**

| Breakpoint | Padding (L/R) | Padding (T/B) |
|-----------|---------------|---------------|
| Desktop | 64px | 80px |
| Tablet | 48px | 60px |
| Mobile | 24px | 40px |

---

## Typography in Webflow

### Font Setup

1. **Site Settings > Fonts tab**
   - Add Google Fonts
   - Select only weights you use (each = separate file)
   - Language: Usually "Latin"

2. **Variable Fonts (Recommended)**
   - Download from Google Fonts
   - Upload to Webflow
   - Single file includes all variations
   - GDPR compliant (hosted on your domain)

3. **Fallback Fonts**
   - Serif fallback: Georgia
   - Sans-serif fallback: Arial
   - Ensure readable even if custom font fails to load

### Typography Scale

**Desktop:**
- H1: 90-100px, line-height 95-100%
- H2: 60px, line-height 130%
- H3: 32px, line-height 130%
- Body: 18px, line-height 160%
- Small: 14px, line-height 150%

**Mobile:**
- H1: 40-48px (scale down proportionally)
- H2: 32px
- H3: 24px
- Body: 16px (NEVER below 16px on mobile)
- Small: 12px

### Create Typography Styles

1. **Text element**
2. **All Pages** toggle (right side)
3. **Save as**
4. Name: "H1", "Body Text", "Small Caption"
5. Reuse globally (auto-update all instances)

---

## Color Variables

### Setup

1. **Site Settings > Variables tab**
2. **Create new color variable**
3. Naming: `colors/brand-primary`, `colors/text-dark`, etc.
4. Benefits: Global updates (change once, update everywhere)

**Essential Variables:**
```
colors/primary:        #0066FF (brand color)
colors/secondary:      #667733 (complementary)
colors/text-dark:      #333333 (primary text)
colors/text-medium:    #666666 (secondary text)
colors/border-light:   #EEEEEE (dividers)
colors/bg-light:       #F9F9F9 (backgrounds)
```

### Using Variables in Webflow

1. Select element
2. Background color picker
3. Bottom of picker: "Variables"
4. Choose saved color variable
5. Now linked globally (change variable = updates everywhere)

---

## Naming Conventions (BEM-Inspired)

**Structure:** `[component]-[element]-[modifier]`

### Examples

```
.hero-section          // Main component
.hero-image            // Element within component
.hero-content          // Another element

.button-primary        // Component + variant
.button-secondary      // Different variant
.button:hover          // State (not a class)

.text-large            // Utility (no component)
.text-center           // Another utility
.bg-white              // Color utility
```

### Component Naming Rules

1. **Start with what it is:** `text-*`, `button-*`, `card-*`
2. **Then the variant:** `text-large`, `button-primary`
3. **Avoid position names:** Don't use `left-column` (breaks on mobile)
4. **Use semantic names:** `hero-section` not `big-image-section`
5. **Group related classes together** (nav, nav-item, nav-link)

### Utility Class Separation

**Create utilities independently:**
```
.text-center        // Only text-align: center
.text-large         // Only font-size + line-height
.margin-top-large   // Only margin-top
```

**Never create combos for utilities:**
```
❌ WRONG: Apply text-center to card, becomes "card--text-center"
✅ RIGHT: Apply text-center separately, stays reusable
```

---

## 38-Step Webflow Build Checklist

Complete checklist covering all 6 phases: setup, structure, content layout, interactions, forms, and optimization.

For the full 38-step checklist broken into phases, read `references/build-checklist.md`.

---

## Exact Spacing & Typography Values

Standard values for responsive design: Section padding, internal gaps, font sizes, and line heights.

For complete spacing and typography values with component patterns (button, card, form), read `references/spacing-typography-values.md`.

---

## Client Handoff Workflow

Hand off Webflow sites smoothly with proper access setup, CMS training, documentation, and testing.

For complete client handoff workflow including access levels, CMS training, documentation templates, and testing checklist, read `references/client-handoff.md`.

---

## Performance Best Practices

Optimize images, fonts, animations, and Core Web Vitals for fast-loading Webflow sites.

For complete performance guidance including image optimization, font loading, GPU-accelerated animations, and Core Web Vitals metrics, read `references/performance-optimization.md`.

---

## When to Read References

**Read 01_webflow_layout_patterns.md if:**
- Setting up hero, card grid, footer
- Need specific flex/grid patterns
- Unsure about responsive breakpoints

**Read 02_webflow_responsive.md if:**
- Building for multiple screen sizes
- Typography scaling questions
- Grid column changes at breakpoints

**Read 03_webflow_handoff.md if:**
- Preparing site for client
- Creating training documentation
- Setting up CMS editing access
- Pre-launch testing

---

## Quick Start: Building a Simple Site

**Timeline: 4-6 hours for simple marketing site**

1. Setup (1 hour): Fonts, colors, styles
2. Structure (1 hour): Nav, footer, page template
3. Content (2 hours): Hero, sections, CTA
4. Interactions (1 hour): Hovers, scrolls
5. Optimization (1 hour): Images, testing, performance

---

## Troubleshooting

**Problem: Flexbox items not centering**
- Check: justify-content: center (main axis)
- Check: align-items: center (cross axis)

**Problem: Grid items won't span**
- Check: Column span value is correct
- Check: Parent has grid-template-columns defined

**Problem: Responsive changes don't show**
- Check: Breakpoint selector at bottom right
- Check: Override at that breakpoint (not inheriting)

**Problem: Sticky nav stops working**
- Check: position: sticky applied
- Check: top: 0 value set
- Check: Parent doesn't have overflow: hidden

**Problem: Images stretched/distorted**
- Check: object-fit: cover (crops, not stretches)
- Check: Image aspect ratio set correctly

---

## Cross-References

**Related skills:**
- **web-layout** — Design phase (before building)
- **ui-components** — Component patterns used in Webflow
- **animation-interactions** — Interaction implementation
- **visual-foundations** — Spacing and typography rules

---

**Last Updated:** March 12, 2026
**Source:** Webflow Masterclass 5.0 & 5.1 Pro, Ran Segall
**Status:** Complete, implementation-ready
