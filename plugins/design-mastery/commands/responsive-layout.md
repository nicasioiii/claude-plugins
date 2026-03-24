---
name: Responsive Layout
description: "Design a responsive website layout with desktop, tablet, and mobile breakpoints plus Webflow implementation."
---

# Responsive Layout

Design a responsive website layout for any site type. This provides section breakdowns, spacing guidelines, component recommendations, and Webflow implementation techniques.

---

## What This Command Does

You tell me what type of website you're designing, and I'll provide:
- Full-page layout breakdown (hero, features, testimonials, CTA, footer)
- Responsive breakpoint strategy (desktop, tablet, mobile)
- Spacing and sizing by breakpoint
- Component recommendations for each section
- Figma layout templates
- Webflow implementation techniques
- Mobile-first design strategy
- Image aspect ratios and handling

**Time to answer:** 2 minutes
**Time to receive layout:** 10-15 minutes

---

## Scoping Questions

**QUESTION 1: What type of website?**

Choose one:
- **Marketing Website** (agency, product, company)
- **SaaS Landing Page** (tool, platform, B2B)
- **E-commerce Product Page** (store, shopping)
- **Portfolio/Personal Site** (designer, developer, creator)
- **Blog/Content Site** (news, education, publishing)
- **Web App** (internal tool, admin panel)
- **Other:** Describe briefly

---

**QUESTION 2: What's the primary goal?**

What action should users take?
- *Examples: "Sign up for free trial," "Purchase product," "Schedule demo," "Read article," "Browse products"*

---

**QUESTION 3: Key sections you need?** (Optional)

List the main sections (I can suggest if unsure):
- *Examples: Hero, Benefits, Features, Pricing, Testimonials, FAQ, CTA, Footer*

---

## By Website Type

Once you answer, I'll provide a customized layout. Here's what each type typically includes:

### 1. MARKETING WEBSITE

**Standard Sections:**
1. **Hero Section** (headline, subheading, CTA button, background image)
2. **Value Props** (3-4 key benefits, icon + text cards)
3. **Features Section** (detailed feature breakdown, alternate image/text layout)
4. **Testimonials** (3-5 quotes from happy clients, avatar + name)
5. **CTA Section** (final push, compelling copy, button)
6. **Footer** (links, contact, social, copyright)

**Layout Patterns:**
- Desktop: Full width sections, centered content area (max 1200px)
- Tablet: 90% width, reduce padding
- Mobile: 100% width, single column, stacked sections

**Key Metrics:**
```
Hero height:           500-600px (desktop), 400px (mobile)
Section padding:       60-80px top/bottom (desktop), 40px (tablet), 24px (mobile)
Container max-width:   1200px
Cards grid:            3 columns (desktop), 2 columns (tablet), 1 column (mobile)
Gap between cards:     24px (desktop), 16px (mobile)
```

**Component Recommendations:**
- Hero: Large heading (48px), subheading (20px), prominent button
- Value Props: Icon (48px), title (18px), description (14px)
- Features: Mix image and text (50/50 split)
- Testimonials: Quote cards with avatar (48px), name (14px), title (12px)
- CTA: Centered block, heading, subheading, button, optional form

---

### 2. SAAS LANDING PAGE

**Standard Sections:**
1. **Hero Section** (product headline, value prop, CTA, product screenshot)
2. **Problem Statement** (the problem they face, visually)
3. **Solution Features** (how product solves it, 4-6 features with icons)
4. **Pricing Section** (3-tier pricing table, highlight recommended)
5. **FAQ Section** (accordion, 6-8 common questions)
6. **Final CTA** (free trial signup, low pressure)
7. **Footer** (standard footer)

**Layout Patterns:**
- Hero: Split layout (text left, screenshot right) on desktop
- Features: Alternating image/text (image right, then left, then right)
- Pricing: Side-by-side cards, highlight middle with shadow
- FAQ: Accordion (collapsed by default, expand on click)

**Key Metrics:**
```
Hero height:           400-500px
Screenshot aspect:     16:9 or 4:3
Section padding:       80px top/bottom (desktop), 40px (mobile)
Feature cards:         2 columns (desktop), 1 column (mobile)
Pricing cards:         3 columns (desktop), 1 column (mobile)
Card shadows:          2px, 8px, 16px blur
```

