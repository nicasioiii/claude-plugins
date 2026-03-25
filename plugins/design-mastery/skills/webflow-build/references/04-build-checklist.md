---
name: Build Checklist & QA
description: "10-step build order, starter project contents, QA process, asset export, SEO/accessibility checklist, client handoff."
---

# Webflow Build Checklist & QA

Step-by-step build order and quality assurance process for Webflow projects.

---

## PRE-BUILD SETUP

### Before You Start
- [ ] Disable subdomain indexing immediately (triple-check)
- [ ] Duplicate starter project (never start from scratch)
- [ ] Export all images from Figma at 2x
- [ ] Compress all images via Cloud Convert
- [ ] Upload all images to Webflow organized by category
- [ ] Review design file for all font weights needed
- [ ] Verify you have all assets (logos, icons, photography)
- [ ] Confirm CMS structure plan

### Starter Project Contents
- [ ] Nav component (global)
- [ ] Footer component (global)
- [ ] Main wrapper + page wrapper
- [ ] Global styles (body, headings, links)
- [ ] Style guide page
- [ ] Utility classes (padding, margin tokens)
- [ ] 404 page (styled with nav/footer + home button)
- [ ] Contact page
- [ ] Thank you page (with dynamic name)
- [ ] All-forms page (centralized form management)
- [ ] Legal docs template (privacy, terms)
- [ ] Auto-updating copyright year snippet
- [ ] Footer social links + agency credit

---

## 10-STEP BUILD ORDER

### Step 1: Style Guide Setup
- [ ] Upload global logo
- [ ] Update all color variables
- [ ] Update body styles (font-family, font-size, line-height, color)
- [ ] Update heading styles (H1-H6 + extras)
- [ ] Update text size classes
- [ ] Update button styles (primary, secondary, outline)
- [ ] Update link styles
- [ ] Verify spacing token variables

### Step 2: Navigation & Footer (Eat the Frog)
Build the hardest parts first -- everything accelerates after this.
- [ ] Desktop navigation fully built
- [ ] All dropdown/mega menu states working
- [ ] Mobile hamburger menu built
- [ ] Mobile menu animation working
- [ ] Footer fully built and responsive
- [ ] Logo component with variants

### Step 3: Link Up Entire Website
- [ ] Create all pages (empty shells)
- [ ] Connect all nav links
- [ ] Connect all footer links
- [ ] Connect CMS page links
- [ ] Verify zero dead links

### Step 4: Build Easy Sections
Start with simplest sections across all pages:
- [ ] Hero sections (each page)
- [ ] Simple text/image sections
- [ ] CTA sections
- [ ] Basic card grids
- Creates momentum and sense of progress

### Step 5: Build Tricky Sections
Complex components, often composed of easy parts already built:
- [ ] Testimonial sliders
- [ ] Tabbed content
- [ ] Interactive elements
- [ ] CMS-connected sections
- [ ] Custom layouts

### Step 6: Technical SEO
- [ ] One H1 per page (verify heading hierarchy)
- [ ] Meta titles on every page (unique, under 60 chars)
- [ ] Meta descriptions on every page (unique, under 160 chars)
- [ ] Open Graph images uploaded (1200 x 630px per page)
- [ ] Web clip uploaded (256 x 256px)
- [ ] Favicon uploaded (32 x 32px)
- [ ] 301 redirects mapped (if replacing existing site)
- [ ] Clean URL slugs (no "copy-of-" artifacts)

### Step 7: Integrations & Automations
- [ ] Form submissions connected (native or Zapier/Make)
- [ ] Email marketing integration (Mailchimp, Klaviyo)
- [ ] Analytics installed (Google Analytics, etc.)
- [ ] CRM connections active
- [ ] Any third-party embeds working

### Step 8: Make It Sexy
Animations added AFTER site is fully functional. See `webflow-animations` skill.
- [ ] Scroll animations applied
- [ ] Hover effects on interactive elements
- [ ] Page transitions (if desired)
- [ ] Custom scrollbar (if desired)
- [ ] Preloader (if desired)
- [ ] Finsweet Fluid Responsiveness applied

