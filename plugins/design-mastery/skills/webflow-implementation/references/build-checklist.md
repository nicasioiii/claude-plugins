# Comprehensive Webflow Build Checklist

A detailed, step-by-step guide covering all phases of building a Webflow site from scratch to launch. This checklist ensures nothing is missed and serves as a quality assurance gate at each stage.

---

## PHASE 1: FOUNDATIONAL SETUP (Steps 1-12)

### Site Creation & Configuration

- [ ] **Step 1: Create Webflow Site**
  - [ ] Name site appropriately (will appear in Webflow dashboard)
  - [ ] Select hosting plan (Free, Starter, Professional, Business)
  - [ ] Choose site language/region
  - [ ] Create workspace if needed for team collaboration

- [ ] **Step 2: Configure Custom Domain**
  - [ ] Register domain (GoDaddy, Namecheap, or Webflow Domains)
  - [ ] Add to Webflow: Site Settings > Domain
  - [ ] Point nameservers or update DNS records
  - [ ] Wait 24-48 hours for propagation
  - [ ] Verify SSL certificate auto-installed (green lock icon)

- [ ] **Step 3: Upload and Manage Fonts**
  - [ ] Go to Site Settings > Fonts tab
  - [ ] Import Google Fonts: Search by name, select weights needed
  - [ ] Select only required weights (400, 600, 700 typically)
  - [ ] **Critical:** Choose language "Latin" for efficiency
  - [ ] For GDPR compliance: Download variable fonts and upload directly to Webflow
  - [ ] Set fallback fonts: Georgia (serif), Arial (sans-serif)
  - [ ] Test font loading on 3G connection (Settings > Audit)

- [ ] **Step 4: Create Color Variables**
  - [ ] Go to Site Settings > Variables panel
  - [ ] Create color variables following naming convention: `colors/[name]`
  - [ ] Include: `colors/primary`, `colors/secondary`, `colors/neutral-dark`, `colors/neutral-light`
  - [ ] Add semantic colors: `colors/text`, `colors/borders`, `colors/backgrounds`
  - [ ] Store brand hex values in variables (allows global updates)
  - [ ] Test: Change one color variable, verify updates across entire site

- [ ] **Step 5: Define Typography Styles**
  - [ ] Create typography variables: `fonts/heading`, `fonts/body-text`
  - [ ] Set baseline font sizes (Desktop/Tablet/Mobile):
    - [ ] H1: 90px desktop, 60px tablet, 40px mobile
    - [ ] H2: 60px desktop, 40px tablet, 32px mobile
    - [ ] H3: 32px desktop, 28px tablet, 24px mobile
    - [ ] H4: 24px desktop, 20px tablet, 18px mobile
    - [ ] Body: 18px desktop, 16px tablet, 16px mobile (never below 16px)
    - [ ] Small: 14px desktop, 12px tablet, 12px mobile
  - [ ] Set line heights: Titles 95-100%, Body 160%, Small 150%
  - [ ] Apply styles to global elements (H1, H2, H3, P, small)

- [ ] **Step 6: Configure Site-Wide Settings**
  - [ ] Add favicon: Site Settings > General
  - [ ] Set default open graph image (1200x630px for social sharing)
  - [ ] Set default language metadata
  - [ ] Add site description (meta description)
  - [ ] Configure analytics (GA4, GTM ID if needed)

- [ ] **Step 7: Create Global Styles**
  - [ ] Set body background color
  - [ ] Set default text color (use color variable)
  - [ ] Style default link color and hover state
  - [ ] Set focus states for keyboard accessibility (outline or custom)
  - [ ] Apply global heading styles to H1-H6 elements
  - [ ] Create utility classes: `text-center`, `text-large`, `round-corners`, `background-color-[color]`

- [ ] **Step 8: Test Basic Element Styles**
  - [ ] Create temporary test page with all element types
  - [ ] Verify heading hierarchy (H1 largest, H2, H3, etc.)
  - [ ] Test paragraph formatting and line height
  - [ ] Test link styling (default, hover, visited)
  - [ ] Test button default styling
  - [ ] Test form input fields
  - [ ] Delete test page when complete

