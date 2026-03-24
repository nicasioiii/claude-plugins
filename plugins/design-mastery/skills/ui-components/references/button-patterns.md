# Button Patterns — Deep Dive

## Button Hierarchy & When to Use Each Type

### 1. Primary Button (Most Important Action)

**Visual Specification:**
```
Background: Brand color (primary)
Text: White or high-contrast color
Padding: 16px vertical × 24px horizontal
Border-radius: 8px
Font: 16px, semi-bold (600 weight)
Minimum height: 48px (touch target)
```

**State Definitions:**

| State | Visual | Code Example |
|-------|--------|--------|
| **Default** | Solid primary background, white text, no shadow | `bg-primary text-white` |
| **Hover** | 10% darker (increase saturation), subtle shadow | `bg-primary-dark shadow-sm` |
| **Active** | 20% darker, inset shadow (pressed feeling) | `bg-primary-darker shadow-inset` |
| **Focus** | 3px solid outline, 2-3px offset, brand color | `outline: 3px solid primary` |
| **Disabled** | 50% opacity, gray background, cursor: not-allowed | `opacity-50 cursor-not-allowed` |
| **Loading** | Spinner icon, text hidden or "Loading..." | `disabled opacity-75 pointer-events-none` |

**Hover Color Calculation (HSB Model):**
- Default: Hue 220°, Saturation 80%, Brightness 90%
- Hover: Same hue, Saturation +10% (90%), Brightness -10% (80%)
- Active: Same hue, Saturation +10%, Brightness -20% (70%)

**Size Variations:**

| Size | Text | Padding | Height | Use Case |
|------|------|---------|--------|----------|
| **Large** | 18px | 20px V × 28px H | 56px | Hero sections, main CTA |
| **Default** | 16px | 16px V × 24px H | 48px | Most common, forms |
| **Small** | 14px | 12px V × 16px H | 40px | Inline actions, secondary |
| **Compact** | 12px | 8px V × 12px H | 32px | Rare, only in dense UIs |

**Real Example from Shift Nudge Critique Vault:**
```
✓ CORRECT: Primary button 48px height, 24px horizontal padding
✗ WRONG: Primary button 32px height (too small for touch targets)
✓ CORRECT: Hover state 15% darker (maintains brand color saturation)
✗ WRONG: Hover state changes to completely different color
```

### 2. Secondary Button (Alternative Action)

**Visual Specification:**
```
Background: Transparent or 10% brand color
Border: 2px solid primary color
Text: Brand color (primary)
Padding: 16px vertical × 24px horizontal
```

**State Behavior:**
- **Default:** Outlined (transparent), colored border and text
- **Hover:** Fills with light brand color (10-15% opacity)
- **Active:** Solid filled with brand color (like primary button)
- **Focus:** Same 3px outline as primary
- **Disabled:** 50% opacity, lighter border

**When to Use:**
- Multiple CTAs on same section (one primary, one secondary)
- Less critical actions (Cancel, Close, Back, Learn More)
- Filters or toggles
- Navigation-adjacent buttons

**Contrast Consideration:**
If using transparent secondary button, ensure border color has 4.5:1 contrast with background.

### 3. Tertiary Button (Minimal Action)

**Visual Specification:**
```
Background: None (transparent)
Border: None or 1px border (optional)
Text: Primary color or secondary color
Padding: 8px vertical × 12px horizontal
Font: 14px, regular or semi-bold
```

**State Behavior:**
- **Default:** Colored text only, no background/border
- **Hover:** Add subtle underline (2px, brand color) or 5% background
- **Active:** Deepened color (10% darker)
- **Focus:** Text outline or background highlight
- **Disabled:** 50% opacity

**Use Cases:**
- "Skip", "More", "Learn More", "Cancel" on secondary CTAs
- Inline text links styled as buttons
- Breadcrumb navigation
- Table row actions ("Edit", "Delete")

**Tertiary vs Link Distinction:**
- Buttons: Usually larger, more prominent, trigger primary actions
- Links: Smaller, embedded in text, navigate between pages
- Tertiary buttons sit between them in visual weight

---

## Advanced Button Patterns

### Icon Buttons (Icon-Only)

