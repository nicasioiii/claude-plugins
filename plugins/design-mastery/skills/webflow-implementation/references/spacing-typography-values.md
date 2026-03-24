# Exact Spacing & Typography Values from Ran Segall Courses

Precise measurements for typography, spacing, and component sizing based on professional Webflow design standards. These values create visual harmony and maintain consistent proportions across responsive breakpoints.

---

## SECTION PADDING (Content Spacing)

Section padding creates consistent vertical and horizontal spacing between major page sections.

### Desktop Layout (1440px+)

| Element | Top/Bottom | Left/Right |
|---------|-----------|-----------|
| Section | 80px | 64px |
| Container (max-width) | — | 1200px |
| Container centering | — | margin: 0 auto |

**Usage:**
```
Section full-width, padding: 80px 64px
├── Container max-width: 1200px, margin: 0 auto
└── Content inside container
```

**Example:** Hero section
- Full width section with padding 80px (top/bottom), 64px (left/right)
- Content container inside max 1200px wide, centered
- Maintains readable line length and consistent margins

### Tablet Layout (1024px)

| Element | Top/Bottom | Left/Right |
|---------|-----------|-----------|
| Section | 60px | 48px |
| Container (max-width) | — | 1000px |

**Scaling ratio:** 75% of desktop padding
- From 80px to 60px (25% reduction)
- From 64px to 48px (25% reduction)
- Maintains proportions as viewport shrinks

### Mobile Layout (480px and below)

| Element | Top/Bottom | Left/Right |
|---------|-----------|-----------|
| Section | 40px | 24px |
| Container (max-width) | — | 100% (full width) |

**Scaling ratio:** 50% of desktop padding
- From 80px to 40px (50% reduction)
- From 64px to 24px (62.5% reduction, slightly more aggressive)
- Maximizes content area on small screens

### Responsive Padding Breakpoints

Complete breakdown across all standard Webflow breakpoints:

| Breakpoint | Device Type | Top/Bottom | Left/Right | Notes |
|-----------|-----------|-----------|-----------|-------|
| 1920px+ | Desktop (large) | 80px | 64px | Full desktop experience |
| 1440px | Laptop | 80px | 64px | Standard desktop |
| 1024px | Tablet landscape | 60px | 48px | Optimized for tablet |
| 768px | Tablet portrait | 50px | 36px | Refined tablet spacing |
| 480px | Mobile | 40px | 24px | Compact mobile layout |

---

## INTERNAL GAPS (Element Spacing)

Gaps between elements in flex containers and grids. Use these values consistently for visual rhythm.

### Gap Scale

| Scale | Pixels | Use Case |
|-------|--------|----------|
| XS | 8px | Tight grouping (rare) |
| Small | 12px | Small element groups |
| Medium | 24px | Default flex/grid gap |
| Large | 32px | Prominent separation |
| XL | 48px | Major section breaks |
| 2XL | 64px | Large separation |

### Common Gap Applications

#### Flex Row (Horizontal)
- Navigation menu items: 32px gap
- Button groups: 16px gap
- Inline text blocks: 24px gap
- Hero content items: 32px gap

#### Flex Column (Vertical)
- Paragraph spacing: 24px gap
- Section sub-elements: 16px gap
- Card content items: 16px gap
- Form fields: 16px gap

#### Grid (2D Layout)
- Card grid: 32px gap
- Feature grid: 32px gap
- Gallery grid: 24px gap
- Bento layout: 24px gap

#### Between Sections
- Horizontal: Use section left/right padding (64px desktop, 24px mobile)
- Vertical: Use section top/bottom padding (80px desktop, 40px mobile)
- Never use margin between sections (use padding instead)

---

## TYPOGRAPHY SCALE

Professional typography hierarchy with specific font sizes for each heading level and body text.

### Desktop Typography (1440px)

| Element | Font Size | Line Height | Font Weight | Usage |
|---------|-----------|-----------|-----------|--------|
| H1 | 90px | 95-100% | 700 (Bold) | Main page heading |
| H2 | 60px | 130% | 700 (Bold) | Section heading |
| H3 | 32px | 130% | 700 (Bold) | Subsection heading |
| H4 | 24px | 140% | 600 (Semi-bold) | Small heading |
| Body | 18px | 160% | 400 (Regular) | Paragraph text |
| Small | 14px | 150% | 400 (Regular) | Caption, small text |
| Tiny | 12px | 140% | 400 (Regular) | Footer, meta info |

### Tablet Typography (1024px)

| Element | Font Size | Line Height | Notes |
|---------|-----------|-----------|-------|
| H1 | 60px | 130% | Reduce 33% from desktop |
| H2 | 40px | 130% | Reduce 33% from desktop |
| H3 | 28px | 130% | Reduce 12.5% from desktop |
| H4 | 20px | 140% | Reduce 17% from desktop |
| Body | 16px | 160% | Reduce to 16px (min readable) |
| Small | 12px | 150% | Reduce 14% from desktop |

### Mobile Typography (480px)

