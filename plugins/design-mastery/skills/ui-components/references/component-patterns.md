# UI Component Patterns: Complete Reference

## Button Patterns

### Primary Button (Main Call-to-Action)

**Structure:**
- Padding: 16px vertical × 24px horizontal (8px grid divisible)
- Corner radius: 8px (modern, not cartoonish)
- Typography: 14-18px, semi-bold weight
- Background: Brand primary color
- Text color: White or high-contrast color

**States:**
- **Default:** Solid primary color background, white text
- **Hover:** 10-15% darker shade (increase saturation)
- **Active/Pressed:** 20% darker, slight inset shadow
- **Disabled:** 50% opacity or neutral gray background
- **Focus:** 3px solid outline in brand color (offset 2-3px)
- **Loading:** Replace text with spinner, disable interaction

**Size Variations:**
- **Large:** 18px text, 20px vertical × 28px horizontal padding (CTA sections)
- **Default:** 16px text, 16px vertical × 24px horizontal padding (most common)
- **Small:** 14px text, 12px vertical × 16px horizontal padding (inline actions)

**Real Example (from Shift Nudge critiques):**
- Primary CTA on marketing sites: 48px minimum height (for touch targets)
- E-commerce: Often use full-width primary buttons on mobile
- Apps: 44px height (iOS minimum touch target)

### Secondary Button (Alternative Action)

**Structure:**
- Same padding/sizing as primary
- Background: Transparent or 10% brand color
- Border: 2px solid brand color
- Text: Brand color

**States:**
- **Default:** Transparent with colored border
- **Hover:** Light background fill (10-20% brand color)
- **Active:** Solid filled with brand color
- **Disabled:** 50% opacity border and text
- **Focus:** Same 3px outline as primary

**When to Use:**
- Multiple CTAs on one section
- Less important actions next to primary
- Filters, "Cancel", "Close" actions
- Alternative pathways

### Tertiary/Text Button (Minimal Action)

**Structure:**
- No padding box (text only)
- Color: Brand primary or secondary
- Typography: Same weight as primary, but no background

**States:**
- **Default:** Colored text, no background
- **Hover:** Add subtle underline or background
- **Active:** Color deepens
- **Disabled:** 50% opacity
- **Focus:** Outline or background highlight

**Use Case:** "Learn more", "Skip", "Cancel", secondary actions

### Button Size Guidelines

**Desktop Target Sizes:**
- Minimum touch target: 44×44px (WCAG AAA)
- Recommended minimum: 48×48px (common practice)
- Safe sizing: 44px height is baseline

**Mobile Target Sizes:**
- Absolute minimum: 44×44px
- Comfortable: 48×56px
- Spacing between buttons: 12px minimum

## Card Components

### Image Card (Photo + Text)

**Structure:**
```
┌─────────────────┐
│   Image Area    │  Height: 200-300px (aspect ratio 4:3 or 16:9)
│   (Auto-fit)    │
├─────────────────┤
│ Title (16-18px) │  Padding: 16px
│ 2-line max      │
├─────────────────┤
│ Description     │  Body: 14px, 75 chars max
│ (14px, gray)    │  Line height: 150%
├─────────────────┤
│ CTA Button      │  Optional: Primary button
└─────────────────┘
```

**Spacing Breakdown:**
- Image-to-title: 16px
- Title-to-description: 8px
- Description-to-button: 12-16px
- Card padding: 16px on all sides

**Hover State:**
- Shadow elevation (0 → 8px blur, 0 4px 12px rgba(0,0,0,0.12))
- Slight scale up (1.02x)
- Image brightens 5-10% (opacity or overlay)

**Responsive Behavior:**
- Desktop: 4 cards in grid (3-column each, 12-column grid)
- Tablet: 3 cards (2-column each, 6-column grid)
- Mobile: 1-2 cards full width

### Feature Card (Icon + Title + Text)

**Structure:**
```
┌──────────────────┐
│  Icon (48px)     │  Icon: 2-3 colors max, 48-64px
├──────────────────┤
│ Title (18px)     │  Semi-bold weight
│ Bold            │
├──────────────────┤
│ Description     │  14px body, 3 lines max
│ (3 lines max)   │  Neutral gray color
└──────────────────┘
```

**Padding:** 24px
**Gap between icon and title:** 12px
**Gap between title and description:** 8px

**Grid Layout:**
- Desktop: 3 columns (4 cards per row = 3-column width each)
- Tablet: 2 columns
- Mobile: 1 column

### Testimonial Card (Quote + Avatar + Name)

**Structure:**
```
┌──────────────────────────┐
│ "Quote text here..."     │  14-16px italic
│                          │  Line height: 150%
├──────────────────────────┤
│ ⭐⭐⭐⭐⭐ (optional)    │  Rating if applicable
├──────────────────────────┤
│ [Avatar] Name            │  48px circle avatar
│         Title/Company    │  12px gray metadata
└──────────────────────────┘
```

