# Data Display Patterns — Tables, Charts, Metrics — Quick Reference

## METRIC CARD PATTERNS

### Pattern 1: Simple Metric
```
┌──────────────────────────┐
│ Total Revenue            │
│ $145,230                 │
│ ▲ 12.5% vs last month   │
└──────────────────────────┘
```
- Best for: headline KPIs at top of dashboard
- Card count: 3-4 across in a row

### Pattern 2: Metric + Sparkline
```
┌──────────────────────────┐
│ Active Users       3,842 │
│ ▲ 8.3%                   │
│ ───────────────────      │
│ [sparkline chart]        │
└──────────────────────────┘
```
- Best for: trend-aware metrics
- Sparkline height: 32-48px, no axes or labels needed

### Pattern 3: Metric + Progress
```
┌──────────────────────────┐
│ Storage Used             │
│ 67.2 GB / 100 GB        │
│ ████████████░░░░░ 67%   │
└──────────────────────────┘
```
- Best for: quota/capacity metrics
- Progress bar height: 6-8px, rounded

### Pattern 4: Metric + Comparison
```
┌──────────────────────────┐
│ Conversion Rate          │
│ 3.24%                    │
│ Target: 4.00%            │
│ ██████████░░░░ 81%       │
└──────────────────────────┘
```
- Best for: goal-tracking metrics

### Metric Value Formatting
| Type | Format | Example |
|------|--------|---------|
| Currency | $ + comma separated | $1,234,567 |
| Large numbers | Abbreviated | 1.2M, 845K |
| Percentages | 1-2 decimal places | 3.24%, 12.5% |
| Counts | Comma separated | 3,842 |
| Time | Human-readable | 2h 34m, 45 days |
| Rates | Per-unit suffix | 99.9% uptime |

---

## DATA TABLE PATTERNS

### Standard Data Table
```
┌────────────────────────────────────────────────────────────┐
│ Customers                            [Search] [+ Add New] │
├────────────────────────────────────────────────────────────┤
│ [Filters: Status ▼] [Date Range ▼] [Segment ▼]           │
├──────┬──────────────┬──────────┬──────────┬───────┬───────┤
│  □   │ Name ▲       │ Status   │ Revenue  │ Date  │       │
├──────┼──────────────┼──────────┼──────────┼───────┼───────┤
│  □   │ Acme Corp    │ ● Active │   $4,200 │ Mar 1 │  ···  │
│  □   │ Beta Inc     │ ○ Trial  │     $800 │ Feb 8 │  ···  │
│  □   │ Gamma LLC    │ ● Active │  $12,400 │ Jan 5 │  ···  │
│  ☑   │ Delta Co     │ ✕ Churned│   $2,100 │ Dec 1 │  ···  │
├──────┴──────────────┴──────────┴──────────┴───────┴───────┤
│ 1 selected  [Archive] [Export]    Showing 1-10 of 247  →  │
└────────────────────────────────────────────────────────────┘
```

### Table Header Actions
| Position | Actions |
|----------|---------|
| Top-left | Page title, record count |
| Top-right | Search, filter toggles, export, create new |
| Below header | Active filter chips (removable) |
| Table footer | Pagination, bulk action bar (when rows selected) |

### Column Types & Alignment
| Column Content | Alignment | Width |
|---------------|-----------|-------|
| Text (name, title) | Left | Auto or min 120px |
| Number/currency | Right | 80-120px |
| Status badge | Left or center | 80-120px |
| Date | Left | 100-120px |
| Checkbox | Center | 40-48px |
| Action menu | Right | 48px |
| Avatar + name | Left | 180-240px |
| Email | Left | 180-240px |
| Progress bar | Left | 120-160px |

### Row Action Patterns
| Pattern | When to Use |
|---------|-------------|
| Hover-reveal icons | Desktop, few actions (edit, delete) |
| Three-dot menu (···) | Any device, many actions |
| Row click navigates | Detail view exists |
| Inline actions | Quick toggles (enable/disable) |
| Bulk action bar | Multi-select operations |

### Empty State
```
┌──────────────────────────────────────┐
│                                      │
│        [Illustration/Icon]           │
│                                      │
│      No customers yet                │
│                                      │
│  Start by adding your first          │
│  customer to get started.            │
│                                      │
│     [+ Add Customer]                 │
│                                      │
└──────────────────────────────────────┘
```
- Centered in table area
- Helpful message (not just "No data")
- Clear CTA for creating first record
- Optional illustration (keep small and relevant)

### Loading State
- Skeleton rows: 5-8 gray animated shimmer bars
- Match approximate column widths
- Header remains static and visible
- Alternative: spinner overlay on existing data

---

## CHART DESIGN PATTERNS

### Line Chart (Time Series)
```
Revenue Over Time
$50K ┤
     │          ╱──╲
$40K ┤    ╱────╱    ╲──
     │   ╱
$30K ┤──╱
     │
$20K ┤
     ├────┬────┬────┬────┬────
     Jan  Feb  Mar  Apr  May
```

