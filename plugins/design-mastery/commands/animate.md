---
name: Animate
description: Design and implement animation patterns for web projects. Covers scroll animations, Lottie, GSAP, Spline, hover states, preloaders, and motion accessibility.
skill: webflow-animations
---

# /animate

You are helping the user add animations and interactions to a web project. Follow this workflow:

## Step 1: Understand the Animation Need

Ask the user:
1. **What needs animating?** (page entrance, scroll reveals, hover states, loading, navigation)
2. **What platform?** (Webflow native, custom code with GSAP, Lottie files, Spline 3D)
3. **What is the motion style?** (subtle/professional, bold/playful, cinematic, minimal)
4. **Any performance constraints?** (mobile priority, slow connections, heavy page)
5. **Accessibility requirements?** (prefers-reduced-motion support needed?)

## Step 2: Choose Animation Type

| Animation Type | Tool | Best For |
|---------------|------|---------|
| Scroll reveals | Webflow Interactions | Section entrances, fade-in-up patterns |
| Parallax | Webflow scroll trigger | Depth effects on scroll |
| Hover states | Webflow hover interaction | Buttons, cards, links, images |
| Lottie | Lottie files + Webflow | Icons, illustrations, micro-interactions |
| Complex sequences | GSAP via custom code | Timeline-based, staggered reveals, text splits |
| 3D elements | Spline | Interactive 3D objects, backgrounds |
| Preloaders | Webflow page load trigger | Initial page entrance experience |
| Marquees | Webflow or GSAP | Infinite horizontal scrolling text or logos |

## Step 3: Define Timing and Easing

Core timing principles:
- **Duration:** 200-400ms for micro-interactions, 600-1000ms for section reveals
- **Easing:** Ease-out for entrances, ease-in for exits, ease-in-out for movement
- **Delay:** Stagger elements by 50-100ms for sequential reveals
- **Never exceed 1.5s** for a single animation unless cinematic intent

Common easing curves:
- **Ease-out (decelerate):** Most natural for elements appearing
- **Ease-in-out:** Smooth for elements moving position
- **Spring/bounce:** Playful, use sparingly
- **Linear:** Only for infinite loops (marquees, spinners)

## Step 4: Implement the Pattern

For Webflow scroll animations:
1. Select the trigger element (section or component)
2. Set trigger type: scroll into view, while scrolling, page load
3. Define initial state (opacity 0, translateY 20px)
4. Define final state (opacity 1, translateY 0)
5. Set duration and easing
6. Test at multiple scroll speeds

For hover interactions:
1. Set initial and hover states
2. Keep transitions under 300ms
3. Ensure the hover state is reversed on mouse-out
4. Add subtle transform (scale 1.02-1.05) for cards and images

## Step 5: Accessibility

- Respect `prefers-reduced-motion` media query
- Provide alternative for motion-sensitive users (reduce or remove animations)
- Never rely on animation alone to convey critical information
- Avoid flashing content (3+ flashes per second)
- Provide controls for auto-playing content

## Step 6: Performance Check

- Animate only `transform` and `opacity` properties (GPU-accelerated)
- Avoid animating `width`, `height`, `margin`, `padding` (triggers layout recalculation)
- Compress Lottie JSON files
- Lazy-load Spline scenes and heavy assets
- Test animation performance on mobile devices

## Step 7: Recommend Next Steps

- If layout needs work → recommend `/homepage-structure`
- If build is not started → recommend `/webflow-build`
- If ready for review → recommend `/design-audit`

## Skills Activated

- **webflow-animations** (primary)
- Cross-references: webflow-build, web-layout, ui-components
