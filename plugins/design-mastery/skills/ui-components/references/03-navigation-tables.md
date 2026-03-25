# Navigation & Table Patterns — Quick Reference

## NAVIGATION TYPE DECISION TREE

```
What type of interface?
├── Marketing website
│   ├── Few pages (< 8) → Top horizontal nav
│   ├── Many pages (8+) → Top nav + mega menu dropdown
│   └── Single page → Sticky nav with scroll anchors
├── Web application / SaaS
│   ├── 3-5 main sections → Top horizontal nav + sidebar for sub-nav
│   ├── 6+ sections → Sidebar navigation (collapsible)
│   └── Dense data app → Sidebar nav + top utility bar
├── Mobile app
│   ├── 3-5 core features → Bottom tab bar
│   ├── 6+ features → Bottom tab bar (5) + hamburger for rest
│   └── Content-focused → Top nav + back arrow pattern
└── E-commerce
    ├── Simple catalog → Top nav with categories
    └── Large catalog → Mega menu with category grid
```

## TOP NAVIGATION BAR

### Desktop Layout (Auto Layout)
```
┌──────────────────────────────────────────────────────────┐
│ [Logo]        [Nav Item] [Nav Item] [Nav Item]    [CTA]  │
└──────────────────────────────────────────────────────────┘
```
- Auto Layout: horizontal, Space Between
- Height: 56-72px
- Internal padding: 16-24px vertical, 24-48px horizontal
- Logo: left-aligned, max height 32-40px
- Nav items: center group, gap 24-32px between items
- CTA button: right-aligned

### Scroll State Pattern [Segall]
| State | Background | Shadow | Logo | Padding | Trigger |
|-------|-----------|--------|------|---------|---------|
| Landing | Transparent | None | White (if on hero) | 24px vertical | Page top |
| Scrolled | White or dark | Subtle (0 2px 8px rgba) | Dark or brand | 12-16px vertical | After hero |

- Transition: 0.3s ease on all properties
- Optional: hide on scroll down, show on scroll up

