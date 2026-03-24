---
name: Dashboard Systems
description: "Design SaaS dashboards with sidebar navigation, data visualization, tables, and dense interfaces. MANDATORY TRIGGERS: dashboard layout, SaaS interface, data dashboard, sidebar navigation, app navigation, metric cards, data visualization, table design, dense UI. Do NOT use for websites — use web-layout instead. Do NOT use for individual components — use ui-components instead."
---

# Dashboard Systems

## When You Need This Skill

Use this skill when:
- Designing a SaaS product dashboard or admin interface
- Planning app navigation (sidebar, top bar, bottom tabs)
- Structuring data-heavy interfaces with tables and charts
- Organizing metrics and KPI displays
- Creating responsive dashboard layouts for mobile/tablet
- Designing information-dense interfaces with clear hierarchy

**Do NOT use for:**
- Website layouts → see **web-layout**
- Individual components (buttons, forms, cards) → see **ui-components**
- Website navigation patterns → see **web-layout**

---

## Dashboard Anatomy

### The Standard Structure

```
┌────────────────────────────────────────────┐
│ Logo  Search  User Profile  [⋮]           │  Top header (56-64px)
├──────────┬──────────────────────────────────┤
│ Dashboard│ Main Content Area               │
│ Sidebar  │ [Metrics] [Table] [Charts]     │
│ Home     │                                  │
│ Reports  │                                  │
│ Users    │                                  │
│ Settings │                                  │
│          │                                  │
└──────────┴──────────────────────────────────┘
```

**Three Core Sections:**

1. **Top Header** — Search, notifications, user menu
2. **Sidebar Navigation** — Primary navigation (collapsible)
3. **Main Content Area** — Metrics, tables, charts

---

## Sidebar Navigation

### Desktop Sidebar

