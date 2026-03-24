# Website Section Anatomy

## Hero Section

**Purpose:** First impression, establish brand, communicate main value proposition

**Structure:**
```
┌──────────────────────────────────────┐
│ ┌────────────────────────────────┐   │
│ │                                 │   │  Background (full viewport height or 600px)
│ │  [H1 Headline 48px]            │   │
│ │  [Description 18px, 100 chars] │   │
│ │  [CTA Button]                   │   │
│ │                                 │   │
│ │  [Optional: Background image]   │   │
│ └────────────────────────────────┘   │
└──────────────────────────────────────┘
```

**Sizing:**
- **Height:** 600-800px (or full viewport height, `100vh`)
- **Padding:** 100-128px vertical, 64px horizontal
- **Headline:** H1, 48-64px, bold weight
- **Description:** 16-20px, gray text, max 80 characters
- **CTA Button:** 56px height, large primary button

**Background Options:**
1. **Solid color:** Brand primary or neutral background
2. **Gradient:** 2-3 color gradient (top-left to bottom-right)
3. **Image:** Full-bleed background image, 16:9 or 3:1 aspect ratio
4. **Image + Overlay:** Image with semi-transparent color overlay (rgba(0,0,0,0.3))
5. **Pattern:** SVG background, geometric shapes, or texture

**Text Placement:**
- **Left-aligned:** Text left, image right (common)
- **Centered:** Both text and image centered (formal, balanced)
- **Text overlay:** Text positioned over image (dramatic)

**Responsive Behavior:**
```
Desktop: Text left, image right (2-column layout)
Tablet:  Text left, image right (stacked on scroll, or single column)
Mobile:  Text centered above image (single column, image below text)
```

## Feature Section (3-Column)

**Purpose:** Highlight 3-5 key benefits or features

**Structure:**
```
┌────────────────────────────────────────┐
│ Section Title (32px)                   │
│ Section description (16px gray)        │
├────────────────────────────────────────┤
│ ┌──────────┐ ┌──────────┐ ┌──────────┐│
│ │ Feature1 │ │ Feature2 │ │ Feature3 ││
│ │ Icon     │ │ Icon     │ │ Icon     ││
│ │ Title    │ │ Title    │ │ Title    ││
│ │ Desc     │ │ Desc     │ │ Desc     ││
│ └──────────┘ └──────────┘ └──────────┘│
└────────────────────────────────────────┘
```

**Spacing:**
- **Section padding:** 80-128px vertical, 64px horizontal
- **Title margin:** Bottom 24px
- **Description margin:** Bottom 48px
- **Card gap:** 24-40px between feature cards
- **Card padding:** 24px

**Typography:**
- **Section title:** 32-40px, semi-bold
- **Card title:** 18-20px, semi-bold
- **Card description:** 14px gray, 2-3 lines max
- **Icon size:** 48-64px

**Grid Layout:**
```
Desktop (1440px): 3 columns (4-column width each in 12-column grid)
Tablet (800px):   2 columns (3-column width each in 6-column grid)
Mobile (390px):   1 column (full width, stacked)
```

## Call-to-Action Section

**Purpose:** Drive conversions, move users to action

**Structure:**
```
┌──────────────────────────────────────┐
│ Ready to get started?                │  Headline: 32-40px
│                                      │
│ Join 1,000+ happy customers.         │  Description: 16-18px gray
│                                      │
│         [Get Started] [Learn More]   │  Primary + Secondary buttons
│                                      │
└──────────────────────────────────────┘
```

**Styling:**
- **Background:** Brand primary or secondary color (contrasting)
- **Padding:** 80px vertical, 64px horizontal
- **Text color:** White (if dark background) or dark (if light background)
- **Alignment:** Centered or left-aligned
- **Buttons:** Large (56px), white text on colored background

**Responsive:**
```
Desktop: Multi-column layout (image + text)
Mobile:  Single column, centered text, buttons stacked
```

## Testimonial Section

**Purpose:** Build trust through social proof

**Structure:**
```
┌──────────────────────────────────────┐
│ What our customers say                │  Section title: 32px
├──────────────────────────────────────┤
│ ┌────────────┬────────────┬────────┐ │
│ │ "Quote..."  │ "Quote..."  │ Quot...│ │  3-4 cards
│ │ Name, Title │ Name, Title │ N, Ti.│ │
│ │ [⭐⭐⭐⭐⭐] │ [⭐⭐⭐⭐⭐] │ [★★★] │ │
│ └────────────┴────────────┴────────┘ │
└──────────────────────────────────────┘
```

**Card Sizing:**
- **Card width:** 280-320px
- **Card padding:** 20px
- **Quote text:** 14-16px, italic
- **Name:** 14px, bold
- **Title:** 12px gray
- **Rating:** 5 stars, 16px each

**Grid:**
```
Desktop: 3-4 testimonials per row (4-column width each)
Tablet:  2 testimonials per row
Mobile:  1 testimonial (carousel or scroll)
```

## Footer Section

**Purpose:** Navigation, legal, social, contact

**Structure:**
```
┌──────────────────────────────────────────────┐
│ [Logo]  [Links]  [Links]  [Social icons]    │  Footer content
├──────────────────────────────────────────────┤
│ © 2026 Company. All rights reserved.         │  Copyright line
│ Privacy Policy  |  Terms  |  Sitemap         │  Legal links
└──────────────────────────────────────────────┘
```

**Sections:**
1. **Logo/Brand:** 32-40px logo, left-aligned
2. **Navigation columns:** 3-5 columns (20-30 links total)
3. **Social icons:** 24-32px icons, linked
4. **Newsletter signup:** Optional email form
5. **Contact info:** Optional address, phone, email

**Spacing:**
- **Footer padding:** 60-80px vertical, 64px horizontal
- **Column gap:** 40-60px
- **Copyright section padding:** 20px vertical, 64px horizontal
- **Border-top:** Optional 1px divider above copyright

**Link styling:**
- **Font:** 12-14px
- **Hover:** Color change or underline
- **Column header:** 14px, bold (section title)
- **Column links:** 12px, gray, regular weight

**Responsive:**
```
Desktop: Multi-column layout, all information visible
Mobile:  Single column, stacked sections, collapsed navigation
```
