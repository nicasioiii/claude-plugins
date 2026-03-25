---
name: Dashboard & App Design
description: "SaaS dashboards, sidebar navigation, data visualization, tables, dense interfaces, metric cards, app navigation patterns, UX laws applied to product design. FOR: designing SaaS dashboards, admin panels, analytics interfaces, data-heavy layouts, app interfaces, metric displays, high-density UIs. MANDATORY TRIGGERS: dashboard, SaaS, app design, admin panel, analytics, metric card, data table, sidebar navigation, navigation drawer, data visualization, chart design, KPI, dense interface, application interface, product design, high-density layout, enterprise UI, settings page, user management. Do NOT use for — use web-layout for marketing websites, use ui-components for individual component patterns, use webflow-build for Webflow implementation."
---

# Dashboard & App Design

Dashboards and app interfaces are fundamentally different from marketing websites. They prioritize information density, scanability, and task efficiency over visual storytelling. This skill covers the UX laws, layout patterns, and data display techniques specific to product/app design.

## HIGH DENSITY vs LOW DENSITY [MDS]

The context determines appropriate density:

| Context | Density | Spacing | Type Size | Target User |
|---------|---------|---------|-----------|-------------|
| First-time user experience | Low | Generous | Larger | New user |
| Power user tools | **High** | Compact | Smaller | Expert |
| Marketing/sales | Low | Generous | Larger | Prospect |
| Admin/management | **High** | Compact | Smaller | Internal |
| Onboarding wizard | Low | Generous | Larger | Any |
| Data dashboard | **High** | Compact | Smaller | Analyst |

**Key principle**: Dense information needs less negative space. Marketing pages need more. Dashboards serve information-seeking users who want efficiency, not aesthetics-first design.

---

## UX LAWS FOR PRODUCT DESIGN

### Hick's Law [Arash]
**Decision time increases with number of choices.**

Application to dashboards:
- Limit primary navigation to 5-7 top-level items
- Group related items into sub-menus rather than showing 20+ options
- Three-tiered pricing strategy works because it limits choice
- Progressive disclosure: show summary first, expand for detail
- Filter/sort panels: start with most-used filters visible, hide advanced in expandable section

### Fitts's Law [Arash]
**Time to reach target = function of distance + target size.**

Application to dashboards:
- Frequently used actions (save, submit) should be large and in easy-to-reach areas
- Place primary actions near the data they affect (not far away in a toolbar)
- Bottom of screen on mobile = easy to reach with thumb
- Group related actions together to reduce cursor travel
- Touch targets on tablets: minimum 44x44px

### Jakob's Law [Arash]
**Users expect your app to work like other apps they use.**

Application to dashboards:
- Sidebar navigation on left (established SaaS pattern)
- Settings gear icon in expected position
- Search bar at top
- Notifications bell in top-right
- User profile/avatar in top-right corner
- Table sorting via column header click
- Breadcrumbs for deep navigation

### Miller's Law [Arash]
**People remember 7 +/- 2 pieces of information at a time.**

Application to dashboards:
- Chunk data into digestible groups
- Use cards to contain related metrics
- [CONTRARIAN] Common misapplication: designers limit menus to 7 items. Menu items are visible -- users don't need to remember them. Don't artificially limit visible navigation [Arash]

### Von Restorff Effect [Arash]
**Items that stand out from surroundings are more likely remembered.**

Application to dashboards:
- Highlight critical metrics with contrasting color
- Alert badges in red stand out from neutral UI
- Use color coding sparingly -- when everything is highlighted, nothing is

### Gestalt Principles [Arash]
**Proximity, similarity, continuity, closure, figure-ground, common region.**

Application to dashboards:
- **Proximity**: Group related metrics in the same card or section
- **Similarity**: Same visual treatment for same data types
- **Common region**: Use card borders/backgrounds to group related information
- **Figure-ground**: Key data stands out from background interface chrome
- Long forms: divide into smaller chunks for easier processing

### Fogg Behavior Model [Designership]
**Behavior = Motivation x Ability x Prompt.**

