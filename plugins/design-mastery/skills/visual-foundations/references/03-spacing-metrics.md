# Spacing Metrics & Scale

Consistent spacing is invisible when it works and obvious when it doesn't. These exact measurements come from production work and scale across every context.

---

## 8-Pixel Base Grid System

**Core principle:** All measurements should be divisible by 8px.

**Why 8 pixels?**
- Scalability: Can divide by 4 or 2 (8→4→2) without breaking visual rhythm
- 16px browser base: 8px = 0.5em in CSS (clean calculations)
- Consistency: Every component aligns to grid
- Universality: Scales perfectly across displays (8px on mobile = 8px on desktop, but appears proportional due to relative density)

**Application:** Use 8px grid for ALL hard values:
- Font sizes
- Icon sizes
- Padding
- Gaps/gutters
- Corner radius
- Any explicit measurement

---

## Safe Spacing Scale

Use this for padding, margins, and gaps between elements. **Commit to this scale—don't improvise.**

### Micro-Spacing (Tight)
- **4px** — Micro adjustments, rare
- **8px** — Between small elements, icon padding
- **6px** — Between form field elements

### Small Spacing (Standard)
- **12px** — Button padding (vertical), item spacing
- **16px** — Component padding, standard gaps

### Medium Spacing (Breathing Room)
- **24px** — Section padding, between major elements
- **32px** — Between sections, vertical rhythm

### Large Spacing (Premium Feel)
- **40px** — Between major blocks
- **60px** — Hero section padding, large gaps
- **80px** — Page section spacing
- **100px+** — Extra breathing room (luxury feel)

### Full Scale Reference

| Size | Use Case | Em (16px) |
|------|----------|-----------|
| 4px | Micro adjustment | 0.25em |
| 8px | Small padding | 0.5em |
| 12px | Button padding | 0.75em |
| 16px | Standard padding | 1em |
| 24px | Section gap | 1.5em |
| 32px | Medium section | 2em |
| 40px | Large gap | 2.5em |
| 60px | Hero section | 3.75em |
| 80px | Page section | 5em |

---

## Application by Context

### Web Design (Desktop, 1440px)

**Container/Page:**
- Outside margins: 64px (premium feel) or 24px (compact)
- Max-width: 1312px (1440 - 64×2)
- Gutter (gap between columns): 24-40px

**Section Spacing:**
- Section padding: 64px top/bottom
- Between sections: 80-128px (half of 128px on each side = 64px prevents double)
- Hero section: 64-100px padding

**Component Spacing:**
- Card padding: 16-24px
- Button padding: 16px vertical, 24px horizontal
- Form field gap: 12-16px
- Navigation item gap: 24-32px

### Mobile Design (390px)

**Container/Page:**
- Side margins: 16px (tight) or 24px (generous)
- No max-width needed (full width)

**Section Spacing:**
- Section padding: 24-32px top/bottom (smaller than desktop due to screen height)
- Between sections: 40-60px

**Component Spacing:**
- Card padding: 12-16px (smaller than desktop)
- Button padding: 12px vertical, 16px horizontal (smaller targets)
- Form field gap: 8-12px
- Stack items: 12-16px gap

### Tablet Design (800px)

**Container/Page:**
- Side margins: 32-40px
- Max-width: Content-driven (usually full width)

**Section Spacing:**
- Section padding: 40-56px top/bottom
- Between sections: 60-80px

**Component Spacing:**
- Card padding: 16px (compromise between mobile/desktop)
- Button padding: 16px vertical, 24px horizontal
- Form field gap: 12px

---

## 12-Column Grid System (Desktop)

**Specifications for 1440px width:**

| Property | Value |
|----------|-------|
| Total width | 1440px |
| Columns | 12 |
| Column width | 80px |
| Margins (left/right) | 64px |
| Gutters (gap between columns) | 24-40px |
| Content max-width | 1312px (1440 - 128) |

### Responsive Breakpoints & Column Adjustments

