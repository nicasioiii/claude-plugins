# Webflow Layout Patterns & Structure

## Hero Section Pattern

**Use case:** Large, prominent top section with image and content

```
Hero (flex, row, height: 100vh, gap: 24px)
├── Image (width: 50%, height: 100%, object-fit: cover)
└── Content (width: 50%, flex column, center aligned)
    ├── H1 (headline)
    ├── Paragraph (subheading)
    └── Button (CTA)
```

**CSS/Webflow settings:**
```
Hero section:
  display: flex
  flex-direction: row
  height: 100vh
  gap: 24px
  padding: 64px left/right
  align-items: center
  justify-content: space-between

Hero image:
  width: 50%
  height: 100%
  object-fit: cover

Hero content:
  width: 50%
  display: flex
  flex-direction: column
  justify-content: center
  align-items: flex-start
```

**Responsive:**

Desktop (100vh height, side-by-side):
```
Hero: flex-direction: row, height: 100vh
Image: width: 50%
Content: width: 50%
```

Mobile (auto height, stacked):
```
Hero: flex-direction: column, height: auto
Image: width: 100%, height: 300px
Content: width: 100%
```

---

## Card Grid Pattern

**Use case:** Display multiple items (products, team, testimonials)

```
Container (display: grid)
├── Grid settings
│   ├── grid-template-columns: repeat(4, 1fr)
│   └── gap: 24px
└── Cards (4 per row, equal width)
    ├── Image (width: 100%, height: 200px, object-fit: cover)
    ├── Title (H3)
    ├── Description (paragraph)
    └── Link/Button
```

**Responsive breakdown:**

```
Desktop (1440px): 4 columns
  grid-template-columns: repeat(4, 1fr)

Tablet (800px): 2 columns
  grid-template-columns: repeat(2, 1fr)

Mobile (390px): 1 column
  grid-template-columns: 1fr
```

**Webflow:**
1. Create div (this will be grid)
2. Display: Grid
3. Grid columns: 4 (or use repeat(4, 1fr) in custom CSS)
4. Gap: 24px
5. Add card elements inside
6. Each card: grid column span 1
7. Change at breakpoint: 2 columns, then 1 column

---

## Bento Grid Layout (Asymmetric)

**Use case:** Show mixed content with varying card sizes

```
Container (display: grid, 4 columns)
├── Large card (spans 2 columns)
├── Large card (spans 2 columns)
├── Small card (spans 1 column)
├── Small card (spans 1 column)
└── Full-width card (spans 4 columns)
```

**Implementation:**

```
Grid settings:
  grid-template-columns: repeat(4, 1fr)
  gap: 24px

Card 1:
  grid-column: span 2
  grid-row: span 1

Card 2:
  grid-column: span 2
  grid-row: span 1

Card 3:
  grid-column: span 1
  grid-row: span 1

Card 4:
  grid-column: span 1
  grid-row: span 1

Card 5 (full-width):
  grid-column: span 4
```

**Mobile responsive:**
```
Mobile (all cards full width):
  grid-template-columns: 1fr
  All cards: grid-column: span 1
  Result: Stacked vertical
```

---

## Two-Column Layout

**Use case:** Content on left, image on right (or vice versa)

```
Section (display: flex, flex-direction: row)
├── Content (width: 50%, padding: 40px)
│   ├── H2
│   ├── Paragraph
│   └── List items
└── Image (width: 50%, height: auto, object-fit: cover)
```

**Settings:**
```
Section:
  display: flex
  flex-direction: row
  gap: 40px
  align-items: center

Content:
  width: 50%
  flex: 0 0 50%

Image:
  width: 50%
  flex: 0 0 50%
  height: 400px (or auto, depending on design)
```

**Responsive (Stack on mobile):**

```
Desktop:
  flex-direction: row
  width: 50% each

Mobile:
  flex-direction: column
  width: 100% each
  Image height: 300px (smaller on mobile)
```

---

## Navigation Pattern (Desktop + Mobile)

### Desktop Navigation