**Sizing:**
- **Width:** 250-280px (collapsed: 64px)
- **Background:** Dark gray (#2D2D2D) or brand dark color
- **Text color:** White (#FFF) or light gray

**Item Structure:**
```
┌──────────────────────────┐
│ Dashboard               │  Icon (24px) + Text
│   Home                  │  Nested: 20px smaller indent
│   Analytics             │  Hover: Light background (20% white)
│   Billing               │  Active: Highlight color or left border
│ Tools                   │
│   Settings              │
│   Users                 │
└──────────────────────────┘
```

**Sizing Specifications:**
- **Item height:** 44-48px
- **Icon:** 20-24px, left-aligned
- **Text:** 14px, regular weight
- **Icon-to-text gap:** 12px
- **Nested items:** 20px left padding (double indent)
- **Section headers:** 12px, gray, uppercase, 12px padding
- **Gap between sections:** 24px

### Sidebar States

**Default (Not Selected):**
- Text: Light gray (#AAA)
- Background: Transparent
- Icon: Light gray

**Hover:**
- Background: 20% white overlay
- Text: White
- Icon: White

**Active (Current Page):**
- Background: Brand primary color or darker shade
- Text: White
- Icon: White
- Optional: Left border 3px solid brand color

**Disabled:**
- Opacity: 50%
- Cursor: not-allowed
- Hover: No change

### Collapsible Sidebar

**Expanded (250px):**
```
[Icon] Dashboard
[Icon] Reports
[Icon] Users
```

**Collapsed (64px):**
```
[Icon]  (only icon visible)
[Icon]
[Icon]
Tooltip on hover: "Dashboard", "Reports", "Users"
```

**Animation:**
- Width transition: 200ms
- Easing: ease-out
- Icons center within 64px space

### Sticky Sidebar

```css
.sidebar {
  position: sticky;
  top: 0;
  height: 100vh;
  overflow-y: auto;
}
```

- Sidebar stays visible when scrolling
- User can navigate while viewing content
- Improves multi-page experience

---

## Top Header

### Elements & Sizing

```
┌────────────────────────────────────────────┐
│ Logo  [Search bar]  [Notification] [User]  │
│ 48px   200px        24px            32px   │
└────────────────────────────────────────────┘
```

**Height:** 56-64px (recommend 64px for balance)

**Sections:**

1. **Logo/Brand (Left):** 40×40px container, logo 32×32px
2. **Search Bar (Center):** 200-300px, gray border, placeholder
3. **Notifications (Right):** Bell icon 24px, red badge "5"
4. **User Menu (Right):** Avatar 32px or initials in circle

**Spacing:**
- Logo: 16px left margin
- Search bar: 24px from logo
- Icons: 16px gap between each, 16px right margin

### Search Bar Styling

```
┌──────────────────┐
│ 🔍 Search...     │  Height: 40px
└──────────────────┘
```

- Width: 200-300px
- Height: 40px
- Border: 1px solid #E0E0E0
- Padding: 10px left, 12px right (after icon)
- Border radius: 4px
- Placeholder: "Search dashboards, users, reports..."
- Icon: Magnifying glass, 20px, gray

**Focus State:**
- Border: 2px primary color
- Background: Light brand color (5% opacity)

**Results Dropdown:**
- Width: Match search bar width
- Max-height: 300px (scrollable)
- Results: Grouped by type (Dashboards, Users, Reports)
- Highlight on hover
- Result item height: 44px

---

## Metric Cards (KPI Display)

Basic and advanced metric cards with sizing, grid layouts, and mini chart options.

For complete metric card patterns including sizing, grid layouts, advanced cards with charts, and card states, read `references/metric-cards-charts.md`.

---

## Data Tables in Dashboards

Table structure, column sizing, features (sorting, filtering, pagination), and responsive layouts.

For complete table patterns including sizing, column widths, features, and responsive behavior, read `references/dashboard-tables.md`.

---

## Data Visualization (Charts & Graphs)

Chart types, sizing guidelines, and styling for dashboards.

For complete chart information including types, sizing options, and styling guidelines, read `references/metric-cards-charts.md`.

---

## Dashboard Layout Patterns

### Pattern 1: Metrics Row + Full-Width Table

```
[Metric 1] [Metric 2] [Metric 3] [Metric 4]
─────────────────────────────────────────
[Full-width data table with pagination]
```

**Use case:** Analytics dashboard, admin panel
**Responsive:** Metrics stack on tablet/mobile, table scrolls

### Pattern 2: Sidebar Metrics + Main Chart

```
[Left sidebar]  [Chart title]
[Metric 1]      [Large line/bar chart]
[Metric 2]      [Legend below]
[Metric 3]
```

**Use case:** Sales dashboard, performance dashboard
**Responsive:** Sidebar collapses, chart full-width on mobile

### Pattern 3: 2×2 Grid of Charts

```
[Chart 1] [Chart 2]
[Chart 3] [Chart 4]
```

**Use case:** Comprehensive dashboard overview
**Responsive:** 2 per row (desktop), 1 per row (mobile)

### Pattern 4: List of Data + Side Panel

```
[Data list]    [Detail panel]
[Item 1]       Shows info for
[Item 2]       selected item
[Item 3]       Can edit/update
[Item 4]       here
```

**Use case:** User management, product list with details
**Responsive:** Detail panel below list on mobile

For complete layout patterns with responsive behavior at all breakpoints, read `references/layout-patterns.md`.

---

## Mobile App Navigation (Tabbed Bottom Nav)

**Common for mobile-first SaaS apps:**

```
┌────────────────────┐
│ [Dashboard content] │
├────────────────────┤
│ 🏠 📊 🔔 👤 [⋮]    │  Tab bar (56px height)
└────────────────────┘
```

**Tab Sizing:**
- **Height:** 56px (safe zone above for iPhone)
- **Icons:** 24px
- **Gap:** Equal width tabs (5 max)
- **Label:** Optional, 10px below icon

**Common Tabs:**
1. Home/Dashboard
2. Analytics/Reports
3. Notifications
4. Profile/Account
5. More/Settings (three-dot menu)

**Active Tab:**
- Icon: Brand color
- Background: Subtle highlight (5% darker)
- Label: Visible and colored

---

## Accessibility in Dashboards

- [ ] Sidebar links keyboard-navigable (Tab key)
- [ ] Focus ring visible (3px outline)
- [ ] Color contrast: 4.5:1 for all text
- [ ] Tables: Keyboard navigation (arrow keys in focusable cells)
- [ ] Charts: Data table alternative (CSV download or data table view)
- [ ] Aria labels: "Open user menu", "Search dashboard"
- [ ] Status updates: Live regions for async updates
- [ ] Loading states: "Loading dashboard..." text, not spinner-only
- [ ] No keyboard traps (can Tab out of modal/sidebar)
- [ ] Skip links: "Skip to main content"

---

## Dashboard Anti-Patterns

### ❌ Overwhelming Metrics

```
12 metric cards above the fold
(Too much info, hard to scan)
```

**Fix:** Show top 4 metrics, let users customize.

### ❌ Dense Table Without Pagination

```
1000 rows loaded, no scroll or pagination
(Slow, hard to navigate)
```

**Fix:** Paginate (10-25 rows per page), add search/filter.

### ❌ Charts Without Context

```
Line chart with no title, no legend, no axis labels
(What am I looking at?)
```

**Fix:** Add title, legend, axis labels, tooltips.

### ❌ Non-responsive Sidebar

```
Sidebar always 250px, even on mobile
(Takes 60% of screen)
```

**Fix:** Collapse to hamburger menu on mobile.

### ❌ No Data States

```
Empty dashboard shows nothing (blank page)
(User doesn't know if it loaded or broken)
```

**Fix:** Show "No data yet" message with empty state.

---

## When to Read Reference Files

| Need | Reference |
|------|-----------|
| Sidebar navigation, top bar, menu patterns | **dashboard-structure.md** |
| Chart types, visualizations, graph sizing | **data-visualization.md** |
| Table design, pagination, responsive tables | **table-design.md** |
| Navigation patterns for different devices | **navigation-app.md** |
| Information density, whitespace, scanning | **interface-density.md** |

---

## Cross-Skill References

- **visual-foundations** → For typography, color, spacing in dashboards
- **ui-components** → For buttons, form fields, modals within dashboards
- **figma-workflows** → For building dashboard component libraries
- **animation-interactions** → For micro-interactions and transitions
- **webflow-implementation** → If building dashboard in Webflow (rare)

---

## Quick Dashboard Layout Checklist

- [ ] Sidebar navigation clear and organized (max 10 items visible)
- [ ] Top header includes search and user menu
- [ ] Metric cards grid responsive (4→2→1 columns)
- [ ] Tables have pagination (max 25 rows per page)
- [ ] Charts are labeled (title, legend, axis labels)
- [ ] Empty states designed (no data, error, loading)
- [ ] Mobile navigation designed (hamburger or bottom tabs)
- [ ] Colors consistent across interface (brand palette)
- [ ] Hover and active states clear on all interactive elements
- [ ] All text 4.5:1 contrast minimum
- [ ] Tables keyboard-navigable
- [ ] Responsive behavior tested at 1440px, 800px, 390px