| Breakpoint | Width | Columns | Margins | Gutters | Use Case |
|-----------|-------|---------|---------|---------|----------|
| Desktop | 1440px | 12 | 64px | 24-40px | Primary |
| Tablet (large) | 1024px | 8 | 40px | 24px | iPad landscape |
| Tablet | 800px | 6 | 40px | 24px | iPad portrait, tablets |
| Mobile | 390px | 1-4 | 24px | 16px | Phones |

### How Columns Work

**12-column divisibility:**
- Full width: 12 columns
- 2 equal sections: 6 columns each
- 3 equal sections: 4 columns each
- 4 equal sections: 3 columns each
- 6 equal sections: 2 columns each

**Example: 3-column layout (1440px)**
- Each column: 4 columns wide (80px × 4 = 320px)
- Gap between: 24px
- 4 cols (320) + gap (24) + 4 cols (320) + gap (24) + 4 cols (320) = 1328px

### Responsive Changes at Breakpoints

**Desktop (1440px) → Tablet (1024px):**
- 12 columns → 8 columns
- Card layout: 4 cards (3 col each) → 4 cards (2 col each, wraps to 2 rows)
- Or: 3 columns → 2 columns

**Tablet (1024px) → Mobile (390px):**
- 8 columns → 1-4 columns (usually 1 or 2)
- Most content stacks vertically
- Cards go full width (1 column)

---

## Section Spacing Strategy

### Hero Section

**Desktop:**
- Top padding: 64px minimum (100px for luxury feel)
- Bottom padding: 64px-100px
- Text alignment: Left, center, or with offset based on image

**Mobile:**
- Top padding: 32px (less room)
- Bottom padding: 40-48px
- Often full-height or 80vh on desktop → 50-60vh on mobile

### Feature Sections

**Typical structure:**
- Top padding: 64px
- Bottom padding: 64px
- Between section blocks: 40-60px
- Between feature items: 24-32px

**Example: 3-feature section**
```
Section top padding: 64px
  ├─ Feature 1
  ├─ Gap: 32px
  ├─ Feature 2
  ├─ Gap: 32px
  └─ Feature 3
Section bottom padding: 64px
```

### CTA Sections

**Emphasis through space:**
- Top padding: 80-100px (generous)
- Bottom padding: 80-100px (generous)
- Creates pause and focus

### Footer

**Typical structure:**
- Top padding: 64px
- Bottom padding: 32px (smaller than sections above)
- Internal gaps: 24-32px between columns

---

## Negative Space: Breathing Room

### The Water Flow Test

Imagine pouring water on your design. Would it flow smoothly?
- Tight bottlenecks = problem areas
- Generous spacing = premium feel

### Spacing Guidelines

**Minimum breathing room:**
- 20px padding around contained text
- 16-24px between line items
- 60-80px between major sections

**Premium feel:**
- 24-32px padding around text
- 24-40px between line items
- 80-100px+ between sections

### Impact Example

**Cramped version:**
- ~20px top/bottom spacing
- Feels cheap, crowded

**Breathable version:**
- ~100px top/bottom spacing
- Feels premium, luxurious
- No size changes, only spacing

Difference is dramatic without changing content.

---

## Padding Patterns

### Card Padding (Common)
- **Compact:** 12px padding
- **Standard:** 16px padding
- **Generous:** 24px padding

**By component type:**
- Image cards: 16px (image fills well with modest padding)
- Text-heavy cards: 20-24px (more breathing room)
- Icon cards: 12-16px (tight, compact feel)

### Button Padding

**Mobile-first approach:**
- Vertical: 12-16px (must be 44-48px tap target minimum)
- Horizontal: 16-24px

**Desktop approach:**
- Vertical: 12-16px (no tap target requirement)
- Horizontal: 20-32px (larger, more spacious)

**Size variations:**
- Small: 8px vertical, 12px horizontal
- Medium: 12px vertical, 16px horizontal (standard)
- Large: 16px vertical, 24px horizontal

### Form Field Padding

**Input fields:**
- Vertical: 8-12px
- Horizontal: 12-16px
- Baseline: 12px × 16px (standard)

**Between fields:**
- 16px gap (standard)
- 24px gap (generous, breathing room)

---

## Corner Radius Scale