```
Nav (display: flex, flex-direction: row, sticky top: 0)
├── Logo (width: auto, flex: 0 0 auto)
├── Menu items (flex: 1, display: flex, gap: 32px)
│   ├── Link
│   ├── Link
│   └── Link
└── CTA Button (flex: 0 0 auto)
```

**Settings:**
```
Nav:
  display: flex
  flex-direction: row
  justify-content: space-between
  align-items: center
  padding: 16px 64px
  position: sticky
  top: 0
  z-index: 100
  background: white
  box-shadow: 0 2px 8px rgba(0,0,0,0.1) [on scroll]

Logo:
  width: 40px or 60px
  flex: 0 0 auto

Menu:
  display: flex
  flex-direction: row
  gap: 32px
  flex: 1
  justify-content: flex-start [or center]

Button:
  flex: 0 0 auto
```

### Mobile Navigation (Hamburger)

```
Nav (same styling as desktop, but hamburger visible on mobile)
├── Logo (visible all sizes)
├── Hamburger icon (hidden on desktop, visible on mobile)
└── Menu (desktop visible, mobile off-screen until opened)

Menu slide-in (position: fixed or absolute):
  position: fixed
  left: 0
  top: 0
  width: 100%
  height: 100vh
  display: flex
  flex-direction: column
  gap: 24px
  padding: 80px 24px
  transform: translateX(-100%) [closed]
  transform: translateX(0) [open]
  z-index: 99 [below nav]
```

**Webflow:**
1. Create nav component
2. Hide menu on mobile: Display: none
3. Create mobile menu div
4. Set position: fixed, left: 0, top: 0, width: 100vw
5. Add hamburger button
6. Interaction: Click hamburger → slide menu in (transform: translateX)
7. Add close button or click outside to close

---

## Footer Pattern

```
Footer (display: flex, flex-direction: column)
├── Content section (display: grid, 4 columns)
│   ├── Column 1: Logo + description
│   ├── Column 2: Links
│   ├── Column 3: Links
│   └── Column 4: Newsletter signup
├── Divider (height: 1px, background: light gray)
└── Bottom section (display: flex, justify-content: space-between)
    ├── Copyright text
    ├── Social links
    └── Legal links (Privacy, Terms)
```

**Settings:**
```
Footer:
  display: flex
  flex-direction: column
  padding: 80px 64px
  gap: 40px
  background: dark color or different background

Content grid:
  display: grid
  grid-template-columns: repeat(4, 1fr)
  gap: 40px

Bottom section:
  display: flex
  justify-content: space-between
  align-items: center
  border-top: 1px solid light gray
  padding-top: 40px
```

**Responsive (Mobile: stacked):**
```
Content grid on mobile:
  grid-template-columns: repeat(2, 1fr)
  or: 1fr (all stacked)

Padding mobile:
  24px 24px (much smaller)

Bottom section mobile:
  flex-direction: column
  align-items: flex-start
  gap: 16px
```

---

## Container & Max-Width Pattern

**Essential for readable content:**

```
Section (width: 100%, background: color)
└── Container (max-width: 1200px, margin: 0 auto, padding: 64px)
    └── Content
```

**Why this pattern:**
- Section: Full viewport width (background stretches)
- Container: Content stays at readable max-width
- Margin auto: Centers horizontally
- Padding: Internal spacing

**Values:**
```
Max-width: 1200px (most common)
or: 1280px, 1440px (depends on design)

Desktop padding: 64px left/right
Tablet padding: 48px left/right
Mobile padding: 24px left/right
```

**Webflow implementation:**
```
1. Create section div (width: 100%)
2. Inside: Create container div
3. Container settings:
   - width: 100%
   - max-width: 1200px
   - margin: 0 auto (centers it)
   - padding: 64px 64px
4. Change padding at breakpoints
```

---

## Section Spacing Pattern

**Consistent vertical rhythm:**

```
Hero (padding-top: 80px, padding-bottom: 80px)
[100px gap]
Features (padding-top: 80px, padding-bottom: 80px)
[100px gap]
Testimonials (padding-top: 80px, padding-bottom: 80px)
[100px gap]
CTA (padding-top: 80px, padding-bottom: 80px)
```