**IMPORTANT:** Never use icon-only buttons without labels or tooltips. Accessibility requirement: users must understand button purpose.

**Pattern 1: Icon with Hidden Label (Accessible)**
```html
<button aria-label="Close menu">
  <CloseIcon />
</button>
```
- Icon: 24px
- Background: Transparent or subtle color
- Padding: 8px (makes 40×40px touch target)
- Tooltip on hover: "Close menu" (optional visual enhancement)

**Pattern 2: Icon with Tooltip**
- Icon: 24×24px
- Container: 48×48px (48px touch target)
- Tooltip: Appears on hover/focus, 12px gray text
- Tooltip delay: 500-700ms (prevent accidental display)

**Common Icon Buttons:**
- Close (X icon): Primary placement top-right
- Menu (hamburger): Primary placement top-left or top-right
- Search: Usually right-aligned in header
- Settings: Usually right-aligned in app nav
- Delete (trash icon): Right-aligned in rows

### Button Groups (Multiple Buttons)

**Horizontal Button Group:**
```
[Primary] [Secondary] [Tertiary]
 12px gap   12px gap
```

**Sizing:**
- Gap between buttons: 12px minimum
- If buttons are full-width (mobile): Stack vertically, 12px gap
- Button width on mobile: Full width minus margins

**Spacing Example (Mobile):**
```
┌─────────────────────────┐
│     [Save Changes]      │  Full width - 16px margins (2x)
├─────────────────────────┤
│      [Cancel]           │  Same width
└─────────────────────────┘
 12px gap between buttons
```

**Alignment Rules:**
- Primary button: Always rightmost (or top-right on mobile)
- Secondary button: Left of primary
- Tertiary button: Leftmost or below other buttons

### Loading Button State

**Visual Progression:**

1. **Default State:** Button shows text and icon
2. **Click → Loading:**
   - Immediately show spinner (100-200ms)
   - Hide text or keep text as "Loading..."
   - Disable interaction (pointer-events: none)
   - Opacity: 75-80% (slight dimming)
3. **Success/Error:**
   - Show success/error icon (brief)
   - Auto-revert to default after 2-3 seconds OR
   - Replace with "Continue" button

**Implementation Details:**
```
Button width: Lock width to prevent jumping (no text = narrower)
Spinner size: 16-20px (match text line height)
Spinner color: White (same as text)
Animation: 1-2 second rotation
```

**Best Practice:**
Don't disable the button during loading (confusing). Instead:
- Gray out the button (opacity: 0.6)
- Show spinner overlaying text
- Set pointer-events: none to prevent double-clicks
- Show loading state for minimum 500ms (even if fast, feels responsive)

### Button with Badge or Counter

**Structure:**
```
[Primary Button]  ⓷
```

**Badge Positioning:**
- Position: Absolute, top-right corner
- Size: 20-24px circle
- Background: Red or accent color
- Text: White, 10-12px, centered
- Count limit: Show "9+" if more than 9 items

**Example: Notification Button**
```
🔔 Notifications  (with red circle showing "5")
```

### Dropdown Button (Trigger Menu)

**Structure:**
```
[Button Label  ▼]  Chevron: 16px right-aligned
```

**On Click/Focus:**
```
[Button Label  ▲]
├─ Menu Option 1
├─ Menu Option 2
├─ Menu Option 3
└─ Menu Option 4
```

**Dropdown Menu Styling:**
- Position: Below button (or above if space)
- Width: Match button width or 200px minimum
- Gap: 4-8px between button and menu
- Background: White with 1px border
- Shadow: 0 4px 12px rgba(0,0,0,0.12)
- Item height: 40-44px
- Item padding: 12px horizontal

---

## Button Sizing Reference Table

**Desktop Touch Targets:**

| Context | Height | Width (Min) | Font | Padding |
|---------|--------|------------|------|---------|
| Hero CTA | 56px | 200px | 18px | 20V × 28H |
| Form submit | 48px | 140px | 16px | 16V × 24H |
| Navigation | 48px | 100px | 14px | 12V × 16H |
| Inline action | 40px | 80px | 14px | 12V × 16H |
| Table row | 32px | 60px | 12px | 8V × 12H |