**Also use 8px-based scale for consistency:**

| Value | Use Case |
|-------|----------|
| 0px | Sharp (button, card borders) |
| 4px | Subtle rounding (small components) |
| 8px | Standard rounding (buttons, cards, inputs) |
| 12px | Moderate rounding (larger cards) |
| 16px | Round (modern, playful) |
| 24px | Very round (trendy, soft) |

**Rule:** All corner radius in design should be 0, 4, 8, 12, 16, or 24px (all divisible by 4).

---

## Responsive Spacing Changes

### Rule: Spacing shrinks on mobile, grows on desktop

**Example: Section padding**

```
Desktop: 80px top, 80px bottom
Tablet: 56px top, 56px bottom (0.7×)
Mobile: 32px top, 32px bottom (0.4×)
```

**Example: Gap between items**

```
Desktop: 32px gap
Tablet: 24px gap
Mobile: 16px gap
```

### Strategy

1. Design for desktop first with generous spacing
2. Maintain spacing hierarchy on tablet (slightly reduce)
3. Compress significantly on mobile (but maintain proportions)

**Key:** Mobile needs proportional spacing reductions to stay usable.

---

## Spacing Decision Framework

When determining padding/gap values, ask yourself:

1. **Does this spacing group content?** (Proximity = relationship)
2. **Is there enough breathing room?** (Cramped areas?)
3. **Is it balanced?** (Visually proportionate?)
4. **Is it cohesive?** (Matches system scale?)
5. **Does it work at every breakpoint?** (Test responsive)

---

## Quick Spacing Checklist

Before finalizing spacing:

- [ ] All spacing values on 8px scale (4, 8, 12, 16, 24, 32, etc.)
- [ ] Section padding: 64px (desktop), 40px (tablet), 24px (mobile)
- [ ] Component padding: 12-24px (consistent across components)
- [ ] Gaps between items: 8-32px (defined by spacing scale)
- [ ] Breathing room adequate (no cramped areas)
- [ ] Responsive adjustments planned for mobile/tablet
- [ ] Max-width set for desktop+ (1312px)
- [ ] Grid system consistent (12 cols desktop, adjusts per breakpoint)
- [ ] Negative space tested (water flow test passes)
- [ ] Visual hierarchy supported by spacing (larger gaps = bigger sections)

---

## Common Spacing Mistakes

1. **Arbitrary spacing:** 7px, 13px, 18px (not on scale)
   - **Fix:** Commit to 8px-based scale only

2. **Inconsistent padding:** Cards have different padding values
   - **Fix:** Define standard (16px) and stick to it

3. **No responsive adjustments:** Same spacing on mobile as desktop
   - **Fix:** Scale spacing down for mobile (40% reduction)

4. **Cramped layouts:** No breathing room
   - **Fix:** Add 25% more space if feeling tight

5. **Too much negative space:** Looks sparse, disconnected
   - **Fix:** Reduce spacing between related items

---

## Tools

- **Spacing guides:** Figma rulers, grid, layout grid
- **Measuring:** Figma measure tool, browser dev tools
- **Documentation:** Spreadsheet of spacing values
- **Color overlay:** Design system documentation with spacing standards

---

## Spacing Documentation Template

```
# Spacing System

## Scale (8px base)
- Micro: 4px, 8px
- Small: 12px, 16px
- Medium: 24px, 32px
- Large: 40px, 60px, 80px

## Component Padding
- Card: 16px
- Button: 12px vertical, 16px horizontal
- Input: 12px vertical, 12px horizontal
- Navigation: 16px horizontal, 8px vertical

## Section Spacing
- Desktop: 64px top/bottom
- Tablet: 40px top/bottom
- Mobile: 24px top/bottom

## Gaps
- Between cards: 24px (desktop), 16px (mobile)
- Between buttons: 8px
- Between form fields: 16px

## Grid
- Desktop: 12 columns, 64px margins, 24-40px gutters
- Tablet: 6 columns, 40px margins, 24px gutters
- Mobile: 1 column, 24px margins

## Max-width
- Desktop+: 1312px (1440 - 64×2)
- Centered with auto margins
```
