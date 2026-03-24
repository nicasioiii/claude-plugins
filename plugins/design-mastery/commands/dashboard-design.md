---
name: Dashboard Design
description: "Design a SaaS dashboard interface with layout structure, navigation, and data visualization patterns."
---

# Dashboard Design

Design a SaaS dashboard or app interface with proper structure, navigation patterns, and data visualization. This provides layout templates, component recommendations, and best practices for building complex interfaces.

---

## What This Command Does

You describe your app use case, and I'll provide:
- Dashboard layout structure (sidebar, header, content)
- Navigation patterns (tabs, menus, breadcrumbs)
- Data display recommendations (tables, charts, metrics)
- Grid layout and spacing guidelines
- Responsive behavior (mobile dashboard collapse)
- Component patterns (metric cards, tables, dropdowns)
- Information hierarchy for dense UIs
- State handling (empty, loading, error states)
- Interaction patterns (sorting, filtering, pagination)

**Time to answer:** 3-5 minutes
**Time to receive dashboard:** 15-20 minutes

---

## Scoping Questions

**QUESTION 1: What's the main use case?**

What does this dashboard help users do? (e.g., "Track fitness workouts," "Manage projects," "Monitor server performance")

---

**QUESTION 2: Primary user?**

Who is the user? What's their technical level? (e.g., "Gym enthusiasts, basic tech," "Project managers, moderate tech," "Engineers, advanced tech")

---

**QUESTION 3: Key data points?**

What are the 5-10 most important metrics/data this dashboard needs to show?

*Examples for fitness app:*
- Total workouts (this week, month, year)
- Calories burned
- Exercises completed
- Streak (consecutive days)
- Personal records
- Body measurements

*Examples for project management:*
- Active projects
- Team members
- Tasks in progress
- Deadline overview
- Team availability
- Budget spent

---

**QUESTION 4: Main actions?**

What should users be able to DO in the dashboard?

*Examples:*
- Create new item (project, workout, alert)
- Edit existing items
- Delete items
- Filter/search
- Export data
- Share with team

---

**QUESTION 5: Device requirement?**

Must this work on mobile/tablet? Or desktop-only?

---

## Dashboard Architecture

Once you answer, I'll provide a dashboard structure suited to your app type.

### TYPICAL DASHBOARD LAYOUT

```
┌─────────────────────────────────────────────┐
│  LOGO  │  NOTIFICATIONS  │  SEARCH  │  USER │  ← Header (56px)
├──────┬───────────────────────────────────────┤
│      │                                       │
│ SIDE │      MAIN CONTENT AREA               │
│ BAR  │  ┌─────────────────────────────────┐ │
│      │  │ BREADCRUMB / TITLE BAR          │ │
│ NAV  │  ├─────────────────────────────────┤ │
│      │  │ METRIC CARDS / SUMMARY          │ │
│ (240 │  ├─────────────────────────────────┤ │
│ px)  │  │ MAIN CONTENT                    │ │
│      │  │ (Charts, Tables, Grids)         │ │
│      │  │                                 │ │
│      │  │                                 │ │
│      │  └─────────────────────────────────┘ │
└──────┴───────────────────────────────────────┘
```

### DASHBOARD COMPONENTS

#### 1. HEADER (56px height)
- **Left side:** Logo, app name
- **Center:** Breadcrumb or page title (optional)
- **Right side:** Search, notifications, user menu
- **Sticky:** Stays at top during scroll

#### 2. SIDEBAR (240px width, collapsible)
- **Navigation items** (5-10 main sections)
- **Active state** (current section highlighted)
- **Hover state** (background color change)
- **Collapsible** (hamburger on mobile)
- **Icons + labels** (desktop and tablet)

#### 3. MAIN CONTENT AREA
- **Max-width:** Usually 1200-1400px (less constrained than website)
- **Padding:** 24-32px on desktop, 16px on tablet, 12px on mobile
- **Single column** (content stretches to available width)