Application to dashboards:
- Reduce friction (increase ability): minimize steps for common tasks
- Clear CTAs (prompts): obvious buttons for primary actions
- Communicate value (motivation): show what completing an action achieves

---

## DASHBOARD LAYOUT PATTERNS

### Standard SaaS Dashboard Layout
```
┌───────────┬──────────────────────────────────────────┐
│           │ [Search]     [Notifications] [Avatar]    │
│  [Logo]   ├──────────────────────────────────────────┤
│           │                                          │
│  Nav 1 ●  │  [Metric] [Metric] [Metric] [Metric]   │
│  Nav 2    │                                          │
│  Nav 3    │  ┌──────────────────┐ ┌────────────────┐│
│  Nav 4    │  │                  │ │                ││
│  Nav 5    │  │  Chart Area      │ │  Table/List    ││
│           │  │                  │ │                ││
│  ──────   │  │                  │ │                ││
│  Settings │  └──────────────────┘ └────────────────┘│
│  Help     │                                          │
│  Profile  │  ┌──────────────────────────────────────┐│
│           │  │  Data Table (full width)              ││
│           │  │                                      ││
│           │  └──────────────────────────────────────┘│
└───────────┴──────────────────────────────────────────┘
```

### Layout Zones
| Zone | Content | Sizing |
|------|---------|--------|
| Sidebar | Primary navigation | 240-280px expanded, 64px collapsed |
| Top bar | Search, notifications, profile | 56-64px height |
| Metric row | KPI cards | 4 across, equal width |
| Primary content | Charts, featured data | 60-70% width |
| Secondary content | Lists, recent activity | 30-40% width |
| Full-width section | Data tables, reports | 100% of content area |

### Sidebar Navigation
- **Expanded**: 240-280px, icon + label
- **Collapsed**: 64-72px, icon only (with tooltip on hover)
- **Active item**: Left border accent (3-4px) + filled background or bold text
- **Section dividers**: 1px line with 16px vertical margin
- **Bottom group**: Settings, Help, Profile (separated from main nav)
- **Collapse trigger**: hamburger icon or auto-collapse at tablet breakpoint

### Top Utility Bar
```
[Breadcrumb / Page Title]                    [Search] [Bell] [Avatar ▼]
```
- Height: 56-64px
- Left: page title or breadcrumb navigation
- Right: search input, notification bell (with badge count), user avatar with dropdown
- Background: white with subtle bottom border (1px gray-200)

---

## METRIC CARD DESIGN

### Anatomy
```
┌────────────────────────────┐
│ Revenue           [icon]   │  ← Label: 12-14px, gray, uppercase optional
│ $45,230                    │  ← Value: 24-36px, bold, primary text
│ ▲ 12.5% vs last month     │  ← Trend: 12-14px, green/red + arrow
│ ─────────────────          │  ← Sparkline (optional)
└────────────────────────────┘
```

### Metric Card Sizing
| Element | Value |
|---------|-------|
| Card padding | 16-20px |
| Label | 12-14px, medium weight, gray-500 |
| Value | 24-36px, bold, gray-900 |
| Trend text | 12-14px, green-600 (up) or red-600 (down) |
| Trend arrow | 12px icon inline with text |
| Sparkline height | 32-48px |
| Card min-width | 200px |
| Card gap in row | 16-24px |

### Metric Card Grid
- Desktop: 4 across (or 3 for larger cards)
- Tablet: 2 across
- Mobile: 1 per row or 2 compact
- All cards same height (align bottom edges)

