---
name: Webflow Animations
description: "Animations, interactions, scroll animations, Lottie, GSAP, Spline, timing/easing, hover states, preloaders, marquees, staggered reveals, accessibility, and motion design principles. Synthesizes Ran Segall (Flow Gurus), Arash (Figma UI Design), and Matt Jumper (Flux) approaches. MANDATORY TRIGGERS: animation, animate, scroll animation, Lottie, GSAP, Spline, hover state, preloader, marquee, parallax, scroll trigger, easing, timing, micro-interaction, motion design, page transition, stagger, reveal animation, 3D web. FOR: Adding motion to Webflow sites, designing scroll-triggered animations, implementing Lottie/GSAP/Spline, creating hover effects, preloaders, infinite marquees, accessibility for motion. Do NOT use for Webflow build fundamentals (layout, CMS, responsive) — use webflow-build instead. Do NOT use for Figma prototyping only — use design-systems instead. Do NOT use for UI component state design — use ui-components instead."
---

# Webflow Animations

Strategic use of motion to enhance user experience. This skill covers when, why, and how to animate in Webflow -- from simple hover states to GSAP-powered scroll sequences and 3D Spline integrations.

---

## CORE PRINCIPLE: EVERY ANIMATION MUST EARN ITS PLACE

**The Rule:** Never animate just because you can. Every animation must serve one of four purposes:

1. **Feedback** -- user action gets a response (button press, form focus)
2. **Guidance** -- animation directs attention where to look
3. **Transition** -- smooths visual change between states
4. **Delight** -- subtle personality (only after other purposes are met)

**Animation that fails:**
- Decorative movement with no purpose
- Parallax that makes the page feel slow
- Auto-playing video that interrupts reading
- Rapid or spinning movement that triggers vestibular issues

**When to add animations:** Step 8 of the build process. Site must be fully built and functional first. See `webflow-build` skill.

---

## TIMING & EASING QUICK REFERENCE

### Duration by Animation Type

| Type | Duration | Use Case |
|------|----------|----------|
| Hover feedback | 150-200ms | Button hover, link underline |
| Click response | 200ms | Button press, checkbox |
| Focus state | 150ms | Form input focus |
| Entrance (fade) | 400-600ms | Hero section, cards appearing |
| Entrance (slide) | 600ms | Slide up/in on load |
| Scroll trigger | 600-800ms | Fade on scroll, slide on scroll |
| Stagger delay | 100-200ms increment | Sequential card reveals |
| Loading spinner | 1000ms loop | Infinite rotation |
| Toast notification | 300ms enter/exit | 3000ms visible between |
| Modal entrance/exit | 300ms | Slide up + fade |

### Easing Functions

| Easing | Feel | Best For |
|--------|------|----------|
| `linear` | Constant, robotic | Spinners, continuous loops |
| `ease-out` | Fast start, slow end | Entrances, hover states |
| `ease-in` | Slow start, fast end | Exits, dismissals |
| `ease-in-out` | Slow both ends | Medium interactions, while-scrolling |
| `power-out-3` (GSAP) | Fast start, gentle deceleration | Scroll-triggered reveals |

**Default recommendation:** `ease-out` for most interactions. `power-out-3` for GSAP scroll triggers.

---

## FOUR SCROLL ANIMATION TECHNIQUES

### Technique 1: While Page Is Scrolling (Continuous)

Ties animation progress to scroll position (0% at top, 100% at bottom). Plays forward on scroll down, backward on scroll up, pauses when scroll stops.

**Problem:** Creates intermediate states (e.g., nav background at 50% opacity) that cause issues with other interactions.

**Best for:** Simple decorative effects where intermediate states are acceptable.

**Setup:**
- Select element to animate
- Interactions > While scrolling in view
- Set start keyframe (e.g., opacity 0) and end keyframe (e.g., opacity 1)
- Smoothing: 60-75% for responsive feel without lag

### Technique 2: Element Scrolls Into View (Trigger)

Select a section as trigger. When it scrolls into view, play a defined animation to completion.

**Best for:** Nav background changes, element reveals where you need a definitive end state. Animation reaches final state cleanly -- no intermediate issues.

**Setup:**
- Select trigger section
- Interactions > Scroll into view
- Offset: 20% (delays trigger until element is partially visible)
- Duration: 0.3-0.6s
- Easing: ease-out

### Technique 3: Webflow Presets

Pre-built animations: slide from bottom, slide from left, grow big, spin, fade in.

**Best for:** Quick section reveals and card staggering. Apply with a few clicks.

**Stagger pattern:**
- Element 1: offset 10%, delay 0ms
- Element 2: offset 10%, delay 200ms
- Element 3: offset 10%, delay 400ms

### Technique 4: GSAP + Custom Attributes (Reusable)

Add a custom attribute (e.g., `animation="slide-up"`) to any element. In GSAP interactions panel, create a scroll trigger targeting that attribute.

**Best for:** Scaling animations across large sites with many repeating elements. Configure once, reapply by adding the attribute.

**Setup:**
- GSAP panel > Create scroll trigger targeting attribute name
- Duration: 0.5s
- Easing: power-out-3
- Mode: Trigger (plays once, not tied to scroll position)
- Markers: enable for debugging, hide before publishing

For full technique details and code patterns, see `references/01-scroll-animation-techniques.md`.

---

## SPECIFIC ANIMATION PATTERNS

### Nav Background on Scroll
- Trigger: "element scrolls into view" on section below hero
- Offset: 20%
- Animate: nav background transparent to solid (0.3s)
- Animate: logo color white to black simultaneously
- This gives a clean final state -- critical for mobile hamburger menu

