---
name: Animation & Interactions
description: "Micro-interactions, scroll animations, timing/easing curves, hover states, loading states, accessibility (prefers-reduced-motion). Includes specific timing values (200-300ms interactions, 600-800ms entrances), easing curves, while-scrolling setup, 3D transforms, and Webflow implementation. MANDATORY TRIGGERS: animation, micro-interaction, scroll animation, timing, easing, hover state, loading state. Do NOT use for visual design — use visual-foundations or web-layout instead. Do NOT use for component design — use ui-components instead."
---

## Animation & Interactions

Strategic use of motion to enhance user experience without distraction. This skill covers when, why, and how to animate.

## Core Principle: Animation Adds Value

**The Rule:** Every animation must serve a purpose. Never animate just because you can.

**Purposes animation serves:**
1. **Feedback** — User action gets response (button press → visual feedback)
2. **Guidance** — Animation guides attention where to look
3. **Transition** — Animation smooths visual change between states
4. **Delight** — Subtle motion adds personality (only after other purposes met)

**Animation that fails:**
- ❌ Decorative movement with no purpose
- ❌ Parallax that makes page feel slow
- ❌ Auto-playing video that interrupts reading
- ❌ Movement that triggers vestibular issues (rapid, spinning)

---

## Quick Reference: Timing Values

**Interaction animations (user response):**
- Duration: 200-300ms
- Easing: ease-in-out
- Examples: button hover, form input focus, tooltip show

**Entrance animations (content appears):**
- Duration: 600-800ms
- Easing: ease-out
- Examples: fade in on page load, slide in on scroll

**While-scrolling animations:**
- Duration: Varies (see calculation section)
- Easing: linear or ease-in-out
- Smoothness: 75% (platform-dependent)

**Loading states:**
- Duration: 1000-2000ms (continuous)
- Easing: ease-in-out or linear
- Examples: spinner, skeleton screens

---

## Micro-Interactions (200-300ms)

Subtle animations in response to user action: button hovers, form focus states, tooltips, loading states.

For button hover patterns, form input animations, tooltips, and loading state examples, read `references/micro-interactions.md`.

---

## Scroll-Triggered Animations

Content animates as user scrolls down the page using while-scrolling containers with sticky positioning.

For while-scrolling setup, timing calculations, card sequencing, and 3D depth effects, read `references/scroll-animations.md`.

### 3D Transform Depth Effect

Add depth as cards animate:

```
Perspective setup: perspective(3000px) on parent
Card animations:
- At 9%: translateZ(0), Y = 32.5vh
- At 27%: translateZ(-4vh), Y = 0
- At 45%: translateZ(-8vh), Y = -2vh
```

Progressive Z-offset creates depth illusion. Cards move back as they move forward.

**Overlay darkening (optional):**
```
Background opacity:
- At 9%: rgba(0,0,0,0)
- At 45%: rgba(0,0,0,0.15)
Progressively darkens as cards move back in space
```

---

## Easing Curves

Easing determines how animation accelerates and decelerates.

### Common Easing Functions

**ease-out** (start fast, slow down)
- Use for: Entrance animations (appears and settles)
- Feel: Natural, coming into rest
- Example: Fade in, slide in, scroll reveal
- Timing: 600-800ms

**ease-in-out** (slow start, fast middle, slow end)
- Use for: Hover states, transitions between fixed states
- Feel: Mechanical, precise
- Example: Button hover, focus state, color change
- Timing: 200-300ms

**ease-in** (slow start, fast end)
- Use for: Rarely (feels unnatural)
- When OK: Exit animations (disappearing)
- Timing: 300ms

**linear** (constant speed)
- Use for: Loading spinners, continuous loops
- Feel: Mechanical, ongoing
- Example: Spinner rotation, infinite scroll
- Timing: 1000-2000ms continuous

**cubic-bezier(n, n, n, n)** (custom)
- Use for: Highly customized, specific feel
- Examples:
  - cubic-bezier(0.34, 1.56, 0.64, 1) = elastic bounce
  - cubic-bezier(0.17, 0.67, 0.83, 0.67) = smooth curve

### Quick Reference Table

| Animation | Timing | Easing | Feel |
|-----------|--------|--------|------|
| Button hover | 200ms | ease-in-out | Responsive |
| Form input focus | 150ms | ease-in-out | Immediate |
| Fade in (entrance) | 600ms | ease-out | Settling |
| Slide in (entrance) | 800ms | ease-out | Flowing |
| While-scrolling | Varies | linear | Smooth |
| Loading spinner | 1000ms | linear | Continuous |
| Scale (expand) | 300ms | ease-out | Bouncy |

---

## Accessibility: prefers-reduced-motion

Critical: Many users can't handle motion (vestibular disorder, migraine, epilepsy).

### Implementation

```css
/* Default: animations enabled */
@media (prefers-reduced-motion: no-preference) {
  .button {
    transition: all 200ms ease-in-out;
  }
}

/* User has motion preferences: disable animations */
@media (prefers-reduced-motion: reduce) {
  .button {
    transition: none;
  }
}
```

**In Webflow:**
- Check "Auto" under animation duration (respects user setting)
- Or manually create two animation states (with and without motion)

### What to Disable

**Disable for accessibility:**
- Parallax scrolling (causes motion sickness)
- Rapid spinning (triggers seizures)
- Continuous bouncing (distracting)
- Flash rates > 3/second (seizure risk)

