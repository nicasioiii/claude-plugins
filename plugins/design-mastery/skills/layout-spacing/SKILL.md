---
name: Layout & Spacing Systems
description: "MANDATORY TRIGGERS: grid system, 8px grid, 4pt grid, spacing tokens, alignment, negative space, density, responsive breakpoints, box model, visual balance, white space, composition, pacing, spacing values. FOR: Grid systems (column, baseline, modular, hierarchical), 8px and 4pt spacing grids, alignment rules, negative space, density guidelines, responsive breakpoints, box model, optical vs math centering, pacing in layouts, visual weight, asymmetrical balance, content-out design, and grid-breaking techniques. Do NOT use for full web page layout and section design (use web-layout), dashboard-specific layout patterns (use dashboard-app-design), Webflow flexbox implementation (use webflow-build), typography spacing like line-height and letter-spacing (use typography-systems)."
---

# Layout & Spacing Systems

Define grid systems, spacing tokens, and alignment rules. Layout and spacing are the structural bones of every interface -- they create the implicit hierarchy that users feel before they read a single word.

## CORE PRINCIPLE: EVERYTHING IS A BOX [MDS]

From this point forward, think of every piece of interface as a box -- every text string, every container, every image (round or not).

**CSS Box Model:** Content > Padding > Border > Margin
- **Padding** = insulation around the object (space inside, can have color)
- **Margin** = space around the object where nothing can go (space between)
- Everything is boxes within boxes within boxes

---

## GRID SYSTEM SELECTION

### The 8px vs 4pt Debate

**DISAGREEMENT:**
- Segall/Traditional: 8px grid -- all values multiples of 8 (8, 16, 24, 32, 40...)
- [CONTRARIAN] Arash: 4pt grid is better -- more flexible, all values multiples of 4

| Grid | Values | Advantage | Disadvantage |
|------|--------|-----------|-------------|
| 8px | 8, 16, 24, 32, 40, 48... | Clean divisions; aligns with em/rem | Lacks flexibility for small elements |
| 4pt | 4, 8, 12, 16, 20, 24... | More granular; 12px fills the gap between 8 and 16 | More values to manage |

**Why 8px works:** Divides cleanly by 4 and 2. Base font 16px = 1em; all em increments (0.5em=8px, 0.25em=4px) produce clean numbers. [Segall]

**Why 4pt is better [Arash]:** You frequently need values like 4 or 12 for small elements. 8pt gives either 8px (too tight) or 16px (too big) -- 12px (4pt system) is often perfect.

**Resolution:** Use 4pt grid for UI design (more flexibility for components). Use 8px grid for web spacing and section-level layout. Both are valid.

---

## FOUR GRID TYPES [Gareis]

### 1. Column Grids
- Vertical divisions; most common type
- **12-column** is standard for web -- divides into 2, 3, 4, 6, 12 [MDS, Segall, Flux]
- Symmetrical = balanced, formal; Asymmetrical = dynamic, energetic
- Nested grids: column grid inside a column grid for finer control
- If using asymmetrical grid, maintain across entire site

### 2. Baseline Grids
- Horizontal guidelines for consistent vertical rhythm
- Increment based on primary body text line height (e.g., 18px line height = 18px baseline grid)
- Even non-text elements (images) should align to baseline
- Professional detail that elevates work from amateur to professional [Gareis]

### 3. Modular Grids
- Matrix of rows and columns creating cells/modules
- Modules can be combined for larger content areas
- Excellent for: catalogs, data-heavy presentations, complex interfaces
- Modules determined by content requirements

### 4. Hierarchical Grids
- Combine multiple grid types based on content importance
- Most sophisticated: combine column + baseline + modular grids
- Create distinctive zones for different content types

### Choosing Grid Type

| Content Type | Best Grid | Why |
|-------------|----------|-----|
| Text-heavy | Column | Readability |
| Diverse content | Modular or hierarchical | Structure variety |
| Data-heavy | Modular | Precision alignment |
| Simple/focused | Column (fewer columns) | Clarity |

See `references/01-grid-systems.md` for detailed grid specs and breaking rules.

---

## SPACING VALUES [MDS + Arash]

### Three Spacing Ranges [Arash]

| Range | Relationship | Pixel Values | Use |
|-------|-------------|-------------|-----|
| **Small** | Very related elements | 4-8px | Padding within buttons/cards |
| **Medium** | Related elements | 12-20px | Padding of large containers |
| **Large** | Unrelated elements | 24px+ | Spacing between sections |

### Spacing Relationship Table [MDS]

| Relationship | Distance | Example |
|-------------|----------|---------|
| Related elements | 4-8px | Label to input field |
| Loosely related | 12-16px | Input field to next field |
| Section breaks | 24-40px | Form section to next section |
| Major divisions | 48-80px+ | Hero to next section |
| Component internal | 12-20px | Card padding |
| Module margin (mobile) | 16-20px | Screen edge to content |
| Module margin (desktop) | 40-60px | Screen edge to content |

