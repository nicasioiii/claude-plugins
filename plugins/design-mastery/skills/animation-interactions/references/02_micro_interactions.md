# Micro-Interactions Design Guide

## Button Interactions (Most Frequent)

### Primary Button Hover

**Visual behavior:**
```
Default:
  Background: Brand color (e.g., #0066FF)
  Text: White
  Shadow: none
  Cursor: pointer

Hover:
  Background: Darker brand color (e.g., #0052CC)
  Text: White
  Shadow: 0 10px 30px rgba(0,0,0,0.15)
  Cursor: pointer (stays same)

Active/Pressed:
  Background: Darkest brand color (e.g., #003d99)
  Shadow: 0 5px 15px rgba(0,0,0,0.2)
```

**Animation:**
```
Duration: 200ms
Easing: ease-in-out
Properties changing: background-color, box-shadow
```

**Webflow implementation:**
1. Select button
2. Interactions > "+" > Trigger: "Mouse over"
3. Action: "Animate" → Set all properties above
4. Duration: 200ms
5. Easing: ease-in-out
6. Add reverse on "Mouse out"

### Secondary Button (Outline)

**Visual behavior:**
```
Default:
  Background: Transparent
  Border: 2px solid brand color
  Text: Brand color
  Padding: 14px vert, 22px horiz (accounts for 2px border)

Hover:
  Background: Light brand color (e.g., #E6F0FF)
  Border: 2px solid brand color
  Text: Brand color
```

**Animation:**
```
Duration: 200ms
Easing: ease-in-out
Properties: background-color, border-color
```

