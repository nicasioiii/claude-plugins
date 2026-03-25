---
name: Web Layout
description: "Website page structures, hero sections, homepage anatomy, responsive web design, section spacing, containers, navigation mega-menus, footer patterns, page architecture, responsive breakpoints. FOR: designing full web pages, structuring homepages, responsive layout decisions, section-by-section design, navigation design, footer design. MANDATORY TRIGGERS: website layout, homepage, hero section, web page structure, responsive design, responsive breakpoints, mobile design, section design, footer, navigation bar, mega menu, landing page, page sections, web structure, container width, website architecture, above the fold, social proof section, features section, testimonials, pricing section, CTA section, FAQ section. Do NOT use for — use ui-components for individual component patterns, use dashboard-app-design for SaaS app interfaces, use webflow-build for Webflow implementation, use shopify-ecommerce for Shopify store design."
---

# Web Layout

This skill covers page-level design: how to structure websites, design sections, and handle responsive behavior. Components from ui-components are assembled here into full page layouts.

## THE DESIGN-FIRST PROCESS

### Web Design Workflow [Flux, Segall]
1. **Brief review**: Extract audience, brand personality, competitors, mandatory elements
2. **Wireframes**: High-fidelity (buildable) or quick hand sketches. High-fi saves time because you design on top of them [Flux]
3. **Inspiration gathering**: Separate web layout inspiration from aesthetic/brand inspiration
4. **Fonts and colors**: Choose from scratch when no brand guidelines exist
5. **Image direction**: Establish 2-3 visual directions from references
6. **Concepting**: Create 2-3 unique concepts with different fonts, colors, image styles
7. **Refinement**: Consolidate colors, align to guides, standardize typography, polish spacing
8. **Navigation design**: Landing state, scroll state, open/dropdown state
9. **Inner pages**: Design at least one inner page template
10. **Responsive breakdown**: Desktop, tablet, mobile for homepage and navigation minimum

### Three Project Scenarios [Flux]
- **Blank canvas**: No branding or assets. Build everything from scratch
- **Brief + brand**: Brand questionnaire + copy deck. Pull inspiration, quick wireframes
- **Redesign**: Existing brand. Audit current site, identify what works, create accessible palette

---

## HOMEPAGE ANATOMY (Section by Section)

### Standard Homepage Flow [Arash, Segall, Flux]
```
1. Navigation Bar
2. Hero Section (above the fold)
3. Social Proof / Logo Bar
4. Features / Services
5. How It Works / Process
6. Detailed Feature Showcase
7. Testimonials / Case Studies
8. CTA Section
9. FAQ (optional)
10. Footer
```

This pattern follows Jakob's Law: users expect sites to work like other sites they've used. The similarity is not coincidence -- it follows established user expectations [Arash].

### Section Design Rules
- Each section has a clear single purpose
- Visual distinction between sections (alternating backgrounds, dividers, or spacing)
- Sections can have different vertical padding from each other -- "consistent, not identical" [Segall]
- Vertical section padding: 64-120px typical range (reduce on mobile)

---

## HERO SECTION DESIGN

### Hero Layout Patterns
| Pattern | Structure | Best For |
|---------|-----------|----------|
| **Split hero** | Content left, image/visual right | SaaS, tech products |
| **Centered hero** | Centered headline + CTA, background image/gradient | Brand-first, simple message |
| **Full-bleed image** | Full-width image with overlay text | Photography, lifestyle, editorial |
| **Video hero** | Background video with overlay content | High-impact landing pages |
| **Minimal hero** | Large text only, no image | Typography-driven brands |

### Hero Content Hierarchy
1. **Headline** (largest text on page): What is this? What value does it provide?
2. **Subheadline/description**: Supporting detail, expand on the promise
3. **CTA button(s)**: Primary action (filled) + optional secondary (outlined or text)
4. **Social proof** (optional): "Trusted by 10,000+" or logo bar inline