| Element | Font Size | Line Height | Critical Notes |
|---------|-----------|-----------|-----------------|
| H1 | 40-48px | 120% | Use responsive scaling (min-max) |
| H2 | 32px | 130% | Readable but not huge on small screen |
| H3 | 24px | 130% | Standard mobile heading |
| H4 | 18px | 140% | Small mobile heading |
| Body | 16px | 160% | **NEVER reduce below 16px** |
| Small | 12px | 150% | Acceptable for captions |

### Responsive Typography Scaling

**For H1 (Most Dynamic):**
```
Desktop: 90px
Tablet: 60px (66.7% of desktop)
Mobile: 40-48px (responsive min-max)

Formula: min(10vh, 9vw)
This scales with viewport, clamping between responsive units
```

**For H2:**
```
Desktop: 60px
Tablet: 40px (66.7% of desktop)
Mobile: 32px
```

**For Body Text:**
```
Desktop: 18px
Tablet: 16px
Mobile: 16px (locked at minimum)

IMPORTANT: Never reduce body text below 16px
- Impacts readability
- Accessibility standard
- Users pinch-to-zoom if smaller
```

---

## LINE HEIGHT SPECIFICATIONS

Line height affects readability and visual hierarchy. Higher line heights improve readability, especially on longer content.

### By Content Type

| Content | Line Height | Reasoning |
|---------|-----------|-----------|
| Headings (H1-H4) | 100-130% | Tight (headings are short, high readability naturally) |
| Subheadings | 130-140% | Balanced readability |
| Body paragraphs | 160% | Open line height for comfort |
| Small text/captions | 140-150% | Slightly more than body |
| Code blocks | 150% | Open enough for monospace fonts |

### Specific Values

**Heading Line Heights:**
- H1: 95-100% (very tight, for impact)
- H2: 130% (standard heading)
- H3: 130% (consistent with H2)
- H4: 140% (slightly more open)

**Body Line Heights:**
- Body paragraph: 160% (comfortable reading)
- Body in narrow columns: 160-180% (more open)
- List items: 150% (slightly less than paragraph)

**Small Text Line Heights:**
- Captions: 140-150%
- Footer text: 140%
- Meta information: 140%

---

## COMPONENT SIZING

Exact dimensions for common UI components.

### Button Component

#### Primary Button
```
Height: 48px (touchable minimum)
Padding: 16px vertical, 36px horizontal
Border radius: 999px (fully rounded)
Font size: 16px (body text size)
Font weight: 600 (semi-bold)

Responsive:
- Desktop: 48px height
- Tablet: 44px height
- Mobile: 44px height (min touchable)

States:
- Default: background black, text white
- Hover: scale 1.05, shadow 0 10px 30px rgba(0,0,0,0.15)
- Active: opacity 0.9
- Disabled: opacity 0.5, cursor not-allowed
```

#### Secondary Button
```
Height: 48px
Padding: 14px vertical, 34px horizontal (accounts for 2px border)
Border: 2px solid (matches text color)
Border radius: 999px
Font size: 16px
Font weight: 600

Responsive:
- Same height as primary
- Border consistent

States:
- Default: transparent background, border + text color
- Hover: background becomes color (10-20% opacity), text white
- Active: full opacity background
```

#### Button Spacing in Groups
```
Gap between buttons: 16px
Example: Two buttons in flex row, 16px gap
```

### Card Component

#### Card Container
```
Background: light color or white
Padding: 40px (all sides, desktop)
Border radius: 16-32px (depends on design)
Box shadow: 0 4px 12px rgba(0,0,0,0.08) (subtle)

Tablet: Padding 32px
Mobile: Padding 24px

Hover state:
- Transform: translateY(-4px)
- Shadow: 0 12px 24px rgba(0,0,0,0.15)
- Duration: 300ms
- Easing: ease-out
```

#### Card Content
```
Image (top of card):
- Border radius: 16px (matches card, minus shadow)
- Object-fit: cover
- Aspect ratio: 3:2 (600x400px)
- Height: 240px (on desktop cards)

Heading (inside card):
- Font size: 24px (H4 size)
- Margin bottom: 12px
- Font weight: 600

Description:
- Font size: 16px (body)
- Line height: 160%
- Margin bottom: 16px
- Color: secondary text color

Link/Button:
- Margin top: 16px
- Standard button sizing
```

### Form Input Fields

#### Text Input / Textarea
```
Height: 40px (single line)
Padding: 10px vertical, 12px horizontal
Border: 1px solid #CCCCCC
Border radius: 8px
Font size: 16px (matches body text)
Background: white

States:
- Focus:
  - Border color: primary color
  - Box shadow: 0 0 0 3px rgba(primary, 0.1)
  - Outline: none (remove default)
- Error:
  - Border color: red (#EF4444)
  - Box shadow: 0 0 0 3px rgba(red, 0.1)
- Disabled:
  - Background: #F5F5F5
  - Cursor: not-allowed
  - Opacity: 0.6

Responsive:
- Desktop: 40px height
- Mobile: 44px height (larger touch target)
```

#### Label
```
Font size: 14px
Font weight: 600
Margin bottom: 8px
Color: text-dark
Required indicator: * (red color)
```