**Specs:**
- Y-axis: left, labeled with unit ($ or %)
- X-axis: bottom, time labels
- Grid lines: horizontal only, subtle gray (gray-100)
- Line width: 2px
- Data points: 4-6px circles on hover
- Tooltip: show exact value on hover
- Legend: below chart if multiple series

### Bar Chart (Category Comparison)
```
Sales by Product

Product A  ████████████████  $45K
Product B  ██████████████    $38K
Product C  ██████████        $28K
Product D  ████████          $22K
Product E  ██████            $16K
```

**Specs:**
- Horizontal bars: better for labels and ranking
- Vertical bars: better for time comparison
- Bar gap: 40-50% of bar width
- Sort: highest to lowest (or alphabetical if no ranking)
- Color: single color for one series, multiple colors for categories
- Value labels: inline at bar end or on hover tooltip

### Donut Chart (Composition)
```
    ╭──────╮
   │ ████  │  ● Traffic: 45%
   │ ████  │  ● Referral: 30%
   │ ░░░░  │  ● Direct: 15%
   │ ▓▓▓▓  │  ● Email: 10%
    ╰──────╯
   Total: 12,450
```

**Specs:**
- Center: total value or primary metric
- Max segments: 5-6 (combine smaller into "Other")
- Legend: right side or below
- Hover: segment expands slightly, tooltip shows value
- Don't use pie chart -- donut is always better (center adds utility)

### Chart Color Palette
Use a sequential palette for data series:
```
Series 1:  #2563EB (blue-600)
Series 2:  #7C3AED (violet-600)
Series 3:  #059669 (emerald-600)
Series 4:  #D97706 (amber-600)
Series 5:  #DC2626 (red-600)
Series 6:  #0891B2 (cyan-600)
```
- Ensure sufficient contrast between adjacent series
- Use semantic colors for semantic data: green=positive, red=negative
- Avoid relying on color alone -- add patterns or labels for accessibility

---

## SIDEBAR NAVIGATION SPECS

### Expanded State (240-280px)
```
┌────────────────────────┐
│ [Logo]          [<<]   │  ← Collapse button
│                        │
│ 🏠 Dashboard           │  ← Active: left border + bg
│ 📊 Analytics           │
│ 👥 Customers           │
│ 📦 Products            │
│ 💰 Billing             │
│                        │
│ ──────────────────     │  ← Section divider
│                        │
│ ⚙️ Settings            │
│ ❓ Help                │
│ 👤 John D.      [▼]   │  ← User menu
└────────────────────────┘
```

### Collapsed State (64-72px)
```
┌──────┐
│ [≡]  │  ← Hamburger to expand
│      │
│ 🏠   │  ← Icon only + tooltip on hover
│ 📊   │
│ 👥   │
│ 📦   │
│ 💰   │
│      │
│ ───  │
│      │
│ ⚙️   │
│ ❓   │
│ [•]  │  ← Avatar circle
└──────┘
```

### Sidebar Item Specs
| Property | Expanded | Collapsed |
|----------|----------|-----------|
| Height | 40-44px | 40-44px |
| Icon size | 20px | 20px |
| Icon-to-label gap | 12px | -- |
| H-padding | 12-16px | center-aligned |
| Font | 14px, regular | -- (icon only) |
| Active bg | Primary/50 or gray-100 | Same |
| Active border | 3px left, primary color | 3px left |
| Hover bg | gray-50 | gray-50 |
| Tooltip | -- | Show on hover (200ms delay) |

### Sub-Navigation (Nested Items)
```
│ 📦 Products        [▼] │
│    All Products         │  ← Indented 24px from icon
│    Categories           │
│    Inventory            │
│    Import/Export        │
```
- Indent sub-items 24px from parent icon position
- Chevron indicates expandable
- Collapse sub-items when parent is not active (optional)

---

## NOTIFICATION & ALERT PATTERNS

### Notification Bell
- Position: top-right utility bar
- Badge: red circle with count (8-16px, centered on bell)
- Badge count: "9+" for double digits
- Click: dropdown list of recent notifications
- Dropdown width: 320-400px
- Notification item: avatar + text + time + unread indicator

### In-Page Alerts
| Type | Color | Icon | Dismissible |
|------|-------|------|------------|
| Info | Blue background (#EFF6FF) | ℹ️ | Yes |
| Success | Green background (#ECFDF5) | ✓ | Yes |
| Warning | Yellow background (#FFFBEB) | ⚠️ | Optional |
| Error | Red background (#FEF2F2) | ✕ | No (until resolved) |

### Alert Anatomy
```
┌─────────────────────────────────────────────────┐
│ [icon]  Alert title (optional)            [X]   │
│         Alert description text that explains     │
│         what happened and what to do next.       │
│         [Action Link]                            │
└─────────────────────────────────────────────────┘
```
- Full-width within content area
- 12-16px padding all sides
- Border-left: 4px in alert color (optional accent)
- Border-radius: 8px
