# Interface Density — Information Hierarchy, Whitespace, and Scanning Patterns

## Information Density Spectrum

### Low Density (Minimal, Marketing-focused)

```
┌──────────────────────────┐
│                          │
│  Revenue Dashboard       │  Lots of whitespace
│  $124,567                │  Large text
│  ↑ 12% from last month   │  Limited info
│                          │
│                          │
└──────────────────────────┘
```

**Use case:** Onboarding, dashboard home, marketing dashboards
**Whitespace:** 60-100px between elements
**Text:** 16-20px for important metrics
**Cards:** Generous padding (24px), single metric per card

### Medium Density (Balanced, Most Common)

```
┌──────────────────────────┐
│ Metric 1: $124K          │
│ Metric 2: 5,234 users    │  Some whitespace
│ Metric 3: 92.3% uptime   │  Organized grid
│                          │  Multiple metrics visible
└──────────────────────────┘
```

**Use case:** Standard SaaS dashboard, analytics
**Whitespace:** 24-40px between elements
**Cards:** 16px padding
**Grid:** 3-4 metric cards per row

### High Density (Compact, Data-heavy)

```
┌────────────────────────────┐
│ Rev:$124K Usr:5K Uptime:92%│
│ Q1:$500K Q2:$580K Q3:$650K │ Minimal whitespace
│ [Table with many rows]     │ Small text (12px)
│ [Chart with detailed data] │ Packed with info
└────────────────────────────┘
```

**Use case:** Power users, analysts, data scientists
**Whitespace:** 8-16px between elements
**Cards:** 12px padding
**Font:** 12-14px for body text
**Grid:** 4-6 items per row

## Whitespace Guidelines

### Vertical Spacing (Between Sections)

**Low density:**
```
Section A
[80px gap]
Section B
```

**Medium density:**
```
Section A
[40px gap]
Section B
```

**High density:**
```
Section A
[16px gap]
Section B
```

### Element Spacing

**Cards/items within grid:**
```
Low:    24-32px gap between cards
Medium: 16-20px gap
High:   8-12px gap
```

### Internal Padding (Inside Cards/Components)

```
Low:    24-32px padding all sides
Medium: 16-20px padding
High:   12px padding (min)
```

## Typography for Scanning

### Hierarchy Levels (Most Important First)

**Level 1 — Metric Value (What matters most)**
- Size: 32-40px
- Weight: Bold (700)
- Color: Dark gray or black
- Position: Top of card

