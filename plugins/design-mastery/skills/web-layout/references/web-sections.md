# Web Sections — Hero, Features, CTA, Testimonials, Footer

## Hero Section Deep Dive

### Hero Height Options

**Full Viewport Height (100vh):**
- Pro: Dramatic, takes full screen
- Con: Content below is pushed way down on mobile
- Best for: Homepage, dramatic brand statements
- Mobile consideration: 60-80vh instead (header takes space)

**Fixed Height (600-800px):**
- Pro: Consistent, predictable scrolling
- Con: Less dramatic on ultra-wide screens
- Best for: Most websites, consistent feel
- Recommended: 640px or 720px

**Content-Based (Auto):**
- Pro: Content dictates height
- Con: Variable heights can feel disjointed
- Best for: When content amount varies per page

### Hero Content Positioning

**Left-Aligned (Text on left, Image on right):**
```
[H1 48px]              [Image 16:9]
[Description]
[CTA button]
(Text 40% width, Image 60% width)
```
- Most readable
- Common on B2B sites
- Text legible over any image

**Centered (All content centered):**
```
     [H1 48px centered]
     [Description centered]
     [CTA button centered]
     [Optional: Image below]
```
- Formal, balanced
- Good for premium brands
- Less image visibility (text takes priority)

**Overlay (Text over image):**
```
[H1, description, CTA overlaid
on large background image]
[Image covers full area]
```
- Dramatic, modern
- Risk: Text may be hard to read
- Requires semi-transparent overlay (rgba(0,0,0,0.3-0.5))

### Hero Background Options

**Solid Color:** Simple, fast-loading, professional
```
Hero padding: 128px top/bottom
Background: Brand primary or neutral
Text: White or dark, high contrast
```

**Gradient:** 2-3 colors, subtle to dramatic
```
Gradient direction: Top-left to bottom-right (45deg)
Colors: Brand primary + secondary
Opacity: Solid (100%) or transparent
```

**Image + Overlay:** Most common
```
Background image: High-quality photo, 16:9 aspect
Overlay: Semi-transparent dark color (rgba(0,0,0,0.3))
Purpose: Darken image so text is readable
```

### Hero Text Sizing & Spacing

**Headline (H1):**
- Desktop: 48-64px
- Tablet: 40-48px
- Mobile: 32-40px
- Weight: Bold (700), all-caps optional
- Color: White (if dark background) or dark

**Subheading/Description:**
- Size: 16-20px
- Weight: Regular (400)
- Color: Light gray or white
- Max-width: 80 characters (readability)
- Margin below H1: 24px

**CTA Button:**
- Size: 56px height, 28px H padding
- Style: Primary button (solid color)
- Position: Below description, 24px gap

**Overall Spacing:**
- H1 to description: 24px
- Description to button: 24px
- Button to bottom: 60-100px (balance)

---

## Feature Section (3-Column Benefits)

### Section Anatomy

```
┌─────────────────────────────────────────┐
│ Section Title (32px)                    │
│ "Why Choose Us"                         │
├─────────────────────────────────────────┤
│ Section Description (16px gray)         │
│ "We believe in quality and..."          │
├─────────────────────────────────────────┤
│ ┌──────────┐ ┌──────────┐ ┌──────────┐ │
│ │ 📊       │ │ 🎯       │ │ 🚀       │ │
│ │ Feature1 │ │ Feature2 │ │ Feature3 │ │
│ │ Title    │ │ Title    │ │ Title    │ │
│ │ Desc...  │ │ Desc...  │ │ Desc...  │ │
│ └──────────┘ └──────────┘ └──────────┘ │
└─────────────────────────────────────────┘
```

### Section Spacing

- **Top padding:** 128px
- **Bottom padding:** 128px
- **Title margin-bottom:** 12px
- **Description margin-bottom:** 48px
- **Card gap:** 24px (horizontal)

### Feature Card Details

**Card Width:** 280-320px on desktop
**Card Padding:** 24px all sides
**Icon:** 48-64px, centered, brand color
**Icon-to-title gap:** 16px
**Title:** 18-20px, semi-bold
**Title-to-description gap:** 12px
**Description:** 14px gray, 2-3 lines max

### Responsive Behavior

```
Desktop (1440px): 3 cards (4-col width each)
Tablet (800px):   2 cards (3-col width each)
Mobile (390px):   1 card (full width), stacked
```

---

## Testimonial Section

### Card Structure

```
┌─────────────────────┐
│ "Customer quote...  │
│ ...lives forever."  │  14-16px italic
│                     │
│ ⭐⭐⭐⭐⭐         │  5-star rating
│                     │
│ [Avatar] Name       │  48px avatar, left
│           Title     │  Name: 14px bold
│           Company   │  Title: 12px gray
└─────────────────────┘
```

### Testimonial Sizing

**Card:** 280-320px wide, 400px tall (flexible)
**Avatar:** 48px circle
**Quote text:** 14-16px, italic, 150% line height
**Name:** 14px, bold
**Title/Company:** 12px, gray
**Rating:** 16px stars, 4px gap between

### Section Layout

```
Desktop: 3-4 cards per row
Tablet:  2 cards per row
Mobile:  1 card (carousel or scroll)
```

