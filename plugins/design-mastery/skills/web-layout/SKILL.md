---
name: Web Layout
description: "Design website structures with hero sections, responsive layouts, containers, breakpoints, and section spacing. MANDATORY TRIGGERS: website layout, responsive design, hero section, footer, container patterns, breakpoints, mobile-first, section spacing, layout grid. Do NOT use for individual components — use ui-components instead. Do NOT use for app dashboards — use dashboard-systems instead."
---

# Web Layout

## When You Need This Skill

Use this skill when:
- Designing the overall structure of a website page
- Planning responsive behavior across desktop, tablet, mobile
- Determining section spacing and rhythm
- Creating container and max-width patterns
- Building hero sections, feature sections, CTAs, footers
- Deciding breakpoint strategy

**Do NOT use for:**
- Individual component design → see **ui-components**
- Full SaaS dashboard layouts → see **dashboard-systems**
- Animation and interactions → see **animation-interactions**

---

## Website Layout Foundation

### The Three-Breakpoint System

**Standard Web Design operates on 3 primary breakpoints:**

| Breakpoint | Width | Columns | Margins | Gutters | Device |
|-----------|-------|---------|---------|---------|--------|
| **Desktop** | 1440px | 12 | 64px | 24-40px | 21.5"+ monitors, desktops |
| **Tablet** | 800px | 6 | 40px | 20-32px | 10-13" tablets, large phones |
| **Mobile** | 390px | 2-4 | 16-24px | 12-16px | 5-6" smartphones |

**Why These Numbers:**
- **1440px:** Natural breakpoint after 1280px (old standard), accommodates modern 27-34" monitors
- **800px:** iPad breakpoint, separates true tablet from mobile
- **390px:** iPhone 12 Pro Max width, covers modern small-to-large phones

**Important:** These are TRIGGERS, not hard stops. Design must work fluidly between breakpoints.

### Container & Max-Width Pattern

**The Foundation:**
```
┌──────────────────────────────────────────────┐
│  Full viewport width (1440px+)               │
├──────────────────────────────────────────────┤
│  64px margin                                  │
│  ┌────────────────────────────────────┐     │
│  │ Content max-width: 1312px          │     │
│  │ (1440 - 64×2 margins)              │     │
│  │                                     │     │
│  │ Centered with auto margins          │     │
│  └────────────────────────────────────┘     │
│  64px margin                                  │
└──────────────────────────────────────────────┘
```

**Math:**
- Available width = 1440px - (64px × 2) = 1312px
- Never squeeze content below this
- Always use `max-width` + `margin: 0 auto`

**Responsive Adjustments:**
```
Desktop (1440px): max-width 1312px, margin 64px
Tablet (800px):   max-width 720px, margin 40px
Mobile (390px):   max-width 100%, margin 16px
```

### Grid System (12-Column)

**Desktop Grid Structure:**
```
12 equal columns, 24px gutters

Col1  Col2  Col3  Col4  Col5  Col6  Col7  Col8  Col9  Col10 Col11 Col12
[24] [24] [24] [24] [24] [24] [24] [24] [24] [24]  [24] [24]
     ↑gutter: 24px between each
```

**Column Width Calculation:**
```
(1312px - (11 gutters × 24px)) / 12 columns
= (1312 - 264) / 12
= 1048 / 12
= ~87.3px per column
```

**Common Grid Usage:**
- **Full width:** 12 columns
- **Half width:** 6 columns (50%)
- **Third:** 4 columns (33%)
- **Quarter:** 3 columns (25%)

**Image Grid Example:**
```
Desktop: 3 images side-by-side (4 columns each)
Tablet:  2 images side-by-side (6 columns each)
Mobile:  1 image full-width (2 columns or full)
```

---

## Website Section Anatomy

## Website Sections

### Hero Section

**Purpose:** First impression, establish brand, communicate main value proposition

For complete hero section details, sizing, background options, and responsive behavior, read `references/section-anatomy.md`.

### Feature, CTA, Testimonial & Footer Sections

For complete section anatomy including feature sections, CTAs, testimonials, and footers with sizing, spacing, and responsive layouts, read `references/section-anatomy.md`.

---

## Section Spacing & Rhythm

Vertical spacing system, why consistent spacing matters, and half-padding technique to avoid gaps doubling up.

For complete spacing guidelines including spacing levels, application patterns, and responsive adjustments, read `references/spacing-responsive.md`.

---

## Responsive Image Handling

Image aspect ratios, object-fit strategies, and responsive sizing.

