# Data Visualization — Charts, Graphs, and Metrics

## Chart Types & Use Cases

### Line Chart (Trends Over Time)

**When to use:** Revenue trends, user growth, historical data
**Sizing:** 400×250px minimum, up to 600×350px
**Key elements:**
- X-axis: Time periods (days, months, quarters)
- Y-axis: Values (revenue, users, orders)
- Line: 2-3px width, brand primary color
- Points: Optional, 4-6px circles
- Grid: Light gray, optional
- Legend: Below chart, 12px
- Tooltip: Dark background, white text, 300ms delay

**Best practices:**
- Max 3 lines (avoid spaghetti charts)
- Different colors for multiple metrics
- Area fill under line (optional, 20% opacity)
- Hover shows exact value in tooltip

### Bar Chart (Comparison)

**When to use:** Monthly sales, category comparison, performance metrics
**Sizing:** 400×250px standard
**Key elements:**
- Bars: 40-60px width per category
- Gap: 10-20px between bars
- Color: Brand primary or category colors
- Labels: Below bars, 12px
- Y-axis: Shows scale (0-100%, $0-$10K)
- Value on hover: Tooltip with exact number

**Variations:**
- **Vertical bars:** Most common, time-based data
- **Horizontal bars:** Long category names
- **Stacked bars:** Comparing parts of a whole
- **Grouped bars:** Multiple metrics per category

### Pie/Donut Chart (Proportions)

**When to use:** Market share, budget allocation, percentage breakdown
**Sizing:** 300×300px (square container)
**Key elements:**
- Segments: Different colors (max 5-6)
- Labels: Outside pie with lines pointing to segment
- Percentage: On segment or in legend
- Center text (donut): Key metric or company name
- Tooltip: Shows percentage and absolute number

**Legend:**
- Right-aligned or below
- Color + label + percentage
- 12px font

**Best practices:**
- Limit to 5-6 segments (use "Other" for rest)
- Largest segment first (clockwise from top)
- Use accessible color palette (no red+green together for colorblind)

### Metric Sparkline (Mini Chart)

**When to use:** Quick trend in metric card
**Sizing:** 60×40px (fits in metric card)
**Types:**
- Simple line: 2px stroke
- Mini bar: 4-5 bars
- Trend arrow: ↑ green or ↓ red

**Styling:** Match dashboard color scheme, 1px strokes

## Chart Styling Standards

### Colors & Contrast

**Primary colors for charts:**
- Brand primary: #0066CC (main metric)
- Brand secondary: #FF6B35 (secondary metric)
- Neutral: #999 (background, grid)
- Status: Green #00AA00 (up), Red #CC0000 (down)

**Multiple series:**
- Use up to 3 colors per chart
- Ensure 3:1 minimum contrast
- Don't rely on color alone (use patterns if needed)

### Typography in Charts

**Title:** 16px bold, dark gray
**Axis labels:** 12px regular
**Legend:** 12px regular
**Tooltip:** 12px white on dark background
**Data labels:** 11px (on bars/segments)

### Sizing Hierarchy

**Small Widget:** 300×200px (summary, metric page)
**Medium Widget:** 400×250px (standard dashboard)
**Large Widget:** 600×300px (detailed analysis, full focus)
**Full-width:** 1200px×400px (trend analysis, featured chart)

## Metric Card Design

### Metric Card with Icon

```
┌──────────────┐
│ 📈 Revenue   │  Icon (24px) + Label (12px)
├──────────────┤
│ $124,567     │  Value (40px bold)
│ ↑ 12% WoW    │  Change (12px green)
└──────────────┘
```

**Padding:** 20px
**Card size:** 200-250px width, ~140px height
**Gap between elements:** 8-12px

### Metric with Sparkline

```
┌─────────────────┐
│ Revenue         │  Label (12px)
│ [Tiny chart]    │  Sparkline (60×40px)
│ $124,567        │  Value (36px)
│ ↑ 12%           │  Change (12px)
└─────────────────┘
```

**Chart type:** Simple line or mini bar
**Chart color:** Brand primary
**Position:** Inline right or above value

## Tooltip Design

### Tooltip for Charts

```
┌──────────────┐
│ Jan 15, 2026 │  Date/category (12px white bold)
│ Revenue: $45K│  Metric name + value (12px white)
│ Orders: 234  │  Multiple values if multi-series
└──────────────┘
```

**Styling:**
- Background: Dark (#333) or brand dark
- Text: White, 12px
- Padding: 8px 12px
- Border-radius: 4px
- Arrow: Pointing to data point
- Max-width: 150px
- Delay: 300-500ms (don't show on quick hover)
- Fade transition: 200ms

**Position:** Follow cursor or pin to data point

## Dashboard Chart Grid

### 2-Column Chart Layout

```
┌──────────────┬──────────────┐
│ Chart 1      │ Chart 2      │
│ (400×250)    │ (400×250)    │
├──────────────┼──────────────┤
│ Chart 3      │ Chart 4      │
│ (400×250)    │ (400×250)    │
└──────────────┴──────────────┘
```

**Desktop:** 2 columns, 24px gap
**Tablet:** 1 column, full-width
**Mobile:** 1 column, scrollable

### 3-Column Layout

```
┌────────┬────────┬────────┐
│Chart 1 │Chart 2 │Chart 3 │  (3 × 300×200px)
├────────┼────────┼────────┤
│Chart 4         │Chart 5 │  (1 large + 1 small)
└────────┴────────┴────────┘
```

**Desktop:** 3 columns
**Tablet:** 2 columns, wrap
**Mobile:** 1 column

### Asymmetric Layout

```
┌─────────────────┬────────┐
│ Large chart     │ Small  │
│ (600×300)       │ metric │
│                 │ cards  │
├─────────────────┼────────┤
│ Table           │        │
│ (Full width)    │        │
└─────────────────┴────────┘
```

**Use case:** Feature prominent trend, support with metrics

## Empty Chart States

### No Data

```
┌─────────────────┐
│                 │
│   No data yet   │
│                 │
│ [Generate data] │
│                 │
└─────────────────┘
```

### Loading State

```
┌─────────────────┐
│                 │
│  [spinner]      │
│  Loading...     │
│                 │
└─────────────────┘
```

### Error Loading

```
┌─────────────────┐
│                 │
│  ⚠️ Error       │
│                 │
│ [Retry]         │
│                 │
└─────────────────┘
```

## Chart Interaction Patterns

### Hover Interactions

- **Point hover:** Highlight point, show tooltip
- **Bar hover:** Highlight bar, darken color 10%
- **Line hover:** Thicken line slightly, show tooltip
- **Pie segment hover:** Scale up 1.05x, show tooltip

### Click Interactions

- **Bar click:** May drill down to detail page
- **Legend item click:** Show/hide that series
- **Pie segment click:** Show detailed breakdown

### Responsive Chart Behavior

**Desktop:**
- Full interactive tooltips
- Hover effects
- Click drill-downs

**Tablet:**
- Touch-friendly tooltips (tap to show)
- Simplified hover (may not show)
- Click available

**Mobile:**
- Tap to show/hide data
- Simplified chart (fewer data points)
- Vertical scrolling for tall charts

## Chart Library Recommendations

**Popular:** Chart.js, D3.js, Recharts, Apache ECharts
**Design:** Figma plugins (Charts, Miro, etc.) for static mockups

**Key features to look for:**
- Responsive sizing
- Tooltip customization
- Color/styling options
- Export to PNG/SVG
- Accessibility (ARIA labels, keyboard nav)

