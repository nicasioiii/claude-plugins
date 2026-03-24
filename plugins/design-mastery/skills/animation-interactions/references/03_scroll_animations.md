# Scroll-Triggered Animations & While-Scrolling Effects

## Container Architecture (Critical)

All while-scrolling animations require this exact structure:

```
Section (height: 600vh)
  └── Main Container
      ├── position: sticky
      ├── top: 0
      ├── height: 100vh
      └── Content (elements that animate)
```

**Why this structure works:**
- **Section height** = total scroll distance (600vh = 6x viewport heights)
- **Sticky positioning** keeps container fixed while section scrolls behind it
- **Content inside** animates as section scrolls
- **100vh container** = viewport height (visible area)

---

## Height Calculation Guide

**Section height determines animation speed.**

```
Height: 400vh
Effect: Slow, prolonged animation (~4 seconds of scrolling)

Height: 600vh (STANDARD)
Effect: Moderate animation (~6 seconds of scrolling)

Height: 800vh
Effect: Very slow, elongated animation (~8 seconds)

Height: 1200vh
Effect: Extremely long (12 seconds, rarely used)
```

**Choose based on animation complexity:**
- Simple fade: 400-600vh
- Multi-step animation: 600-800vh
- Complex 3D: 800-1200vh

---

## Keyframe Distribution (6 Cards Example)

### Basic Distribution

**Formula:** 100% ÷ number of elements = % per element

```
6 cards
100% ÷ 6 = 16.67% per card

Keyframes:
Card 1: 0% - 16.67%
Card 2: 16.67% - 33.33%
Card 3: 33.33% - 50%
Card 4: 50% - 66.67%
Card 5: 66.67% - 83.33%
Card 6: 83.33% - 100%
```

### Fine-Tuned Distribution (For Visual Polish)

Adjust so first card starts slightly visible, last card ends visible:

```
Adjust by: ±1-2% per card

Refined keyframes:
Card 1: 8% - 26%     (first visible early)
Card 2: 27% - 45%
Card 3: 46% - 64%
Card 4: 65% - 83%
Card 5: 84% - 100%+  (final visible)
Card 6: 101%+ (ends off-screen)

OR simpler:
9%, 27%, 45%, 63%, 81%, 99%
(spread across full range)
```

---

## Transform Values (Y Axis Movement)

### Starting Position (Off-Screen Below)

Elements start below viewport and animate upward.

```
Viewport height: 100vh
Container padding: 10vh (top space)
Title height: 25vh

Available space: 100vh - 10vh - 25vh = 65vh

Card half-visible below:
Needs: -32.5vh Y offset (half the available space)

Formula: -(available space ÷ 2) = starting position
```

### Animation Sequence (Single Card)

```
Keyframe 9%:    translateY(32.5vh)   ← Off-screen, below
Keyframe 27%:   translateY(0)         ← Center, visible
Keyframe 45%:   translateY(-1vh)      ← Slightly above
```

**Interpretation:**
- 9%: Card starts below (32.5vh down)
- 27%: Card reaches center (0 = center position)
- 45%: Card exits upward (-1vh = moving up)

---

## While-Scrolling Animation Example: 6 Cards

**Setup:**
- Section: 600vh height
- 6 cards total
- Each card: 18% of animation timeline
- Refined keyframes: 9%, 27%, 45%, 63%, 81%, 99%

**Card 1 Animation:**
```
Keyframe 9%:
  opacity: 0
  transform: translateY(32.5vh)

Keyframe 27%:
  opacity: 1
  transform: translateY(0)

Keyframe 45%:
  opacity: 0.8
  transform: translateY(-1vh)
```

**Card 2 Animation:**
```
Keyframe 27%:
  opacity: 0
  transform: translateY(32.5vh)

Keyframe 45%:
  opacity: 1
  transform: translateY(0)

Keyframe 63%:
  opacity: 0.8
  transform: translateY(-1vh)
```

**Pattern continues:** Each card starts where previous card's first keyframe was

---

## 3D Depth Effect (Z-Axis)

Add depth perception as cards animate.

### Setup

```
Parent container: perspective(3000px)
(Tells browser: 3D perspective 3000px away)
```

### Card Animation with Depth

```
Keyframe 9%:
  translateZ(0)        ← In plane (viewer's plane)
  translateY(32.5vh)

Keyframe 27%:
  translateZ(-4vh)     ← Move away (into page)
  translateY(0)

Keyframe 45%:
  translateZ(-8vh)     ← Even farther away
  translateY(-1vh)
```

**Effect:**
- As card moves up, it also moves back in 3D space
- Creates illusion of depth/distance
- Cards appear to recede into background

### Z-Values Guide

```
0:     On viewer plane (closest)
-4vh:  Moderately far
-8vh:  Quite far
-12vh: Very far
-16vh: Distant

Use progressive values for visual hierarchy:
Card 1: 0 → -4vh
Card 2: 0 → -8vh
Card 3: 0 → -12vh
etc.
```

---

## Overlay Darkening (Optional Polish)

Darken background as cards move back in depth.

```
Background element opacity:
  0%:    rgba(0,0,0,0)      ← Transparent
  50%:   rgba(0,0,0,0.08)   ← Slightly dark
  100%:  rgba(0,0,0,0.15)   ← More visible

Timing: Keyframes should match card animation
```

