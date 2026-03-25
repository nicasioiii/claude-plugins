---
name: Responsive Check
description: Cross-skill responsive design audit covering breakpoint behavior, typography scaling, spacing adjustments, navigation patterns, and device testing.
skill: web-layout, webflow-build
---

# /responsive-check

You are conducting a responsive design audit. This is a cross-skill command that combines web-layout and webflow-build knowledge. Follow this workflow:

## Step 1: Gather Context

Ask the user:
1. **What am I reviewing?** (live URL, Figma responsive frames, Webflow preview)
2. **What breakpoints were targeted?** (desktop, tablet, mobile, or custom)
3. **What is the primary device?** (desktop-first or mobile-first)
4. **Any known problem areas?**

## Step 2: Desktop Audit (1440px+)

- [ ] Container max-width is set (typically 1200-1440px)
- [ ] Grid is working correctly (12-column layout)
- [ ] Content does not stretch past readable widths
- [ ] Images maintain aspect ratio and quality
- [ ] Navigation shows all primary items
- [ ] Hover states are functional

## Step 3: Tablet Audit (768-1024px)

- [ ] Grid collapses appropriately (12 → 6 columns)
- [ ] Side-by-side layouts stack where needed
- [ ] Navigation switches to hamburger or condensed pattern
- [ ] Touch targets meet 44px minimum
- [ ] Font sizes adjust (reduce hero sizes, maintain body readability)
- [ ] Spacing scale reduces proportionally
- [ ] No horizontal scrolling

## Step 4: Mobile Audit (375-414px)

- [ ] Single-column layout where appropriate
- [ ] Navigation is hamburger menu or bottom nav
- [ ] Buttons are full-width or comfortably tappable
- [ ] Body text is 16px minimum (prevents iOS auto-zoom)
- [ ] Images scale correctly (no overflow, no pixelation)
- [ ] Forms are usable (inputs large enough, labels visible)
- [ ] No content is cut off or hidden unintentionally
- [ ] Scroll experience is smooth (no janky animations)

## Step 5: Typography Responsive Check

| Element | Desktop | Tablet | Mobile |
|---------|---------|--------|--------|
| Hero title | 60-96px | 40-60px | 32-48px |
| Section title | 34-48px | 28-36px | 24-32px |
| Body copy | 16-18px | 16-18px | 16px minimum |
| Captions | 12-14px | 12-14px | 12-14px |

Verify:
- Line-heights remain appropriate at each size
- Body copy width stays within 45-75 character range
- Heading hierarchy is maintained (not all headings same size on mobile)

## Step 6: Spacing Responsive Check

- Section padding reduces proportionally at smaller breakpoints
- Component gaps tighten on mobile (but maintain proximity relationships)
- Card padding adjusts (desktop 24-32px → mobile 16-20px)
- Page margins adjust (desktop 40-60px → mobile 16-24px)

## Step 7: Interactive Element Check

- [ ] All buttons and links have adequate touch targets on mobile
- [ ] Dropdown menus work on touch devices
- [ ] Modals/dialogs fit within mobile viewport
- [ ] Form validation messages are visible on small screens
- [ ] Scroll animations perform well on mobile (test on real device)
- [ ] Sticky elements do not obscure content

## Step 8: Performance Check

- [ ] Images use responsive srcset or Webflow responsive images
- [ ] No large assets loaded unnecessarily on mobile
- [ ] Page load time under 3 seconds on mobile connection
- [ ] Animations do not cause jank on mobile

## Step 9: Deliver Findings

List issues by breakpoint and severity:
- **Critical:** Broken layouts, unusable interactions, text overflow
- **Major:** Poor touch targets, unreadable text, missing responsive adjustments
- **Minor:** Spacing inconsistencies, alignment tweaks

## Step 10: Recommend Fixes

- Layout issues → reference `/layout-grid`
- Typography scaling → reference `/type-system`
- Build implementation → reference `/webflow-build`
- Animation performance → reference `/animate`

## Skills Activated

- **web-layout** (responsive strategy)
- **webflow-build** (implementation and QA)
- Cross-references: layout-spacing, typography-systems, webflow-animations