**OK to keep subtle:**
- Button hover changes (instant or 100ms max)
- Fade transitions (doesn't cause motion sickness)
- Scroll reveals (gentle, not rapid)

**Rule:** If animation causes motion, provide alternative without it.

---

## When NOT to Animate

**Don't animate if:**
- Animation is purely decorative (no purpose)
- User performance is poor (creates jank)
- Content is critical and motion distracts from reading
- Accessibility impact (vestibular issues)
- Loading is slow on poor connections

**Example bad animation:**
```
Auto-playing hero video that:
- Loads slowly on 3G
- Distracts from reading headline
- Can't be paused by user
- Violates accessibility (no pause option)
❌ Remove this animation
```

**Example good animation:**
```
Button scales 1.05 on hover:
- Provides feedback to user action
- Loads instantly (no performance cost)
- Respects prefers-reduced-motion
- Enhances UX without being essential
✅ Keep this animation
```

---

## Implementation in Webflow

### Hover Interaction (Simple)

1. Select element (button, card, link)
2. Interactions panel > "+" button
3. Trigger: "Mouse over"
4. Action: "Set animations" > Choose animation
5. Common options:
   - **Transform:** Scale (1 to 1.05)
   - **Opacity:** Fade in/out
   - **Background color:** Change color
6. Duration: 200-300ms
7. Easing: ease-in-out
8. Add reverse animation on "Mouse out"

### While-Scrolling Animation (Complex)

1. Create container with height: 600vh
2. Inside: Sticky container (position: sticky, top: 0, height: 100vh)
3. Inside sticky: Elements to animate
4. Select element
5. Interactions > "+" > Trigger: "While scrolling in view"
6. Add animation keyframes:
   - 0%: translateY(32.5vh)
   - 50%: translateY(0)
   - 100%: translateY(-2vh)
7. Set offset to match timing calculation
8. Duration: Automatic (matches scroll distance)
9. Smoothness: 75% (platform default)

### Loading State Animation

1. Select spinner element
2. Interactions > "+" > Trigger: "Page start"
3. Animation: Rotate 360 degrees
4. Duration: 1000ms
5. Easing: linear
6. Set repeat: "Infinite" (loops)
7. On page load complete: Fade out/remove spinner

---

## Common Patterns & Examples

Copy-paste ready animation patterns: fade in on scroll, scale on hover, color changes, slide menu, skeleton loading.

For specific values, timing, and copy-paste animation code, read `references/animation-patterns.md`.

---

## Performance Considerations

### What Animates Fast (GPU)
- `transform` (scale, rotate, translateX/Y/Z)
- `opacity`
- These use GPU acceleration = smooth even with many elements

### What Animates Slow (CPU)
- `width`, `height`
- `left`, `right`, `top`, `bottom`
- `padding`, `margin`
- These cause page reflow = janky

**Rule:** Use transform instead of position/size changes.

**Bad:**
```css
.button:hover {
  width: 200px; /* Causes reflow */
  height: 60px; /* Causes reflow */
}
```

**Good:**
```css
.button:hover {
  transform: scale(1.05); /* GPU accelerated */
}
```

### will-change Property

Hint to browser: "This element will animate"

```css
.button {
  will-change: transform;
}

.button:hover {
  transform: scale(1.05);
}
```

**Remove after animation:**
```css
.button {
  will-change: auto; /* Reset after animation ends */
}
```

---

## Decision Tree: Should I Animate This?

```
User performs action (hover, click, scroll)

1. Does animation provide feedback?
   → YES: Continue
   → NO: Don't animate

2. Is animation <500ms (doesn't delay user)?
   → YES: Continue
   → NO: Reduce duration or skip

3. Does animation respect prefers-reduced-motion?
   → YES: Continue
   → NO: Add accessibility

4. Does animation enhance UX without being essential?
   → YES: Animate ✅
   → NO: Skip or reconsider ❌
```

---

## Contrarian Insights

**Insight 1: Most animations should be removed.**
Counter-intuitive: 80% of animations added to designs aren't needed. Keep only animations that serve clear purpose.

**Insight 2: Micro-interactions matter more than big animations.**
The small 200ms button hover is more noticed and appreciated than grand entrance animations.

**Insight 3: Slow is often better than fast.**
Intuition: Faster = better
Reality: Slower animation (800ms) feels more intentional than fast (200ms)
Test both; slow usually wins.

**Insight 4: Most devices can't handle parallel animations.**
If 20 elements animate simultaneously, devices lag. Stagger animations with 100ms delays instead.

---

## When to Read References

**Read 01_animation_patterns.md if:**
- You need specific fade/slide/scale values
- You're unsure which easing to use
- You want copy-paste animation code

**Read 02_micro_interactions.md if:**
- Designing button/form/loading states
- Need to specify hover behavior
- Building component interactions

**Read 03_scroll_animations.md if:**
- Building while-scrolling effects
- Calculating keyframe offsets
- Setting up 3D depth animations
- Working with large scroll sections

---

## Cross-References

**Related skills:**
- **visual-foundations** — Understand spacing and hierarchy (animations enhance these)
- **ui-components** — Micro-interactions are part of component design
- **webflow-implementation** — Webflow-specific animation tools and limitations
- **web-layout** — Scroll animations work with page structure

---

## Quick Start Scenarios

**"I need a button to respond to hover"**
→ Scale 1 to 1.05, 200ms ease-in-out

**"I want content to fade in as user scrolls"**
→ Opacity 0 to 1, 600ms ease-out on scroll trigger

**"Need a loading spinner"**
→ Rotate 360 degrees infinite, 1000ms linear

**"Form input should highlight when focused"**
→ Border color change + subtle scale, 150ms ease-in-out

**"Mobile menu should slide in from left"**
→ TranslateX -100% to 0, 300ms ease-out

---

**Last Updated:** March 12, 2026
**Source:** Webflow Masterclass 5.1 Pro, Shift Nudge course, Flux Academy
**Status:** Actionable, implementation-ready