- [ ] **Step 9: Set Spacing Scale Variables**
  - [ ] Create spacing variables: `space/small` (12px), `space/medium` (24px), `space/large` (32px), `space/xl` (48px), `space/2xl` (64px)
  - [ ] These will be used consistently for gap, padding, margin
  - [ ] Document the scale for team reference

- [ ] **Step 10: Create Container Component Pattern**
  - [ ] Build reusable container: max-width 1200px, margin 0 auto
  - [ ] Set padding: 64px (desktop), 48px (tablet), 24px (mobile)
  - [ ] Save as reusable component for consistency

- [ ] **Step 11: Establish Naming Conventions**
  - [ ] Use BEM-inspired pattern: `[component]-[element]-[modifier]`
  - [ ] Examples: `hero-section`, `hero-image`, `button-primary`, `text-center`
  - [ ] Document naming conventions in project notes
  - [ ] Never use position-based names (breaks on mobile)

- [ ] **Step 12: Quality Test - Setup Phase**
  - [ ] Verify all fonts load correctly
  - [ ] Verify all colors appear correctly
  - [ ] Test on mobile, tablet, desktop at actual breakpoints
  - [ ] Check no console errors
  - [ ] Verify domain setup complete and SSL active

---

## PHASE 2: STRUCTURAL COMPONENTS (Steps 13-25)

### Navigation & Header

- [ ] **Step 13: Build Navigation Component**
  - [ ] Create nav section: flex row, sticky position, top: 0, z-index: 100
  - [ ] Add logo: 40-48px width, left align
  - [ ] Add menu items: flex row, gap 32px, center aligned
  - [ ] Set nav styling: transparent on hero, solid background elsewhere
  - [ ] Add CTA button: right align, primary styling
  - [ ] Apply hover states: underline or color change (200ms ease-in-out)

- [ ] **Step 14: Build Mobile Navigation**
  - [ ] Create separate mobile nav (hidden on desktop)
  - [ ] Add hamburger icon (☰) component
  - [ ] Build slide-out menu (flex column, full width)
  - [ ] Add close button inside menu
  - [ ] Set interaction: hamburger toggles menu visibility
  - [ ] Test: Clicks outside menu close it

- [ ] **Step 15: Responsive Navigation Breakpoints**
  - [ ] Desktop (1440px+): Horizontal menu visible, hamburger hidden
  - [ ] Tablet (1024px): Test menu spacing, may hide non-essential items
  - [ ] Mobile (480px): Hamburger visible, desktop menu hidden
  - [ ] Test actual device sizes, not just browser resize

- [ ] **Step 16: Build Footer Component**
  - [ ] Create footer section: dark background, padding 80px 64px (desktop)
  - [ ] Build 4-column content grid:
    - [ ] Column 1: Logo/Brand
    - [ ] Column 2: Product/Services links
    - [ ] Column 3: Company/Legal links
    - [ ] Column 4: Contact/Social CTA
  - [ ] Add divider line above bottom section
  - [ ] Add bottom bar: flex space-between
    - [ ] Left: Copyright text
    - [ ] Center: Social media links
    - [ ] Right: Legal links (Privacy, Terms)
  - [ ] Set responsive: 4 columns desktop, 2 columns tablet, 1 column mobile

- [ ] **Step 17: Test Navigation & Footer**
  - [ ] All links clickable and working
  - [ ] Hover states visible and smooth
  - [ ] Mobile menu opens/closes properly
  - [ ] Footer appears on every page
  - [ ] Links are keyboard accessible (tab through)

- [ ] **Step 18: Create Page Structure**
  - [ ] Create page list: Home, About, Services, Contact
  - [ ] Duplicate home page for template structure
  - [ ] Apply nav + footer to all pages
  - [ ] Update page titles in browser tab (SEO)
  - [ ] Add meta descriptions (150-160 characters)