**Component Recommendations:**
- Hero heading: 48-56px, bold
- Subheading: 18-20px, regular weight
- Feature icons: 48-64px, consistent color
- Pricing cards: 300px width each, highlight with color change or scale
- Button: Consistent primary blue, 40px height

---

### 3. E-COMMERCE PRODUCT PAGE

**Standard Sections:**
1. **Product Hero** (large image, side-by-side with title/price/options)
2. **Product Details** (images carousel, zoom on hover)
3. **Product Description** (full details, specifications, materials)
4. **Reviews Section** (star rating, review list, add review)
5. **Related Products** (recommendations, grid of products)
6. **FAQ Section** (product-specific questions)
7. **Footer** (standard)

**Layout Patterns:**
- Desktop: Product image left (60%), details right (40%)
- Tablet: Stack image and details vertically
- Mobile: Stack everything single column

**Key Metrics:**
```
Product image:         Square (1:1) or 3:4 ratio
Image carousel:        Thumbnails below main image
Product details:       Right column, 320px width on desktop
Spacing:               24px between title, price, options
Related products:      4 columns (desktop), 2 columns (tablet), 1 column (mobile)
Product card height:   Aspect ratio consistent (3:4 for clothing, 1:1 for general)
```

**Component Recommendations:**
- Product image: Large, zoomable on hover, carousel for multiple images
- Price: Large (24-28px), prominent, show sale price if applicable
- Options: Select dropdowns or swatches (color swatches, size buttons)
- Add to Cart: Large prominent button (40-48px height), shows on scroll
- Reviews: Star rating, text reviews, sortable
- Related products: Grid cards with image, title, price, rating

---

### 4. PORTFOLIO/PERSONAL SITE

**Standard Sections:**
1. **Hero Section** (name/title, brief bio, portrait, CTA)
2. **About Section** (longer bio, skills, background)
3. **Work/Projects Section** (3-6 featured projects, grid)
4. **Process Section** (how you work, 3-4 steps)
5. **Testimonials** (optional, client feedback)
6. **Contact Section** (email, contact form, or links)
7. **Footer** (standard)

**Layout Patterns:**
- Hero: Centered with portrait image
- About: 2-column (text + image) on desktop, single on mobile
- Work: Masonry grid or uniform grid (3 columns)
- Contact: Centered form or simple email link

**Key Metrics:**
```
Hero height:           400-500px
Portrait image:        400x400px (square) or 3:4 aspect
Work grid:             3 columns (desktop), 2 (tablet), 1 (mobile)
Project card aspect:   3:4 or 16:9 (consistent)
About section width:   Split 50/50 or full width
Contact form:          Max 500px width, centered
```

---

### 5. BLOG/CONTENT SITE

**Standard Sections:**
1. **Header/Navigation** (site logo, main nav, search)
2. **Hero Banner** (featured article or site title)
3. **Featured Articles** (grid of 3-4 latest/trending)
4. **Categories** (filter by topic, horizontal scrolling or tabs)
5. **Article Grid** (paginated list of all articles, 2-3 columns)
6. **Sidebar** (optional, related articles, author bio, newsletter signup)
7. **Footer** (standard)

**Layout Patterns:**
- Article grid: 2 columns (desktop), 1 column (mobile)
- Cards: Image, title, excerpt, author, date, category
- Featured: Larger cards or hero layout

**Key Metrics:**
```
Featured article:      Full width, 400-500px height
Article card:          2 columns (desktop), stacked (mobile)
Article image:         16:9 aspect ratio
Text width:            Max 800px for readability
Sidebar width:         300px (optional, desktop only)
Excerpt length:        2-3 lines, then "Read more"
```

---

## Responsive Breakpoint Strategy

I'll provide layouts for these breakpoints:

```
Desktop:               1200px and above
Tablet:                768px to 1199px
Mobile:                Below 768px
```

**At each breakpoint:**
- Column count (3 columns → 2 columns → 1 column)
- Padding/margins (80px → 40px → 20px)
- Font sizes (scale down 10-15% on mobile)
- Image aspect ratios (may stay same, but width changes)
- Navigation (horizontal → hamburger)

---

## Layout Template Output

Once you describe your site, I'll provide:

### ✓ WIREFRAME BREAKDOWN
Sketch of layout at each breakpoint:
- Desktop (1440px wide)
- Tablet (768px wide)
- Mobile (375px wide)