**Level 2 — Metric Label (Context)**
- Size: 12-14px
- Weight: Regular (400)
- Color: Gray (#666)
- Position: Above or below value

**Level 3 — Change/Trend (Supporting info)**
- Size: 12px
- Weight: Regular (400)
- Color: Green (#00AA00) or red (#CC0000)
- Position: Below value

**Level 4 — Timestamp or meta (Least important)**
- Size: 11px
- Weight: Regular (400)
- Color: Light gray (#999)
- Position: Bottom

### Font Sizes for Different Densities

**Low Density:**
- Heading: 24-32px
- Body: 16-18px
- Small: 12-14px

**Medium Density:**
- Heading: 18-24px
- Body: 14-16px
- Small: 12px

**High Density:**
- Heading: 16-18px
- Body: 12-14px
- Small: 10-11px

## Scanning Patterns

### F-Pattern (Website Reading)

```
→ → → → (Eye scans across top)
↓
→ → (Scans second-level)
↓
↓ (Scans down left side)
```

**Application:**
- Put most important info top-left
- Secondary info in header
- Navigation on left sidebar
- Supporting content down left edge

### Z-Pattern (Card/List Scanning)

```
→ → → (Top-left to top-right)
  ↓
← ← (Right to left)
↓
← ← ← (Bottom-left to bottom-right)
```

**Application:**
- Label top-left
- Value top-right
- Change/status bottom-left
- Action button bottom-right

### Grid Scanning (Table/Grid)

```
Top row: Headings (most important columns first)
Column 1: Identification (name, ID)
Column 2-4: Key metrics
Last column: Actions
```

**Order important metrics left to right**
**Put actions last (right side)**
**Keep row height consistent for rhythm**

## Attention & Emphasis

### Drawing Attention (Visual Hierarchy)

**1. Size (Biggest = Most important)**
```
Large metric card = Primary KPI
Medium metric card = Secondary KPI
Small metric card = Tertiary KPI
```

**2. Color (Darkness)**
```
Dark text = More important
Gray text = Less important
Red/green = Status/alert
```

**3. Weight (Bold = More important)**
```
700 weight = Headlines
600 weight = Subheadings
400 weight = Body text
```

**4. Position (Top-left = Most important)**
```
Top-left: Primary metric
Top-right: Secondary
Bottom-left: Tertiary
Bottom-right: Least important
```

**5. Isolation (White space around element)**
```
Element surrounded by whitespace = More important
Element packed with others = Less important
```

### Contrast & Emphasis

**High contrast = Draws attention:**
```
Dark text on light background
Light text on dark background
Colored element among grays
```

**Low contrast = De-emphasizes:**
```
Gray text on white background
Disabled state (50% opacity)
Background elements
```

## Data Density Best Practices

### Rule 1: Information Scent

Every element should help users understand what's available
```
Clear labels (what is this metric?)
Visual grouping (related items together)
Consistent patterns (familiar UI patterns)
```

### Rule 2: Progressive Disclosure

Show essential info first, hide detail behind expand/click
```
Card: Shows headline metric
Expand: Shows trend details
Click: Goes to detailed report
```

### Rule 3: Batch Related Information

Group related metrics and controls together
```
Revenue section (revenue metric + chart + filters)
User section (user metric + user table)
Don't scatter revenue info across page
```

### Rule 4: Consistent Spacing System

Use limited set of spacing values
```
4px: Micro spacing (gap in form field)
8px: Small spacing (between icons)
16px: Standard spacing (between sections)
24px: Large spacing (between major sections)
40px: Extra large (section padding)
```

### Rule 5: Color Coding for Status

Use consistent color meanings
```
Green: Active, success, positive trend
Red: Error, critical, negative trend
Yellow/Orange: Warning, pending
Gray: Inactive, disabled, normal
Blue: Information, interactive
```

## Dense Dashboard Anti-Patterns

### ❌ Too Much Info Without Hierarchy

```
All metrics same size
No visual emphasis
Can't tell what's important
```

**Fix:** Use size, color, weight to emphasize primary metrics.

### ❌ Inconsistent Spacing

```
8px gap here, 40px gap there
Scattered cards
No rhythm
```

**Fix:** Define spacing scale (8, 16, 24, 40px) and use consistently.

### ❌ Tiny Font (Too Compressed)

```
10px body text
11px even for tables
Hard to read
```

**Fix:** Minimum 12px for body, 14px for tables.

### ❌ No Visual Grouping

```
Random cards scattered
No clear sections
Looks chaotic
```

**Fix:** Use consistent gaps and card styling to group related items.

### ❌ Too Many Colors

```
10+ different colors
Rainbow dashboard
Confusing, no meaning
```

**Fix:** Limit to 5-6 colors (brand primary, secondary, neutral, status colors).

## Responsive Density Changes

### Desktop (1440px)

**Medium density optimal:**
- 3-4 metric cards per row
- 16-20px padding inside cards
- 16px gaps between cards
- 14px body text
- Full tables with all columns

### Tablet (800px)

**Shifts toward medium-high:**
- 2 metric cards per row
- 16px padding
- 14px body text
- Tables: Hide less important columns

### Mobile (390px)

**Shifts toward high density:**
- 1 metric card per row
- 12px padding
- 12px body text (minimum)
- Tables: Card view (label + value pairs)
- Prioritize most important metrics

## Metric Card Density Example

**Low Density Card:**
```
┌────────────────────────┐
│                        │
│  Revenue               │  32px label
│                        │
│  $124,567              │  40px value (bold)
│                        │
│  ↑ 12% from last month │  12px change text
│                        │
│  Updated 2 hours ago   │  11px timestamp
│                        │
└────────────────────────┘
Padding: 24px, Height: ~160px, Width: 250px
```

**Medium Density Card:**
```
┌─────────────────┐
│ Revenue         │  12px label
│ $124,567        │  36px value
│ ↑ 12%           │  12px change
│ 2h ago          │  10px timestamp
└─────────────────┘
Padding: 16px, Height: ~120px, Width: 200px
```

**High Density Card:**
```
┌─────────────────┐
│Rev:$124K ↑12%   │  All info inline
│(2h ago)         │  12px text
└─────────────────┘
Padding: 12px, Height: ~60px, Width: 150px
```

