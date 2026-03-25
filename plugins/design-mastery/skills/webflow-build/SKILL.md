---
name: Webflow Build
description: "Webflow development from design to live site: HTML/CSS fundamentals, flexbox patterns, CSS positioning, CMS setup, responsive design, starter projects, build checklist, QA process, client handoff, SEO, accessibility, and ecosystem tools. Synthesizes Ran Segall (Flow Gurus) and Matt Jumper (Flux) methodologies. MANDATORY TRIGGERS: Webflow, build, flexbox, CSS grid, responsive, CMS, client handoff, starter project, Finsweet, Client-First, QA, publish, deploy, SEO Webflow, accessibility Webflow, mega menu build, forms Webflow. FOR: Building websites in Webflow, responsive development, CMS-driven sites, Webflow project setup, QA and launch, client handoff workflows. Do NOT use for animation/scroll effects — use webflow-animations instead. Do NOT use for visual design decisions — use web-layout, typography-systems, or color-systems instead. Do NOT use for Shopify builds — use shopify-ecommerce instead."
---

# Webflow Build

Build responsive, performant websites in Webflow. This skill covers the complete workflow from design handoff through live deployment, including HTML/CSS translation, layout patterns, CMS architecture, responsive cascading, QA, and client handoff.

---

## CORE PRINCIPLE: DOCUMENT FLOW

The web works like a document, not like Figma. Elements stack vertically by default. Every deviation from this flow requires explicit CSS.

**Three display modes that matter:**
1. **Block** (default) -- elements stack vertically, take full width
2. **Flex** -- one-dimensional layout (row or column), alignment via main/cross axes, gap for spacing
3. **Grid** -- two-dimensional layout (columns + rows), span elements across cells

**The Box Model** governs all sizing:
- Content + Padding (inside space) + Border + Margin (outside space)
- Every element is a rectangular box, even circles (border-radius)

---

## HTML/CSS IN WEBFLOW

Webflow's left panel (Navigator) = HTML structure. Right panel (Styles) = CSS properties.

**Semantic HTML matters:**
- H1-H6 are not just "big text" -- they carry meaning for Google and screen readers
- H1 = one per page only (book title). H2 = chapter names. Never skip levels
- Use heading elements, not styled paragraphs
- Link blocks make everything inside clickable (images, cards)
- Div blocks are the primary building container

**Nesting and cascading:**
- Children inherit CSS from parents (font, color, etc.)
- Style the body element correctly and everything inherits -- avoids repetitive styling
- Siblings at the same level do not affect each other's styles
- Responsive cascade: desktop changes flow DOWN to tablet/mobile. Never UP
- **Always build desktop-first.** Styles do not cascade upward

**Cascading pitfalls:**
- Structural changes (dragging elements in Navigator) are GLOBAL across all breakpoints
- Manual line breaks affect all breakpoints
- Element settings (not style panel) affect all breakpoints
- Only style panel changes are breakpoint-specific

For detailed element reference and box model specifics, see `references/01-html-css-webflow.md`.

---

## FLEXBOX PATTERNS

### Even Columns
- Parent: `display: flex`
- Each child: `flex-basis: 100%`
- Children push equally, creating even columns regardless of count
- Do NOT use percentage like 33.3% -- use 100% so it works for any number of children

### Grid-ish Layout (Auto-Wrapping)
- Parent: `display: flex`, wrap enabled
- Each child: `flex-grow: 1`, `flex-basis` in REMs (e.g., 15.5rem)
- Children wrap to next line automatically when space is insufficient
- Responsiveness comes free -- no breakpoint changes needed

### Content + Sidebar
- Parent: `display: flex`, wrap enabled
- Content: `flex-grow: 1`, `flex-basis: 70%`
- Sidebar: `flex-grow: 1`, `flex-basis: 30%`, `min-width: 15rem`
- Sidebar wraps below content when viewport shrinks below min-width

### Flexbox Masonry (Horizontal)
- Gallery list: `display: flex`, wrap, `gap: 0.5rem`
- Gallery item: `height: 36vh`, `flex-grow: 1`, `flex-shrink: 1`
- Gallery image: `width: 100%`, `height: 100%`, `object-fit: cover`
- Last empty item trick: `flex-grow: 10` with `aria-hidden="true"`

For all flexbox patterns with responsive adjustments, see `references/02-flexbox-positioning.md`.

---

## CSS POSITIONING

| Position | In Flow? | Relative To | Use Case |
|----------|----------|-------------|----------|
| Static | Yes | Normal flow | Default for all elements |
| Relative | Yes | Own normal position | Offset + create context for absolute children |
| Absolute | No | Nearest positioned ancestor | Overlays, decorative elements |
| Fixed | No | Viewport | Persistent navigation |
| Sticky | Yes until threshold | Scroll container | Sticky nav, sidebar |

