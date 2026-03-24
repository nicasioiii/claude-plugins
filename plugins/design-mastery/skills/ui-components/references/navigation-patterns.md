# Navigation Patterns — Desktop and Mobile

## Desktop Horizontal Navigation

### Standard Web Header Structure

```
┌──────────────────────────────────────────────────────┐
│ [Logo]  Menu1  Menu2  Menu3  Menu4     [CTA Button]  │
│ 32px    40px   40px   40px   40px        56px        │
└──────────────────────────────────────────────────────┘
  ↑ 64px header height
```

**Component Sizing:**

| Element | Size | Notes |
|---------|------|-------|
| **Header height** | 64-80px | 64px is modern standard |
| **Logo** | 32-40px | Height, width varies by logo shape |
| **Logo container** | 40×40px | Padding around logo |
| **Menu item text** | 14-16px | Semi-bold weight |
| **Menu item padding** | 16px H, 8px V | Creates 40px clickable area |
| **Gap between items** | 20-32px | Depends on spacing system |
| **CTA button** | 48px height | Full nav spacing |

**Container Specification:**
```
Max-width: 1440px
Padding: 0 64px (or 0 40px smaller screens)
Display: Flex, items-center, justify-space-between
```

**Logo Area:**
```
┌──────────┐
│  [Logo]  │  Container padding: 8px
│  40×40   │  Logo actual: 32×32 (inside container)
└──────────┘
```

**Menu Items (Flex Layout):**
```
Menu Item 1 [.....] Menu Item 2 [.....] Menu Item 3
   16px H padding   20px gap between items
```

**Alignment:**
- Logo: Left-aligned
- Menu items: Center (flex, justify-center)
- CTA button: Right-aligned (flex, ml-auto)

### Navigation States

**Default State:**
```
Text color: Dark gray or primary color
Font weight: 600 (semi-bold)
Background: White or transparent
Underline: None
```

**Hover State:**
```
Text underline: 2px solid brand color
Duration: 200ms ease-out
Alternative: Add background color (5% gray)
```

**Active State (Current Page):**
```
Text color: Brand primary (slightly darker)
Underline: 3px solid brand color
Persistence: Stays until user navigates away
```

**Focus State (Keyboard Navigation):**
```
Outline: 3px solid brand color
Offset: 2-3px
Visible: Must be clear for accessibility
```

### Dropdown Menu (Submenu)

**Trigger:**
```
Menu Item (with ▼)
    on hover/click → Opens submenu
```

**Submenu Structure:**
```
┌─────────────────────┐
│ [Main Menu Item ▼]  │
├─────────────────────┤
│ Sub Item 1          │  40px height each
│ Sub Item 2          │
│ Sub Item 3          │
│ Sub Item 4          │
└─────────────────────┘
```

**Positioning:**
- Display: Position absolute, below parent
- Left alignment: Align with parent menu item
- Width: 200-250px minimum
- Top spacing: 8px gap from parent

**Submenu Item Styling:**
```
Height: 40px
Padding: 12px horizontal, 8px vertical
Font: 14px, regular weight
Background hover: 5% gray (#FAFAFA)
Border: None (full-width background fill on hover)
```

**Icon in Submenu:**
```
[Icon] Text (Icon 16px, left-aligned)
Gap: 12px between icon and text
```

**Nested Submenu (3 Levels):**
```
Main Menu
├─ Sub Item 1 (hover)
│  ├─ Sub-sub Item 1
│  ├─ Sub-sub Item 2
│  └─ Sub-sub Item 3
├─ Sub Item 2
└─ Sub Item 3
```

Positioning: Nested submenu opens to the right (position: absolute, left: 100%, top: 0)

**Animation:**
```
Entrance: Fade-in (200ms) + slight scale (0.95 → 1.0)
Exit: Fade-out (100ms, faster exit)
Easing: ease-out
```

### Sticky Navigation

**Behavior on Scroll:**

1. **Default (Top of Page):**
   - Normal nav height (64px)
   - Full padding and spacing
   - All elements visible

2. **On Scroll Down:**
   ```
   Background: Add white background (if transparent)
   Shadow: Add subtle drop shadow (0 2px 8px rgba(0,0,0,0.08))
   Height: Reduce to 56px (optional)
   Animation: Smooth transition (300ms)
   ```

3. **On Scroll Back Up:**
   - Revert to original state

