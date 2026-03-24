# Metric Cards & Data Visualization

## Metric Cards (KPI Display)

### Basic Metric Card

```
┌──────────────────┐
│ Total Revenue    │  Label (12px gray)
│ $124,567         │  Value (32-40px, bold)
│ ↑ 12% from last  │  Change (12px, green)
│   month          │
└──────────────────┘
```

**Sizing:**
- **Card:** 200-250px wide, ~140px tall
- **Padding:** 20px
- **Label:** 12px gray, regular weight
- **Value:** 32-40px, bold, dark color
- **Change:** 12px, color-coded (green=up, red=down)
- **Icon:** Small arrow (↑↓) or percentage

**Grid Layout:**
```
Desktop: 4 cards per row (3-column width each in 12-col)
Tablet:  2 cards per row
Mobile:  1 card per row
```

**Cards Spacing:** 24px gap between cards, 20px padding within

### Advanced Metric Card (With Chart)

```
┌───────────────────┐
│ Monthly Revenue   │  Header: Label
│ [Small chart/bar] │  12x12px mini chart
├───────────────────┤
│ $124,567          │  Value display
│ ↑ 12%             │  Change indicator
└───────────────────┘
```

**Mini Chart Options:**
- Sparkline (tiny line chart)
- Mini bar chart (3-4 bars)
- Donut percentage
- Trend arrow

**Chart Sizing:** 60×40px maximum

### Card States

**Default:** White background, 1px border
**Hover:** Subtle shadow, light background
**Selected:** Border highlight (2px primary color)

## Data Visualization (Charts & Graphs)

### Chart Types & When to Use

| Chart | Use Case | Sizing |
|-------|----------|--------|
| **Line chart** | Trends over time | 400×200px minimum |
| **Bar chart** | Comparison, categories | 400×200px |
| **Pie/Donut** | Proportions, percentages | 300×300px |
| **Area chart** | Volume trends | 400×200px |
| **Scatter plot** | Correlation, outliers | 400×300px |

### Chart Sizing in Dashboards

**Small Widget:** 300×200px (summary)
**Medium Widget:** 400×250px (detailed)
**Large Widget:** 600×300px (full-width focus)
**Minimal Sparkline:** 60×40px (within metric card)

### Chart Styling

**Colors:** Use consistent color palette (brand primary, accent)
**Fonts:** 12px labels, 14px titles
**Padding:** 16px around chart content
**Legend:** Below or right-aligned, 12px text
**Gridlines:** Light gray, 1px, optional
**Tooltips:** Dark background, 12px white text, 300ms delay