---

### Main Content Sections

- [ ] **Step 19: Build Hero Section**
  - [ ] Setup: section with 100vh height
  - [ ] Create flex container: flex row, gap 24px, justify-content space-between
  - [ ] Add hero image: 50% width (desktop), object-fit cover, height 100%
  - [ ] Add hero content: 50% width, flex column, centered, padding 64px
  - [ ] Content hierarchy:
    - [ ] H1: 90px, line-height 95%, brand color or white
    - [ ] Subheading: 24px, line-height 140%, secondary text color
    - [ ] Button: Primary style, 48px height, hover scale 1.05
  - [ ] Responsive: Stack vertically on mobile (100% width each)
  - [ ] **Mobile:** Column layout, image on top, content below

- [ ] **Step 20: Build Features/Services Section**
  - [ ] Create section: full width, padding 80px 64px
  - [ ] Build container: max-width 1200px, margin 0 auto
  - [ ] Create heading: H2 or H3, centered
  - [ ] Build 3-column grid (or customize based on design):
    - [ ] Gap: 32px between cards
    - [ ] Each card: flex column, padding 40px, border-radius 16px
    - [ ] Each card contains: icon/image, heading, description, link/button
  - [ ] Responsive: 3 columns desktop, 2 columns tablet, 1 column mobile
  - [ ] Hover state: Slight lift (translateY -4px), shadow increase

- [ ] **Step 21: Build Testimonials Section**
  - [ ] Create section: light background, padding 80px 64px
  - [ ] Build container and heading (H2, centered)
  - [ ] Create testimonial grid: 2-3 columns
  - [ ] Testimonial card structure:
    - [ ] Avatar: 48px circle image, border-radius 999px
    - [ ] Quote: 18px, italic, line-height 160%
    - [ ] Author name: 16px, semi-bold
    - [ ] Author title: 14px, secondary text
  - [ ] Responsive: 2 columns tablet, 1 column mobile
  - [ ] Add stars/rating if applicable

- [ ] **Step 22: Build CTA Section**
  - [ ] Create dedicated section: full width, dark background (or brand color)
  - [ ] Center content: flex column, center aligned, padding 80px 64px
  - [ ] Layout:
    - [ ] Heading: H2 or H3, white/light text
    - [ ] Subheading: 24px, secondary text
    - [ ] Button: Primary or secondary style, prominent
  - [ ] Optional: Add background pattern or gradient
  - [ ] Responsive: Maintain centered layout, adjust padding on mobile

- [ ] **Step 23: Test All Content Sections**
  - [ ] Desktop (1440px): All sections render correctly
  - [ ] Tablet (1024px): Responsive changes apply
  - [ ] Mobile (480px): Single-column layout, readable text
  - [ ] Spacing: Verify 80px gaps between sections (desktop), 40px (mobile)
  - [ ] Alignment: All elements centered or aligned to grid
  - [ ] Images: Load properly, object-fit working

- [ ] **Step 24: Verify Spacing Consistency**
  - [ ] Section top padding: 80px desktop, 60px tablet, 40px mobile
  - [ ] Section left/right padding: 64px desktop, 48px tablet, 24px mobile
  - [ ] Internal gaps: Use `space/medium` (24px) or `space/large` (32px)
  - [ ] Vertical rhythm: Consistent spacing between elements
  - [ ] Grid alignment: All elements snap to established grid

- [ ] **Step 25: Test Responsive Breakpoints**
  - [ ] Desktop (1920px): Full layout, generous spacing
  - [ ] Laptop (1440px): Refined version of desktop
  - [ ] Tablet landscape (1024px): Adjusted columns, maintained readability
  - [ ] Tablet portrait (768px): Single column where needed
  - [ ] Mobile (480px): Optimized for small screens, full width content
  - [ ] Test intermediate sizes: 640px, 800px, 1200px

---

