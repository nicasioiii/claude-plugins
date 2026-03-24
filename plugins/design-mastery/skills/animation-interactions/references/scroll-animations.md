# Scroll-Triggered Animations

Content animates as user scrolls down the page. This covers while-scrolling setup, timing calculations, and 3D effects.

## Setup: While-Scrolling Container

Critical pattern from Webflow Masterclass:

```
Section (height: 600vh)
  └── Main Container
      ├── position: sticky
      ├── top: 0
      ├── height: 100vh
      └── Content (animates while section scrolls)
```

**Why this works:**
- Section height = total scroll distance
- Container stays fixed (sticky)
- Content animates as section scrolls behind it

**Height guide:**
- 400vh: ~4 seconds of scrolling (slow animation)
- 600vh: ~6 seconds of scrolling (moderate animation)
- 800vh: ~8 seconds of scrolling (very slow, prolonged)

## Example: Cards Moving In Order

**Setup:**
```
Section: 600vh height
6 cards arranged vertically
Each card starts below viewport (Y = 32.5vh)
Each card animates to center (Y = 0) as section scrolls
```

**Keyframe distribution:**
- Base: 100% ÷ 6 cards = 16.67% per card
- Adjust: 9%, 27%, 45%, 63%, 81%, 99% (fine-tuned)

**Card 1 animation:**
- Keyframe 9%: Y = 32.5vh (off-screen below)
- Keyframe 27%: Y = 0 (center, visible)
- Keyframe 45%: Y = -1vh (moving up slightly)

**Card 2 animation:**
- Keyframe 27%: Y = 65vh (starts lower)
- Keyframe 45%: Y = 0 (enters center)
- Keyframe 63%: Y = -1vh (moving up)

Each card has 18% of timeline to complete its animation.

## While-Scrolling Timing Calculation

**Formula:**
```
If section = 600vh, want animation to end at last 100vh:
Offset = (100vh ÷ 600vh) × 100 = 16.6%
Animation runs from 0% to 83.4% (ends at 16.6% from bottom)
```

**Practical example:**
```
Section height: 600vh
Want last 100vh free (no animation): 100 ÷ 600 = 16.6%
Animation timeline: 0% to 83.4%
Cards fade out in final 16.6%
```

## 3D Transform Depth Effect

Add depth with 3D transforms during scroll:

```
Element starts: perspective 1200px, rotateX(45deg), translateZ(-500px)
Element animates: rotateX(0), translateZ(0)
Duration: Entire scroll animation
Result: Element "flips in" and moves closer to viewer
```

**Use cases:**
- Product showcase animations
- Image galleries with depth
- Parallax effects with perceived depth

**Key properties:**
- `perspective`: Parent container (1200px standard)
- `rotateX/Y/Z`: 3D rotation axis
- `translateZ`: Distance from viewer (positive = closer, negative = farther)
- `transform-style: preserve-3d`: Keep 3D effect on child elements