### Step 9: Clean Up
- [ ] Delete unused media (select all > delete > publish > refresh)
- [ ] Add alt text to ALL images
- [ ] Remove unused CSS classes
- [ ] Remove unused interactions
- [ ] Remove unused components
- [ ] Remove test/placeholder content
- [ ] Verify no lorem ipsum remains

### Step 10: QA Audit
- [ ] Complete visual check (see QA Process below)
- [ ] Complete click check
- [ ] Complete SEO check
- [ ] Complete CMS check
- [ ] Complete accessibility check

---

## QA PROCESS

### Visual Check
1. Open design on one monitor
2. Open staging site in browser on second monitor (or split screen)
3. Hold real phone in hand with staging URL open
4. Scroll section-by-section, comparing:
   - [ ] Spacing matches design
   - [ ] Font weights match
   - [ ] Image sizes and crops correct
   - [ ] Colors accurate
   - [ ] Check desktop AND mobile simultaneously

### Click Check
- [ ] Every navigation link works
- [ ] Every button works
- [ ] Every dropdown opens/closes correctly
- [ ] Every form submits successfully
- [ ] Every CMS link goes to correct item
- [ ] Logo links to homepage
- [ ] Social links open in new tab
- [ ] Footer links work
- [ ] 404 page displays correctly for bad URLs

### SEO Check
- [ ] Exactly one H1 per page
- [ ] Heading hierarchy logical (no skipped levels)
- [ ] Meta titles filled (every page)
- [ ] Meta descriptions filled (every page)
- [ ] Alt text on every image
- [ ] Sitemap accessible
- [ ] Robots.txt not blocking important pages

### CMS Check
- [ ] URL structures correct
- [ ] Collection page templates display correctly
- [ ] Reference connections working
- [ ] CMS filters/sort working
- [ ] Pagination working (if applicable)
- [ ] Empty states handled gracefully

### Accessibility Check
- [ ] Semantic HTML used (headings, lists, buttons)
- [ ] All images have alt text
- [ ] Color contrast meets AA (4.5:1 text, 3:1 large text)
- [ ] Form labels properly associated with inputs
- [ ] Skip navigation link present
- [ ] ARIA attributes on decorative elements
- [ ] Tab order logical
- [ ] Focus states visible

---

## CLIENT FEEDBACK PROCESS

### Tools
- **Markup.io** (recommended) -- visual feedback pinned to page locations
- Share staging link (never live link) through Markup
- Client comments show device and exact position

### Rules
- One reviewer at a time (not a communication tool)
- Resolve comments one by one as fixes are made
- Redirect all feedback to Markup (not email, Slack, or DMs)
- Free plan works for most freelancers (delete projects after completion)

---

## PRE-LAUNCH CHECKLIST

- [ ] All QA checks passed
- [ ] Client approval received
- [ ] Project transferred to client's Webflow account
- [ ] Custom domain connected
- [ ] SSL certificate active
- [ ] Integrations re-linked (forms, analytics, CRM)
- [ ] 301 redirects active (if migrating)
- [ ] Subdomain indexing STILL disabled
- [ ] Google Search Console configured
- [ ] Sitemap submitted

---

## POST-LAUNCH

### 30-Day Review
- [ ] Check site performance
- [ ] Fix any reported issues
- [ ] Gather client feedback

### Client Handoff Deliverables
- [ ] Support video library:
  - How to edit CMS content
  - How to update blog posts
  - How to add/edit pages
  - Technical documentation
  - Full site tour video
- [ ] Credentials and access documented
- [ ] Case study created (screenshot all pages, publish)
- [ ] Social media promotion (promote client, not yourself)

### Ongoing Support
- Communication cadence: scheduled check-ins (e.g., every Monday)
- Support channel: single defined channel (Slack, email)
- Scope for additional work: hourly rate with estimated range