#### 4. CONTENT SECTIONS
- **Metric Cards** (key numbers, quick overview)
- **Charts/Graphs** (data visualization)
- **Data Tables** (detailed information, sortable/filterable)
- **Action Cards** (things user can do)
- **Modals/Forms** (create/edit functionality)

---

## Key Dashboard Patterns

### PATTERN 1: METRIC CARD LAYOUT

**Purpose:** Show key numbers at a glance

**Structure:**
```
┌──────────────────────┐
│ LABEL                │
│ (Small, gray)        │
│                      │
│ 2,485                │  ← Big number (28-32px)
│                      │
│ ↑ 12% vs last week   │  ← Comparison (12px, green/red)
└──────────────────────┘
```

**Metrics:**
- Card width: 200-280px (flex to fill available space)
- Label: 12px, gray
- Number: 28-32px, bold
- Comparison: 12px, green (up) or red (down)
- Icon (optional): 32px, left side
- Padding: 16px
- Border: None or subtle border
- Hover: Slight shadow or scale

**Grid Layout:**
- Desktop: 4 cards in a row (or 5 if narrow cards)
- Tablet: 2 cards in a row
- Mobile: 1 card per row (full width)

**Common Metrics:**
- Total (today, this week, this month)
- Change from last period (↑ 12% or ↓ 5%)
- Status (on track, at risk, complete)
- Trend (sparkline mini-chart)

---

### PATTERN 2: DATA TABLE

**Purpose:** Show detailed, structured information

**Structure:**
```
┌─────┬────────────────┬──────────┬─────────┐
│ ☐   │ COLUMN 1       │ COLUMN 2 │ ACTIONS │  ← Header row (40px)
├─────┼────────────────┼──────────┼─────────┤
│ ☐   │ Item A         │ Value    │ ⋮       │  ← Data row (40px)
├─────┼────────────────┼──────────┼─────────┤
│ ☐   │ Item B         │ Value    │ ⋮       │
├─────┼────────────────┼──────────┼─────────┤
│ ☐   │ Item C         │ Value    │ ⋮       │
└─────┴────────────────┴──────────┴─────────┘
```

**Metrics:**
- Header row: 40px, bold text, subtle background
- Data rows: 40px, regular text
- Column padding: 12-16px horizontal
- Row border: 1px #eee between rows (or alternating rows)
- Row hover: Slight background highlight
- Checkbox: Left side, for bulk actions
- Actions: Right side (edit, delete, etc.)

**Features:**
- Sortable columns (click header to sort A-Z, Z-A)
- Searchable (filter box above table)
- Pagination (show 10, 25, 50, 100 items per page)
- Selectable rows (checkboxes, bulk actions)
- Expandable rows (click to see details)

**Responsive:**
- Desktop: Full width, all columns visible
- Tablet: May need horizontal scroll for wide tables
- Mobile: Swipe right to scroll, or collapse to card view

---

### PATTERN 3: CHART/GRAPH

**Purpose:** Visualize trends and distributions

**Chart Types:**

| Chart Type | Use Case | Example |
|-----------|----------|---------|
| **Line Chart** | Trends over time | Revenue by month |
| **Bar Chart** | Compare values | Sales by region |
| **Pie Chart** | Show proportions | Market share |
| **Area Chart** | Show cumulative growth | User growth over time |
| **Heatmap** | Show intensity/density | Activity by hour/day |
| **Gauge** | Show progress to goal | Completion %, target reached |

**Sizing:**
- Small chart: 300x300px (metric detail page)
- Medium chart: 500x300px (dashboard card)
- Large chart: 600x400px or full-width

**Colors:**
- Use brand colors (primary, secondary)
- Max 5 colors per chart (avoid rainbow)
- Use accessible colors (high contrast, colorblind safe)
- Include legend if multiple data sets