### Hero Sizing
- Desktop: 80-100vh (full viewport) or content-determined height
- Content max-width: 600-800px for centered text blocks
- Image/illustration: at least 40% of hero width in split layouts
- CTA buttons: Large size (48px+ height)

---

## NAVIGATION DESIGN

### Landing State vs Scroll State [Segall]
| Property | Landing (Top of Page) | Scrolled |
|----------|----------------------|----------|
| Background | Transparent | White or dark solid |
| Shadow | None | Subtle (0 2px 8px rgba) |
| Logo | White or full color | Dark or brand color |
| Vertical padding | 24px | 12-16px |
| Transition | -- | 0.3s ease on all properties |

### Scroll Behavior Pattern
- On scroll down: nav hides (slides up on Y axis)
- On scroll up (intent to return): nav slides back down
- Creates more content space while maintaining accessibility

### Desktop Nav Structure [Arash, Segall]
```
[Logo]          [Nav Item] [Nav Item] [Nav Item] [Nav Item]          [CTA Button]
```
- Auto layout: horizontal, Space Between
- Height: 56-72px
- Logo: max 32-40px height
- CTA: distinct from nav items (filled button)

### Mega Menu [Segall]
- Navigation links in columns + featured content card on one side
- Divider line between link groups and featured content
- Chevron icon on trigger rotates to indicate open/closed
- Full container width, centered

### Mobile Navigation [Segall]
- Custom hamburger menu (not default Webflow navbar)
- Full-screen overlay with animated open/close
- Staggered reveal for menu items
- Build and test mobile nav separately from desktop

---

## SECTION SPACING SYSTEM

### Vertical Padding Between Sections
- Hero: 80-120px bottom (or full-viewport)
- Standard sections: 64-96px top and bottom
- CTA/highlight sections: 48-80px top and bottom
- Footer: 48-64px top, 24-32px bottom

### Internal Section Spacing
- Section heading to first content: 32-48px
- Between content blocks within section: 24-32px
- Between cards in a grid: 16-24px gap

### The Hierarchy of Negative Space [MDS]
- More negative space = more importance/gravitas
- Hero sections get the most generous padding
- Secondary sections get less
- The DIFFERENCE in space between sections IS the hierarchy
- Dense information (dashboards) needs less; marketing pages need more

---

## RESPONSIVE DESIGN

### Breakpoint Standards [Segall]
| Breakpoint | Width | Columns | Use |
|-----------|-------|---------|-----|
| Desktop | 1440px (design at) | 12 | Primary design canvas |
| Tablet | 810px | 6 | iPad-ish |
| Mobile | 390px | 4 or 2 | Phone |

Three breakpoints is the standard minimum. Add 1-2 above desktop for complex designs.

### Key Responsive Adjustments [Segall]
- **Layout direction**: Horizontal to vertical when content no longer fits side-by-side
- **Font sizes**: Reduce heading sizes per breakpoint (H1 from 90px desktop to 64px tablet to 40px mobile)
- **Body text**: Consider 18px to 16px on tablet/mobile
- **Spacing**: Desktop padding too generous on smaller screens -- reduce proportionally
- **Images**: object-fit cover with adjusted position (top-align portraits when cropped)
- **Hero height**: 100vh to auto, or split (50vh image + 50vh content)
- **Grid to stack**: Multi-column grids become single-column on mobile

### Container Width
- If no max-width set, designs stretch edge-to-edge on large monitors [Segall]
- Common max-width: 1200-1440px, centered
- Side margins: 24-64px desktop, 16-24px mobile
- Column gaps: 24-40px desktop, 16-24px mobile

### Mobile-Specific Rules
- Full-width buttons (fill container)
- Stack all multi-column layouts to single column
- Hamburger menu replaces horizontal nav
- Bottom tab bar for app-like experiences (3-5 items)
- Increase touch targets to 44px minimum
- Hide non-essential desktop elements (display none)

---

