---
name: Component Pattern
description: "Show the best design pattern for a specific UI component with variations, states, and best practices."
---

# Component Pattern

Get the best design patterns for any UI component. This provides variations, sizing guidelines, state patterns, and when to use each variant.

---

## What This Command Does

You tell me which component you want to design, and I'll provide:
- Multiple design variations (primary, secondary, outline, etc.)
- Sizing guidelines (small, medium, large)
- State patterns (default, hover, active, disabled, loading, error)
- Color combinations and contrast checks
- Spacing and alignment recommendations
- Best practices and common mistakes
- When to use each variant
- Real-world examples

**Time to answer:** 1 minute
**Time to receive patterns:** 5-10 minutes

---

## Scoping Question

**Which component do you want patterns for?**

Choose one:

### Common Components
- **Button** (primary, secondary, tertiary, icon, text, loading)
- **Card** (image card, feature card, testimonial card, metric card)
- **Navigation** (desktop nav, mobile hamburger, dropdown menu, breadcrumbs)
- **Form Input** (text input, select, checkbox, radio, switch, toggle)
- **Modal** (modal dialog, alert dialog, popover, sheet, toast notification)
- **Table** (data table, sortable table, expandable rows)
- **Badge** (status badge, label badge, number badge)
- **Pagination** (numbered pagination, next/prev, scroll pagination)
- **Tooltip** (hover tooltip, icon tooltip, info popover)
- **Icon** (icon button, icon with text, icon grid)

Or describe another component if not listed above.

---

## Pattern Library: By Component Type

Once you choose, I'll provide:

### 1. BUTTON PATTERNS

**Variants:**
- Primary Button (highest emphasis, main action)
- Secondary Button (medium emphasis, alternative action)
- Tertiary Button (low emphasis, tertiary action)
- Danger Button (destructive action)
- Icon Button (icon-only)
- Text Button (minimal style)

**Sizing:**
```
Small:     32px height, 12px padding sides, 12px font
Medium:    40px height, 16px padding sides, 14px font (default)
Large:     48px height, 20px padding sides, 16px font
```

**States:**
- Default (static)
- Hover (brightens or darkens 10%)
- Active/Pressed (darkens 15%)
- Disabled (reduce opacity to 50%, remove hover)
- Loading (swap text for spinner)
- Focused (add blue border for keyboard users)

**Best Practices:**
✓ Minimum 44px height for touch targets
✓ Consistent padding (not stretched to fit container)
✓ Clear visual distinction between primary and secondary
✓ Disabled state obvious (not just color, but opacity)
✓ Loading state shows activity (spinner, dots)