**Labels:**
- Y-axis: Clear units (%, $, count)
- X-axis: Clear time periods or categories
- Legend: List all data sets
- Tooltip: Show exact values on hover

---

### PATTERN 4: FILTER/SEARCH BAR

**Purpose:** Let users find and filter data

**Structure:**
```
┌──────────────────┬──────────┬──────────┐
│ 🔍 Search...     │ Filter ▼ │ Sort ▼   │
└──────────────────┴──────────┴──────────┘
```

**Components:**
- Search input (magnifying glass icon)
- Filter dropdown (dropdowns for each field)
- Sort dropdown (A-Z, newest, etc.)
- Export button (optional)
- Refresh button (optional)

**Behavior:**
- Real-time search (filter as you type)
- Filter dropdowns (multi-select options)
- Applied filters shown as tags (removable)
- "Clear filters" button if filters applied

---

### PATTERN 5: MODAL / OVERLAY

**Purpose:** Create new item, edit item, confirm action

**Structure:**
```
┌───────────────────────────────────────┐
│ CREATE NEW ITEM             [X]       │  ← Header
├───────────────────────────────────────┤
│                                       │
│  FIELD 1  [Input]                    │  ← Form content
│                                       │
│  FIELD 2  [Input]                    │
│                                       │
│  FIELD 3  [Select]                   │
│                                       │
├───────────────────────────────────────┤
│  [Cancel]                [Create]     │  ← Actions
└───────────────────────────────────────┘
```

**Sizing:**
- Width: 400-600px (depends on form complexity)
- Modal centered on screen
- Backdrop: Semi-transparent (50% opacity)

**States:**
- Default (empty form)
- Filled (user has entered data)
- Submitting (button shows spinner)
- Success (brief confirmation, then close)
- Error (show error message, highlight fields)

---

## Information Hierarchy in Dense UIs

**Make dashboards scannable:**

**Use size hierarchy:**
- Most important metric: 28-32px
- Secondary metric: 18-20px
- Body text: 14px
- Captions: 12px

**Use color strategically:**
- Primary numbers in dark (high contrast)
- Labels in gray (secondary)
- Status in color (green = good, red = alert)
- Actions in blue (standard interaction color)

**Use whitespace:**
- Sections separated by 24-32px padding
- Cards have breathing room
- Don't cram content (no wall of text)

**Use visual grouping:**
- Related cards grouped together
- Sections have clear boundaries
- Align items to grid (not random)

**Use icons:**
- Icons help scan faster (heart = favorites, settings = preferences)
- Consistent icon style
- Icons should be obvious (not cryptic)

---

## Responsive Dashboard Design

**Desktop (1200px+):**
- Sidebar fully visible (240px)
- 2-4 columns of metric cards
- Full-width tables and charts
- All navigation visible

**Tablet (768-1199px):**
- Sidebar visible or collapsible (toggle with hamburger)
- 2 columns of metric cards
- Tables may scroll horizontally
- Simplified navigation

**Mobile (Below 768px):**
- Sidebar collapsed (hamburger menu)
- Full-width content (single column)
- Metric cards stack vertically
- Tables convert to card view (swipe to scroll)
- Modals full-screen

**Hamburger Menu Structure:**
```
☰ MENU
├─ Dashboard
├─ Projects
│  ├─ Project A
│  └─ Project B
├─ Team
├─ Settings
└─ Help
```

---

## State Handling

**Empty State** (no data)
```
📭
No projects yet
Create your first project to get started
[+ Create Project]
```

**Loading State** (fetching data)
```
⚙️ Loading...
```
Or show skeleton screens:
```
┌───────────────┐
│ ░░░░░░░░░░░░ │  ← Placeholder shimmer
├───────────────┤
│ ░░░░░░░░░░░░ │
├───────────────┤
│ ░░░░░░░░░░░░ │
└───────────────┘
```

**Error State** (failed to load)
```
⚠️ Failed to load data
[Retry]
```