### ✓ SPACING BLUEPRINT
```
Desktop Section Padding:    80px top, 80px bottom
Tablet Section Padding:     40px top, 40px bottom
Mobile Section Padding:     24px top, 24px bottom
Container Max-Width:        1200px
Horizontal Margin:          60px (desktop), 40px (tablet), 20px (mobile)
```

### ✓ COMPONENT RECOMMENDATIONS
For each section:
- Specific components to use (hero, cards, buttons)
- Sizing guidelines
- Grid layouts by breakpoint
- Image aspect ratios

### ✓ MOBILE-FIRST CSS STRATEGY
Start with mobile layout, add complexity as screen grows:
- Mobile: Single column, full-width
- Tablet: 2 columns, slight padding
- Desktop: 3+ columns, constrained width, enhanced spacing

### ✓ FIGMA TEMPLATE
Structure for setting up responsive design:
- Frame sizes for each breakpoint
- Component variants for responsive changes
- Constraints setup
- Auto layout patterns

### ✓ WEBFLOW IMPLEMENTATION
Specific techniques:
- Flexbox vs. Grid for each section
- Responsive breakpoint approach
- Mobile-first ordering
- Image optimization settings

---

## Mobile-First Strategy

**Key principle:** Design mobile first, enhance desktop

**Mobile (375px):**
- Single column layout
- Full-width sections
- Simplified navigation (hamburger)
- Stacked components (cards below each other)
- Larger touch targets (48px minimum)
- Simplified hero (image above text)

**Tablet (768px):**
- 2-column layouts appear
- Increase padding and spacing
- Hero can split (image right, text left)
- Cards in 2x2 grid
- Navigation may expand (tabs instead of hamburger)

**Desktop (1200px):**
- 3+ column layouts
- Max-width container (1200px), centered
- Full-featured navigation
- Advanced layouts (alternating image/text)
- Optimized spacing and breathing room

**In Webflow:**
- Start with mobile breakpoint
- Set mobile padding, spacing, sizes
- Add tablet breakpoint for adjustments
- Add desktop breakpoint for enhancements
- Test in between breakpoints (600px, 900px, etc.)

---

## Image Aspect Ratio Guide

**For Different Sections:**

| Section | Aspect Ratio | Reasoning |
|---------|------------|-----------|
| Hero Background | 16:9 or 2:1 | Wide cinematic look |
| Hero Product | 1:1 or 4:3 | Portrait orientation, square on mobile |
| Feature Cards | 16:9 or 4:3 | Horizontal cards, thumbnail-like |
| Blog/Article | 16:9 | Standard video aspect ratio |
| Product Photos | 3:4 or 1:1 | Portrait for fashion/products |
| Testimonial Avatar | 1:1 | Square circle crops nicely |
| Portfolio Projects | 16:9 or 3:4 | Depends on project type |

**Mobile Considerations:**
- Taller aspect ratios (4:3, 3:4) work better on mobile
- Wider aspect ratios (16:9) may need taller mobile crops
- Always test on actual phone size

---

## Next Steps

Based on your website type, you'll be ready to:

1. **Use `/design-system`** to set up Figma with responsive components
2. **Use `/animation-help`** to add hover/scroll animations
3. **Use `/responsive-layout` output** in Webflow to build
4. **Use `/design-audit`** to review responsive quality
5. **Use `web-layout` skill** for deep reference on each section type

---

## Pro Tips

**Mobile-First Testing:**
- Always design mobile first
- View on actual devices (not just browser resize)
- Test touch interactions (buttons, links)
- Test on slow network (image loading)

**Spacing Consistency:**
- Use consistent spacing scale (8px, 16px, 24px, 32px, 40px, 48px, 56px, 64px, 80px)
- Sections have consistent padding (not random)
- Gaps between cards consistent

**Image Optimization:**
- Use exact aspect ratios (not stretched)
- Compress images (use Webflow's optimization)
- Use object-fit: cover for background fills
- Provide alt text for SEO

**Accessibility:**
- Ensure 44px+ touch targets on mobile
- Test color contrast on all sections
- Ensure buttons are keyboard accessible
- Test with screen reader

---

## Ready?

Tell me:
1. **What type of website** are you designing?
2. **What's the primary goal** (signup, purchase, download, etc.)?
3. **Key sections** you need (or I can suggest defaults)

I'll provide your complete responsive layout blueprint with all breakpoints, spacing, components, and Webflow implementation techniques!
