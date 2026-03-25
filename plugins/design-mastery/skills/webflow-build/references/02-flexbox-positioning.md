---
name: Flexbox & Positioning Patterns
description: "Even columns, grid-ish auto-wrap, content+sidebar, masonry patterns, position types, z-index strategy for Webflow builds."
---

# Flexbox & Positioning Patterns

Reusable layout patterns for Webflow development. Each pattern includes parent and child settings.

---

## FLEXBOX PATTERNS

### Pattern 1: Even Columns

**Goal:** Equal-width columns regardless of count.

```
Parent:  display: flex
         gap: 24px (or your spacing token)
Child:   flex-basis: 100%
         (each child pushes equally)
```

- Works for 2, 3, 4, or any number of children
- Do NOT use 33.3% or 25% -- use 100% for flexibility
- Responsive: on tablet/mobile, switch flex-direction to column

### Pattern 2: Grid-ish Auto-Wrap

**Goal:** Cards that automatically wrap to next row.

```
Parent:  display: flex
         flex-wrap: wrap
         gap: 24px
Child:   flex-grow: 1
         flex-basis: 15.5rem (tune per design)
```

- Children wrap to next line when space is insufficient
- REMs for flex-basis (not %) allows natural viewport-based wrapping
- Responsiveness comes free -- often no breakpoint changes needed
- Adjust flex-basis value to control when wrapping occurs

### Pattern 3: Content + Sidebar

**Goal:** Main content area with collapsible sidebar.

```
Parent:  display: flex
         flex-wrap: wrap
         gap: 32px
Content: flex-grow: 1
         flex-basis: 70%
Sidebar: flex-grow: 1
         flex-basis: 30%
         min-width: 15rem
```

- When viewport shrinks below sidebar min-width, sidebar wraps below
- Both fill their respective rows completely
- Good for blog layouts, documentation pages

### Pattern 4: Flexbox Masonry (Horizontal)

**Goal:** Pinterest-style horizontal masonry for galleries.

```
Gallery List:  display: flex
               flex-wrap: wrap
               gap: 0.5rem
Gallery Item:  height: 36vh (tune per image set)
               flex-grow: 1
               flex-shrink: 1
Gallery Image: width: 100%
               height: 100%
               object-fit: cover
Last Empty:    flex-grow: 10
               flex-shrink: 0
               aria-hidden: true
```

- Responsive: adjust gallery item height per breakpoint
  - Desktop: 36vh
  - Tablet: 28vh
  - Mobile portrait: 45vh
  - Mobile landscape: width-based (28vw) with height auto

### Pattern 5: Centered Content Block

**Goal:** Section with max-width content and centered alignment.

```
Section:   display: flex
           justify-content: center
           padding: 80px 24px
Container: max-width: 1200px
           width: 100%
```

---

## FLEX CHILD PROPERTIES (Webflow)

Access via three-dot icon in flex child dropdown:

| Property | Purpose | Common Values |
|----------|---------|---------------|
| Grow | How much element expands to fill space | 0 (don't grow), 1 (grow equally) |
| Shrink | How much element contracts when tight | 0 (don't shrink), 1 (shrink equally) |
| Basis | Starting size before grow/shrink apply | auto, 100%, rem values |

**Key combinations:**
- `grow: 1, basis: 100%` = even columns
- `grow: 1, basis: 15rem` = auto-wrapping cards
- `grow: 0, shrink: 0, basis: auto` = fixed-size element (logo in nav)

---

## CSS POSITIONING

### Position Types

**Static (Default)**
- Element follows normal document flow
- Cannot use top/right/bottom/left offsets
- Use for: most elements

**Relative**
- Still in document flow (takes up original space)
- Can be offset with top/right/bottom/left
- Creates positioning context for absolute children
- Use for: subtle offsets, parent container for absolute elements

**Absolute**
- Removed from document flow (no space reserved)
- Positioned relative to nearest positioned ancestor (or viewport)
- Use for: overlaying elements, decorative backgrounds, badges, tooltips

**Fixed**
- Removed from flow
- Stays in place relative to viewport during scroll
- Use for: persistent navigation, floating CTAs, cookie banners

**Sticky**
- Stays in flow until scroll threshold, then sticks
- Requires: parent with `overflow: visible` (NOT hidden)
- Requires: container taller than the sticky element
- Set `top` value to determine where it sticks
- Use for: sticky sidebar, sticky nav on scroll

---

## Z-INDEX STRATEGY

### Layered Section Pattern
```
Background decorative layer:  z-index: 0
Interactive middle (3D/Spline): z-index: 1
Content layer (text, buttons):  z-index: 2
```

### Site-Wide Z-Index Scale
| Layer | Z-Index Range | Elements |
|-------|-------------|----------|
| Background | 0 | Decorative images, patterns |
| Content | 1-9 | Page sections, cards |
| Sticky elements | 10-19 | Sticky sidebar |
| Navigation | 50-99 | Fixed nav, dropdowns |
| Overlays | 100-199 | Modal backgrounds |
| Modals | 200-299 | Modal content |
| Tooltips | 300+ | Tooltips, toasts |

### Z-Index Rules
- Only positioned elements (relative, absolute, fixed, sticky) respond to z-index
- Static elements ignore z-index
- Higher z-index = closer to viewer
- Stacking contexts: a parent with z-index creates a new context (children cannot escape)

---

## HORIZONTAL SCROLLING SECTION

### Structure
```
Outer wrapper:    height: 300vh-400vh (scroll room)
Inner section:    position: sticky, top: 0
                  height: 100vh, overflow: hidden
Cards container:  display: flex, horizontal, no-wrap
Individual cards: fixed width or percentage
```

### Behavior
- User scrolls vertically
- Sticky section stays visible
- Content scrolls horizontally (driven by scroll position)
- Once all cards pass through, sticky section unsticks

### Cards with 3D Flip
- Front face and back face as separate elements
- CSS `transform: rotateY(180deg)` on hover/click
- `backface-visibility: hidden` on both faces
- Parent needs `perspective` set for 3D depth

---

## NAVIGATION PATTERNS (BUILD)

### Fixed/Sticky Nav
- Position fixed, z-index high enough to stay above content
- Full width, consistent padding

### Mega Menu Build
- Navigation items and featured content side-by-side in dropdown
- Column guides for alignment
- Feature promoted item (case study card) beside link list
- Divider line between links and featured content
- Chevron icon rotates on open state
- Fixed-height button (e.g., 40px) with calculated padding

### Mobile Nav (Custom Build)
- Custom-built hamburger, not Webflow's default navbar component
- Full-screen overlay with animated open/close
- Staggered reveal for menu items
- Build and test mobile nav separately from desktop

### Logo Component ("Super Logo")
- Single component with multiple logo variations
- SVG with `currentColor` for CSS color control
- Hide/show variations using component properties
- One component across entire site -- update once, updates everywhere