**Section padding:** 128px vertical
**Card gap:** 24px

### Testimonial Variants

**Type 1: Quote + Avatar + Name**
```
"Great service!" ⭐⭐⭐⭐⭐
[Avatar] Sarah Chen
```

**Type 2: Full Quote, Longer Testimonial**
```
"We've been using this service for 2 years
and it's transformed our workflow..."
[Avatar] John Smith, CEO
```

**Type 3: Video Testimonial**
```
[Play button on video thumbnail]
Quote overlay
Name below
```

---

## Call-to-Action Section

### Types & Uses

**Type 1: Centered CTA (Most Common)**
```
Ready to get started?
Join 1,000+ happy customers.

[Get Started] [Learn More]
```

**Type 2: Image + Text CTA**
```
[Image on left]  Ready to...? [CTA]
                 Learn more [text link]
```

**Type 3: Form CTA (Email Signup)**
```
Get updates delivered to your inbox
[Email field] [Subscribe button]
```

### Styling

**Background:**
- Color: Brand primary or secondary
- Gradient: Optional, top to bottom
- Image: Semi-transparent overlay if using background image

**Text Color:**
- White text on dark background
- Dark text on light background
- Contrast: 4.5:1 minimum

**Padding:** 80-100px vertical, 64px horizontal
**Text alignment:** Centered
**Max-width:** 600px (center content)

### Button Arrangement

```
[Get Started] [Learn More]
   12px gap
   Primary button left, secondary right
   OR primary centered, secondary below
```

**Mobile:** Stack buttons vertically, full-width each

---

## Newsletter/Email Section

### Structure

```
Get updates from us
Enter your email to stay informed

[Email input field] [Subscribe button]

We don't spam. Unsubscribe anytime.
```

### Form Sizing

**Input field:** 44-48px height, flexible width
**Button:** 48-56px height, minimum 100px width
**Gap:** 12px between input and button
**Mobile:** Stack or full-width input

### Styling

**Background:** Light gray or brand color
**Input:** White background, gray border
**Button:** Primary button style
**Helper text:** 12px gray, below form

---

## Footer Section

### Standard Footer Structure

```
┌────────────────────────────────────────┐
│ [Logo]  [Col1 Links]  [Col2 Links]    │
│         [Col3 Links]  [Social icons]   │
├────────────────────────────────────────┤
│ © 2026 Company, Inc.                  │
│ Privacy  •  Terms  •  Sitemap         │
└────────────────────────────────────────┘
```

### Footer Sections

1. **Logo/Brand:** 32-40px logo, top-left
2. **Navigation Columns:** 3-5 columns, 20-30 links total
3. **Social Icons:** 24-32px icons, top-right or bottom-right
4. **Newsletter Signup:** Optional, right column
5. **Copyright:** Bottom section, 20px padding
6. **Legal Links:** Bottom, "Privacy | Terms | Sitemap"

### Footer Spacing

- **Main padding:** 60-80px vertical, 64px horizontal
- **Column gap:** 40-60px
- **Copyright padding:** 20px vertical, 64px horizontal
- **Border-top:** Optional 1px divider above copyright

### Link Styling

**Column Header (Section Title):**
- 14px, semi-bold, dark color
- Margin-bottom: 12px

**Column Links:**
- 12px, gray color, regular weight
- Line-height: 200% (spacious vertical)
- Hover: Color change or underline

**Social Icons:**
- 24-28px size
- Outline style (not filled)
- Hover: Color change or fill

### Responsive Footer

**Desktop:** Multi-column, all content visible
```
[Logo] [Col1] [Col2] [Col3] [Social]
```

**Tablet:** 2-3 columns, wrap as needed
```
[Logo] [Col1] [Col2]
[Col3] [Social]
```

**Mobile:** Single column, stacked
```
[Logo]
[Col1]
[Col2]
[Col3]
[Social icons]
```

---

## Section Layout Combinations

### Homepage Flow (Most Common)

```
[Navigation]
[Hero Section] - Full screen, CTA button
[Feature Section] - 3 benefits, icons
[Testimonials Section] - 3-4 quotes
[CTA Section] - Final conversion push
[Footer]
```

### Product Page Flow

```
[Navigation]
[Hero] - Product image, headline
[Benefits] - 3-4 feature cards
[Detailed feature] - Image + text description
[Comparison table] - Product vs competitors (optional)
[Testimonials] - Social proof
[CTA] - Purchase or demo
[FAQ] - Common questions (optional)
[Footer]
```

### Service Page Flow

```
[Navigation]
[Hero] - Service headline
[Problem section] - What problem does it solve?
[Solution section] - How do you solve it?
[Process section] - Step-by-step (3-5 steps)
[Results/Benefits] - Why choose us?
[Testimonials] - Proof it works
[CTA] - Contact or try
[Footer]
```

---

## Section Spacing Reference Table

| Section Type | Top Padding | Bottom Padding | Notes |
|-------------|-----------|----------------|-------|
| **Hero** | 0 (full bleed) | 128px | Usually starts at top |
| **Feature** | 128px | 128px | Standard section |
| **Testimonial** | 128px | 128px | Standard section |
| **CTA** | 100px | 100px | Can be full-width bg |
| **Footer** | 80px | 20px | Different padding |