**Effect:**
- Provides depth cue
- Makes cards feel like they're going into background
- Subtle, shouldn't dominate

---

## Offset Calculation (Advanced)

**Problem:** Animation should end before user reaches bottom

**Formula:**
```
If section = 600vh, want final 100vh to have no animation:

Offset = (free space ÷ total height) × 100
Offset = (100vh ÷ 600vh) × 100 = 16.6%

Animation runs: 0% to 83.4%
User scrolls: 83.4% to 100% (final 16.6%) without animation
```

**Application:**
- Set animation start offset: 0%
- Set animation end offset: 83.4%
- Final 16.6% is free (no animation)

---

## Webflow Implementation Steps

### 1. Create Section with Height

```
Section element
- Set height: 600vh (or 400/800 as needed)
- Background: white or neutral (won't be visible)
- Padding: 0
```

### 2. Create Sticky Container

```
Inside section, create div:
- Display: sticky
- Top: 0
- Height: 100vh
- Width: 100%
- Overflow: hidden (important, contains animated content)
```

### 3. Add Content to Sticky Container

```
Inside sticky container:
- Padding: 10vh 20px (top/bottom padding, sides)
- Create cards/content

Each card:
- Width: calc(100% - 40px) or 100%
- Height: auto or fixed
- Position: relative (for animations)
```

### 4. Set Up Animation

Select first card:
```
Interactions > "+"
Trigger: "While scrolling in view"
Action: Animate

Keyframe 9%:
  Opacity: 0%
  Transform: translateY(32.5vh) translateZ(0)

Keyframe 27%:
  Opacity: 100%
  Transform: translateY(0) translateZ(-4vh)

Keyframe 45%:
  Opacity: 80%
  Transform: translateY(-1vh) translateZ(-8vh)
```

Duration: Leave on "Auto" (matches scroll)
Smoothness: 75% (platform default)

### 5. Repeat for Remaining Cards

Copy same animation structure, shift keyframes:
- Card 2: 27%, 45%, 63%
- Card 3: 45%, 63%, 81%
- Card 4: 63%, 81%, 99%
- etc.

---

## Fade In on Scroll (Simpler Alternative)

**Setup:**
```
Section: 400vh
No sticky container needed

Element:
Trigger: "While scrolling in view"
Animation:
  0%: opacity 0
  50%: opacity 1
  100%: opacity 1
```

**Timing:** Automatic (matches scroll)

**Effect:** Element fades in as user scrolls to it

---

## Performance Optimization

### Mobile Considerations

While-scrolling animations can be laggy on mobile.

**Solutions:**
1. Reduce section height (400vh instead of 600vh)
2. Fewer simultaneous animations (4 cards instead of 8)
3. Simpler transforms (just translateY, no 3D)
4. Test on actual mobile device (browser dev tools not accurate)

### GPU Acceleration

Ensure smooth animation:
```
Use only:
- transform: translateY, translateZ
- opacity

Avoid:
- width/height changes
- left/right positioning
- padding/margin changes
```

### will-change Property

```
.card {
  will-change: transform, opacity;
}

(Use only during animation, remove after)
```

---

## Timing Reference

**Common animations (600vh section):**

```
Single card movement:
Duration: 18% of timeline
= 0.18 × 6 seconds scroll = ~1 second animation per card

6 cards visible over full scroll:
Each card has 1 second to animate while visible
Total scroll time: ~6 seconds

Fast scroll: Animation smoother
Slow scroll: Animation plays out in detail
```

---

## Troubleshooting

**Problem: Animation doesn't appear**
- Check: Section height > 100vh
- Check: Sticky container has position: sticky + top: 0
- Check: Animation start offset < 50%

**Problem: Animation too fast**
- Increase section height (400vh → 600vh)
- Animation stretches over longer scroll distance

**Problem: Animation too slow**
- Decrease section height (600vh → 400vh)
- Animation compresses into shorter scroll distance

**Problem: Cards don't align**
- Check: Container has overflow: hidden
- Check: Cards have same width
- Check: No margin between cards (or account for it)

**Problem: Laggy on mobile**
- Reduce: Section height (400vh)
- Reduce: Number of animated elements
- Simplify: Remove 3D transforms (Z-axis)
- Test: On real device (not browser dev tools)

---

## Real-World Example: ACE Project

**Setup:**
- Section: 600vh
- 6 testimonial cards
- Viewport: 100vh
- Padding top: 10vh
- Title height: 25vh

**Available space:** 65vh

**Starting position:** -32.5vh (half available)

**Card 1:**
- 9%: Y=32.5vh (off-screen below), opacity 0
- 27%: Y=0 (center), opacity 1, Z=0
- 45%: Y=-1vh (exiting), opacity 0.8, Z=-4vh

**Card 2:**
- 27%: Y=32.5vh (starts below)
- 45%: Y=0 (enters center)
- 63%: Y=-1vh (exits), Z=-4vh

**Pattern continues** through Card 6

**Result:** Testimonials flow upward, each entering and exiting as user scrolls

---

**Last Updated:** March 12, 2026
**Source:** Webflow Masterclass 5.1 Pro, Ran Segall course materials
