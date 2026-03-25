---
name: Grid Systems Reference
description: |
  When to Read: Setting up a column grid, choosing grid type, implementing baseline grids, combining grid types, or intentionally breaking grids.
  Cross-references: layout-spacing SKILL.md (grid selection decision tree), 02-spacing-values.md (values within grid), web-layout (page-level grid application).
---

# Grid Systems Reference

## 12-COLUMN GRID SPECIFICATION [Segall + MDS + Flux]

### Desktop (1440px)

| Property | Value |
|----------|-------|
| Columns | 12 |
| Column type | Flexible (stretch or centered) |
| Margins | 24-64px (outside edges) |
| Gutters | 24-40px (between columns) |
| Max content width | Set via centering or explicit max-width |

### Tablet (~810px)

| Property | Value |
|----------|-------|
| Columns | 6 |
| Margins | max 32px |
| Gutters | max 32px |

### Mobile (~390px)

| Property | Value |
|----------|-------|
| Columns | 4 or 2 |
| Margins | 24px |
| Gutters | 24px |

**Key:** Columns maximize usable space on mobile.

### Why 12 Columns

12 has factors of 1, 2, 3, 4, 6, 12 -- maximum layout flexibility. [Flux]

Common column spans:
- Full width: 12 columns
- Two equal: 6+6
- Three equal: 4+4+4
- Four equal: 3+3+3+3
- Sidebar + content: 3+9 or 4+8
- Narrow + wide + narrow: 2+8+2

---

## BASELINE GRID [Gareis]

### Setup

1. Determine primary body text line height (e.g., 18px)
2. Set baseline grid increments to that value
3. Align ALL text to baseline grid
4. Align images and non-text elements to baseline as well

### Rules

- Smaller text can span multiple baseline increments
- Text does not need the same line height as the grid -- it just needs to start and end on grid lines
- Even images should align top and bottom edges to baseline
- Consistent vertical rhythm across columns creates professional alignment

### When to Use

| Situation | Use Baseline Grid? |
|-----------|-------------------|
| Editorial/long-form content | Yes -- creates reading rhythm |
| Multi-column layouts | Yes -- aligns text across columns |
| Data-heavy interfaces | Optional -- modular grid may be better |
| Single-column mobile | Rarely needed -- simpler alignment |

---

## MODULAR GRID [Gareis]

### Structure

Grid of rows AND columns creating rectangular cells (modules):
- Modules can be used individually or combined
- Product image in one module, product info in separate module
- Each module can have its own internal structure

### Best Applications

- E-commerce product grids
- Image galleries
- Data-heavy dashboards
- Complex multi-type content layouts
- Catalog designs

### Module Sizing

- Large enough for content comfort
- Small enough for useful organization
- Determined by content requirements, not arbitrary divisions

---

## HIERARCHICAL GRID [Gareis]

The most sophisticated type -- combine multiple grid approaches:

### Example Composition

1. 3-column asymmetrical grid for overall layout
2. Baseline grid for vertical text alignment
3. Modular system for repeating content blocks
4. Distributed horizontal spacing for navigation

### When to Use

- Complex pages with diverse content types
- Editorial layouts with varying content densities
- Pages that need distinct zones for different purposes
- Sophisticated brand/marketing sites

---

## GRID BREAKING RULES [Gareis]

### When to Break

- Creating emphasis or focal points
- Generating energy and visual interest
- Developing distinctive layouts
- Expressing experimental/innovative brand personality
- Simple content (single product showcase)
- Straightforward messaging that needs a "wow moment"

### When NOT to Break

- Traditional, rigid brands (law firms, banks)
- Complex, data-heavy content where structure aids comprehension
- When the break would confuse rather than emphasize

### How to Break Safely

1. **Break ONE grid principle at a time** while maintaining others (e.g., break column width but maintain baseline alignment)
2. Use grid breaking as **punctuation, not the default** -- most effective for specific emphasis
3. Even when breaking, maintain visual harmony
4. Bold headlines can break out of grid while body text stays within

### Breaking Examples

- Oversized images extending past column boundaries
- Offset avatars that overlap section dividers
- Pull quotes shifted outside the content column
- Full-bleed photography sections between gridded content

---

## IMPLICIT GRID [MDS]

An implicit grid emerges from consistent spacing values applied throughout the design.

Rather than a formal column grid, use consistent values:
- 8, 12, 16, 20, 24, 32, 40, 48

Especially powerful for mobile design where formal column grids are less useful.

### Content-Out Approach [MDS]

1. Design content first
2. Let content dictate grid structure
3. Apply grid as things solidify
4. Internal container padding creates the effective content area

**Key insight:** The grid is not the goal. Balance and harmony are the goal. [MDS]

---

## MAX WIDTH ON DESKTOP [Segall]

Without a max-width, designs stretch edge-to-edge on large monitors.

**Options:**
1. Set columns to center -- implicitly caps content width
2. Set explicit max-width on content container
3. If columns are set to stretch, margins and gaps stay fixed while columns grow -- document this for developers

---

## VERTICAL PADDING BETWEEN SECTIONS [Segall]

- Sections can have different vertical padding from each other
- Rule: "consistent, not identical" -- visual cohesion matters more than numeric uniformity
- Sections with different visual elements can justify different internal padding
- Hero section: largest padding (100px+)
- Content sections: medium padding (60-80px)
- Tight related sections: smaller padding (32-48px)