**Z-Index strategy for layered sections:**
- Background decorative: z-index 0
- Interactive middle (3D model): z-index 1
- Content (text, buttons): z-index 2

**Sticky requirements:**
- Parent must NOT have `overflow: hidden`
- Element needs scroll room (container taller than element)
- Set `top` value for stick position

---

## WEBFLOW CMS

**Plan CMS structure before building.** Define all fields upfront: image, text, rich text, reference, multi-reference, color, switch.

**Common blog fields:** thumbnail image, main image, title, slug, author (reference), categories (multi-reference), publish date, body (rich text).

**CMS in starter projects:** Pre-build blog CMS structure so every new site has it ready. Include blog card component, author collection, category collection, and URL structures.

**CMS filtering:**
- Simple: native Webflow tabs component (each tab = category)
- Complex: Finsweet Attributes CMS Filter (free, powerful multi-filter/search/sort/pagination)

**CMS sliders:** Webflow's native slider does not support CMS binding. Use Finsweet Slider.

**Content import:** For large datasets, use CMS Bridge to import from Airtable/CSV. Batch import saves enormous time vs. manual entry.

For full CMS setup guide, see `references/03-cms-setup.md`.

---

## RESPONSIVE DESIGN PROCESS

### Build Order
1. Desktop first (styles cascade down)
2. Tablet
3. Mobile landscape
4. Mobile portrait
- Never skip to mobile -- work through tablet first

### Key Responsive Adjustments
- **Layout direction:** Flex row to column when content won't fit side-by-side
- **Font sizes:** Reduce headings per breakpoint (H1 from 90px desktop to 75px tablet to smaller)
- **Body text:** Consider 18px to 16px on tablet
- **Spacing:** Desktop padding/margins may be too generous on smaller screens
- **Images:** `object-fit: cover` with adjusted position (top-align portraits when cropped)
- **Hero height:** May change from 100vh to auto or split (50vh image + 50vh content)
- **Grid to flex:** Quick technique -- switch CSS grid to single-column flex on smaller breakpoints

### Common Responsive Bugs
- **Horizontal scroll on mobile:** Content extending beyond viewport width. Always test for this
- **Overflow hidden:** Check which element is wider than viewport
- **Display none:** Hide desktop-only elements on mobile. Hide on CLASS, not combo class

### Image Loading Strategy
- Set most images to "load with page" (not lazy load) -- avoids janky pop-in
- Exception: blog articles with many images should use lazy loading
- [CONTRARIAN -- Segall] Accept extra milliseconds of load for smooth visual experience

### Responsive Typography
- For full-width text that scales with viewport, use vw units
- Text fills section regardless of screen size, no container needed

---

## STARTER PROJECT STRATEGY

**Never start from scratch.** Always duplicate a starter project.

### Include in Starter
- Nav component and footer component
- Main wrapper and global styles
- Page wrapper with structured classes
- 404 page (styled with nav/footer and home button)
- Contact page and thank you page (with dynamic name via custom code)
- All-forms page (centralized form management)
- Legal docs template (privacy policy, terms)
- Auto-updating copyright year (JS snippet)
- Footer social links and "website by [agency]" link

### Relume Starter Kit
- Based on Finsweet Client-First framework
- Includes: style guide page, utility classes, global styles for smooth rendering
- Clone from relume.io, customize colors/fonts/components per project

---

## BUILD ORDER (10-STEP CHECKLIST)

1. **Style guide setup:** Upload logo, update colors, body styles, headings/text styles
2. **Nav and footer first** [CONTRARIAN -- Segall: "eat the frog"] -- build completely, fully responsive, all dropdowns, mobile menu done. Hardest part first
3. **Link up entire website:** All nav links, footer links, CMS page links, buttons. Zero dead links from day one
4. **Build easy sections:** Start with simplest sections across all pages. Creates momentum
5. **Build tricky sections:** Complex components, often composed of easy parts already built
6. **Technical SEO:** H-tag structure, meta titles/descriptions, OG images (1200x630), web clip (256x256), favicon (32x32)
7. **Integrations:** Mailchimp, Zapier, Make.com, custom APIs
8. **Make it sexy:** Scroll animations, hover effects, page transitions, preloader. See `webflow-animations` skill
9. **Clean up:** Delete unused media, add alt text, remove unused classes/interactions/components
10. **QA audit:** Side-by-side comparison -- design on monitor + staging on screen + real phone in hand

**Critical:** Disable subdomain indexing immediately when creating project. Triple-check this.

For the full checklist with sub-steps, see `references/04-build-checklist.md`.

