# Animation Patterns & Timing Reference

## Fade In (Most Common)

**Use case:** Content appears on page load or scroll

```css
/* CSS */
@keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

.element {
  animation: fadeIn 600ms ease-out;
}

/* Webflow */
- Trigger: On scroll / On page load
- Animation: Opacity 0% → 100%
- Duration: 600ms
- Easing: ease-out
```

**Timing:**
- Fast: 300-400ms (snappy)
- Standard: 600ms (comfortable)
- Slow: 800-1000ms (deliberate)

**Variations:**
- Fade + Slide: Opacity 0→1 + translateY(20px)→(0)
- Fade + Scale: Opacity 0→1 + scale(0.9)→(1)

---

## Slide In (Directional)

**From left:**
```css
@keyframes slideInLeft {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(0); }
}
```

**From right:**
```css
@keyframes slideInRight {
  0% { transform: translateX(100%); }
  100% { transform: translateX(0); }
}
```

**From top:**
```css
@keyframes slideInTop {
  0% { transform: translateY(-50px); }
  100% { transform: translateY(0); }
}
```

**From bottom:**
```css
@keyframes slideInBottom {
  0% { transform: translateY(50px); }
  100% { transform: translateY(0); }
}
```

**Timing:** 600-800ms ease-out (entrance)

**Common use:**
- Menu slide-in: 300ms from left
- Content reveal: 600ms from bottom
- Sidebar: 300-400ms from left

---

## Scale / Zoom

**Grow (enlarge):**
```css
@keyframes scaleUp {
  0% { transform: scale(0.9); }
  100% { transform: scale(1); }
}
.element {
  animation: scaleUp 400ms ease-out;
}
```

**Shrink (reduce):**
```css
@keyframes scaleDown {
  0% { transform: scale(1.1); }
  100% { transform: scale(1); }
}
```

**Hover scale (interactive):**
```css
.button:hover {
  transform: scale(1.05);
  transition: transform 200ms ease-in-out;
}
```

**Values:**
- scale(0.9): 10% smaller
- scale(1.05): 5% larger (standard hover)
- scale(1.1): 10% larger (noticeable)
- scale(1.2): 20% larger (exaggerated)

---

## Rotate / Spin

**Full rotation (360°):**
```css
@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

.spinner {
  animation: spin 1000ms linear infinite;
}
```

**Timing:**
- Fast spinner: 800ms (1 rotation / 0.8s)
- Standard spinner: 1000ms (1 rotation / 1s)
- Slow spinner: 1500ms (1 rotation / 1.5s)

**Easing:** Always linear for continuous rotation

**Partial rotation (entrance):**
```css
@keyframes rotateIn {
  0% { transform: rotate(-10deg); opacity: 0; }
  100% { transform: rotate(0deg); opacity: 1; }
}
```

---

## Color Change

**Background color:**
```css
.button {
  background-color: #0066FF;
  transition: background-color 200ms ease-in-out;
}

.button:hover {
  background-color: #0052CC;
}
```

**Text color:**
```css
.link {
  color: #0066FF;
  transition: color 200ms ease-in-out;
}

.link:hover {
  color: #0052CC;
}
```

**Multiple properties:**
```css
.button {
  background-color: #0066FF;
  color: white;
  box-shadow: none;
  transition: all 200ms ease-in-out;
}

.button:hover {
  background-color: #0052CC;
  box-shadow: 0 10px 30px rgba(0,0,0,0.15);
}
```

**Timing:** 150-200ms (fast interaction)
**Easing:** ease-in-out (responsive feel)

---

## Combination Animations

**Fade + Slide (Most Polished):**
```css
@keyframes fadeSlideIn {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
```

**Timing:** 600ms ease-out

**Use:** Card entrance, section reveal

---

**Scale + Fade (Elegant):**
```css
@keyframes scaleInFade {
  0% {
    opacity: 0;
    transform: scale(0.9);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}
```

**Timing:** 500ms ease-out

**Use:** Modal appear, emphasis

---

**Color + Shadow (Interactive):**
```css
.button {
  background-color: #0066FF;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  transition: all 200ms ease-in-out;
}

.button:hover {
  background-color: #0052CC;
  box-shadow: 0 10px 30px rgba(0,0,0,0.2);
}
```

**Timing:** 200ms (instant feedback)

---

## Timing Quick Reference Table

| Animation | Duration | Easing | Use |
|-----------|----------|--------|-----|
| Button hover | 200ms | ease-in-out | Immediate response |
| Form focus | 150ms | ease-in-out | Quick highlight |
| Fade entrance | 600ms | ease-out | Content appears |
| Slide entrance | 600-800ms | ease-out | Flowing reveal |
| Scale entrance | 500ms | ease-out | Emphasis |
| Spinner | 1000ms | linear | Loading (continuous) |
| Color change | 200ms | ease-in-out | Hover feedback |
| Shadow change | 200ms | ease-in-out | Depth feedback |

---

## Easing Curves Explained

**ease-out:** Start fast, slow down (deceleration)
- Feels natural, like object coming to rest
- Use: Entrances (things appearing)
- Timing: 600-800ms

**ease-in-out:** Slow start, fast middle, slow end
- Feels mechanical, precise
- Use: Hover states, transitions
- Timing: 200-300ms

**ease-in:** Slow start, fast end (acceleration)
- Feels unnatural, rarely used
- Use: Exit animations (things leaving)
- Timing: 300-400ms

**linear:** Constant speed throughout
- Feels mechanical, ongoing
- Use: Loading spinners, infinite loops
- Timing: 1000-2000ms continuous

---

## Animation Performance: GPU vs CPU

**GPU Accelerated (Fast, Use These):**
- `transform: scale()`
- `transform: rotate()`
- `transform: translateX/Y/Z()`
- `opacity`

**CPU Intensive (Slow, Avoid):**
- `width` / `height` (causes reflow)
- `left` / `right` / `top` / `bottom` (causes reflow)
- `padding` / `margin` (causes reflow)
- `font-size` (causes reflow)

**Rule:** If animation feels janky, check that you're animating transform/opacity only.

---

**Last Updated:** March 12, 2026
**Source:** Webflow Masterclass, Shift Nudge, CSS Animation Standards
