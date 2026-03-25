# Responsive Design Patterns — Quick Reference

## BREAKPOINT REFERENCE

### Standard Three-Breakpoint System [Segall]
| Name | Design Width | Columns | Margin | Gap | Notes |
|------|-------------|---------|--------|-----|-------|
| Desktop | 1440px | 12 | 24-64px | 24-40px | Primary design canvas |
| Tablet | 810px | 6 | 16-32px | 16-32px | iPad approximation |
| Mobile | 390px | 4 or 2 | 16-24px | 16-24px | iPhone standard |

### Extended System (Complex Sites)
| Name | Width | Use Case |
|------|-------|----------|
| Ultra-wide | 1920px+ | Dashboard apps, data-heavy |
| Desktop L | 1440px | Standard desktop |
| Desktop S | 1280px | Smaller laptops |
| Tablet L | 1024px | iPad landscape |
| Tablet P | 768px | iPad portrait |
| Mobile L | 480px | Phone landscape |
| Mobile P | 375-390px | Phone portrait |

### Max-Width Strategy
- Content container: 1200-1440px max-width, centered
- If no max-width: content stretches edge-to-edge on large monitors
- Text blocks: 680-720px max-width for readability (45-75 characters)
- Centered content: auto margins on left and right

---

## RESPONSIVE LAYOUT TRANSFORMATIONS

### Two-Column to Stack
```
Desktop:  [Content 60%] [Image 40%]
Tablet:   [Content 100%]
          [Image 100%]
```
- Switch flex direction from row to column
- Both elements become full-width
- Adjust spacing: horizontal gap becomes vertical gap

### Three-Column Grid to Stack
```
Desktop:  [Card] [Card] [Card]  (3 across)
Tablet:   [Card] [Card]        (2 across, 1 wraps)
Mobile:   [Card]               (1 per row)
          [Card]
          [Card]
```
- Use flex-wrap with min-width per card (280-320px)
- Or manually switch grid columns per breakpoint

### Sidebar to Full-Width
```
Desktop:  [Sidebar 25%] [Main Content 75%]
Tablet:   [Sidebar collapsed or hidden]
          [Main Content 100%]
Mobile:   [Main Content 100%]
          [Sidebar as bottom section or hamburger]
```

### Navigation Transformation
```
Desktop:  [Logo] [Nav Items] [CTA]
Tablet:   [Logo] [CTA] [Hamburger]
Mobile:   [Logo] [Hamburger]
```
- Hide nav items behind hamburger at tablet or mobile
- CTA may persist on tablet, hide on mobile
- Full-screen overlay menu on mobile

---

## RESPONSIVE TYPOGRAPHY SCALING

### Heading Scale Per Breakpoint
| Level | Desktop | Tablet | Mobile |
|-------|---------|--------|--------|
| Display/Hero | 64-80px | 48-56px | 36-44px |
| H1 | 48-56px | 36-44px | 28-36px |
| H2 | 36-40px | 28-32px | 24-28px |
| H3 | 24-28px | 20-24px | 18-22px |
| H4 | 20-22px | 18-20px | 16-18px |
| Body | 16-18px | 16px | 16px |
| Small/Caption | 14px | 14px | 12-14px |

### Responsive Typography Technique [Segall]
For full-width text that should scale with viewport: use vw units.
Text fills the section regardless of screen size. No container needed.

### Line Height Adjustments
- Titles: stay at ~100% across breakpoints
- Body: stay at ~150% across breakpoints
- No need to change line-height ratios responsively

---

## SECTION PADDING RESPONSIVE SCALE

### Recommended Vertical Section Padding
| Section Type | Desktop | Tablet | Mobile |
|-------------|---------|--------|--------|
| Hero | 80-120px bottom | 64-80px | 48-64px |
| Standard section | 80-96px | 64-72px | 48-56px |
| CTA section | 64-80px | 48-64px | 40-48px |
| Footer | 48-64px top | 40-48px | 32-40px |