#### Placeholder Text
```
Font size: 14px
Color: #999999
Opacity: 0.7
Avoid placeholder-only (accessibility issue)
```

#### Form Gap (Between Fields)
```
Margin bottom: 20px (space between inputs)
Alternative: 16px if fields are very simple
```

### Navigation Component

#### Desktop Navigation
```
Height: 60-80px (including padding)
Padding: 16px 64px (top/bottom and sides)
Background: transparent (on hero), white/color (elsewhere)
Position: fixed or sticky, top: 0
Z-index: 100+

Logo:
- Height: 40-48px
- Width: auto (maintain aspect ratio)

Menu items:
- Gap: 32px (between items)
- Font size: 16px
- Font weight: 400
- Text color: matches page colors
- Hover: underline or color change (200ms)

CTA Button:
- Standard button sizing (48px height)
- Right aligned
```

#### Mobile Navigation
```
Hamburger icon: 24x24px
Menu container:
- Position: fixed
- Top: 0, left/right: 0
- Height: 100vh
- Width: 80-90% (or full screen)
- Background: white or dark
- Z-index: 99

Menu items:
- Flex column layout
- Gap: 24px between items
- Font size: 18px
- Padding: 24px 24px (inside menu)
- Full width touch targets

Animation:
- Slide from left or right
- Duration: 300ms
- Easing: ease-out
```

### Hero Section

```
Height: 100vh (full viewport height)
Background: image (cover) or color

Layout:
- Flex row (desktop)
- Flex column (mobile)
- Gap: 24px
- Padding: 64px left/right (desktop), 24px (mobile)

Image:
- Width: 50% (desktop), 100% (mobile)
- Height: 100%
- Object-fit: cover

Content:
- Width: 50% (desktop), 100% (mobile)
- Display: flex, flex-direction: column
- Justify-content: center
- Align-items: flex-start (or center)
- Padding: 64px (on content side)

Typography in hero:
- H1: 90px (desktop), 48px (mobile)
- Subheading: 24px (desktop), 18px (mobile)
- Line height: 140% (subheading)
- Color: typically white or brand color
- Gap between H1 and subheading: 16px
- Gap between text and button: 32px
```

---

## RESPONSIVE BREAKPOINT VALUES

The exact breakpoint pixel values Webflow uses for responsive design:

| Device | Breakpoint | Width | Description |
|--------|-----------|-------|-------------|
| Desktop | Large | 1920px | Large monitors |
| Desktop | Standard | 1440px | Most desktop displays |
| Tablet | Landscape | 1024px | Landscape iPad, large tablets |
| Tablet | Portrait | 768px | Portrait iPad |
| Mobile | Landscape | 768px | Mobile in landscape |
| Mobile | Portrait | 480px | iPhone standard |
| Mobile | Small | 320px | Small phones (if supporting) |

**Build strategy:**
1. Design and build for 1440px (desktop) first
2. Set up 1024px breakpoint (tablet, adjust to 2 columns)
3. Set up 768px (tablet portrait, 1-2 columns)
4. Set up 480px (mobile, 1 column, optimized)
5. Never go below 16px font size
6. Test actual devices, not just browser resize

---

## SPACING REFERENCE TABLE (Quick Lookup)

### All Spacing Values

| Purpose | XS | SM | MD | LG | XL | 2XL |
|---------|-----|-----|-----|-----|-----|-----|
| Internal gap | 8px | 12px | 24px | 32px | 48px | 64px |
| Button padding | — | — | 16px | — | — | — |
| Card padding | — | — | 40px | — | — | — |
| Section padding (top/bottom) | — | — | 80px | 60px | 40px | — |
| Section padding (left/right) | — | — | 64px | 48px | 24px | — |

### Copy-Paste Values

**Section padding mobile-first approach:**
```css
/* Mobile first */
padding: 40px 24px;

/* Tablet */
@media (min-width: 768px) {
  padding: 60px 48px;
}

/* Desktop */
@media (min-width: 1440px) {
  padding: 80px 64px;
}
```

**Typography mobile-first approach:**
```css
/* Mobile first */
font-size: 40px;
line-height: 120%;

/* Tablet */
@media (min-width: 768px) {
  font-size: 60px;
  line-height: 130%;
}

/* Desktop */
@media (min-width: 1440px) {
  font-size: 90px;
  line-height: 95%;
}
```

---

## DESIGN SYSTEM VARIABLES

Create these variables in Webflow for consistency:

### Spacing Variables
```
space/xs: 8px
space/sm: 12px
space/md: 24px
space/lg: 32px
space/xl: 48px
space/2xl: 64px
```

### Typography Variables
```
type/h1: 90px, line-height 95%
type/h2: 60px, line-height 130%
type/h3: 32px, line-height 130%
type/h4: 24px, line-height 140%
type/body: 18px, line-height 160%
type/small: 14px, line-height 150%
```

### Sizing Variables
```
size/button-height: 48px
size/button-padding: 16px 36px
size/card-padding: 40px
size/card-radius: 16px
size/container-max-width: 1200px
```

**Benefits:**
- Change all H1s globally by updating one variable
- Ensures consistency across entire site
- Quick adjustments for client reviews
- Easier to maintain and update