**Padding:** 20px
**Avatar styling:** 48px circle, border: none or 2px border
**Quote styling:** Use quotes as design element (20-50% opacity)

## Navigation Components

### Desktop Horizontal Navigation

**Structure:**
```
┌─────────────────────────────────────┐
│ Logo  Menu Item 1  Item 2  CTA Btn  │
└─────────────────────────────────────┘
```

**Sizing:**
- Nav height: 64-80px
- Logo size: 32-48px
- Menu text: 14-16px, semi-bold
- Padding: 16px horizontal per item
- Gap between items: 20-32px

**States:**
- **Default:** Black/primary text on white background
- **Hover:** Underline (2px, brand color) or background highlight
- **Active:** Underline + slight color change
- **Mobile scroll:** Add background color, reduce height

**Dropdown Menu:**
- Position: Absolute, below parent menu item
- Width: 200-250px minimum
- Items: 40px height each
- Padding: 8px vertical, 12px horizontal
- Background: White with 1px border
- Shadow: 0 4px 12px rgba(0,0,0,0.12)
- Hover item: 5-10% background fill

### Mobile Hamburger Navigation

**States:**

1. **Closed State:**
   - Icon: 3 horizontal lines (hamburger)
   - Size: 24px
   - Color: Match nav text color
   - Position: Top-right of nav

2. **Open State:**
   - Icon: X (rotated hamburger, 45°)
   - Menu: Full-screen overlay or slide panel
   - Background: White or semi-transparent
   - Items: Stack vertically, 60px height each
   - Padding: 16px per item
   - Close padding: 8px

**Animation:**
- Hamburger → X rotation: 200-300ms
- Panel slide-in: 300ms
- Easing: ease-out

**Mobile Nav Structure:**
```
┌─────────────────┐
│ Logo  ☰ Close  │ (Logo + close button)
├─────────────────┤
│ Navigation Item │  60px height each
│ Navigation Item │  Full-width items
│ Navigation Item │
├─────────────────┤
│ [CTA Button]    │  Full-width button
└─────────────────┘
```

## Form Input Patterns

### Text Input Field

**Structure:**
```
Label (12px, gray, 400 weight)
┌──────────────────────────┐
│ Placeholder text (14px)  │  Height: 44-48px
└──────────────────────────┘
Helper text (12px, gray)
```

**Padding:** 12px horizontal, 10-12px vertical
**Border:** 1px solid #CCCCCC (default), 2px on focus
**Focus state:** 2px solid primary color
**Corner radius:** 4-8px

## Modal / Dialog Patterns

### Basic Modal Structure

```
┌─────────────────────────────────────┐
│ Title (24px, semi-bold)        [X]  │
├─────────────────────────────────────┤
│                                     │
│ Modal content area                  │
│ (Padding: 24px)                     │
│                                     │
├─────────────────────────────────────┤
│            [Cancel]  [Confirm]      │
└─────────────────────────────────────┘
```

**Sizing:**
- Default width: 400-600px
- Max width: 80% of viewport (mobile: 90%)
- Padding: 24-32px
- Corner radius: 8-12px
- Backdrop: Dark overlay (rgba(0,0,0,0.5))

**Title:**
- 20-24px, semi-bold
- Color: Dark gray or black
- Margin bottom: 12px
- Include close button (X icon, top-right)

**Content Area:**
- Scrollable if exceeds max height
- Line height: 150% for body text
- Form fields: 16px spacing between

**Buttons:**
- Primary button: Right side
- Secondary button: Left or outside modal
- Padding: 12px spacing between
- Full-width on mobile

**Backdrop Interaction:**
- Click outside modal: Close (default)
- Consider disabling close on critical actions (data deletion)

**Animation:**
- Fade-in backdrop: 200ms
- Scale modal: 0.9 → 1.0 (300ms, ease-out)

## Table Components

### Data Table Structure

```
┌─────────────────────────────────────────┐
│ Column 1    Column 2    Column 3    ... │  Header: 14px semi-bold
├─────────────────────────────────────────┤
│ Row 1 Data  Data        Data       ...  │  Row height: 48px
│ Row 2 Data  Data        Data       ...  │  Row padding: 12px vertical
│ Row 3 Data  Data        Data       ...  │
└─────────────────────────────────────────┘
```

**Styling:**
- Header background: Light gray (#F5F5F5) or brand color (light tint)
- Header text: 12-14px, semi-bold, dark color
- Body text: 14px, regular
- Row height: 48-56px
- Row padding: 12px vertical, 16px horizontal
- Border between rows: 1px #EEEEEE

**Interactions:**
- **Hover row:** Light background fill (2-5% darker)
- **Sortable columns:** Up/down arrow icon, cursor: pointer
- **Selectable rows:** Checkbox column (left), highlight on select
- **Sticky header:** Keep header visible on scroll

**Responsive Behavior:**
- Desktop: Full table visible
- Tablet: Horizontal scroll or column hiding
- Mobile: Card view or stacked row layout
