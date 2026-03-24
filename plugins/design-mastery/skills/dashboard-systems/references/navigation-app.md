# App Navigation — Sidebar, Top Bar, Bottom Tabs, and Mobile Patterns

## Sidebar Navigation (Desktop & Tablet)

### Expanded Sidebar (250-280px)

**Structure:**
```
┌────────────────────────┐
│ [Logo] App Name        │  Logo area (40px)
├────────────────────────┤
│ Dashboard              │  Primary nav items
│  Home                  │  (Nested: indented)
│  Analytics             │
│ Tools                  │
│  Settings              │
│  Users                 │
├────────────────────────┤
│ Help & Support         │  Secondary nav
│  Docs                  │
│  Contact               │
└────────────────────────┘
```

**Sizing:**
- Width: 250-280px
- Logo height: 40-48px
- Logo padding: 16px
- Nav item height: 44px
- Icon: 20-24px
- Text: 14px
- Padding: 12px V, 16px H
- Gap between sections: 24px

**Styling:**
- Background: Dark (#2D2D2D or brand dark)
- Text: White (#FFF)
- Hover: 20% white overlay
- Active: Brand primary background or left border (3px)
- Nested indent: 20px additional left padding

**Sticky Behavior:**
```css
position: sticky;
top: 0;
height: 100vh;
overflow-y: auto;
```

### Collapsed Sidebar (64px)

**When collapsed:**
- Logo: Icon only or initials
- Nav items: Icons only (20px, centered)
- Tooltip on hover: "Dashboard", "Settings"
- Width transition: 250px ↔ 64px (200ms ease-out)

**Toggle button:**
- Icon: Chevron left/right (16px)
- Position: Bottom of sidebar or top
- Hover: Highlight background

**Responsive:**
- Desktop: User can collapse/expand manually
- Tablet: Collapses automatically when switching to smaller breakpoint
- Mobile: Hamburger menu (full slide-out panel)

## Top Header

### Standard Header Layout

```
┌─────────────────────────────────────────┐
│ ☰ [Search] [Breadcrumb] [!] [@] [⋮]   │
└─────────────────────────────────────────┘
```

**Height:** 56-64px
**Spacing:** 16px padding left/right

**Components:**

1. **Hamburger (Mobile):** 24px icon, 12px padding
2. **Search:** 200-300px input or search icon
3. **Breadcrumb (Optional):** "Dashboard > Reports > Q1" (12px gray)
4. **Notification Bell:** 24px, red badge with count
5. **User Avatar:** 32×32px circle
6. **Menu Icon:** Vertical three-dot menu (⋮)

### Search Bar in Header

**Desktop:**
```
[🔍 Search dashboards...]
Width: 250px
Height: 40px
Position: Center or left (depends on design)
```

**Mobile:**
```
[🔍]  (Icon only, expands on tap)
```

**Results Dropdown:**
- Max-height: 300px (scrollable)
- Results grouped: "Dashboards", "Reports", "Users"
- Result height: 44px each
- Hover: Light background

## Bottom Tab Navigation (Mobile)

### iOS-Style Bottom Navigation

```
┌────────────────────┐
│ App content        │
├────────────────────┤
│ 🏠 📊 🔔 👤 [⋮]   │  Tab bar (56px height)
└────────────────────┘
```

**Sizing:**
- Height: 56px (safe area above for notched phones)
- Icons: 24px
- Labels: Optional, 10px below icon (if included)
- Gap: Equal width distribution (5 tabs max)

**Tab Structure:**
- Icon (24px, centered)
- Label (optional, 10px gray)
- Tap target: Full tab width (78px for 5 tabs on 390px)

**Common Tabs (Order):**
1. Home/Dashboard (house icon)
2. Analytics/Reports (chart icon)
3. Notifications (bell icon)
4. Profile/Account (person icon)
5. More/Menu (three-dot icon)

**Active Tab:**
- Icon: Brand primary color
- Background: Subtle highlight (2-3% darker)
- Label: Bold if present

**Inactive Tab:**
- Icon: Gray (#666)
- Background: White

### SafeArea Consideration (iPhone X+)

**Without adjustment:**
```
Bottom tab bar at 56px
But notch/home indicator at bottom
Content gets hidden
```

**Solution:**
```
Add bottom padding-bottom: 16px (safe area)
Total height: 56 + 16 = 72px
Content: Has proper breathing room
```

## Hamburger Menu (Mobile)

### Icon States

**Closed:**
```
☰  (Three horizontal lines)
24×24px
Color: Match header text color
```

**Open:**
```
✕  (X icon, rotated hamburger)
Same 24×24px
Rotation: 45° (200ms)
```

### Menu Panel

**Slide-out from left:**
```
├─ Dashboard      (Primary items)
├─ Reports        
├─ Users
├─ Settings
├─────────────────   (Divider)
├─ Docs           (Secondary items)
├─ Support
├─────────────────
├─ Logout         (Danger action)
```

**Sizing:**
- Width: 80-90% of viewport (max 300px)
- Item height: 60px
- Text: 16px
- Icon: 24px left-aligned
- Padding: 16px
- Background: White

**Animation:**
- Entrance: slideX(-100%) → slideX(0) (300ms)
- Exit: slideX(0) → slideX(-100%) (200ms)
- Backdrop: Fade 0 → 0.5 opacity (300ms)

**Close on:**
- Clicking backdrop (optional)
- Selecting item
- Tapping X/close button
- Pressing Escape key

## Breadcrumb Navigation

**Appearance:**
```
Home › Products › Edit Product › Inventory
```

**Styling:**
- Font: 12px gray
- Separator: › or >
- Gap: 4px around separator
- Active (last): Bold or darker color

**Interaction:**
- Clickable: Navigate to parent level
- Last item: Not clickable (current page)
- Hover: Underline on clickable items

**Responsive:**
- Desktop: Full breadcrumb visible
- Mobile: First + last item only ("Home › Inventory")
- Or hide entirely and show in title

## Notification Bell & Dropdown

### Bell Icon

```
🔔
```

- Size: 24px
- Color: Gray until notifications exist
- Badge: Red circle, right-top corner (48px from left)
- Badge content: "5" (white text, 10px font)

### Notification Dropdown

**On click:**
```
┌──────────────────────────┐
│ Notifications            │  Header (14px bold)
├──────────────────────────┤
│ You have 3 new messages  │  Item (12px)
│ 5 min ago                │  Time (10px gray)
├──────────────────────────┤
│ Payment received         │
│ 1 hour ago               │
├──────────────────────────┤
│ [View All Notifications] │
└──────────────────────────┘
```

**Position:** Below bell, right-aligned with right edge
**Width:** 300-350px
**Max-height:** 400px (scrollable)
**Background:** White with 1px border
**Shadow:** 0 4px 12px rgba(0,0,0,0.15)

## User Profile Menu

**On Avatar Click:**
```
┌───────────────────────┐
│ Sarah Chen            │  Name (14px bold)
│ sarah@company.com     │  Email (12px gray)
├───────────────────────┤
│ My Profile            │  Menu items
│ Settings              │  (12px, 40px height)
│ Preferences           │
│ Help & Feedback       │
├───────────────────────┤
│ Sign Out              │  Danger action (red)
└───────────────────────┘
```

**Sizing:**
- Width: 200-240px
- Item height: 40px
- Padding: 12px 16px
- Background: White
- Border: 1px #E0E0E0
- Shadow: 0 4px 12px

**Interaction:**
- Click item: Navigate or perform action
- Click outside: Close menu
- Escape key: Close menu

## Responsive Navigation Changes

### Desktop (1440px)
- Sidebar: Visible, expandable (250px or 64px)
- Header: Full search, breadcrumb, notifications
- Bottom nav: None

### Tablet (800px)
- Sidebar: Collapsed by default (64px icons)
- Or: Hamburger menu (full slide panel)
- Header: Simplified (search icon, notifications)
- Bottom nav: Optional (if space allows)

### Mobile (390px)
- Sidebar: Hamburger menu only
- Header: Icon-only search, notifications
- Bottom nav: Tab-based navigation
- Breadcrumb: Hidden or simplified

## Mobile App Navigation Patterns

### Pattern 1: Hamburger + Bottom Tabs (Most Common)

```
┌─────────────────────┐
│ ☰ [App Name] [⋮]   │  Header
├─────────────────────┤
│ App content         │
│                     │
├─────────────────────┤
│ 🏠 📊 🔔 👤 [⋮]    │  Bottom tabs
└─────────────────────┘
```

**Use case:** iOS-style navigation, modern mobile apps
**Pro:** Bottom tabs are easy to reach (thumb)
**Con:** Takes screen space

### Pattern 2: Hamburger + Top Header (Android-style)

```
┌─────────────────────┐
│ ☰ Title       [⋮]  │  Top header
├─────────────────────┤
│ App content         │
│ (scrollable)        │
│                     │
└─────────────────────┘
```

**Use case:** Android native style
**Pro:** More content space
**Con:** Top menu harder to reach

### Pattern 3: Tab Navigation Only (iPad)

```
┌─────────────────────┐
│ Dashboard │Reports  │  Tab bar (40px height)
│ Users     │Settings │
├─────────────────────┤
│ Tab content         │
│                     │
└─────────────────────┘
```

**Use case:** Tablet or iPad
**Pro:** Clear content area, no hidden nav
**Con:** Only works with few tabs (3-4 max)