### Nav Link Styling
| State | Color | Weight | Decoration |
|-------|-------|--------|-----------|
| Default | Gray-600 (#4B5563) | Regular (400) | None |
| Hover | Gray-900 (#111827) | Regular (400) | Optional underline |
| Active/Current | Gray-900 or Primary | Semi-bold (600) | Underline or bold |

### Mega Menu Structure [Segall]
```
┌─────────────────────────────────────────────────┐
│ Category 1      Category 2      [Featured Card] │
│ - Link          - Link          [Image]         │
│ - Link          - Link          [Title]         │
│ - Link          - Link          [CTA]           │
│ - Link          - Link                          │
├─────────────────────────────────────────────────┤
│ [Divider]                                       │
│ [View All Products →]                           │
└─────────────────────────────────────────────────┘
```
- Column guides for link alignment
- Featured content card beside link columns to fill space and drive engagement
- Chevron icon on trigger rotates to indicate open state

## SIDEBAR NAVIGATION (Apps)

### Layout
```
┌──────────┬──────────────────────────────┐
│ [Logo]   │                              │
│          │                              │
│ Nav 1 ●  │    Main Content Area         │
│ Nav 2    │                              │
│ Nav 3    │                              │
│ Nav 4    │                              │
│          │                              │
│ ──────── │                              │
│ Settings │                              │
│ Profile  │                              │
└──────────┴──────────────────────────────┘
```

### Sidebar Specs
- Width: 240-280px expanded, 64-72px collapsed (icon-only)
- Item height: 40-44px
- Item padding: 12px horizontal, 8px vertical
- Active indicator: left border accent (3-4px) or filled background
- Icon size: 20-24px, 12px gap to label
- Section divider: 1px line with 16px vertical margin
- Collapse trigger: hamburger icon or auto-collapse at breakpoint

## MOBILE TAB BAR

### Specs
- Height: 56px (safe area padding adds to this on notch devices)
- Max items: 5 (if more, use "More" tab with overflow)
- Icon: 24px, centered above label
- Label: 10-12px below icon
- Active state: icon solid + primary color; inactive: icon outline + gray
- Safe area: add extra bottom padding on iPhone (34px for home indicator)

### Tab Bar Item States
| State | Icon Style | Color | Label |
|-------|-----------|-------|-------|
| Inactive | Outline | Gray-400 (#9CA3AF) | Gray-400 |
| Active | Solid/Filled | Primary | Primary |
| Badge | Outline + red dot | Gray-400 + Red | Gray-400 |

## BREADCRUMBS

```
Home  >  Products  >  Category  >  Current Page
```
- Font: 14px, regular weight
- Separator: ">" or "/" or chevron icon, 8px spacing each side
- Previous items: primary/link color, clickable
- Current item: gray, non-clickable, semi-bold optional
- Truncate with "..." for deep paths (show first, last 2, ellipsis in middle)

---

## DATA TABLE REFERENCE

### Column Alignment Rules
| Data Type | Alignment | Reason |
|-----------|-----------|--------|
| Text (names, titles) | Left | Natural reading direction |
| Numbers (amounts, counts) | Right | Decimal/digit alignment for scanning |
| Dates | Left or center | Consistent width, easy scanning |
| Status badges | Center or left | Visual consistency |
| Actions (buttons/icons) | Right | Consistent endpoint |
| Checkboxes | Center | Uniform clickable area |

### Table Spacing
| Element | Value | Notes |
|---------|-------|-------|
| Row height | 48-56px | Standard; 40px for dense/compact |
| Cell H-padding | 12-16px | Between cell border and content |
| Cell V-padding | 12px | Centers content vertically |
| Header height | 48px | Same or slightly taller than rows |
| Header font | 12-14px, semi-bold, uppercase optional | Differentiate from data |
| Data font | 14px, regular | Standard readable size |

### Row Treatments
| Treatment | When to Use |
|-----------|-------------|
| Alternating background (zebra) | Dense tables with many columns |
| Divider lines only | Moderate density, cleaner look |
| No dividers | Minimal tables with few rows |
| Row hover highlight | Always (aids horizontal tracking) |

### Sortable Column Indicator
```
Column Name ▲  ← Ascending (A-Z, 0-9, oldest first)
Column Name ▼  ← Descending (Z-A, 9-0, newest first)
Column Name ◇  ← Unsorted (neutral state)
```

### Pagination Pattern
```
← Previous  1  2  [3]  4  5  ...  12  Next →
```
- Show current page highlighted
- Show first, last, and 2 adjacent pages
- Ellipsis for gaps
- Rows per page selector: "Show: 10 | 25 | 50 | 100"
- Results counter: "Showing 21-30 of 247 results"

### Empty State
- Centered illustration or icon (optional)
- Heading: "No results found" (18px, semi-bold)
- Subtext: "Try adjusting your filters or search terms" (14px, gray)
- CTA: "Clear filters" button (optional)

### Loading State
- Skeleton rows: 5-8 rows of gray animated shimmer bars
- Match column widths to expected content
- Header remains visible and static
- Optional: spinner overlay on table area

### Table Responsive Strategy
- Desktop: full table with all columns
- Tablet: hide least-important columns, add horizontal scroll
- Mobile: transform to card layout (each row becomes a card with label-value pairs)

---

## TAB PATTERNS

### Horizontal Tabs
- Position: below page header, above content
- Tab height: 40-48px
- Tab padding: 12-16px horizontal
- Active indicator: 2-3px bottom border in primary color
- Inactive: no border, lighter text color
- Transition: slide indicator on switch (200ms)

### Vertical Tabs
- Position: left side column
- Tab width: 200-240px
- Active indicator: left border accent or filled background
- Best for: settings pages, multi-section forms

### Tab Rules
- 2-7 tabs maximum visible (scroll or "More" for overflow)
- Tab labels: short (1-2 words), descriptive, no truncation
- Badge counts on tabs: small pill right of label (e.g., "Messages (3)")
- Don't use tabs for sequential steps -- use a stepper/wizard instead

---

## ACCORDION / EXPANDABLE PATTERNS

### Anatomy
```
┌───────────────────────────────────────┐
│ Section Title                    [▼]  │ ← Header: 48px height
├───────────────────────────────────────┤
│ Expanded content area                 │ ← Body: auto height, 16px padding
│ with additional details...            │
└───────────────────────────────────────┘
```

### Rules
- Chevron rotates 180 degrees on expand (or plus/minus icon swap)
- Only one open at a time (exclusive) or multiple allowed (independent)
- Animation: 200-300ms ease for expand/collapse
- Divider between items: 1px gray line
- Content padding: 16px top/bottom, align with header text
