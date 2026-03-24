---
name: Animation Help
description: "Add animation and micro-interactions to design elements with timing, easing, and implementation guidance."
---

# Animation Help

Get guidance on adding animations and micro-interactions to your design. This covers timing principles, easing functions, and how to implement animations in Webflow and other tools.

---

## What This Command Does

You describe what element you want to animate, and I'll provide:
- Animation pattern recommendations (fade, slide, scale, rotate)
- Timing guidance (200ms for interactions, 600ms for entrances)
- Easing function recommendations (ease-out, ease-in-out, custom)
- Trigger points (hover, click, scroll, page load)
- Implementation steps for Webflow
- Performance considerations (GPU acceleration, will-change)
- Accessibility notes (prefers-reduced-motion)
- Real examples and reference designs

**Time to answer:** 2-3 minutes
**Time to receive animations:** 10-15 minutes

---

## Scoping Questions

**QUESTION 1: What element are you animating?**

Choose or describe:
- Button (hover, click)
- Card (hover lift, expand)
- Navigation (menu slide in, item highlight)
- Form input (focus, validation)
- Hero section (scroll-triggered, parallax)
- Text (fade in, slide up)
- Image (zoom, fade in)
- Modal (entrance, exit)
- Notification/Toast (slide in, auto-dismiss)
- Menu (hamburger animation, dropdown)

---

**QUESTION 2: What should happen?**

Describe the animation:
- "When user hovers over button, it should..."
- "When user scrolls to section, it should..."
- "When form is submitted, it should..."

*Examples:*
- "Button should lighten on hover, scale up slightly"
- "Cards should fade in and slide up as user scrolls"
- "Form inputs should glow blue when focused"
- "Modal should slide up from bottom and darken background"

---

**QUESTION 3: Trigger timing** (Optional)

When should animation start?
- **Hover** (mouse over element)
- **Click/Focus** (user interacts)
- **Scroll** (triggered by page scroll)
- **Page Load** (entrance animation)
- **Submission** (form submit or action)

---

## Animation Patterns

Based on your answers, I'll recommend the best animation patterns:

### PATTERN 1: HOVER EFFECTS (Interactions)

**Timing:** 150-250ms (fast feedback)
**Trigger:** Mouse over element

**Common Patterns:**

#### Button Hover
```
Default:    Button in neutral state
Hover:      + Lighten/darken 10%
            + Scale 1.02x (slightly larger)
            + Add subtle shadow
Timing:     200ms ease-out
```

**Easing:** `ease-out` (fast start, slow end = feels responsive)

**Code (Webflow):**
```
Button:
- Default: scale 1, opacity 1
- Hover: scale 1.02, opacity 0.9
- Transition: 200ms ease-out
```

#### Card Hover
```
Default:    Card in place, minimal shadow
Hover:      + Lift up 4-8px (translate Y)
            + Add shadow (8-12px blur)
            + Slight scale (1.01x)
Timing:     300ms ease-out
```

**Easing:** `ease-out` (responsive, natural feel)

#### Link Underline Expand
```
Default:    Underline 0px width
Hover:      Underline expands to full width
Timing:     200ms ease-out
```

**Easing:** `cubic-bezier(0.34, 1.56, 0.64, 1)` (bouncy feel)

---

### PATTERN 2: FOCUS STATES (Keyboard Navigation)

**Timing:** 150ms (same as hover)
**Trigger:** Tab key or click

**Common Patterns:**

#### Input Focus
```
Default:    Gray border (2px, #ccc)
Focus:      Blue border (2px, #0066ff)
            + Subtle glow shadow
Timing:     150ms ease-out
Accessibility: Required for keyboard users
```

#### Button Focus
```
Default:    Normal button
Focus:      Blue outline (3px, #0066ff)
            + Offset 2px from button edge
Timing:     150ms ease-out
```

**Important:** Focus state must be visible (not just hover)

---

### PATTERN 3: ENTRANCE ANIMATIONS (Page Load)

**Timing:** 400-800ms (longer for entrances)
**Trigger:** Element appears on screen

**Common Patterns:**

#### Fade In
```
Start:      Opacity 0 (invisible)
End:        Opacity 1 (fully visible)
Timing:     600ms ease-out
Easing:     ease-out (starts slow, ends fast)
```

#### Slide Up + Fade In
```
Start:      Opacity 0, translate Y +40px (below)
End:        Opacity 1, translate Y 0 (normal position)
Timing:     600ms ease-out
Easing:     ease-out
```

#### Scale In (Zoom)
```
Start:      Scale 0.8, opacity 0
End:        Scale 1.0, opacity 1
Timing:     500ms ease-out
Easing:     ease-out
```

#### Staggered Sequence (Multiple Items)
```
Item 1:     Fade in at 0ms
Item 2:     Fade in at 100ms (offset)
Item 3:     Fade in at 200ms (offset)
Item 4:     Fade in at 300ms (offset)
Each item:  600ms duration
Total:      900ms for full sequence
```

**Easing:** `ease-out` (feels natural, responsive)

