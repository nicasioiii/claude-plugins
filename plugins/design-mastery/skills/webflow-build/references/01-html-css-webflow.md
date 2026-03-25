---
name: HTML/CSS in Webflow Reference
description: "Elements, document flow, box model, nesting/cascading, responsive cascade rules for Webflow development."
---

# HTML/CSS in Webflow

Quick-reference for translating design concepts into Webflow's HTML/CSS model.

---

## KEY ELEMENTS

| Element | Webflow Name | Semantic Role | Use For |
|---------|-------------|---------------|---------|
| H1-H6 | Heading | Document structure | Titles, section headings. H1 = once per page |
| P | Paragraph | Body text | Standard text blocks |
| A | Link / Link Block | Navigation | Link blocks make entire children clickable |
| Button | Button | Interactive | Pre-styled link element |
| Div | Div Block | Container | Primary building block, holds anything |
| Section | Section | Page region | Wraps major content areas |
| List | List / List Item | Grouped content | Screen readers announce count |
| Image | Image | Visual content | Always add alt text |
| Form | Form Block | Data collection | Contains inputs, labels, submit |

**Shortcut:** Command+E (Mac) / Ctrl+E (Windows) = quick add element

---

## DOCUMENT FLOW

Web pages render top-to-bottom, left-to-right by default:
- Elements stack vertically (block elements)
- Each takes full available width
- Content below gets pushed down
- Moving elements in Navigator changes order across ALL breakpoints
- Overlapping requires CSS positioning (not default behavior)

### Breaking Out of Normal Flow
- `display: flex` -- one-dimensional arrangement
- `display: grid` -- two-dimensional arrangement
- `position: absolute/fixed` -- removes from flow entirely
- `position: sticky` -- hybrid (in-flow until scroll threshold)

---

## THE BOX MODEL

```
┌──────────────── Margin ────────────────┐
│  ┌──────────── Border ──────────────┐  │
│  │  ┌──────── Padding ──────────┐   │  │
│  │  │                           │   │  │
│  │  │        Content            │   │  │
│  │  │                           │   │  │
│  │  └───────────────────────────┘   │  │
│  └──────────────────────────────────┘  │
└────────────────────────────────────────┘
```

- **Content:** The actual text/image/element
- **Padding:** Space inside the box between edges and content
- **Border:** Line around the box (optional)
- **Margin:** Space outside the box pushing other elements away
- Every element is a rectangular box (even circles = boxes with border-radius)

**Box Sizing:** Webflow uses `border-box` by default -- padding is included in width/height calculations.

---

## NESTING & INHERITANCE

### Parent-Child Relationship
- Putting elements inside other elements = nesting
- Children inherit CSS properties from parents: font-family, font-size, color, line-height, letter-spacing, text-align
- Properties that do NOT inherit: width, height, margin, padding, border, background, display, position

### Cascade Strategy
Style the topmost element (body) correctly:
- Set font-family on body -- all text inherits
- Set color on body -- all text inherits
- Set line-height on body -- paragraphs inherit
- Override only where you need exceptions

### Siblings
- Elements at the same nesting level
- Do not affect each other's styles
- Use gap (on flex/grid parent) for spacing between siblings

---

## RESPONSIVE CASCADE IN WEBFLOW

### How It Works
```
Desktop (base)
  ↓ cascades down
Tablet (992px)
  ↓ cascades down
Mobile Landscape (768px)
  ↓ cascades down
Mobile Portrait (478px)
```

- Changes on desktop cascade to ALL smaller breakpoints
- Changes on tablet cascade to mobile only (NOT up to desktop)
- Changes on mobile portrait stay on mobile portrait only
- **Rule:** Always build desktop-first

### What Cascades Down
1. Style panel changes (class properties)
2. Breakpoint overrides
3. Class-based styles

### What Does NOT Cascade (Global Changes)
- Dragging elements to reorder in Navigator (affects ALL breakpoints)
- Manual line breaks (Enter key)
- Element settings (image height in element settings panel, not style panel)

### Responsive Editing Pitfalls
- Editing H-tags on tablet may jump to desktop (Webflow quirk)
- Workaround: temporarily remove class, edit H-tag on desired breakpoint, reapply class
- After first change on that breakpoint, subsequent edits work normally

---

## CLASSES & NAMING

### Class Strategy
- One class per styling purpose
- Avoid stacking too many combo classes
- Use utility classes for repeated patterns (padding, margin)
- Name semantically: "hero-section", "card-grid", not "div-block-47"

### Client-First Naming Convention [Finsweet]
```
Component: [component]_[element]
  Example: card_title, nav_link, hero_image

Utility: [property]-[value]
  Example: padding-top-large, margin-bottom-medium

Global: [element-type]
  Example: heading-style-h2, text-size-medium
```

### Heading Styles
- heading-style-h1 through heading-style-h6
- Plus extras: heading-style-jumbo, heading-style-display
- Define ALL styles in style guide before building pages

---

## IMAGE HANDLING

### Export from Figma
- Export at 2x resolution for retina displays
- Compress with Cloud Convert before upload
- Organize in Webflow by category (logos, icons, photography)

### Image Sizes for SEO/Social
| Purpose | Dimensions |
|---------|-----------|
| Open Graph | 1200 x 630px |
| Web Clip | 256 x 256px |
| Favicon | 32 x 32px |

### Loading Strategy
- Default: "load with page" for most images
- Lazy load: only for content-heavy pages (blog articles with many images)
- Always add descriptive alt text

---

## CUSTOM CODE LOCATIONS

| Location | Scope | Use For |
|----------|-------|---------|
| Project Settings > Custom Code > Head | All pages | Analytics, fonts, global CSS |
| Project Settings > Custom Code > Body | All pages | Scripts that need DOM loaded |
| Page Settings > Custom Code | Single page | Page-specific scripts |
| Embed element | Inline | Component-level code |

### Common Custom Code Snippets
- Auto-update copyright year: JS targeting a class
- Dynamic thank you page: pull submitted name, display personalized message
- Font refinements: custom CSS for letter-spacing, OpenType features