**Implementation:**
- Use `position: sticky` (CSS) or `position: fixed` with scroll tracking
- Add shadow only when scrolled (JS detection or ::after pseudo-element)
- Maintain focus management (don't trap focus on sticky element)

---

## Mobile Navigation (Hamburger Menu)

### Hamburger Menu Icon

**Closed State:**
```
☰ (Three horizontal lines)
Width: 24px
Height: 24px
Stroke width: 2px
Color: Match nav text color
```

**Spacing Between Lines:**
```
Line 1
[4px gap]
Line 2
[4px gap]
Line 3
```

**Open State:**
```
✕ (X icon, rotated hamburger)
Same 24px size
Rotate transformation: 45° or full X icon
Duration: 200ms ease-out
```

### Mobile Menu Overlay

**Structure:**

```
┌──────────────────────┐
│ Logo      [Close X]  │ 56px header
├──────────────────────┤
│ Menu Item 1          │
│ Menu Item 2          │
│ Menu Item 3          │  Full-width items
│ Menu Item 4          │  60px height each
│ Menu Item 5          │
├──────────────────────┤
│ [CTA Button - Full]  │
└──────────────────────┘
```

**Mobile Menu Sizing:**

| Element | Size | Notes |
|---------|------|-------|
| **Header height** | 56px | Reduced from desktop 64px |
| **Menu item height** | 60px | Touch-friendly |
| **Menu item padding** | 16px H, 20px V | Generous vertical space |
| **Menu item text** | 16px | Slightly larger for mobile |
| **CTA button** | 56px height | Full-width with 16px margins |
| **Menu width** | 100% | Full screen width |

**Animations:**

1. **Menu Open (Slide from Left):**
   ```
   From: translateX(-100%)
   To: translateX(0)
   Duration: 300ms
   Easing: cubic-bezier(0.25, 0.46, 0.45, 0.94) [ease-out]
   Backdrop: Fade in from transparent to rgba(0,0,0,0.5)
   ```

2. **Menu Close (Slide to Left):**
   ```
   From: translateX(0)
   To: translateX(-100%)
   Duration: 200ms (faster close)
   Easing: ease-in
   ```

### Mobile Menu Variants

**Variant 1: Slide-from-Left (Most Common)**
```
Original page           Menu open
┌──────────────┐       ┌──────────────┐
│ Content      │       │ Menu Overlay │  Slides in from left
│              │  -->  │ [Full width] │
│              │       │              │
└──────────────┘       └──────────────┘
                       (Content dims behind)
```

**Variant 2: Bottom Drawer (Less Common)**
```
Original page           Menu open
┌──────────────┐       ┌──────────────┐
│              │       │              │
│ Content      │       │ Content      │
│              │       ├──────────────┤
└──────────────┘       │ Menu (60%)   │  Slides up from bottom
                       │ Drawer       │
                       └──────────────┘
```

**Variant 3: Hamburger + Search Icon**
```
┌────────────────────────────────┐
│ Logo          [🔍] [☰]        │  Search icon + hamburger
└────────────────────────────────┘
```

### Mobile Menu Content Hierarchy

**Standard Menu Structure:**
```
┌──────────────────────┐
│ Logo      [X]        │  Header with close button
├──────────────────────┤
│ HOME                 │  Main navigation items
│ ABOUT                │  (All caps or title case)
│ SERVICES             │
│ BLOG                 │
│ CONTACT              │
├──────────────────────┤
│ (Divider line)       │  Optional visual separator
├──────────────────────┤
│ Pricing              │  Secondary links
│ Help Center          │  (Smaller text, lighter color)
│ Terms                │
├──────────────────────┤
│ [Sign Up - Full]     │  Primary CTA button
│ [Login - Full]       │  Secondary action (if needed)
└──────────────────────┘
```

**Text Styling:**
- **Main items:** 16px, semi-bold, dark color, 60px tap target
- **Secondary items:** 14px, regular, gray color, 40px tap target
- **Divider:** 1px solid #EEEEEE, 12px margins top/bottom

### Mobile Menu Keyboard Navigation

**Requirements:**
- [ ] Tab navigates through menu items
- [ ] Escape closes menu
- [ ] Focus trap: Tab loops within menu when open
- [ ] Focus management: Return focus to hamburger after close
- [ ] No keyboard shortcuts accidentally trigger on menu item

---

## Dropdown States & Interaction Patterns

### Hover vs. Touch Behavior

**Desktop (Hover-based):**
```
User hovers over menu item
  ↓
Submenu appears immediately (no click needed)
  ↓
User moves to submenu (stays open)
  ↓
User moves away (closes automatically)
```

**Mobile (Touch/Click-based):**
```
User taps menu item with submenu
  ↓
Submenu expands (or navigates to new page)
  ↓
Submenu stays open until user taps away or selects item
  ↓
Close on selection or backdrop tap
```

**Hybrid (Modern Approach):**
```
Desktop: Hover to open, click to navigate
Mobile: Tap icon/arrow to expand, tap text to navigate
```

---

## Breadcrumb Navigation

**Structure:**
```
Home › Products › Electronics › Laptops › MacBook Pro
```

**Styling:**
- Font: 12-14px, gray color
- Separator: › or / or >
- Active item (last): Darker color or bold
- Link color: Primary color (underline on hover)
- Padding: 12px 16px

**Markup:**
```html
<nav aria-label="Breadcrumb">
  <ol>
    <li><a href="/">Home</a></li>
    <li><a href="/products">Products</a></li>
    <li><a href="/products/electronics">Electronics</a></li>
    <li aria-current="page">MacBook Pro</li>
  </ol>
</nav>
```

---

## Accessibility Checklist (Navigation)

- [ ] Keyboard navigation works (Tab through items, Enter/Space to activate)
- [ ] Focus ring visible (3px outline, high contrast)
- [ ] Dropdown items keyboard accessible
- [ ] Escape key closes dropdowns/mobile menu
- [ ] Focus management: Trap focus in mobile menu
- [ ] ARIA labels: `aria-label`, `aria-expanded` on dropdowns
- [ ] Current page indicator: `aria-current="page"`
- [ ] Mobile menu button has label and state
- [ ] Color contrast: 4.5:1 for text
- [ ] Touch targets: 48×48px minimum (mobile)

---

## Navigation Anti-Patterns

### ❌ Hidden Navigation (Too Clever)

```
❌ WRONG: Nav appears only on hover
           (Hard to discover on mobile)
```

**Fix:** Always visible or clear hamburger menu.

### ❌ Unclear Mega Menu

```
❌ WRONG: 20+ items in dropdown
           with no organization
```

**Fix:** Group items with headers, limit to 3-4 columns.

### ❌ No Mobile Navigation Plan

```
❌ WRONG: Same horizontal menu on mobile
           (Items wrap, text truncates, mess)
```

**Fix:** Design hamburger menu for mobile-first.

### ❌ Dropdown Without Indicator

```
❌ WRONG: Menu item opens submenu on hover
           but has no ▼ indicator
```

**Fix:** Always show ▼ or + icon for expandable items.