---

### PATTERN 4: SCROLL-TRIGGERED ANIMATIONS

**Timing:** 600-1200ms (longer for prominent effects)
**Trigger:** User scrolls element into view

**Common Patterns:**

#### Fade In on Scroll
```
Off-screen:  Opacity 0
On-screen:   Opacity 1 (when 50% visible)
Timing:      600ms ease-out
```

#### Slide In on Scroll
```
Off-screen:  Opacity 0, translate X -40px (left)
On-screen:   Opacity 1, translate X 0 (normal)
Timing:      600ms ease-out
Alternate:   Slide from right (translate X +40px)
```

#### Parallax (Background moves slower)
```
Background: Moves at 50% of scroll speed
Foreground: Moves at normal speed
Effect:     Depth illusion
```

#### Counter Animation (Numbers count up)
```
Start:      0
End:        Final number (e.g., 2,485)
Timing:     1000-2000ms
Easing:     linear (consistent pace)
Example:    "2,485 users" animates from 0 to 2485
```

---

### PATTERN 5: MICRO-INTERACTIONS (Feedback)

**Timing:** 200-400ms (immediate feedback)
**Trigger:** User action (click, submit, etc.)

**Common Patterns:**

#### Loading Spinner
```
Rotation:   360 degrees
Timing:     1000ms, infinite loop
Easing:     linear
Color:      Brand primary color
```

#### Form Validation Success
```
Error text: Fade out, slide up
Green icon: Fade in, scale in (0.5 to 1.0)
Timing:     300ms ease-out
```

#### Button Click Feedback
```
Click:      Scale down slightly (0.95x)
Release:    Scale back to 1.0
Timing:     200ms ease-out
Feedback:   Feels tactile, like button press
```

#### Toast Notification Slide
```
Enter:      Translate Y +100px (below), opacity 0
Show:       Translate Y 0, opacity 1
Wait:       Visible for 3000ms
Exit:       Translate Y +100px, opacity 0
Timing:     300ms ease-out
Total:      3600ms lifecycle
```

#### Checkbox Animation
```
Unchecked:  Empty box
Checked:    Fill with color, checkmark appears
Timing:     250ms ease-out
Easing:     cubic-bezier for bouncy feel
```

---

## Easing Functions Guide

**Choose the right easing for feel:**

| Easing | Feel | Best For | Code |
|--------|------|----------|------|
| **linear** | Constant pace, robotic | Spinners, continuous motion | `linear` |
| **ease-in** | Slow start, fast end | Exits, dismissals | `cubic-bezier(0.42, 0, 1, 1)` |
| **ease-out** | Fast start, slow end | Entrances, hover states | `cubic-bezier(0, 0, 0.58, 1)` |
| **ease-in-out** | Slow both ends | Medium interactions | `cubic-bezier(0.42, 0, 0.58, 1)` |
| **Bouncy** | Spring-like bounce | Playful interactions | `cubic-bezier(0.34, 1.56, 0.64, 1)` |
| **Smooth Overshoot** | Gentle bounce | Icon animations | `cubic-bezier(0.175, 0.885, 0.32, 1.275)` |

**In Webflow:** Most easing is built-in (ease-in, ease-out, linear). For custom, use cubic-bezier.

---

## Animation Timing Reference Table

| Type | Duration | Easing | Use Case |
|------|----------|--------|----------|
| Hover feedback | 150-200ms | ease-out | Button hover, link underline |
| Focus state | 150ms | ease-out | Form inputs, buttons |
| Click response | 200ms | ease-out | Button click, checkbox |
| Loading spinner | 1000ms | linear | Infinite rotation |
| Entrance (fade) | 400-600ms | ease-out | Hero section, cards |
| Entrance (slide) | 600ms | ease-out | Slide up, slide in |
| Scale entrance | 500ms | ease-out | Zoom in effect |
| Stagger delay | 100ms increment | ease-out | Multiple items sequence |
| Scroll trigger | 600-800ms | ease-out | Fade on scroll, slide on scroll |
| Parallax | Varies by speed ratio | linear | Background depth effect |
| Toast notification | 300ms enter/exit | ease-out | 3000ms visible, then exit |
| Modal entrance | 300ms | ease-out | Slide up, fade in |
| Modal exit | 300ms | ease-out | Slide down, fade out |

**General Rule:** 200-300ms for interactions, 400-800ms for entrances, linear for spinners.

---

## Webflow Implementation

### BASIC HOVER ANIMATION

**Steps in Webflow:**
1. Select element (button, card, etc.)
2. Go to Interactions → Hover
3. Add animation:
   - **Transform:** Scale 1.02x
   - **Opacity:** 0.9
   - **Timing:** 200ms ease-out
4. Set return animation (back to default)

### SCROLL-TRIGGERED ANIMATION

**Steps in Webflow:**
1. Select element to animate
2. Go to Interactions → Scroll into view
3. Add animation:
   - **Transform:** Translate Y +40px
   - **Opacity:** 0 (start state)