### Scroll-Triggered Logo Shrink Into Navbar
- Hero section frame: height 200vh (scroll room while hero sticks)
- Hero section: position sticky, height 100vh
- Big logo wrapper: display flex, align center, height 100vh
- Animation: while scrolling, logo height from 20vh to 5vh
- Big logo wrapper height: 100vh to navbar height (e.g., 9vh)
- **Critical:** Final wrapper height MUST equal navbar height for centering
- Use same vh units throughout (Webflow can't animate between unit types)
- Smoothing: 60%

### Staggered Card Reveals
- Apply scroll-into-view trigger to each card
- Card 1: offset 10%, no delay
- Card 2: offset 10%, delay 200ms
- Card 3: offset 10%, delay 400ms
- Creates sequential reveal effect

### Infinite Marquee
- Duplicate content strips inside a flex container
- Animate with continuous horizontal movement
- Finsweet: "infinite draggable marquee with stop on hover" (attributes only, no custom code)

### Pre-loader Animation
- Full-screen overlay with Lottie animation
- On page load: play animation, then fade out overlay
- Use Lottie creator for logo contour animations

---

## ANIMATION TOOLS

### Lottie
- Lightweight vector animations (.json format)
- Natively supported in Webflow
- Controllable via Webflow's scroll/trigger system
- **AI workflow:** Upload reference image to ChatGPT, describe desired animation, request .json file. Iterate on prompt. Preview at lottiefiles.com before importing

### Spline (3D for Web)
- 3D models with interactivity (mouse tracking, scroll control)
- Natively supported in Webflow
- AI generation: prompt-based model creation
- Customize textures in Photoshop
- Set z-index 1 (between background z-0 and content z-2)

### GSAP (GreenSock)
- Code-based animation library being integrated natively into Webflow
- Powers most award-winning websites
- Access via interactions panel (GSAP icon)
- Scroll triggers targeting custom attributes (not just classes)
- Scrub mode (tied to scroll) vs. Trigger mode (plays once)
- Easing: power-out-3 recommended

### Rive
- Combined Lottie + interactivity
- More useful for apps/games than web design
- Embeddable in Webflow

### Unicorn Studio
- WebGL effects with no-code interface
- Paid tool, embeddable in Webflow

### Three.js
- Full JavaScript 3D framework (what Spline uses under the hood)
- Requires coding but AI can help generate code
- Out of scope for most Webflow projects

For tool-specific setup guides, see `references/02-animation-tools.md`.

---

## WEBFLOW VARIABLES FOR ANIMATION

- Create variables in Variables panel (e.g., "navbar-padding" as percentage)
- Link variables to element properties (click purple dot in style panel)
- Animate variables in interaction timeline
- Changes reflect on all linked properties
- Powerful for responsive, dynamic animation values

---

## HOVER STATE DESIGN

### Button Hover
```
Default:  scale 1, opacity 1
Hover:    scale 1.02, opacity 0.9, shadow added
Timing:   200ms ease-out
```

### Card Hover (Lift)
```
Default:  translate-Y 0, minimal shadow
Hover:    translate-Y -4px to -8px, shadow 8-12px blur
Timing:   300ms ease-out
```

### Link Underline Expand
```
Default:  underline width 0
Hover:    underline expands to full width
Timing:   200ms ease-out
```

### Image Zoom on Hover
```
Default:  scale 1, overflow hidden on parent
Hover:    scale 1.05-1.1
Timing:   400ms ease-out
```

---

## ACCESSIBILITY FOR MOTION

### prefers-reduced-motion
Some users have motion sensitivity or vestibular issues. Always respect their OS setting:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

In Webflow: use conditional visibility or custom code to disable animations for users who prefer reduced motion.

### What NOT to Animate
- Flashing content (>3 flashes per second = seizure risk)
- Extreme motion (large parallax, rapid jitter)
- Constantly moving elements (auto-playing carousels)
- Unexpected surprise animations

### Safe Animations
- Subtle fade and scale (under 500ms)
- Scroll-triggered entrance (user-initiated via scroll)
- Hover effects (user controls timing)
- Loading indicators (expected)
- State transitions (button clicks, form validation)

---

## PERFORMANCE

### GPU-Accelerated Properties (Use These)
- `transform: translate()` -- move element
- `transform: scale()` -- resize
- `transform: rotate()` -- spin
- `opacity` -- fade

### CPU-Expensive Properties (Avoid Animating)
- `position: left/top/right/bottom` -- causes layout reflow
- `width/height` -- causes layout reflow
- `margin/padding` -- causes layout reflow

**Rule:** Animate `transform` and `opacity` only. Use `will-change: transform` to hint browser optimization.

---

## ANIMATION DECISION TREE

```
Does the animation help the user understand something?
├── YES: Animate
│   ├── Fast feedback (hover, click)? → 150-250ms, ease-out
│   └── Content appearance? → 400-800ms, ease-out
└── NO: Does it add delight without hurting UX?
    ├── YES: Very subtle only (short duration, small movement)
    └── NO: Don't animate
```

---

## ANTI-PATTERNS

- Animating before the site is fully built (step 8, not step 1)
- Every element fading in on scroll (overwhelming, slows perceived performance)
- Parallax that makes the page feel sluggish
- Linear easing for entrances (feels robotic)
- Animating layout-affecting properties (width, height, margin)
- Infinite spinning logos
- No exit animation for modals/tooltips (abrupt disappearance)
- Ignoring prefers-reduced-motion
- Over-animating -- practice restraint

---

## RELATED SKILLS

- **webflow-build:** For the build process this animation enhances (step 8 of 10)
- **web-layout:** For layout decisions that determine which sections get animation
- **ui-components:** For component state animations (button states, form focus)
- **design-systems:** For Figma prototyping and interactive component design
- **design-critique:** For reviewing animation quality and restraint