**Mobile Minimum:**
- Height: 48px (iPhone safe area)
- Width: Full width minus 16px margins (recommended)
- Padding: 16px V × 24px H (maintains size)

**Spacing Between Multiple Buttons (Mobile):**
- Vertical: 12px gap
- Horizontal: 12px gap (if side-by-side)

---

## Button Color Combinations

### Primary Color On Different Backgrounds

| Background | Text Color | Contrast | Notes |
|-----------|-----------|----------|-------|
| Primary | White | 4.5:1+ | Standard button |
| Primary (dark) | White | 7:1+ | High contrast version |
| Secondary | White | Check ratio | May not meet AA |
| Neutral gray | White | 4.5:1+ | Neutral CTA |
| Light gray (#F0F0F0) | Primary | 4.5:1+ | Light button variant |
| White (outlined) | Primary | Depends on border | Must test |

**Example: Testing Primary Color #0066CC**
```
Contrast check: #0066CC (background) vs White (#FFFFFF)
Result: 4.5:1 ✓ PASS (AA standard)

Contrast check: #0066CC (background) vs Light gray (#CCCCCC)
Result: 2.1:1 ✗ FAIL
```

### Accessible Button Colors for Dark Backgrounds

**On Dark Background (#1A1A1A):**
- Use primary color for contrast
- If primary is too dark, use lighter tint (60-70% brightness)
- Always test: Target 4.5:1 minimum

**Example:**
```
Dark background: #1A1A1A
Primary color (light): #4DA6FF (70% brightness of #0066CC)
Text: White
Contrast: 6.2:1 ✓ PASS
```

---

## Real-World Button Audit Examples

### ✓ CORRECT: E-commerce "Add to Cart"

```
Button size: 48px height, 24px horizontal padding
Color: Brand primary (green)
Text: White, 16px, bold
Hover: Darkened 15% (saturation +10%)
Focus: 3px outline, brand color, offset 2px
States: Clear visual progression (default → hover → active)
Disabled: Shows as unavailable (grayed)
Mobile: Full width, same height
```

### ✗ MISTAKE: Unclear CTA

```
Button size: 32px height (too small)
Text: Gray on light gray (2.1:1 contrast — FAILS)
Hover: Underline only (not obvious on hover)
Focus: No visible focus ring
Disabled: No visual distinction
Mobile: Same width as desktop (too narrow)
```

**Fix:** Increase height to 48px, ensure 4.5:1 contrast, add focus ring, full width on mobile.

### ✓ CORRECT: Form Submit Button

```
Primary button: 48px, 24px padding, brand primary
Secondary (Reset/Cancel): Outlined, same 48px
Spacing: 12px gap between buttons
Mobile: Stack vertically, full width each
Loading: Shows spinner on click, button disabled
Success: Brief checkmark + "Submitted" feedback
```

---

## Button Accessibility Checklist

- [ ] Minimum size: 44×44px (48px preferred)
- [ ] Contrast: 4.5:1 text on background
- [ ] Focus ring: 3px outline, high contrast, visible
- [ ] Keyboard accessible: Tab-navigable, Enter/Space triggers
- [ ] Semantic HTML: `<button>` element, not `<div>`
- [ ] Clear label: "Save", not "OK" or "Submit" (when possible)
- [ ] Icon buttons: ARIA label or visible text
- [ ] Disabled state: Visually distinct, cursor: not-allowed
- [ ] No color-only indicators: Use icon + color for disabled/active
- [ ] Loading state: Clear indication, prevents multiple submits
- [ ] Error feedback: Associated error message below button or adjacent

---

## Button Performance Notes

**Animation Timing:**
- Hover state: Instant (0ms) or 200ms transition
- Click feedback: 100-150ms
- Loading spinner: 1-2 second rotation

**GPU Acceleration:**
Use `transform: scale()` for hover effects, not `width`/`height` changes.

```css
/* ✓ Good: GPU accelerated */
transition: transform 200ms;
&:hover { transform: scale(1.05); }

/* ✗ Bad: CPU intensive */
transition: width 200ms;
&:hover { width: 110%; }
```