4. Set end state:
   - **Transform:** Translate Y 0
   - **Opacity:** 1 (end state)
5. Duration: 600ms, Easing: ease-out

### STAGGER SEQUENCE

**Steps in Webflow:**
1. Add all items to a container
2. Duplicate interaction on each item
3. Add stagger delay:
   - Item 1: Scroll trigger at 0ms
   - Item 2: Scroll trigger at 100ms delay
   - Item 3: Scroll trigger at 200ms delay
4. Set same animation for all items

---

## Accessibility Considerations

**Always respect user preferences:**

### prefers-reduced-motion Media Query

Some users have motion sensitivity or vestibular issues. Always provide option:

```
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

**In Webflow:** Use conditional settings to disable animations for users who prefer reduced motion.

### What NOT to Animate

❌ **Flashing animations** (>3x per second = seizure risk)
❌ **Extreme motion** (large parallax, rapid jitter)
❌ **Constantly moving** (auto-playing carousels, floating elements)
❌ **Unexpected animations** (surprise entrance animations)

### Safe Animations

✓ Subtle fade and scale (under 500ms)
✓ Scroll-triggered entrance (user-initiated)
✓ Hover effects (user controls timing)
✓ Loading indicators (expected)
✓ Transitions between states (button clicks, form validation)

---

## Performance: GPU Acceleration

**For smooth animations, use GPU-accelerated properties:**

✓ **Use these (GPU accelerated):**
- `transform: translate()` (move element)
- `transform: scale()` (resize)
- `transform: rotate()` (spin)
- `opacity` (fade)

❌ **Avoid these (CPU expensive):**
- `position: left/top/right/bottom` (reflows layout)
- `width/height` (reflows layout)
- `margin/padding` (reflows layout)

**Rule:** Animate `transform` and `opacity` only. Use CSS `will-change: transform;` to hint to browser for optimization.

---

## Common Mistakes to Avoid

❌ **Too long durations** (animations feel sluggish over 800ms)
❌ **Animations on every hover** (overload, feels cheap)
❌ **No delay between staggered items** (all animate at once)
❌ **Linear easing for entrances** (feels robotic)
❌ **Animating layout-affecting properties** (causes jank)
❌ **Infinite animations** (spinning logos = annoying)
❌ **No exit animation** (abrupt disappearance)
❌ **Ignoring prefers-reduced-motion** (accessibility violation)

---

## Animation Decision Tree

**When should I animate?**

```
Does it help user understand?
├─ YES: Animate
│   └─ Is it fast feedback? (hover, click)
│       ├─ YES: 150-250ms
│       └─ NO: 400-800ms
└─ NO: Don't animate

Is it decorative only?
├─ YES: Skip it (or very subtle)
└─ NO: Continue planning
```

---

## Real Examples

### EXAMPLE 1: Button Hover
"Create a button that brightens and lifts on hover"

Animations:
- Scale: 1.0 → 1.02
- Y Position: 0px → -4px (translate up)
- Shadow: 0 → 8px blur, 4px offset
- Duration: 200ms
- Easing: ease-out

**Feeling:** Tactile, responsive, inviting

---

### EXAMPLE 2: Card Grid Entrance
"Cards fade in and slide up as page loads, staggered"

Animations:
- Card 1: Fade in + slide up (0ms delay)
- Card 2: Fade in + slide up (100ms delay)
- Card 3: Fade in + slide up (200ms delay)
- Card 4: Fade in + slide up (300ms delay)
- Each card: 600ms duration, ease-out

**Feeling:** Organized, sequential, professional

---

### EXAMPLE 3: Form Input Focus
"Input glows blue with subtle scale when focused"

Animations:
- Border color: #ccc → #0066ff
- Box shadow: none → 0 0 0 3px #0066ff (glow)
- Duration: 150ms
- Easing: ease-out

**Feeling:** Clear feedback, accessible, modern

---

## Deep Dive Skills

For more detail:
- **animation-interactions** skill — Complete animation patterns, timing, implementation
- **webflow-implementation** skill — Building animations in Webflow, performance
- **ui-components** skill — Component state animations, micro-interactions

---

## Pro Tips

**For Micro-Interactions:**
- More is less (not every hover needs animation)
- Consistency matters (all buttons should feel same)
- Speed matters (150-200ms for feedback)
- Easing matters (ease-out feels responsive)

**For Performance:**
- Test on slow devices (low-end phones)
- Monitor frame rate (should be 60fps)
- Use Chrome DevTools Performance tab
- Profile animations before shipping

**For Accessibility:**
- Always respect `prefers-reduced-motion`
- Test with keyboard navigation only
- Provide visible focus states
- Don't use animation for critical info (supplementary only)

---

## Ready?

Tell me:
1. **What element** are you animating?
2. **What should happen** (hover, scroll, click, load)?
3. **How should it feel** (playful, professional, subtle)?

I'll provide:
- Specific animation pattern recommendations
- Exact timing and easing values
- Step-by-step Webflow implementation
- Accessibility guidelines
- Performance considerations

Let's add motion to your design!