For complete image guidance including aspect ratios, object-fit options, and responsive sizing by device, read `references/spacing-responsive.md`.
Full-width hero: 100% viewport width (same)
Featured image: 100% width (full-width container)
Grid images: 100% width (1-column, full-width)
```

---

## Breakpoint-Specific Behaviors

### Desktop (1440px) Specifications

**Container:** max-width 1312px (1440 - 64×2 margins)
**Grid:** 12 columns, 24px gutters
**Margins:** 64px horizontal
**Font sizes:** Full 48/32/24/18/16/14/12px scale
**Spacing:** 100-128px between sections
**Images:** Full resolution, all visible

### Tablet (800px) Specifications

**Container:** max-width 720px (800 - 40×2 margins)
**Grid:** 6 columns, 20px gutters
**Margins:** 40px horizontal
**Font sizes:** Slightly reduced (44/28/20/16/14/12/11px)
**Spacing:** 60-80px between sections
**Images:** Medium resolution, may hide some
**Navigation:** Hamburger menu

### Mobile (390px) Specifications

**Container:** 100% width
**Grid:** 2-4 columns, 12px gutters
**Margins:** 16-24px horizontal (often 16px)
**Font sizes:** Compact (36/24/18/14/13/12/11px)
**Spacing:** 40-60px between sections
**Images:** Single column, 100% width
**Navigation:** Hamburger menu with slide-panel
**Buttons:** Full-width (easier to tap)

---

## Common Layout Mistakes

### ❌ Inconsistent Spacing

```
❌ WRONG: 50px gap here, 120px gap there
           (Rhythm feels broken)
```

**Fix:** Define spacing scale (40, 60, 100, 128px) and use consistently.

### ❌ Text Too Wide

```
❌ WRONG: Body text stretches full viewport (1440px+)
           (Hard to read, eye fatigue)
```

**Fix:** Use max-width: 1312px container or max ~80 characters per line.

### ❌ No Mobile Redesign

```
❌ WRONG: Same layout on mobile as desktop
           (Everything tiny, unreadable)
```

**Fix:** Redesign layout at each breakpoint (don't just shrink).

### ❌ Hero Section Too Short

```
❌ WRONG: Hero height 300px
           (Weak, no impact)
```

**Fix:** Use 600-800px or full viewport height (100vh).

### ❌ Images Without Aspect Ratio Lock

```
❌ WRONG: Images stretch or distort
           (Broken layout, poor UX)
```

**Fix:** Define aspect ratio containers using CSS `aspect-ratio` property.

---

## Web Layout Checklist

Before finalizing any page layout:

- [ ] Responsive layouts for all 3 breakpoints (1440px, 800px, 390px)
- [ ] Container max-width defined (1312px desktop, 720px tablet, 100% mobile)
- [ ] Grid system consistent (12 columns desktop, 6 columns tablet, 2-4 mobile)
- [ ] Section spacing follows scale (40/60/100/128px values)
- [ ] Hero section 600-800px height minimum
- [ ] All images have aspect ratio constraints
- [ ] Footer includes: logo, navigation, social, copyright
- [ ] CTA buttons prominent and accessible (48px+ height)
- [ ] Typography hierarchy clear (H1→H2→H3→body)
- [ ] Color contrast: Text 4.5:1 on backgrounds
- [ ] Mobile-first workflow applied
- [ ] Margin/padding values on 8px grid (divisible by 4 or 8)
- [ ] Layouts tested between breakpoints (not just AT breakpoints)

---

## When to Read Reference Files

| Need | Reference |
|------|-----------|
| Desktop/tablet/mobile breakpoints and column systems | **responsive-web-design.md** |
| Hero section, feature section, CTA, testimonial layouts | **web-sections.md** |
| Common page layout combinations and patterns | **web-layout-patterns.md** |
| Image aspect ratios, object-fit, responsive images | **image-handling.md** |
| Multi-column footer, link structure, copyright | **footer-patterns.md** |

---

## Cross-Skill References

- **visual-foundations** → For typography, color, spacing scales
- **ui-components** → To see how components fit into page layouts
- **dashboard-systems** → For app-specific layouts (NOT for websites)
- **animation-interactions** → For scroll animations within sections
- **webflow-implementation** → For technical build of responsive layouts

---

## Quick Layout Decision Tree

**Choosing a layout for your page:**

```
Do you need a hero section?
├─ YES → Hero Section (600-800px) + Feature Section + CTA + Footer
└─ NO →

Are you featuring products/services?
├─ YES → 3-column Feature Section + Testimonials
└─ NO →

Do you have multiple CTAs?
├─ YES → Include CTA Section + Footer
└─ Single CTA in Hero footer

Structure:
[Navigation]
[Hero Section] (if yes)
[Feature Section] (if yes)
[Testimonials] (optional)
[CTA Section] (if applicable)
[Footer]
```