### Do Not Use Spacing Linearly [Arash]

Skip some values as numbers get bigger. Do not use 4, 8, 12, 16, 20, 24, 28, 32... Instead: 4, 8, 12, 16, 24, 32, 48, 64.

---

## NEGATIVE SPACE [MDS]

One of the most powerful tools in layout design.

- **More negative space around an element = more importance/gravitas**
- Unequal spacing creates grouping: closer = related, further = separate (Gestalt proximity)
- Inner negative space (padding) should typically be less than outer negative space (margin)
- When stacking components, reduce vertical padding between items to avoid excessive cumulative whitespace

### Negative Space Guidelines [MDS]

| Context | Amount | Example |
|---------|--------|---------|
| Large hero sections | 100px+ | Apple.com hero |
| Secondary sections | ~60px | Apple.com below hero |
| Dense information (dashboards) | Less | Efficiency over breathing room |
| Marketing pages | More | Focused messaging, luxury feel |

**The difference in negative space between sections IS the hierarchy.**

### White Space as Active Design Element [Gareis]

- Not empty space -- it is an active design element that directs eye movement
- Increase white space around key elements for emphasis
- Consistent spacing system: same spacing between similar element relationships
- Generous white space = premium, refined, sophisticated feel
- Dense layout = energetic, informative, youthful, urgent
- 30/70 split: 30% white space buffer, 70% content = dynamic asymmetry

---

## ALIGNMENT [MDS + Gareis]

- **Strong vertical left edges = professional, trustworthy design**
- Alignment is more important than the grid itself
- **Baseline alignment** for text of different sizes on the same line -- align to text baseline, not text box top
- Center alignment: mobile title bars, short marketing copy, symmetric layouts
- Center alignment problems: no strong vertical edges; awkward with long text

### Optical vs Math Centering [MDS]

Mathematical alignment is not always visually correct:
- Play triangle centered mathematically looks left-of-center optically -- nudge right 1-2px
- Text next to icons may need optical adjustment even when mathematically aligned
- **Trust your eyes over the measurements,** then verify the design feels balanced

---

## DENSITY [MDS]

| Context | Density | Characteristics |
|---------|---------|----------------|
| First-time user experience | Low | Welcoming, not overwhelming |
| Power user tools | High | Efficient, information-rich |
| Marketing/sales | Low | Focused messaging |
| Admin/management | High | Scanability |
| Onboarding screens | Low | Step-by-step, generous space |
| Data tables | High | Maximum information density |

---

## RESPONSIVE BREAKPOINTS [Segall]

| Breakpoint | Width | Columns | Margins | Gaps |
|-----------|-------|---------|---------|------|
| Desktop | 1440px | 12 | 24-64px | 24-40px |
| Tablet | 810px | 6 | max 32px | max 32px |
| Mobile | 390px | 4 or 2 | 24px | 24px |

Three is the standard minimum number of responsive states. [Segall]

### Responsive Grid Behavior [MDS]

Desktop: 12 columns > Tablet: 6 columns > Mobile: 1-2 columns.

Design at any comfortable size (1440, 1280, etc.) -- responsive design means exact artboard size matters less than the breakpoint rules. [MDS]

---

## PACING [Gareis]

How information density changes throughout the layout:

- Mix dense and open areas -- heavy content next to minimal breathing space
- Create "wow moments" (high-impact visuals/statements) between quieter sections
- Good pacing keeps people engaged; creates sense of journey
- After data-heavy sections, provide clean/minimal to let the brain reset
- Section flow: left-aligned > switch to right-aligned > back to left = keeps layout interesting
- Think of websites like movies -- each scroll panel is part of a cinematic story [Flux]

---

## CONTENT-OUT DESIGN APPROACH [MDS]

[CONTRARIAN] "The goal is not to use a grid. The goal is to achieve balance and harmony." The grid is a tool, not a commandment. [MDS]

- Let content dictate what the grid should be, not the other way around
- Design content first, then apply grid structure as things solidify
- Never used a grid overlay for mobile layouts -- mobile is mostly single-column [MDS]
- Content-out approach often works better than grid-first

---

## ANTI-PATTERNS

- Using spacing values without a system (guessing creates inconsistency)
- Applying the same spacing everywhere regardless of element relationships
- Ignoring optical centering in favor of pixel-perfect math
- Not setting a max-width on desktop (content stretches edge-to-edge on large monitors)
- Using heavy borders instead of white space for visual separation
- Applying same density to marketing pages and data-heavy admin panels
- Breaking the grid randomly vs. intentionally for emphasis

---

## RELATED SKILLS

- **typography-systems:** Type hierarchy decisions feeding into layout composition
- **color-systems:** Background elevation patterns (white on gray) that create spatial hierarchy
- **design-systems:** Creating spacing tokens and variables in Figma
- **web-layout:** Full page-level layout with sections, hero, footer
- **dashboard-app-design:** High-density layout patterns for SaaS
- **design-critique:** Evaluating layout quality against spacing and alignment principles
