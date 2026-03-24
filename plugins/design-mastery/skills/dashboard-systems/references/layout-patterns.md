# Dashboard Layout Patterns

## Pattern 1: Metrics Row + Full-Width Table

```
[Metric 1] [Metric 2] [Metric 3] [Metric 4]
─────────────────────────────────────────
[Full-width data table with pagination]
```

**Use case:** Analytics dashboard, admin panel
**Responsive:** Metrics stack on tablet/mobile, table scrolls

## Pattern 2: Sidebar Metrics + Main Chart

```
[Left sidebar]  [Chart title]
[Metric 1]      [Large line/bar chart]
[Metric 2]      [Legend below]
[Metric 3]
```

**Use case:** Sales dashboard, performance dashboard
**Responsive:** Sidebar collapses, chart full-width on mobile

## Pattern 3: 2×2 Grid of Charts

```
[Chart 1] [Chart 2]
[Chart 3] [Chart 4]
```

**Use case:** Comprehensive dashboard overview
**Responsive:** 2 per row (desktop), 1 per row (mobile)

## Pattern 4: List of Data + Side Panel

```
[Data list]    [Detail panel]
[Item 1]       Shows info for
[Item 2]       selected item
[Item 3]       Can edit/update
[Item 4]       here
```

**Use case:** User management, product list with details
**Responsive:** Detail panel below list on mobile

## Responsive Dashboard Behavior

### Desktop (1440px)

- Sidebar: 250px visible, expandable navigation
- Content: Full-width minus sidebar
- Grid: Multiple columns (3-4 items per row)
- Tables: All columns visible, horizontal scroll if needed
- Charts: Large, detailed

### Tablet (800px)

- Sidebar: Hamburger menu (collapses to 64px)
- Content: Full-width when sidebar collapsed
- Grid: 2 columns (2 items per row)
- Tables: Important columns visible, scroll for others
- Charts: Medium size, may stack

### Mobile (390px)

- Sidebar: Slide-out panel (full-width when open)
- Content: Single column, full-width
- Grid: 1 column (cards stack)
- Tables: Card view (one item per "card")
- Charts: Single column, full-width
