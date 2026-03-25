---
name: Scroll Animation Techniques
description: "4 scroll techniques (continuous, trigger, presets, GSAP), nav background pattern, logo shrink, card stagger, marquee, preloader."
---

# Scroll Animation Techniques

Detailed setup guides for the four scroll animation approaches in Webflow, plus specific animation patterns.

---

## TECHNIQUE 1: WHILE PAGE IS SCROLLING (Continuous)

### How It Works
- Animation progress maps to scroll position: 0% at element top, 100% at element bottom
- Plays forward on scroll down, backward on scroll up, pauses when stopped
- Creates intermediate states at every scroll position

### Setup in Webflow
1. Select element to animate
2. Interactions panel > While scrolling in view
3. Set animation boundaries:
   - Start: when element is fully visible (or custom offset)
   - End: when element is fully invisible (or custom offset)
4. Add keyframes:
   - 0% position: starting state (e.g., opacity 0, translateY 40px)
   - 100% position: ending state (e.g., opacity 1, translateY 0)
5. Smoothing: 60-75%

### When to Use
- Background color transitions
- Decorative parallax layers
- Progress indicators
- Scale/rotation effects on decorative elements

### When NOT to Use
- Nav background changes (intermediate opacity looks broken)
- Element visibility toggles (half-visible states are ugly)
- Anything requiring a clean on/off state

---

## TECHNIQUE 2: ELEMENT SCROLLS INTO VIEW (Trigger)

### How It Works
- Define a trigger section
- When that section enters the viewport, animation plays to completion
- Animation reaches final state cleanly -- no intermediate issues
- Can set offset to delay trigger

### Setup in Webflow
1. Select trigger element (usually a section)
2. Interactions panel > Scroll into view
3. Set offset: 20% (trigger fires when 20% of section is visible)
4. Add animation:
   - Start state: opacity 0, transform translateY 40px
   - End state: opacity 1, transform translateY 0
5. Duration: 0.3-0.6s
6. Easing: ease-out

### Nav Background Pattern (Detailed)
**Goal:** Transparent nav over hero, solid nav after scrolling past hero.

1. Select the section BELOW the hero as trigger
2. Offset: 20%
3. Animate the navbar element:
   - Background color: rgba(0,0,0,0) to rgba(255,255,255,1) [transparent to solid]
   - Duration: 0.3s
4. Simultaneously animate logo:
   - Color: white to black (or vice versa)
5. **Why this works:** Clean binary state change. No 50%-opacity nav on scroll.
6. **Critical for mobile:** Hamburger menu inherits the current nav state. If nav is at 50% opacity from continuous scroll, mobile menu looks broken.

### Card Stagger Pattern (Detailed)
**Goal:** Cards reveal one after another as section scrolls into view.

1. Apply trigger to the cards' parent section
2. Card 1: offset 10%, delay 0ms
3. Card 2: offset 10%, delay 200ms
4. Card 3: offset 10%, delay 400ms
5. Each card animation:
   - Start: opacity 0, translateY 30px
   - End: opacity 1, translateY 0
   - Duration: 0.5s, ease-out

---

## TECHNIQUE 3: WEBFLOW PRESETS

### Available Presets
- Slide from bottom
- Slide from left
- Slide from right
- Grow big (scale)
- Spin
- Fade in

### Setup
1. Select element
2. Interactions panel > Animation presets
3. Choose preset
4. Adjust: duration, delay, easing

### Stagger with Presets
Apply same preset to multiple elements with incremental delays:
- Element 1: 0ms delay
- Element 2: 200ms delay
- Element 3: 400ms delay
- Element 4: 600ms delay

**Best for:** Quick wins on simple sites. Card grids, feature sections, testimonials.

---

## TECHNIQUE 4: GSAP + CUSTOM ATTRIBUTES (Reusable)

### How It Works
- Add custom attribute to any element (e.g., `animation="slide-up"`)
- GSAP scroll trigger targets the attribute name
- Configure animation properties once
- Reapply to any element by adding the same attribute

### Setup in Webflow
1. Select element > Settings panel > Custom Attributes
2. Add: Name = `animation`, Value = `slide-up`
3. Interactions panel > GSAP icon
4. Create scroll trigger:
   - Target: elements with attribute `animation="slide-up"`
   - Start state: opacity 0, translateY 40px
   - End state: opacity 1, translateY 0
   - Duration: 0.5s
   - Easing: power-out-3
   - Mode: Trigger (not Scrub)
5. Enable markers for debugging (disable before publishing)

### Why GSAP for Large Sites
- One animation definition, unlimited elements
- Change the animation once, all instances update
- No per-element interaction configuration
- More performant than Webflow's native system for many elements
- power-out-3 easing: fast start, gentle deceleration (feels natural)

### GSAP Scrub vs. Trigger
| Mode | Behavior | Use For |
|------|----------|---------|
| Scrub | Tied to scroll position, plays/reverses with scroll | Decorative effects, progress bars |
| Trigger | Plays once when scroll threshold is reached | Content reveals, card staggers |

---

## SPECIFIC PATTERNS

### Logo Shrink Into Navbar

**Goal:** Large centered logo shrinks into navbar position as user scrolls.

**Structure:**
```
Hero section frame: height 200vh (creates scroll room)
  Hero section: position sticky, height 100vh
    Big logo wrapper: display flex, align center, height 100vh, relative
      Logo embed: height in vh units
    Navbar: position absolute, top-aligned, height in vh
```

**Animation (while scrolling in view):**
- Logo height: 20vh to 5vh
- Big logo wrapper height: 100vh to navbar height (e.g., 9vh)

**Critical Rules:**
- Final wrapper height MUST equal navbar height (for perfect centering)
- Use same vh units throughout (Webflow can't animate between unit types)
- Smoothing: 60%
- Animation boundaries: starts when fully visible, ends when fully invisible (50% offset)

### Infinite Marquee

**Structure:**
- Outer container: overflow hidden, fixed width
- Inner strip: display flex, duplicate content 2-3x
- Animate: translateX from 0 to -(strip width / duplicates)

**Finsweet solution:** "Infinite draggable marquee with stop on hover" -- no custom code, attributes only.

### Pre-loader

**Structure:**
- Full-screen overlay (z-index above everything)
- Lottie animation or custom animation inside
- On page load trigger:
  1. Play Lottie animation
  2. After animation completes: fade out overlay (opacity 0, 0.5s)
  3. Set overlay to display none

**Logo contour animation:** Use Lottie creator to generate animated logo outline. Upload .json to Webflow.

### Horizontal Scroll Section
See `webflow-build` > `references/02-flexbox-positioning.md` for the structural setup. Animation ties scroll position to horizontal translateX of the cards container.

---

## ANIMATION TIMING CHEAT SHEET

### Quick Reference Values
```
Button hover:        200ms   ease-out
Card lift:           300ms   ease-out
Input focus:         150ms   ease-out
Fade in (entrance):  600ms   ease-out
Slide up (entrance): 600ms   ease-out
Scroll trigger:      500ms   power-out-3 (GSAP)
Stagger delay:       200ms   between items
Nav bg change:       300ms   ease-out
Modal enter:         300ms   ease-out
Modal exit:          250ms   ease-in
Toast enter/exit:    300ms   ease-out
Spinner:             1000ms  linear (infinite)
Preloader fadeout:   500ms   ease-out
```

### Duration Rules
- Under 150ms feels instant (imperceptible)
- 150-300ms feels responsive (micro-interactions)
- 300-600ms feels smooth (entrances, transitions)
- 600-1000ms feels deliberate (prominent reveals)
- Over 1000ms feels slow (avoid unless spinner/loader)