**Difference from primary:**
- No shadow change (outline style doesn't benefit)
- Slight background tint instead of color swap
- Border adds visual complexity; keep animation subtle

### Disabled Button

**Visual (no animation):**
```
Default:
  Background: #E8E8E8 (light gray)
  Text: #AAAAAA (medium gray)
  Cursor: not-allowed (not pointer)
  Opacity: 1 (visible, just disabled)

Hover:
  (No change — disabled buttons don't respond to hover)
```

**Principle:** Disabled buttons should not animate. They're not interactive.

---

## Form Input Interactions

### Text Input Focus

**Visual behavior:**
```
Default (unfocused):
  Border: 1px solid #CCCCCC (light gray)
  Background: #FFFFFF (white)
  Text: #333333 (dark)
  Outline: none

Focus:
  Border: 2px solid #0066FF (brand color)
  Background: #FFFFFF (white)
  Text: #333333 (dark)
  Outline: none
  Box-shadow: 0 0 0 3px rgba(0,102,255,0.1) (subtle glow)
```

**Animation:**
```
Duration: 150ms
Easing: ease-in-out
Properties: border-color, box-shadow
```

**Webflow:**
1. Select input element
2. Interactions > "+" > Trigger: "Focus"
3. Animate: border-color to #0066FF, add box-shadow
4. Duration: 150ms
5. Easing: ease-in-out

### Form Validation States

**Error state:**
```
Border: 2px solid #F44336 (red)
Background: #FFFBF8 (light red tint)
Text: #F44336 (red error message below)
Box-shadow: 0 0 0 3px rgba(244,67,54,0.1)
```

**Success state:**
```
Border: 2px solid #4CAF50 (green)
Background: #F9FFF8 (light green tint)
Text: #4CAF50 (green success message below)
Box-shadow: 0 0 0 3px rgba(76,175,80,0.1)
```

**Warning state:**
```
Border: 2px solid #FF9800 (orange)
Background: #FFF8F4 (light orange tint)
Text: #FF9800 (orange warning message below)
Box-shadow: 0 0 0 3px rgba(255,152,0,0.1)
```

**Animation:** 200ms ease-in-out as user inputs invalid/valid content

---

## Loading States

### Spinner (Most Common)

**Visual:**
```
Shape: Circular progress indicator
Rotation: 360 degrees continuous
Color: Brand color
Size: 24px (small), 32px (medium), 48px (large)
```

**Animation:**
```
@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

duration: 1000ms (1 full rotation per second)
easing: linear (constant speed)
repeat: infinite
```

**Timing options:**
- Fast: 800ms (for quick operations)
- Standard: 1000ms (default)
- Slow: 1500ms (for clarity on slow connections)

**Webflow:**
1. Create circle or import spinner SVG
2. Interactions > "+" > Trigger: "While loading"
3. Animation: Rotate 360 degrees
4. Duration: 1000ms
5. Easing: linear
6. Iteration: Infinite

### Skeleton Screen (Loading Placeholder)

**Visual:**
```
Background: Light gray (#F0F0F0)
Shape: Matches content shape (box for text, tall rect for image)
Animation: Pulsing opacity effect
```

**Animation:**
```
@keyframes pulse {
  0% { opacity: 0.6; }
  50% { opacity: 1; }
  100% { opacity: 0.6; }
}

duration: 1500ms
easing: ease-in-out
repeat: infinite
```

**Layout:**
- Text skeleton: 12px height, repeat 3-4 times for paragraph
- Image skeleton: Full width, 200px height (or aspect ratio)
- Button skeleton: 48px height
- Keep same spacing as real content

**Webflow:**
1. Create skeleton layout matching real content layout
2. Set background color to light gray (#F0F0F0)
3. Add fade animation: opacity 60% → 100% → 60%
4. Duration: 1500ms, infinite

---

## Link Interactions

### Text Link Underline

**Visual behavior:**
```
Default:
  Color: Brand color (#0066FF)
  Text-decoration: none (no underline)
  Opacity: 1

Hover:
  Color: Darker brand color (#0052CC)
  Text-decoration: underline
  Opacity: 1

Alternative (Animated underline):
  Default: border-bottom width 0
  Hover: border-bottom width 2px
  Animation: Width grows in (200ms ease-out)
```

**Timing:** 200ms ease-in-out

**When to use:**
- Use simple color change for navigation links
- Use underline animation for body text links
- Avoid both together (overkill)

---

## Tooltip Interactions

**Visual behavior:**
```
Default (hidden):
  Opacity: 0
  Pointer-events: none (tooltip can't be interacted with)
  Visibility: hidden (or display: none)

Hover/Focus:
  Opacity: 1
  Pointer-events: auto
  Visibility: visible (or display: block)
```

**Optional animation:**
- Fade in: 200ms ease-out
- Slide up: translateY(4px) on appear, 200ms ease-out
- Combined: opacity fade + slide

**Position:**
```
Usually above element:
  Bottom (of tooltip): element.top - 8px

Or below:
  Top (of tooltip): element.bottom + 8px

With arrow pointing to element
```

**Webflow:**
1. Create tooltip element
2. Set display: none or opacity: 0 (default hidden)
3. Parent element: Interactions > "+"
4. Trigger: "Mouse over"
5. Action: Show tooltip, fade in 200ms ease-out
6. Trigger: "Mouse out"
7. Action: Hide tooltip, fade out 200ms

---

## Dropdown / Expand Interactions

**Visual behavior:**
```
Closed:
  Height: 0 or auto-close
  Opacity: 0 or opacity: 1 (depends on design)
  Pointer-events: none (can't interact with hidden menu)
  Transform: translateY(-10px) (optional, slight offset)

Open:
  Height: auto or max-height: 500px
  Opacity: 1
  Pointer-events: auto
  Transform: translateY(0)
```

**Animation:**
```
Duration: 300ms
Easing: ease-out
Properties: height/max-height, opacity, transform
```

**Webflow:**
1. Create dropdown trigger (button) + dropdown content (div)
2. Set dropdown to: display: none (default closed)
3. Button: Interactions > "+"
4. Trigger: "Click"
5. Action: Show dropdown, animate in
6. Duration: 300ms, ease-out
7. Add reverse animation on trigger click (toggle)

---

## Notification/Toast Interactions

**Visual behavior:**
```
Appear (entrance):
  Opacity: 0 → 1
  Transform: translateX(100%) → translateX(0) (slides in from right)
  Duration: 300ms, ease-out

Stay visible: 3000ms (3 seconds)

Disappear (exit):
  Opacity: 1 → 0
  Transform: translateX(0) → translateX(100%)
  Duration: 300ms, ease-in
```

**Timing:**
```
- Appear: 300ms ease-out
- Display: 2000-4000ms (user can read)
- Disappear: 300ms ease-in
- Total time: 2600-4600ms
```

**Position:**
- Bottom right: Popular, doesn't cover content
- Top right: Visible immediately
- Bottom left: Alternative (less common)
- Center top: Works but covers content

**Types:**
- Success: Green background, ✓ icon
- Error: Red background, ✗ icon
- Warning: Orange background, ⚠️ icon
- Info: Blue background, ℹ️ icon

---

## Hover State Patterns

### Card Hover

**Visual:**
```
Default:
  Shadow: none or subtle (0 2px 8px rgba(0,0,0,0.1))
  Transform: none
  Background: white

Hover:
  Shadow: 0 10px 30px rgba(0,0,0,0.15) (larger)
  Transform: translateY(-4px) (slight lift)
  Background: white (no change) or light tint
```

**Animation:** 200ms ease-in-out

**Effect:** Card feels "clickable" and responds to user

### Image Hover (Zoom)

**Visual:**
```
Default:
  Transform: scale(1)

Hover:
  Transform: scale(1.05) (5% larger)
```

**Caveat:** Image must be in container with overflow: hidden

**Animation:** 400ms ease-out (slower for visual interest)

---

## Focus States (Accessibility)

**For keyboard navigation:**

```
Default:
  Outline: none (remove browser default)

Focus (tab key):
  Outline: 3px solid brand-color
  Outline-offset: 2px (space between element and outline)
```

**Webflow:**
```
1. Select button/link
2. States > Add state "Focus"
3. Outline: 3px solid #0066FF
4. Outline-offset: 2px
```

**Why it matters:**
- Users navigate via keyboard (tab key)
- Need visible focus indicator
- Helps accessibility compliance
- Improves usability for all users

---

## Micro-Interaction Checklist

Before finalizing interactions:

- [ ] All hover states respond quickly (200-300ms)
- [ ] Loading states don't block interaction (spinner runs in background)
- [ ] Focus states visible for keyboard navigation
- [ ] Animations respect prefers-reduced-motion
- [ ] No animations on disabled states
- [ ] Animations don't distract from content
- [ ] Timing feels natural (not too fast, not too slow)
- [ ] Color changes have sufficient contrast
- [ ] Animations smooth on mobile (test performance)
- [ ] No multiple animations on same element (too complex)

---

**Last Updated:** March 12, 2026
**Source:** Webflow Masterclass, Shift Nudge, UX Interaction Patterns