**Mistakes to Avoid:**
❌ Primary and secondary too similar
❌ Disabled state still looks clickable
❌ Text button lacks hover feedback
❌ Buttons all different heights
❌ No loading state (users think it's broken)

---

### 2. CARD PATTERNS

**Variants:**
- Image Card (image top, content below)
- Feature Card (icon, title, description)
- Testimonial Card (quote, avatar, name)
- Metric Card (number, label, sparkline)
- Product Card (image, title, price, rating)

**Sizing:**
```
Single Column:  Full width minus padding (mobile)
2-Column:       (container - 16px gap) / 2 each
3-Column:       (container - 32px gaps) / 3 each
4-Column:       (container - 48px gaps) / 4 each
```

**Spacing Inside:**
- Padding: 16px to 24px (consistent on all sides)
- Image-to-content gap: 16px
- Element-to-element: 12px to 16px
- Border radius: 8px to 12px

**Hover States:**
- Lift with shadow (translate Y -4px, add shadow)
- Border highlight (add 2px border)
- Subtle scale (scale 1.02)
- Background color shift (add 5% darker background)

**Best Practices:**
✓ Cards same height (in a grid)
✓ Images same aspect ratio (16:9, 4:3, or 1:1)
✓ Text hierarchy clear (title > subtitle > body)
✓ Padding consistent
✓ Call-to-action visible

**Mistakes to Avoid:**
❌ Cards different heights
❌ Images different aspect ratios
❌ Too much content (text overflows)
❌ No hover feedback
❌ CTA unclear

---

### 3. NAVIGATION PATTERNS

**Desktop:**
- Horizontal top nav (full-width header)
- Sidebar nav (left column)
- Mega menu (large dropdown on hover)
- Tab navigation (horizontal tabs)

**Mobile:**
- Hamburger menu (three-line icon opens drawer)
- Bottom tab bar (5 main sections)
- Nested navigation (menu item → submenu)

**States:**
- Default (not hovered, not active)
- Hover (subtle background or underline)
- Active (bold text or highlighted background)
- Disabled (grayed out, not clickable)

**Sizing:**
```
Desktop:    40-56px header height
Mobile:     56px header, 56px bottom tabs
Text link:  14-16px font
Padding:    12-16px horizontal, 8-12px vertical
```

**Best Practices:**
✓ Main nav visible immediately
✓ Active page clearly indicated
✓ Hover states obvious
✓ Mobile nav accessible (hamburger easy to tap)
✓ All links understandable (not cryptic)

**Mistakes to Avoid:**
❌ Nav hides on scroll (hard to navigate)
❌ Active state unclear
❌ No hover feedback
❌ Hamburger menu hard to find
❌ Too many items in nav (10+)

---

### 4. FORM INPUT PATTERNS

**Input Types:**
- Text Input (email, password, search, etc.)
- Select Dropdown (single choice)
- Multi-Select (multiple choices)
- Checkbox (yes/no, multiple selections)
- Radio Button (single selection from group)
- Toggle/Switch (on/off)
- Textarea (long text)
- Date Picker (calendar selection)

**States:**
- Default (empty)
- Filled (user has entered value)
- Focused (blue border, 2px stroke)
- Placeholder (light gray text, disappears on focus)
- Hover (subtle background color shift)
- Disabled (grayed out, cursor not-allowed)
- Error (red border, error message below)
- Success (green checkmark, optional)
- Loading (spinner, can't submit)

**Sizing:**
```
Input height:      40px (standard)
Input padding:     12px horizontal, 8px vertical
Border:            1px solid #ccc
Border radius:     4-6px
Font:              14px
Label:             12px, medium weight, 8px above input
Error text:        12px, red, 4px below input
```

**Validation States:**
✓ Required indicator (red asterisk or "Required" label)
✓ Real-time validation (show error on blur, not submit)
✓ Clear error messages ("Email must include @" not "Invalid input")
✓ Success state optional (green checkmark or icon)

**Best Practices:**
✓ Label above input (not placeholder text as label)
✓ All inputs same height (aligned vertically)
✓ Error text below input in red
✓ Placeholder text lighter gray (#999)
✓ Focus state visible (2px blue border)
✓ Button disabled until valid

**Mistakes to Avoid:**
❌ Placeholder as label (disappears on focus)
❌ No error states (user doesn't know what's wrong)
❌ Inputs different heights
❌ No focus state (keyboard users lost)
❌ Error text hard to read
❌ Submit button always enabled (confusing)

---

### 5. MODAL PATTERNS

**Variants:**
- Modal Dialog (centered, with backdrop)
- Alert Dialog (confirmation, usually 2 buttons)
- Sheet (slides from bottom, mobile)
- Popover (small popup, positioned near trigger)
- Toast Notification (brief message, auto-dismiss)

**Sizing:**
```
Modal:             500-700px wide, 400-600px tall
Dialog:            400-600px wide, 300-400px tall
Sheet:             Full width mobile, 400px desktop
Toast:             300-400px wide, auto height
```

**Spacing:**
- Header: 20-24px padding
- Content: 20-24px padding
- Footer: 16-20px padding, align buttons right
- Gap between elements: 12-16px

**Backdrop:**
- Semi-transparent black (rgba 0,0,0 / 50%)
- Prevents interaction with background
- Click to dismiss (optional, clear in UX)

**States:**
- Closed (hidden, overlay removed)
- Opening (fade in animation, 200-300ms)
- Open (fully visible, focused)
- Closing (fade out animation, 200-300ms)

**Best Practices:**
✓ Clear header (describes purpose)
✓ Close button visible (X in top right)
✓ Primary action emphasized (blue vs. gray)
✓ Keyboard dismissible (Escape key)
✓ Focus trapped inside (keyboard nav stays in modal)
✓ Clear call-to-action

**Mistakes to Avoid:**
❌ Modal too small (content cramped)
❌ Close button hard to find
❌ Can't escape without action (frustrating)
❌ Multiple modals layered (confusing)
❌ Primary and secondary buttons same color
❌ Backdrop click doesn't dismiss (unclear)

---

### 6. TABLE PATTERNS

**Structure:**
- Header row (bold, background color)
- Data rows (alternating background optional)
- Column alignment (text left, numbers right)
- Row hover (subtle background highlight)

**Sizing:**
```
Row height:        40-48px
Column padding:    12-16px horizontal, 8-12px vertical
Header font:       14px bold
Data font:         14px regular
Borders:           1px #ddd between rows (or alternating rows)
```

**Features:**
- Sortable columns (chevron indicates direction)
- Searchable (filter box above table)
- Pagination (show 10/25/50 rows options)
- Expandable rows (details on click)
- Selectable rows (checkboxes for bulk actions)

**States:**
- Default (all data visible)
- Hover row (subtle background highlight)
- Sorted (column header bold, chevron indicator)
- Selected (background highlight, checkbox checked)
- Empty (show "No data" message)
- Loading (show skeleton rows)

**Best Practices:**
✓ Numbers right-aligned (easier to scan)
✓ Text left-aligned (standard reading)
✓ Row hover visible (easy to track)
✓ Sortable columns clear (chevron direction)
✓ Pagination clear (showing "1-10 of 250")
✓ Responsive scrolls horizontally (not cramped on mobile)

**Mistakes to Avoid:**
❌ Too many columns (overwhelming)
❌ Row height too small (hard to read)
❌ No sortable indicators
❌ Center-aligned text (hard to read)
❌ No empty state (confusing when no data)
❌ Doesn't work on mobile

---

## Now Create Your Pattern

**I'm ready to show you detailed patterns for:** [Your component choice]

Once you specify which component, I'll provide:

1. **Design Variations** — 3-5 common variations with use cases
2. **Sizing Reference Table** — Exact pixel measurements
3. **State Diagram** — How states transition (default → hover → active → disabled)
4. **Color & Contrast** — Specific color values and contrast ratios
5. **Spacing Blueprint** — Exact padding, margins, gaps
6. **Real Examples** — 2-3 real designs using this pattern
7. **Best Practices Checklist** — What to do right
8. **Common Mistakes** — What to avoid
9. **Accessibility Notes** — WCAG compliance, keyboard navigation
10. **Implementation Notes** — How to build in Figma and Webflow

---

## Quick Links to Deeper Skills

For more detail:
- **ui-components** skill — Full component pattern library with variants and states
- **visual-foundations** skill — Color contrast, typography sizing, spacing systems
- **animation-interactions** skill — Hover animations, state transitions, timing
- **web-design-audit** skill — How to critique components for consistency

---

## Ready?

Tell me which component you'd like patterns for, and I'll provide your complete design reference!