## PHASE 3: INTERACTIONS & ANIMATIONS (Steps 26-30)

- [ ] **Step 26: Add Button Hover Interactions**
  - [ ] Primary button: Scale 1.05, shadow 0 10px 30px rgba(0,0,0,0.15), duration 200ms
  - [ ] Secondary button: Color shift or border highlight
  - [ ] All buttons: cursor pointer, ease-in-out easing
  - [ ] Test on mobile: Tap behaves similar to hover

- [ ] **Step 27: Add Link Hover States**
  - [ ] Text links: Underline appear or color change
  - [ ] Duration: 200ms
  - [ ] Easing: ease-in-out
  - [ ] Verify visited state styling (if applicable)

- [ ] **Step 28: Add Card Hover Effects**
  - [ ] Cards: TranslateY -4px, shadow increase
  - [ ] Duration: 300ms
  - [ ] Easing: ease-out
  - [ ] Optional: Background color or opacity shift
  - [ ] Test: Smooth on desktop and mobile

- [ ] **Step 29: Add Scroll Entrance Animations (Optional)**
  - [ ] Use "Scroll into view" trigger for fade-in effect
  - [ ] Timing: 600-800ms duration, ease-out easing
  - [ ] Apply to cards, sections, images as they come into view
  - [ ] Test: Not janky, not too slow

- [ ] **Step 30: Quality Test - Interactions**
  - [ ] All buttons respond to hover/click
  - [ ] Animations smooth (60fps, no stuttering)
  - [ ] Mobile: Touch states work as expected
  - [ ] No console errors during interactions
  - [ ] Keyboard navigation works (tab through interactive elements)

---

## PHASE 4: FORMS & DYNAMIC CONTENT (Steps 31-33)

- [ ] **Step 31: Create Contact Form**
  - [ ] Add form section with heading
  - [ ] Form fields:
    - [ ] Name: Text input, required
    - [ ] Email: Email input, required, validation
    - [ ] Subject: Text input, optional
    - [ ] Message: Textarea, required
    - [ ] Submit button: Primary style
  - [ ] Set field styling: height 40px, padding 10px 12px, border 1px solid #CCC
  - [ ] Focus state: Border color change, glow effect
  - [ ] Responsive: Full width inputs on mobile

- [ ] **Step 32: Configure Form Submission**
  - [ ] Option A: Email notification
    - [ ] Set destination email
    - [ ] Test: Submit form, verify email received
    - [ ] Check: No sensitive data exposed in form code
  - [ ] Option B: CMS integration (if using dynamic collections)
    - [ ] Map form fields to collection fields
    - [ ] Verify entries appear in CMS dashboard
  - [ ] Add success message: "Thank you, we'll be in touch"

- [ ] **Step 33: Test Forms**
  - [ ] Submit with all fields filled
  - [ ] Test validation: Submit with empty fields (should show errors)
  - [ ] Test invalid email: Shows error message
  - [ ] Success message displays
  - [ ] Mobile: Form responsive and usable on small screen

---

## PHASE 5: OPTIMIZATION & QUALITY (Steps 34-45)

### Performance & Image Optimization

- [ ] **Step 34: Optimize All Images**
  - [ ] Export from Figma/design tool at 2x resolution for Retina displays
  - [ ] Compress using TinyPNG, ImageOptim, or similar
  - [ ] Hero images: 2000x1000px max
  - [ ] Card images: 600x400px max
  - [ ] Thumbnails: 200x200px max
  - [ ] Mark as "High DPI" if Retina quality needed
  - [ ] Lazy loading: Enabled by default in Webflow (verify in Settings > Performance)

- [ ] **Step 35: Format Selection for Images**
  - [ ] JPG: Photos, gradients (best compression)
  - [ ] PNG: Graphics with transparency (if WebP not supported)
  - [ ] WebP: Modern format, better compression (enable in Webflow)
  - [ ] SVG: Icons, logos (infinitely scalable, smallest file size)
  - [ ] Verify WebP support in browsers (works in all modern browsers)