### Spacing Reduction Pattern
As a rule: reduce spacing by 20-30% at each breakpoint step.
- Desktop: 96px > Tablet: ~72px > Mobile: ~48px

---

## RESPONSIVE IMAGE HANDLING

### Image Strategies
| Strategy | When | How |
|----------|------|-----|
| Crop (object-fit cover) | Background images, hero | Maintain dimensions, crop excess |
| Scale (object-fit contain) | Product photos, logos | Maintain aspect ratio, reduce size |
| Art direction | Different crops per device | Serve different image files |
| Hide | Desktop-only decorative | display: none on mobile |

### Image Position on Crop
- Portrait photos: position top (keep face visible when cropped)
- Landscape scenes: position center (default)
- Product photos: position center

### Hero Image Responsive Behavior
- Desktop: side-by-side with text (50/50 split)
- Tablet: image below text (full width) or reduced height
- Mobile: image below text, or hero background with overlay

---

## COMMON RESPONSIVE BUGS [Segall]

### Horizontal Scroll
- **Symptom**: Page scrolls left-right on mobile
- **Cause**: Element extending beyond viewport width
- **Fix**: Find the overflowing element, set overflow: hidden on body or parent
- **Test**: Always test mobile viewport for horizontal overflow

### Image Overflow
- **Symptom**: Image pushes past container on small screens
- **Fix**: max-width: 100% on all images (should be global default)

### Fixed-Width Elements
- **Symptom**: Element stays at desktop width on mobile
- **Fix**: Use percentage or Fill Container instead of fixed pixel widths

### Font Size Too Large
- **Symptom**: Desktop heading size breaks mobile layout
- **Fix**: Reduce font size per breakpoint (see scaling table above)

### Touch Target Too Small
- **Symptom**: Buttons/links hard to tap on mobile
- **Fix**: Minimum 44x44px touch target area

---

## RESPONSIVE TESTING CHECKLIST

### Per Breakpoint Checks
- [ ] All text readable (no truncation, no overflow)
- [ ] All images properly sized (no distortion, no overflow)
- [ ] Navigation transforms correctly (hamburger works)
- [ ] Touch targets 44px+ on mobile
- [ ] No horizontal scroll on any breakpoint
- [ ] Buttons accessible (not hidden behind other elements)
- [ ] Forms usable (inputs large enough, keyboard doesn't cover fields)
- [ ] Videos responsive (16:9 container that scales)

### Device Testing [Segall]
- **Use your actual phone** -- do NOT rely on browser device emulation
- Browser emulation misses real-device issues (scrolling behavior, touch accuracy, real font rendering)
- Test on at least one iOS and one Android device

### Responsive Cascading Rule [Segall]
- Desktop styles cascade DOWN to tablet and mobile
- Tablet styles cascade DOWN to mobile only
- Mobile styles affect mobile only
- **Always build desktop-first** -- mobile-first means desktop has nothing since styles don't cascade up

---

## FLEXBOX RESPONSIVE PATTERNS (For Implementation)

### Even Columns (Auto-Responsive)
- Parent: flex, gap 1rem
- Children: flex-basis 100% (push equally, auto-divide)
- Works for any number of children without percentage math

### Grid-ish (Auto-Wrapping) [Segall]
- Parent: flex, wrap enabled, gap 1rem
- Children: flex-grow 1, flex-basis 15.5rem
- Children wrap to next line when insufficient space
- Responsiveness "for free" -- no breakpoint changes

### Content + Sidebar (Collapsing) [Segall]
- Parent: flex, wrap enabled
- Content: flex-grow 1, flex-basis 70%
- Sidebar: flex-grow 1, flex-basis 30%, min-width 15rem
- Sidebar wraps below content when viewport shrinks past min-width

---

## F-PATTERN & SCANNING BEHAVIOR [Arash]

- Users scan pages in F-shaped pattern: horizontal across top, then down left side
- Place most important content along the F-pattern lines
- Headlines and key information at top horizontal sweep
- CTA buttons along the left edge or center (where eyes naturally fall)
- Break the F-pattern intentionally with large images or offset elements to create visual interest