## GRID SYSTEM

### 12-Column Grid [MDS, Segall, Flux]
- Most popular for websites: allows 1, 2, 3, 4, 6, or 12 column layouts
- Responsive behavior: 12 cols desktop > 6 cols tablet > 2-4 cols mobile

### Content-Out vs Grid-First [MDS]
[CONTRARIAN] "The goal isn't to use a grid. The goal is to achieve balance and harmony." -- Content-out approach often works better than grid-first. Let content dictate structure, then apply grid as things solidify.

### Breaking the Grid [MDS]
- Intentionally breaking adds visual interest (oversized images, offset elements)
- Images, decorative elements, and pull quotes can extend past grid boundaries
- Strict grid = corporate/organized feel; grid-breaking = editorial/dynamic feel

### Implicit Grid [MDS]
- No formal column grid -- instead, consistent spacing values (8, 12, 16, 20, 24, 32, 40, 48) create an emergent grid
- Especially powerful for mobile where formal column grids are less useful

---

## FOOTER DESIGN

### Footer Content
- Logo (smaller version or icon)
- Navigation links (organized in columns by category)
- Social media icons
- Contact information
- Legal links (Privacy Policy, Terms of Service)
- Copyright with auto-updating year
- "Website by [Agency]" credit link
- Newsletter signup (optional)

### Footer Layout
- Desktop: 3-4 columns with links, logo top-left or centered
- Mobile: single column, stacked sections
- Background: typically darker than page (dark gray, dark brand color, or inverted)
- Padding: 48-64px top, 24-32px bottom
- Bottom bar: thin line with copyright + legal links

---

## IMAGE & MEDIA GUIDELINES

### Stock Photography Rules [Segall]
- Avoid assets that are obviously stock photography
- Avoid overused free stock (Unsplash/Pexels -- same faces on thousands of sites)
- All graphics on a site must feel stylistically cohesive
- [CONTRARIAN on AI images]: If AI-generated assets are obviously AI-made, they are worse than bad stock because no human crafted them. Use AI only when indistinguishable from custom work [Segall]

### Image Strategy [Flux]
- Establish 2-3 visual directions from references
- Real photography > illustrations > stock > AI (quality hierarchy)
- Consistent color treatment across all images (filters, overlays)
- Image selection criteria from mood board direction

### Graphics Principle [Segall]
Graphics should enhance communication and make the site feel complete, but the site should still perform its primary job if all graphics were removed.

---

## PAGE DESIGN CHECKLIST (Refinement) [Flux]

1. Audit and consolidate color palette (remove duplicates, name systematically)
2. Turn on guides and verify alignment
3. Verify vertical padding is intentional per section
4. Standardize font sizes (H1, H2, body, button, eyebrow)
5. Standardize letter spacing per text style (-1% to -3% typical)
6. Verify line heights (100% for titles, 120-144% for body)
7. Check max-widths on text blocks for readability (45-75 characters)
8. Step back and evaluate cohesion across the full page

---

## ANTI-PATTERNS

- All sections with identical padding (no hierarchy)
- Text blocks wider than 75 characters per line
- Hero without clear CTA
- Navigation with 10+ visible items (use mega menu or grouping)
- Mobile design that is just a squeezed desktop (not redesigned)
- No max-width on content container (stretches on ultra-wide)
- Mixed image aspect ratios in card grids
- Footer with no navigation links

---

## RELATED SKILLS

- **ui-components**: For the components assembled into page layouts
- **layout-spacing**: For the spacing system and grid foundations
- **typography-systems**: For heading and body text sizing in page context
- **color-systems**: For section background colors and contrast decisions
- **design-systems**: For converting page patterns into reusable templates
- **webflow-build**: For implementing these layouts in Webflow
- **shopify-ecommerce**: For e-commerce-specific page structures
- **design-critique**: For reviewing page layouts before build
- **dashboard-app-design**: For app/SaaS layouts (different from marketing pages)
