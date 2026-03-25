# Navigation & Footer Patterns — Quick Reference

## NAVIGATION TYPE SELECTOR

### When to Use Each Nav Pattern
| Pattern | Site Type | Page Count | Complexity |
|---------|-----------|-----------|------------|
| Simple horizontal | Marketing, landing | 3-7 pages | Low |
| Horizontal + dropdown | Corporate, SaaS | 8-15 pages | Medium |
| Mega menu | Enterprise, e-commerce | 15+ pages | High |
| Sidebar | Web app, dashboard | Any | App interface |
| Bottom tab bar | Mobile app | 3-5 core views | App interface |

---

## FIXED/STICKY NAV SPECS

### Desktop Sticky Nav
```css
position: fixed;
top: 0;
left: 0;
width: 100%;
z-index: 100;       /* Above all content */
background: white;
box-shadow: 0 2px 8px rgba(0,0,0,0.08);
```

### Sticky Requirements [Segall]
- Parent must NOT have overflow: hidden
- Element must be inside a container taller than itself
- Set top value to determine stick position
- z-index high enough to stay above all content

---

## SCROLL-STATE NAV PATTERN [Segall]

### Landing State (Page Top)
| Property | Value |
|----------|-------|
| Background | transparent |
| Shadow | none |
| Logo color | white (on dark hero) or brand |
| Link color | white or dark |
| Vertical padding | 20-24px |
| Border radius | 0 |

### Scrolled State
| Property | Value |
|----------|-------|
| Background | white (or dark) |
| Shadow | 0 2px 8px rgba(0,0,0,0.08) |
| Logo color | dark or brand |
| Link color | gray-700 |
| Vertical padding | 12-16px |
| Border radius | 0 or 12-16px (floating pill) |
| Transition | 0.3s ease on all properties |

### Scroll Hide/Show Behavior
- Scroll down > nav slides up (hidden) via translateY(-100%)
- Scroll up > nav slides back down via translateY(0)
- Threshold: trigger after 50-100px of scroll
- Add consistent internal padding (8px around nav content, 16px border-radius if pill style)

---

## MEGA MENU DESIGN [Segall]

### Structure
```
┌──────────────────────────────────────────────────────────┐
│  Products ▼       Solutions ▼      Resources ▼    [CTA]  │
├──────────────────────────────────────────────────────────┤
│                                                          │
│  Category 1        Category 2        ┌──────────────┐   │
│  · Link item       · Link item       │ [Featured    │   │
│  · Link item       · Link item       │  Image]      │   │
│  · Link item       · Link item       │              │   │
│  · Link item       · Link item       │ Featured     │   │
│                                      │ Title        │   │
│  Category 3        Category 4        │ Short desc   │   │
│  · Link item       · Link item       │ [Read More]  │   │
│  · Link item       · Link item       └──────────────┘   │
│                                                          │
├──────────────────────────────────────────────────────────┤
│  [View All Products →]                                   │
└──────────────────────────────────────────────────────────┘
```

### Mega Menu Specs
| Element | Value |
|---------|-------|
| Container width | Full nav width or max-width 1200px |
| Internal padding | 32-40px |
| Column gap | 32-48px |
| Category heading | 14px, semi-bold, uppercase, tracking +50% |
| Link items | 14-16px, regular weight |
| Link hover | Primary color or underline |
| Featured card | 200-280px wide |
| Divider | 1px gray-200 between groups |
| Background | White with subtle shadow |
| Border radius | 8-12px bottom corners |
| Animation | Fade in 200ms or slide down 200ms |

### Chevron Indicator
- Closed: chevron points down (▼)
- Open: chevron rotates 180 degrees (▲)
- Transition: 200ms rotate

---

## MOBILE NAVIGATION

### Hamburger Menu Design [Segall]
**Build custom** -- not Webflow/framework default navbar.

**Hamburger Icon:**
- 3 horizontal lines, 2px thick, 20-24px wide
- Gap between lines: 4-6px
- Touch target: 44x44px minimum (icon smaller, tap area larger)
- Animation: lines morph to X on open (top/bottom rotate, middle fades)

