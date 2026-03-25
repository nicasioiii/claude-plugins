---
name: Webflow Build
description: Build a website in Webflow from design to live deployment. Covers build order, flexbox patterns, CMS setup, responsive cascading, QA, and client handoff.
skill: webflow-build
---

# /webflow-build

You are helping the user build a website in Webflow. Follow this workflow:

## Step 1: Understand the Build

Ask the user:
1. **What design are we building?** (Figma file, design screenshots, or designing in Webflow)
2. **Is this CMS-driven?** (blog, portfolio, catalog, or static pages only)
3. **What starter project?** (blank, Client-First, Finsweet, custom template)
4. **What is the responsive strategy?** (desktop-first, then cascade down)
5. **Any integrations needed?** (forms, analytics, e-commerce, third-party tools)

## Step 2: Set Up the Project

1. Create project with chosen starter or blank canvas
2. Set up global styles: fonts, colors, default body styles
3. Create utility classes for spacing, text styles, and layout patterns
4. Set container max-width (typically 1200-1440px)
5. Define class naming convention (BEM, Client-First, or custom)

## Step 3: Build Order

Follow the top-down, outside-in build order:
1. **Navigation** (global, appears on every page)
2. **Footer** (global, appears on every page)
3. **Hero section** (most complex, sets the pattern)
4. **Content sections** (work down the page)
5. **Interior pages** (reuse section patterns)
6. **CMS templates** (if applicable)

## Step 4: Layout with Flexbox

Core Webflow layout patterns:
- **Horizontal layout:** Flex direction row, align center, justify space-between
- **Vertical stack:** Flex direction column, gap for consistent spacing
- **Grid:** CSS Grid for equal-column layouts (2-col, 3-col, 4-col)
- **Centering:** Flex with align-items center + justify-content center

Key rules:
- Use padding on containers, not margins
- Set max-widths on text containers for readable line lengths
- Use auto margins sparingly; prefer flexbox alignment

## Step 5: CMS Setup (if applicable)

1. Define collection structure (fields, relationships)
2. Create collection template pages
3. Design collection list components for index pages
4. Set up filtering and sorting
5. Create conditional visibility rules for optional fields

## Step 6: Responsive Cascade

Build desktop first, then cascade down:
- Desktop (base) → Tablet → Mobile Landscape → Mobile Portrait
- At each breakpoint: adjust typography, spacing, layout direction, visibility
- Test navigation pattern (hamburger menu on tablet/mobile)
- Verify touch targets meet 44px minimum on mobile

## Step 7: QA Checklist

Before launch, verify:
- All links work (internal and external)
- Forms submit correctly with proper redirects
- Images are optimized (WebP, proper sizing)
- SEO: meta titles, descriptions, OG images on every page
- Favicon and webclip icons set
- 404 page designed and configured
- Responsive behavior on real devices
- Performance: page load speed under 3 seconds

## Step 8: Recommend Next Steps

- If animation is needed → recommend `/animate`
- If ready for review → recommend `/design-audit`
- If responsive issues found → recommend `/responsive-check`

## Skills Activated

- **webflow-build** (primary)
- Cross-references: web-layout, layout-spacing, webflow-animations