### Trend Indicators
| Direction | Color | Icon | Text |
|-----------|-------|------|------|
| Positive | Green (#059669) | ▲ or ↑ | "+12.5%" |
| Negative | Red (#DC2626) | ▼ or ↓ | "-3.2%" |
| Neutral | Gray (#6B7280) | → or − | "0.0%" |

---

## DATA TABLE DESIGN (Dashboard Context)

### Dense Table Specs
| Property | Standard | Compact |
|----------|----------|---------|
| Row height | 48-56px | 36-40px |
| Cell H-padding | 16px | 12px |
| Font size | 14px | 13px |
| Header font | 12px semi-bold | 12px semi-bold |
| Hover background | gray-50 | gray-50 |

### Table Header Pattern
```
┌──────────────────────────────────────────────────────────┐
│ [Page Title]                    [Filter] [Export] [+ New]│
├──────────────────────────────────────────────────────────┤
│ □ Name ▲        Status        Amount ▼       Date       │
├──────────────────────────────────────────────────────────┤
│ □ Acme Corp     ● Active      $2,400        Mar 15     │
│ □ Beta Inc      ○ Pending     $1,200        Mar 14     │
│ □ Gamma LLC     ● Active      $3,800        Mar 13     │
├──────────────────────────────────────────────────────────┤
│ Showing 1-10 of 247         ← 1 2 3 ... 25 →           │
└──────────────────────────────────────────────────────────┘
```

### Table Action Bar
- Above table: filters, search, export, create new
- Bulk actions: appear when rows selected (e.g., "3 selected: [Delete] [Export] [Archive]")
- Row actions: hover-revealed icons or three-dot menu at row end

### Status Indicators in Tables
- Dot + text: small colored circle (8px) + status text
- Badge: colored pill with status text
- Color coding: green = active/success, yellow = pending/warning, red = error/failed, gray = inactive/draft

---

## CHART & DATA VISUALIZATION

### Chart Type Selection
| Data Type | Chart | When |
|-----------|-------|------|
| Trend over time | Line chart | Revenue by month, user growth |
| Category comparison | Bar chart (vertical) | Sales by product, team performance |
| Ranking | Horizontal bar | Top 10 pages, customer segments |
| Composition | Donut/pie | Revenue split, traffic sources |
| Distribution | Area chart | Range of values over time |
| Correlation | Scatter plot | Two variables relationship |

### Chart Design Rules
- Label axes clearly (unit, time period)
- Use 10-20 colors maximum for data series
- Tooltips on hover for exact values
- Legend position: below chart or right side
- Keep charts simple -- one insight per chart
- Dashboard charts are for scanning, not deep analysis

### Chart Sizing
| Placement | Width | Height |
|-----------|-------|--------|
| Full-width card | 100% content area | 300-400px |
| Half-width card | 50% content area | 250-300px |
| Metric card inline | Card width | 48-64px (sparkline) |

---

## APP NAVIGATION PATTERNS

### Navigation Drawer (Mobile)
- Slides from left edge
- Overlay with dark backdrop
- Same items as sidebar nav
- Swipe gesture to open/close
- Close on outside tap

### Settings Page Layout
```
┌──────────────────┬──────────────────────────────┐
│ General          │ Account Settings              │
│ Security         │                               │
│ Notifications ●  │ [Form fields in sections]     │
│ Billing          │                               │
│ Integrations     │ [Save] [Cancel]               │
│ Team Members     │                               │
└──────────────────┴──────────────────────────────┘
```
- Vertical tabs on left (200-240px)
- Form content on right
- Group settings into logical sections with headings
- Save/Cancel buttons at bottom of each section or sticky at bottom

---

## ANTI-PATTERNS

- Marketing-style generous spacing in data-dense dashboards (wastes screen space)
- Too many metrics visible at once without grouping
- Navigation with 15+ unorganized items (use sections and sub-menus)
- Charts without labels, legends, or tooltips
- Color coding without text backup (accessibility failure)
- Same visual weight for all metrics (no hierarchy of importance)
- Full-screen modals for simple confirmations (use inline confirmation or small dialog)
- Sidebar that cannot collapse on smaller screens

---

## RELATED SKILLS

- **ui-components**: For individual component patterns (buttons, forms, tables, cards)
- **layout-spacing**: For the spacing system governing dense layouts
- **color-systems**: For data visualization colors, semantic colors, status indicators
- **design-systems**: For building dashboard component variants in Figma
- **typography-systems**: For compact type scales in high-density interfaces
- **web-layout**: For marketing site pages (different design philosophy)
- **design-critique**: For reviewing dashboard layouts
