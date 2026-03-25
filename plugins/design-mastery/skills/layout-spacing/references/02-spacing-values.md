---
name: Spacing Values & Density Guidelines
description: |
  When to Read: Choosing specific spacing values, setting up a spacing scale, determining appropriate density, or configuring responsive breakpoints.
  Cross-references: 01-grid-systems.md (grid-level spacing), 03-alignment-composition.md (visual balance), design-systems (spacing tokens in Figma).
---

# Spacing Values & Density Guidelines

## 8PX GRID VALUES [Segall]

### Full Scale

| Token | Value | Common Use |
|-------|-------|-----------|
| xs | 4px | Icon padding, tiny gaps (half-step exception) |
| sm | 8px | Related element gap, icon margin |
| md | 16px | Component padding, field gap |
| lg | 24px | Section internal padding |
| xl | 32px | Section gaps |
| 2xl | 40px | Between major sections |
| 3xl | 48px | Hero internal padding |
| 4xl | 64px | Desktop margins |
| 5xl | 80px | Major section dividers |
| 6xl | 96px | Hero vertical padding |

### Why 8px Works

- 8 divides cleanly by 4 and 2
- Base font 16px = 1em; 0.5em = 8px, 0.25em = 4px
- All em increments produce clean round numbers
- A 10px grid fails: dividing by 2 gives 5, which cannot divide further without decimals

## 4PT GRID VALUES [Arash]

### Recommended Scale

| Token | Value | Use Category |
|-------|-------|-------------|
| 2xs | 4px | Small: icon-to-label, compact padding |
| xs | 8px | Small: button padding, inline gaps |
| sm | 12px | Medium: input padding, card internal |
| md | 16px | Medium: component padding |
| lg | 20px | Medium: larger container padding |
| xl | 24px | Large: section internal padding |
| 2xl | 32px | Large: section gaps |
| 3xl | 48px | Large: major divisions |
| 4xl | 64px | Large: hero padding |

### Practical Workflow [Arash]

1. Group elements logically
2. Start with smallest elements, set their padding
3. Move to larger groups, set margins between groups
4. Set outer container padding
5. Example: button padding 8v/16h > text gap 8 > related group gap 20 > card padding 24

---

## SPACING DECISION FRAMEWORK [Segall]

When setting spacing, ask in order:

1. Is this spacing helping **group the right content together** so the user understands which elements are related?
2. Is there enough space between elements to **feel comfortable**?
3. Does anything feel **visually unbalanced**?
4. Does the spacing feel **cohesive** within the element, the section, and the site?

---

## DENSITY GUIDELINES [MDS]

### Low Density (More Space)

| Characteristic | Value Range |
|---------------|------------|
| Section padding | 80-120px+ |
| Element gaps | 24-48px |
| Font sizes | Larger (18-24px body) |
| Content per screen | Less; focused messaging |
| Best for | Marketing, onboarding, luxury |

### High Density (Less Space)

| Characteristic | Value Range |
|---------------|------------|
| Section padding | 16-32px |
| Element gaps | 4-12px |
| Font sizes | Smaller (13-16px body) |
| Content per screen | More; information-rich |
| Best for | Dashboards, admin, settings, data |

### Density by Context

| Context | Density | Why |
|---------|---------|-----|
| First-time user | Low | Welcoming, not overwhelming |
| Power user tools | High | Efficient, quick access |
| Marketing/sales | Low | Focused, persuasive |
| Admin/management | High | Scanability, efficiency |
| Onboarding | Low | Step-by-step clarity |
| Data tables | High | Maximum rows visible |
| Settings screens | Medium-High | Functional, organized |
| Help/documentation | Medium | Readable, not cramped |

---

## RESPONSIVE BREAKPOINT REFERENCE [Segall]

### Design Breakpoints (Figma)

| Device | Width | Use |
|--------|-------|-----|
| Desktop | 1440px | Primary design canvas |
| Tablet | 810px | iPad-size |
| Phone | 390px | Standard mobile |
| Large desktop (optional) | 1920px | For complex designs |

### Key Responsive Rules

- Three is the standard minimum number of responsive states
- Desktop-first in Figma; desktop-first in Webflow (styles cascade down)
- Columns reduce: 12 > 6 > 4/2 > 1
- Gaps and margins shrink at each breakpoint
- Typography may reduce: hero titles especially; body stays 16px+

### Common Responsive Adjustments

| Element | Desktop | Tablet | Mobile |
|---------|---------|--------|--------|
| Hero title | 72-96px | 48-64px | 32-40px |
| Section padding | 80-120px | 48-64px | 32-48px |
| Side margins | 40-64px | 24-32px | 16-24px |
| Column count | 2-4 per row | 1-2 per row | 1 per row |
| Navigation | Full horizontal | Hamburger | Hamburger |
| Images | Full-width or grid | Stack or reduce | Full-width stack |

---

## COMPONENT SPACING PATTERNS

### Button Padding

| Size | Vertical | Horizontal |
|------|----------|-----------|
| Small | 8px | 16px |
| Medium | 12px | 24px |
| Large | 16px | 32px |

### Card Padding

| Density | Internal Padding | Between Elements |
|---------|-----------------|-----------------|
| Compact | 12-16px | 8px |
| Standard | 20-24px | 12-16px |
| Spacious | 32px | 20-24px |

### Form Field Spacing

| Relationship | Spacing |
|-------------|---------|
| Label to input | 4-8px |
| Input to next field | 16-24px |
| Field group to next group | 32-40px |
| Form to submit button | 24-32px |