**Success State** (action completed)
```
✓ Project created successfully
(Toast notification, auto-dismiss in 3 seconds)
```

---

## Dashboard Layout by App Type

### ANALYTICS DASHBOARD
**Key sections:**
- Metrics summary (4-6 key KPIs)
- Main chart (revenue, traffic, etc.)
- Secondary charts (breakdowns)
- Data table (detailed records)

**Layout:**
```
┌─────────────────────┐
│ Metric Cards (4)     │
├─────────────────────┤
│ Main Chart (full)   │
├─────────────────────┤
│ Secondary Charts (2)│
├─────────────────────┤
│ Data Table         │
└─────────────────────┘
```

### PROJECT MANAGEMENT
**Key sections:**
- Project overview (status, progress)
- Tasks list (assignees, due dates)
- Team members (availability)
- Timeline (calendar, Gantt)

**Layout:**
```
┌─────────────────────┐
│ Project Status Card |
├─────────────────────┤
│ Tasks List (table)  │
├─────────────────────┤
│ Team Overview       │
├─────────────────────┤
│ Calendar/Timeline   │
└─────────────────────┘
```

### E-COMMERCE ADMIN
**Key sections:**
- Sales summary (today, week, month)
- Recent orders (table, sortable)
- Products (grid, searchable)
- Inventory levels

**Layout:**
```
┌──────────┬──────────┐
│Sales     │ Orders   │
├──────────┴──────────┤
│ Recent Orders Table  │
├──────────────────────┤
│ Products Grid        │
├──────────────────────┤
│ Low Inventory Alert  │
└──────────────────────┘
```

---

## Complete Dashboard Checklist

- [ ] Layout structure defined (header, sidebar, main area)
- [ ] Navigation patterns clear (main nav, breadcrumbs, user menu)
- [ ] Key metrics identified (5-10 main data points)
- [ ] Metric cards designed (sizing, spacing, layout)
- [ ] Data table designed (columns, sorting, pagination)
- [ ] Charts selected and placed
- [ ] Filter/search bar designed
- [ ] Responsive behavior planned (mobile layout)
- [ ] State handling defined (empty, loading, error, success)
- [ ] Action patterns designed (create, edit, delete, export)
- [ ] Modal/form layouts defined
- [ ] Spacing and alignment consistent
- [ ] Colors and contrast verified
- [ ] Accessibility checked (keyboard nav, labels, contrast)

---

## Next Steps

Based on your dashboard design:

1. **Use `/design-system`** to set up Figma components for dashboard elements
2. **Use `/animation-help`** to add hover states and micro-interactions
3. **Use `/responsive-layout`** principles for mobile adaptation
4. **Use `dashboard-systems` skill** for deep reference on layouts, components, data viz

---

## Pro Tips

**For Dashboards:**
- **Minimize scrolling** (prioritize most important info above fold)
- **Avoid information overload** (max 5-7 sections per page)
- **Use consistent spacing** (8px, 16px, 24px, 32px only)
- **Make actions obvious** (primary buttons prominent, secondary subtle)
- **Test with real data** (mock data doesn't reveal issues)

**For Performance:**
- **Lazy load charts** (load below fold on scroll)
- **Paginate tables** (don't load 1000 rows at once)
- **Cache frequently accessed data** (reduce API calls)
- **Show loading states** (users know something's happening)

**For Usability:**
- **Provide defaults** (pre-fill common filters)
- **Remember user preferences** (sort, filter, view type)
- **Keyboard shortcuts** (power users appreciate these)
- **Tooltips for complex metrics** (explain what numbers mean)

---

## Ready?

Tell me:
1. **What's the main use case** of your dashboard?
2. **Who are the primary users?**
3. **Top 5-10 metrics** to display
4. **Main actions** users need to take
5. **Mobile support needed?**

I'll create your complete dashboard design with all layouts, patterns, and implementation guidance!