---

## QA PROCESS

1. **Visual check:** Design on one monitor, staging in browser, real phone in hand. Section-by-section comparison
2. **Use actual phone** [CONTRARIAN -- Segall] -- browser emulation misses real-world rendering differences
3. **Webflow audit:** Click Publish, check issues count. Fix: missing alt text, broken links, accessibility warnings
4. **Click check:** Every link, button, dropdown, form submission, CMS link
5. **SEO check:** One H1 per page, proper hierarchy, meta titles/descriptions filled
6. **CMS check:** URL structures, collection page templates, reference connections

**Client feedback:** Use Markup.io (not email/Slack). Share staging link through Markup. Client pins comments to specific locations. One reviewer at a time.

---

## ASSET EXPORT WORKFLOW

1. Export ALL images from Figma at 2x resolution at project start
2. Compress ALL images using Cloud Convert in one batch
3. Upload ALL compressed images to Webflow organized by category
4. Do not export-compress-upload one at a time -- context-switching compounds across projects

---

## WEBFLOW ECOSYSTEM & TOOLS

### Finsweet
- **Client-First:** CSS naming convention and structure for scalable projects
- **Fluid Responsiveness:** Smooth responsive transitions
- **CMS Filter:** Advanced filtering, sorting, search
- **Attributes:** Custom attribute system for dropdowns, accordions

### Relume
- Component library, starter kit, icon library
- Import components directly into Webflow projects

### Other Key Integrations
- **Markup.io:** Visual feedback for client review
- **Make.com / Zapier:** Form and CRM automation
- **Memberstack:** Membership/paywall functionality
- **CMS Bridge:** Import data from Airtable
- **Cloud Convert:** Image compression

### Webflow + Figma Plugin
- Import variables (colors, typography tokens) from Figma directly
- Keeps design tokens in sync between design and development

---

## WEBFLOW-SPECIFIC TECHNIQUES

### Variables
- Create color, font, spacing variables at project start
- Global padding variable (e.g., 90px) reused across sections
- Variables can be animated in interactions

### Components
- Nav and footer as global components -- change once, updates everywhere
- CTA buttons, blog cards, forms as components
- Logo as "super component" with variants (primary SVG, secondary, icon-only)
- SVG with `currentColor` for CSS color control

### Page Templates with Slots
- Build page structures as components with designated slot areas
- Content goes into slots; structure stays consistent
- Essential for large sites with many similar pages

### Utility Classes (Client-First)
- Structured naming: padding-left, margin-top, etc.
- Pre-defined spacing values in starter kit
- Heading styles: heading-style-1 through heading-style-6 plus extras

---

## SEO & ACCESSIBILITY

### SEO Basics
- One H1 per page, proper heading hierarchy
- Meta titles and descriptions on every page
- OG images for social sharing (1200x630)
- Alt text on every image
- Clean URL slugs
- Sitemap auto-generated by Webflow
- 301 redirects for migrated sites (map old URLs before launch)

### Accessibility
- Semantic HTML (headings, lists, buttons, links)
- Alt text on all images
- Color contrast meeting AA standards (see `color-systems`)
- Form labels properly associated
- Skip navigation links
- ARIA attributes (e.g., `aria-hidden="true"` on decorative elements)
- Use lists for grouped content (screen readers announce count)

### Privacy
- Cookie consent banner (jurisdiction-dependent)
- Privacy policy and terms pages (pre-built in starter)
- GDPR/CCPA considerations based on audience geography

---

## PUBLISHING & HANDOFF

- Transfer project to client's Webflow account before launching
- Set up custom domain and SSL
- Re-link integrations connected to staging
- Final checks: all links, forms, redirects, subdomain indexing disabled
- Support video library: how to edit CMS, update blog, technical docs, site tour

---

## ANTI-PATTERNS

- Starting from scratch without a starter project
- Building fun sections before nav/footer
- Skipping tablet breakpoint
- Using browser emulation instead of real device testing
- Exporting/uploading images one at a time
- Using percentage-based flex-basis for even columns
- Not disabling subdomain indexing before build
- Sending to client without completing QA audit

---

## RELATED SKILLS

- **webflow-animations:** For scroll animations, Lottie, GSAP, hover effects (step 8 of build)
- **web-layout:** For design decisions feeding into this build (homepage structure, responsive patterns)
- **typography-systems:** For type hierarchy that informs heading styles in style guide
- **color-systems:** For palette that defines color variables in Webflow
- **design-systems:** For Figma tokens that import into Webflow via plugin
- **design-critique:** For pre-build design audit and post-build QA review
- **shopify-ecommerce:** If the project is e-commerce, use Shopify instead of Webflow
