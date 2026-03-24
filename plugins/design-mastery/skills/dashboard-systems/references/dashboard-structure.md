# Dashboard Structure — Sidebar, Header, and Layout Patterns

## Standard Dashboard Layout Components

### Sidebar Navigation (Desktop)

**Expanded State (250px):**
```
┌────────────────────┐
│ [Logo] 40×40       │  10px padding top
├────────────────────┤
│ Dashboard          │  Section header: 12px gray, uppercase
│  ✓ Home            │  Active item: white text, background color
│    Reports         │  Non-active: gray text
│    Analytics       │  Icon 20px + 12px gap + text 14px
├────────────────────┤
│ Management         │
│    Users           │
│    Teams           │
│    Settings        │
├────────────────────┤
│ Help               │
│    Documentation   │
│    Support         │
└────────────────────┘
```

**Sizing:**
- Width: 250px (industry standard)
- Text: 14px regular (items), 12px gray (headers)
- Icon: 20-24px
- Item height: 44px
- Padding: 16px horizontal, 12px vertical per item
- Section spacing: 24px between sections

**Styling:**
- Background: Dark gray (#2D2D2D) or dark brand color
- Text: White (#FFF)
- Item hover: 20% white background overlay
- Item active: Brand primary color or highlight
- Optional: Left border 3px on active item

**Nested Items:**
- Indent: 20px additional left padding
- Font: Slightly smaller (13px)
- Appear on hover or always visible (depends on design)

**Collapsible Sidebar (64px):**
When collapsed:
- Only icons visible (20px, centered)
- Tooltip on hover: "Dashboard", "Reports", etc.
- Transition width: 250px ↔ 64px (200ms)
- Icons stay aligned

**Sticky Sidebar:**
```css
position: sticky;
top: 0;
height: 100vh;
overflow-y: auto;
```

### Top Header (56-64px)

**Layout:**
```
┌─────────────────────────────────────┐
│ Hamburger  [Search]  [!] [@] [⋮]   │
│ (mobile)   (200px)   (Bell) (Avatar) (Menu)
│            Breadcrumb (desktop)     │
└─────────────────────────────────────┘
```

**Desktop Header (640px):**
- Logo/hamburger left side
- Breadcrumb center (optional): "Dashboard > Reports > Q1"
- Search bar center (200-300px)
- Icons/profile right side

**Mobile Header (390px):**
- Hamburger icon (24px)
- Breadcrumb removed (too cramped)
- Search icon only (not full bar)
- Avatar/menu right

**Components Breakdown:**

1. **Hamburger Menu (Mobile Only)**
   - Icon: 24px
   - Padding: 12px
   - Click triggers sidebar slide-out

2. **Search Bar (Desktop)**
   - Width: 200-300px
   - Height: 40px
   - Placeholder: "Search..."
   - Results dropdown on focus

3. **Breadcrumb (Optional, Desktop)**
   - Font: 12px gray
   - Separator: /
   - Last item: Active (bold)
   - Clickable: Navigate to parent pages

4. **Notifications/Bell**
   - Icon: 24px
   - Badge: Red circle with count "5"
   - Click: Open notification panel/dropdown

5. **User Avatar/Menu**
   - Avatar: 32×32px circle
   - Initials or profile photo
   - Click: Open profile menu (Account, Settings, Logout)

---

## Header Dropdown Menu (Profile/User Menu)

**On Avatar Click:**
```
┌──────────────────┐
│ Sarah Chen       │  Name (14px bold)
│ sarah@email.com  │  Email (12px gray)
├──────────────────┤
│ My Profile       │  Menu items (12px)
│ Settings         │  Hover: Light background
│ Preferences      │  Height: 40px each
│ Help             │
├──────────────────┤
│ Logout           │  Danger action (red text)
└──────────────────┘
```

**Positioning:**
- Absolute, top: 100%, right: 0
- Width: 200-240px
- Background: White
- Border: 1px #E0E0E0
- Shadow: 0 4px 12px rgba(0,0,0,0.15)
- Z-index: 100 (above content)

**Item Styling:**
- Height: 40px
- Padding: 12px 16px
- Font: 12-14px
- Hover: #F5F5F5 background

---

## Main Content Area Layout

### Metric Cards Grid

**Desktop (1440px):**
```
[Card 1] [Card 2] [Card 3] [Card 4]
[Card 5] [Card 6] [Card 7] [Card 8]
```
- 4 cards per row
- Each card: ~280px width
- Gap: 24px
- Total: 1312px max-width

**Tablet (800px):**
```
[Card 1] [Card 2]
[Card 3] [Card 4]
```
- 2 cards per row
- Each card: ~320px width
- Gap: 20px

**Mobile (390px):**
```
[Card 1]
[Card 2]
[Card 3]
```
- 1 card per row
- Full-width minus margins (16px each side)
- Gap: 16px vertical

### Metric Card Design

**Structure:**
```
┌─────────────────┐
│ Revenue         │  Label: 12px gray
│ $45,230         │  Value: 32px bold
│ ↑ 12.5% WoW     │  Change: 12px green (up)
└─────────────────┘
```

**Padding:** 20px all sides
**Border:** 1px light gray or no border
**Shadow:** Subtle (0 1px 3px rgba(0,0,0,0.08))
**Corner radius:** 4-8px

**Hover State:**
- Shadow increase (0 4px 12px)
- Background lighten (1% darker)
- Slight scale (1.02x) optional

---

## Table Layout in Dashboards

### Standard Scrollable Table

**Container:**
```
Height: 600px default (scrollable)
Sticky header (stays visible on scroll)
Border: 1px top and bottom
Background: White
```

**Header Row:**
- Height: 48px
- Background: #F5F5F5 or light gray
- Font: 12px semi-bold
- Padding: 12px 16px
- Sticky: position sticky, top 0, z-index 10

**Data Rows:**
- Height: 48px
- Font: 14px regular
- Padding: 12px 16px
- Border-bottom: 1px #F0F0F0
- Hover: Light background (#FAFAFA)

**Pagination:**
```
Bottom of table (if not infinite scroll)
"Showing 1-25 of 500 items"
[← Prev] [1] [2] [3] ... [20] [Next →]
```

### Responsive Table (Mobile)

**Card View (Recommended for mobile):**
```
┌──────────────────┐
│ Name: Sarah      │
│ Email: sarah@... │
│ Status: Active   │
│ [Actions]        │
├──────────────────┤
│ Name: John       │
│ Email: john@...  │
│ Status: Inactive │
│ [Actions]        │
└──────────────────┘
```

Each row becomes a card with label-value pairs

---

## Sidebar + Main Content Split Layout

### Responsive Behavior

**Desktop (1440px):**
```
┌────────────┬──────────────────┐
│ Sidebar    │ Main content     │
│ 250px      │ 1190px           │
└────────────┴──────────────────┘
```

**Tablet (800px):**
```
┌────┬────────────────────────┐
│ SB │ Main content (700px)   │
│ 64 │                        │
└────┴────────────────────────┘
Sidebar collapses to icons only
```

**Mobile (390px):**
```
┌──────────────────────┐
│ Main content (360px) │
│ (full width)         │
│                      │
└──────────────────────┘
Sidebar: Hamburger → Slide panel
```

---

## Empty States & No-Data Design

### "No Data" Illustration

```
┌───────────────────────┐
│                       │
│      📭 No data       │  Icon: 64px, light gray
│                       │
│   No items to show    │  Message: 16px gray
│                       │
│ [Create Item]         │  CTA: Primary button
│                       │
└───────────────────────┘
```

**Styling:**
- Container: Center aligned, 200-300px wide
- Icon: Large (48-64px), light gray (#DDD)
- Text: 16px gray (#666), 200% line height
- Button: Primary CTA or secondary link
- Padding: 60px vertical, 40px horizontal

### Loading State

**Skeleton Screen:**
```
[████████] [████]          (shimmer animation)
[███████████] [██████]
[████████] [████]
(Repeated for multiple rows)
```

**Styling:**
- Placeholder: Light gray (#E6E6E6)
- Shimmer: Left-to-right gradient (1.5s animation)
- Match final layout (rows × columns)

**Alternative: Simple Spinner**
- Icon: 40px loading spinner
- Text: "Loading dashboards..." (not spinner-only)
- Color: Brand primary

### Error State

```
┌─────────────────────┐
│ ⚠️ Error loading    │
│                     │
│ Something went      │
│ wrong. Try again.   │
│                     │
│ [Retry] [Go Back]   │
└─────────────────────┘
```

**Styling:**
- Icon: Warning (orange/red, 48px)
- Message: 14px gray, clear and actionable
- Buttons: Retry (primary), Go Back (secondary)

---

## Dashboard Navigation Patterns

### Tab-Based Navigation (Alternative to Sidebar)

**Horizontal Tabs (Below Header):**
```
┌─────────────────────────────────────┐
│ [Search]  [User menu]               │  Header
├─────────────────────────────────────┤
│ Dashboard │ Reports │ Settings │    │  Tabs (40px height)
├─────────────────────────────────────┤
│ Tab content here                    │
```

**Tab Styling:**
- Height: 40px
- Font: 14px
- Border-bottom: 2px (active tab)
- Active: Brand primary color
- Inactive: Gray text
- Hover: Light background

### Breadcrumb Navigation

```
Home › Products › Edit Product › Inventory
```

**Styling:**
- Font: 12px gray
- Separator: › or >
- Spacing: 4px around separator
- Active (last): Bold or darker

**Clicking breadcrumb:** Navigate to parent page

### Subnav (Section Navigation)

**Under Main Tabs:**
```
Reports
 ├─ Sales
 ├─ Inventory  (active)
 └─ Users

Content for "Inventory" displays
```

**Subnav Styling:**
- Indent: 16px
- Font: 12px
- Active: Highlight color
- Height: 32px per item