- [ ] **Step 36: Verify Font Loading Performance**
  - [ ] Only include weights actually used: 400, 600, 700 typically
  - [ ] Check font file sizes in browser DevTools (Network tab)
  - [ ] Variable fonts: Single file for all weights (much smaller)
  - [ ] Test font display on slow connection: Throttle to 3G
  - [ ] Verify no invisible text flash (FOIT) or layout shift (FOUT)

- [ ] **Step 37: Remove Unused CSS & Code**
  - [ ] Go to Site Settings > Audit
  - [ ] Check for unused classes, styles, components
  - [ ] Delete unused pages, assets, or classes
  - [ ] Review custom code blocks (remove if unused)
  - [ ] Minimize external script loads (only essential)

- [ ] **Step 38: Run Webflow Performance Audit**
  - [ ] Site Settings > Audit tab
  - [ ] Review all recommendations
  - [ ] Fix critical issues (marked in red):
    - [ ] Images not optimized
    - [ ] Fonts impacting load time
    - [ ] JavaScript/CSS issues
    - [ ] Core Web Vitals below threshold
  - [ ] Target metrics:
    - [ ] LCP (Largest Contentful Paint): < 2.5 seconds
    - [ ] FID (First Input Delay): < 100ms
    - [ ] CLS (Cumulative Layout Shift): < 0.1

- [ ] **Step 39: Test Load Time**
  - [ ] Use PageSpeed Insights or GTmetrix
  - [ ] Test on real device with 3G throttling
  - [ ] Target: Full page load under 3 seconds
  - [ ] Largest Contentful Paint appears before 2.5 seconds

### Accessibility & Standards

- [ ] **Step 40: Test Keyboard Navigation**
  - [ ] Tab through all interactive elements (links, buttons, form fields)
  - [ ] Focus indicator visible on each element
  - [ ] Tab order makes sense (logical flow)
  - [ ] No keyboard traps (can't exit any element)

- [ ] **Step 41: Verify SEO Basics**
  - [ ] Each page has unique title (browser tab)
  - [ ] Meta descriptions (150-160 characters, written for users)
  - [ ] H1 appears once per page (main heading)
  - [ ] Images have alt text (describes image for screen readers)
  - [ ] Links have descriptive text (not "click here")

- [ ] **Step 42: Test on Real Devices**
  - [ ] iPhone (iOS Safari): All pages, all interactions
  - [ ] Android (Chrome): All pages, all interactions
  - [ ] Landscape mode: Layout remains usable
  - [ ] Touch interactions: Tap states, no hover issues
  - [ ] Camera/proximity sensors: Not interfering with page

### Final QA & Launch

- [ ] **Step 43: Comprehensive Testing Matrix**
  - [ ] Test each page at 5 breakpoints: 1920px, 1440px, 1024px, 768px, 480px
  - [ ] All navigation links work
  - [ ] All external links open in new tabs (if intended)
  - [ ] All buttons/forms functional
  - [ ] All images display correctly (no broken images)
  - [ ] No console errors (DevTools > Console)
  - [ ] All text readable (no contrast issues)

- [ ] **Step 44: Cross-Browser Testing**
  - [ ] Chrome/Edge (Chromium): Latest version
  - [ ] Safari (Mac & iOS): Latest version
  - [ ] Firefox: Latest version
  - [ ] Older browser (IE11): If clients require (graceful degradation)
  - [ ] Mobile browsers: Chrome Android, Safari iOS

- [ ] **Step 45: Final Launch Checklist**
  - [ ] All pages published (not in draft)
  - [ ] Domain SSL active (green lock icon)
  - [ ] Sitemap auto-generated (check Webflow Settings)
  - [ ] Analytics configured (GA4, Webflow built-in)
  - [ ] Backup created (if applicable)
  - [ ] Client/stakeholder sign-off completed
  - [ ] Documentation provided (if client will manage content)
  - [ ] Go live and monitor for issues in first 24 hours