**Implementation:**
```
Each section:
  padding-top: 80px
  padding-bottom: 80px

Margin between sections:
  margin-bottom: 100px (or no margin, depends on design)

Result: Consistent rhythm, predictable spacing
```

**Mobile responsive:**
```
Padding mobile: 40px top/bottom
Gap mobile: 60px (reduced from desktop's 100px)
Rhythm maintained but tighter for small screens
```

---

## Overlay Pattern (For Hero with Text)

**Use case:** Image with text overlay (hero section)

```
Hero (position: relative)
├── Background image (position: absolute, full coverage)
└── Content (position: relative, z-index: 10)
    ├── H1 (text)
    └── CTA button
```

**Settings:**
```
Hero:
  position: relative
  height: 100vh
  overflow: hidden

Image:
  position: absolute
  top: 0
  left: 0
  width: 100%
  height: 100%
  object-fit: cover
  opacity: 0.7 [optional darkening]

Content:
  position: relative
  z-index: 10
  height: 100%
  display: flex
  justify-content: center
  align-items: center
  flex-direction: column
  text-align: center
  color: white [adjust for contrast]
```

**Dark overlay (optional):**
```
Add pseudo-element or separate div:
  position: absolute
  top: 0
  left: 0
  width: 100%
  height: 100%
  background: rgba(0,0,0,0.3) [30% dark]
  z-index: 5 [between image and content]
```

---

## Sidebar + Content Pattern

**Use case:** Dashboard, docs, admin layout

```
Container (display: flex, flex-direction: row)
├── Sidebar (width: 250px, position: sticky, top: 0)
│   └── Navigation menu
└── Content (flex: 1)
    └── Main content
```

**Settings:**
```
Container:
  display: flex
  gap: 0

Sidebar:
  width: 250px
  flex: 0 0 250px
  position: sticky
  top: 0
  height: 100vh
  overflow-y: auto [scroll if needed]
  background: light gray
  padding: 24px

Content:
  flex: 1
  padding: 40px
  background: white
```

**Mobile responsive:**
```
Mobile:
  flex-direction: column [stack]

Sidebar mobile:
  width: 100%
  height: auto
  position: relative [not sticky]
```

---

## Testimonial/Quote Pattern

**Use case:** Customer testimonial with image, quote, author

```
Card (padding: 24px)
├── Quote (font-style: italic, font-size: 18px)
├── Author section (display: flex, gap: 16px, margin-top: 16px)
│   ├── Avatar (width: 48px, border-radius: 50%)
│   └── Author info
│       ├── Name (font-weight: bold)
│       └── Title (font-size: 12px, color: gray)
```

**Styling:**
```
Quote:
  font-style: italic
  font-size: 18px
  line-height: 150%
  margin-bottom: 24px

Avatar:
  width: 48px
  height: 48px
  border-radius: 50%
  object-fit: cover
  flex: 0 0 48px

Author info:
  display: flex
  flex-direction: column
  gap: 4px
  flex: 1

Author name:
  font-weight: 600
  font-size: 16px

Author title:
  font-size: 12px
  color: #999999
```

---

## CTA Section Pattern

**Use case:** Conversion section with headline, copy, button

```
CTA section (background: brand color, padding: 80px, text-align: center)
├── H2 (color: white or dark)
├── Paragraph (color: white or dark, max-width: 600px, margin: 0 auto)
├── Gap: 24px
└── Button (primary style)
```

**Settings:**
```
CTA section:
  background: brand color
  padding: 80px 64px
  display: flex
  flex-direction: column
  align-items: center
  text-align: center
  gap: 24px

H2:
  color: white (or light text)
  font-size: 48px
  max-width: 800px

Paragraph:
  color: white or light gray
  max-width: 600px
  font-size: 18px

Button:
  margin-top: 24px
```

**Mobile responsive:**
```
Padding: 40px 24px (smaller on mobile)
H2: 32px (scaled down)
Paragraph: 16px (readable on mobile)
Button: Full width or fixed width [depends on design]
```

---

**Last Updated:** March 12, 2026
**Source:** Webflow Masterclass, Ran Segall course materials