**Full-Screen Overlay:**
```
┌─────────────────────────────┐
│ [Logo]              [X]     │
│                             │
│                             │
│     Home                    │
│     Features                │
│     Pricing                 │
│     About                   │
│     Contact                 │
│                             │
│     [CTA Button]            │
│                             │
│     [Social Icons]          │
└─────────────────────────────┘
```

**Overlay Specs:**
| Property | Value |
|----------|-------|
| Background | White or dark (brand) |
| z-index | 999 (above everything) |
| Animation | Slide from right (300ms) or fade (200ms) |
| Link font size | 24-32px (larger than desktop nav) |
| Link spacing | 16-24px gap between items |
| Close button | X icon, top-right, 44x44px tap area |

### Staggered Menu Item Reveal
- Each link fades in with slight delay offset
- First item: 100ms delay
- Second item: 200ms delay
- Third item: 300ms delay
- Creates elegant sequential reveal

---

## BOTTOM TAB BAR (Mobile App Pattern)

### Layout
```
┌───────────────────────────────────────┐
│  [icon]   [icon]   [icon]   [icon]   │
│  Home    Search   Cart    Profile    │
└───────────────────────────────────────┘
```

### Specs
| Property | Value |
|----------|-------|
| Height | 56px + safe area padding |
| Max items | 5 |
| Icon size | 24px |
| Label size | 10-12px |
| Active color | Primary |
| Inactive color | Gray-400 |
| Active icon | Solid/filled |
| Inactive icon | Outline |
| Background | White with top border (1px gray-200) |
| Safe area (iPhone) | +34px bottom for home indicator |

### "More" Tab Pattern
When 5+ sections exist:
- Show 4 most-used tabs
- 5th tab = "More" (three dots icon)
- "More" opens list/grid of remaining sections

---

## BREADCRUMB NAVIGATION

### Layout
```
Home  /  Products  /  Category  /  Current Page
```

### Specs
| Property | Value |
|----------|-------|
| Font size | 14px |
| Separator | "/" or ">" or chevron icon |
| Separator spacing | 8px each side |
| Previous items | Primary color, clickable |
| Current item | Gray, non-clickable |
| Position | Below nav, above page content |
| Padding | 16px vertical |

### Truncation for Deep Paths
```
Home / ... / Parent Page / Current Page
```
Show first item, last 2 items, ellipsis for middle.

---

## FOOTER DESIGN REFERENCE

### Footer Link Column Structure
| Column 1 | Column 2 | Column 3 | Column 4 |
|-----------|-----------|-----------|-----------|
| **Product** | **Resources** | **Company** | **Legal** |
| Features | Blog | About | Privacy Policy |
| Pricing | Help Center | Careers | Terms of Service |
| Changelog | API Docs | Press | Cookie Policy |
| Integrations | Guides | Contact | Sitemap |
| Status | Community | Partners | |

### Footer Sizing
| Element | Value |
|---------|-------|
| Top padding | 48-64px |
| Bottom padding | 24-32px |
| Column gap | 32-48px |
| Link font | 14px, regular |
| Column heading | 14px, semi-bold, uppercase optional |
| Logo height | 24-32px |
| Social icons | 20-24px, 12-16px gap |
| Background | Gray-900, brand dark, or inverted |
| Text color | Gray-400 (links), Gray-500 (sub) |
| Bottom bar | 1px top border, 16px vertical padding |
| Copyright | 12-14px, gray-500 |

### Footer Responsive
- Desktop: 4-5 columns
- Tablet: 2-3 columns (rest wraps below)
- Mobile: single column, accordion sections (collapse link groups)
- Social icons: horizontal row, centered or left
- Bottom bar: stack copyright and legal links vertically

### Auto-Update Copyright Year [Segall]
Small JS snippet targeting a class:
```javascript
document.querySelector('.copyright-year').textContent = new Date().getFullYear();
```
Pre-build this in your starter project so every site has it.

---

## LOGO COMPONENT PATTERN [Segall]

### "Super Logo" Component
Single component with multiple logo variations:
- Primary SVG (full logo, dark)
- Secondary (full logo, white/light)
- Icon-only (mark without wordmark)
- Favicon (simplified for small sizes)

### Implementation
- Use SVG with currentColor for CSS color control
- Hide/show variations using component properties (boolean toggle)
- One component across entire site -- update once, updates everywhere
- Set logo height in parent container, width auto
