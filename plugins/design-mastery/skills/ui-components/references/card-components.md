# Card Components — Layouts, Grids, and Variations

## Card Anatomy

Every card follows a predictable structure:

```
┌────────────────────┐
│   Visual Area      │  Image, icon, or visual element
│   (Image/Icon)     │  Height varies by type
├────────────────────┤
│   Title/Headline   │  Bold, prominent
│   (Required)       │  Max 2 lines, 50-60 chars
├────────────────────┤
│   Description      │  Regular weight, smaller size
│   (Optional)       │  Max 3 lines, ~100 chars
├────────────────────┤
│   CTA or Meta      │  Button, link, or secondary info
│   (Optional)       │  Right-aligned or full-width
└────────────────────┘
```

**Universal Card Padding:** 16-20px on all sides
**Corner Radius:** 8-12px (modern, not cartoonish)
**Box Shadow:** 0 1px 3px rgba(0,0,0,0.12) (default), scale on hover

---

## Card Type 1: Image Card (Most Common)

**Structure & Measurements:**

```
Desktop (1440px):
┌──────────────────────┐
│                      │  Image height: 200-280px
│   Image Area         │  Aspect ratio: 4:3 (common)
│   (Auto-fit)         │  or 16:9 (widescreen)
├──────────────────────┤
│ Product Name         │  Title: 16-18px, semi-bold
│ Category Badge       │  2 lines max, truncate with ...
├──────────────────────┤
│ Brief description    │  Body: 14px, gray (#666)
│ of product...        │  3 lines max
├──────────────────────┤
│                 $49  │  Price: 14px, bold or primary color
│           [Add Cart] │  Button: Full-width or right-aligned
└──────────────────────┘
```

**Spacing Breakdown:**
```
Image area: 0 padding (bleeds to card edges)
Title padding: 16px all sides
Description margin: 8px below title
Price/CTA margin: 12px below description
Padding bottom: 16px
```

**Image Sizing Best Practices:**

| Aspect Ratio | Desktop | Tablet | Mobile | Use Case |
|-------------|---------|--------|--------|----------|
| **4:3** | 300×225px | 240×180px | 160×120px | Product cards |
| **16:9** | 360×202px | 280×158px | 180×101px | Blog thumbnails |
| **1:1** | 280×280px | 220×220px | 140×140px | Avatar/icon cards |
| **3:2** | 320×213px | 240×160px | 160×107px | Photography |

**Object-fit Behavior:**
- Use `object-fit: cover` for consistent sizing
- Prevents aspect ratio distortion
- Centers image if cropping needed

**Hover State:**
- Shadow increases: 0 4px 12px rgba(0,0,0,0.15)
- Image brightens: opacity 0.95 or 5% lighter overlay
- Scale card: 1.02x (subtle elevation)
- Transition: 200ms ease-out

**Responsive Grid Layout:**

| Breakpoint | Columns | Card Width | Gutter |
|-----------|---------|-----------|--------|
| **Desktop** (1440px) | 4 | 300px | 24px |
| **Tablet** (800px) | 3 | 220px | 20px |
| **Mobile** (390px) | 2 | 160px | 12px |

**Grid Calculation:**
```
Desktop (1440px width):
- Margins: 64px (left + right)
- Available: 1312px
- 4 cards × 300px = 1200px
- Gutters: 3 × 24px = 72px
- Total: 1200 + 72 = 1272px ✓ Fits (40px buffer)
```

---

## Card Type 2: Feature Card (Icon + Title + Text)

**Structure:**

```
┌──────────────────────┐
│        📊             │  Icon: 48-64px
│      (Icon)          │  Centered or top-left
├──────────────────────┤
│ Feature Name         │  Title: 18px, semi-bold
│ (1 line)             │
├──────────────────────┤
│ Short description    │  Body: 14px, gray
│ of this feature...   │  2-3 lines max
└──────────────────────┘
```

**Sizing:**
- Card padding: 24px
- Icon size: 48px (standard), 64px (emphasis), 32px (compact)
- Gap icon to title: 16px
- Gap title to description: 12px
- Total card width: 280-350px

**Icon Styling:**
- Color: Brand primary or multi-color
- Outline weight: 1.5-2px (if outline style)
- Filled: Solid primary color + white inside shape

**Text Hierarchy:**
```
Title (18px, bold)
Description (14px, regular, gray #666)
Subtitle (12px, light, gray #999)
```

**When to Use Feature Cards:**
- Benefit/feature lists (3-4 features per section)
- Service offerings
- Solution categories
- Why choose us section
- Pricing plan features

**Desktop Grid:**
- 3 columns on desktop (4-column grid system)
- 2 columns on tablet
- 1 column on mobile

**Hover State:**
- Subtle background color (2-3% darker)
- Icon slightly enlarges (1.1x scale)
- Text might deepen in color
- Shadow increases

---

## Card Type 3: Testimonial Card

**Structure:**

```
┌──────────────────────┐
│  "This product       │  Quote: 14-16px, italic
│  changed my life     │  Line height: 150%
│  completely..."      │  Padding: 20px
├──────────────────────┤
│ ⭐⭐⭐⭐⭐         │  Rating (optional): 5-star
│                      │  Golden color (#FFD700)
├──────────────────────┤
│ [Avatar] Sarah Chen  │  Avatar: 48px circle
│         CEO, ACME    │  Name: 14px, semi-bold
│         ✓Verified    │  Title: 12px, gray
└──────────────────────┘
```

**Styling Details:**

**Quote Element:**
- Font: 14-16px, italic, regular weight
- Color: Dark gray (#333)
- Line height: 150-160%
- Padding: 20px
- Optional: Opening quote mark as design element (20-50% opacity, 40-60px)

**Rating Stars:**
- Size: 16-20px each
- Color: Gold (#FFD700) or brand color
- Spacing between: 4px
- Optional: "Verified purchase" checkmark

**Avatar:**
- Size: 48px circle
- Border: None or 2px subtle border
- Positioning: Left of name/title

**Testimonial Metadata:**
```
[Avatar] Name
         Title / Company
         City / Location (optional)
         ✓ Verified Badge (optional)
```

**Content Specifications:**
- Quote length: 30-100 words (shorter feels punchier)
- Name: 2-3 words max
- Title: 2-5 words (role + company)
- Font size: 12px for metadata

**Hover State:**
- Slight scale (1.02x)
- Shadow increases
- Quote emphasis (maybe increase opacity of quote mark)

**Desktop Grid:**
- 3-4 testimonials per row
- Full-width on mobile
- Carousel on tablet (scroll or pagination)

---

## Card Type 4: Team Member Card

**Structure:**

```
┌──────────────────────┐
│                      │
│   Photo (Square)     │  200×200px (1:1 aspect)
│                      │
├──────────────────────┤
│ Name                 │  18px, semi-bold
├──────────────────────┤
│ Job Title            │  14px, gray
├──────────────────────┤
│ 📧 Email             │  Icon + link, 12px
│ 💼 LinkedIn          │  Social links, optional
└──────────────────────┘
```

**Image Sizing:**
- Square format: 200×200px (desktop), 150×150px (mobile)
- Object-fit: cover
- Border radius: 8px (or 0px for sharp)

**Hover State:**
- Image overlay: Semi-transparent color
- Social icons appear: If hidden by default
- Name might underline or change color

**Grid Layout:**
- Desktop: 4 per row (3-column width each in 12-column)
- Tablet: 3 per row
- Mobile: 2 per row

---

## Card Type 5: Blog/Article Card

**Structure:**

```
┌──────────────────────┐
│ [Blog Thumbnail]     │  Aspect ratio: 16:9
│ [Category Badge]     │  Overlaid badge or separate
├──────────────────────┤
│ Article Headline     │  2-3 line max (48-60 chars)
│ in Multiple Lines    │  20px, semi-bold
├──────────────────────┤
│ Brief excerpt...     │  14px gray, 2 lines
│                      │
├──────────────────────┤
│ Date  Author  [→]    │  12px gray, right-aligned
└──────────────────────┘
```

**Key Elements:**

**Category Badge:**
- Positioning: Top-left corner (or separate line)
- Background: Brand secondary or accent
- Text: 10-12px white
- Padding: 4px 8px
- Border radius: 4px

**Headline:**
- Size: 18-22px, bold or semi-bold
- Color: Dark gray or black
- Line clamp: 2-3 lines
- Truncate with ... if longer

**Excerpt:**
- Size: 14px, regular, #666
- Line clamp: 2 lines
- Responsive: Hide on mobile, show on tablet+

**Metadata:**
```
📅 March 12, 2026  •  By Sarah Chen  •  5 min read  →
```

- Date: Always show
- Author: Show if available
- Read time: Optional (estimated word count ÷ 200)
- Arrow: Indicates link/navigation

**Hover State:**
- Image slight zoom (1.05x)
- Title deepens or changes color
- Arrow becomes more prominent
- Shadow increases

---

## Card Spacing & Padding Reference

**Standard Padding (All Card Types):**
```
Top padding:    16-20px
Right padding:  16-20px
Bottom padding: 16-20px
Left padding:   16-20px
```

**Internal Element Gaps:**
```
Image to title:       16px
Title to description: 8px
Description to CTA:   12px
CTA to bottom edge:   12-16px
```

**Multi-element Gaps (Horizontal):**
```
Icon to text:    12px
Avatar to name:  12px
Badge to title:  12px
```

---

## Card Responsive Behavior

**Breakpoint-Based Changes:**

| Breakpoint | Changes | Notes |
|-----------|---------|-------|
| **Desktop (1440px)** | 4 cards, full details | All content visible |
| **Tablet (800px)** | 2 cards, hide excerpt | Adjusted padding |
| **Mobile (390px)** | 1 card, minimal padding | Touch-friendly spacing |

**Mobile Card Adjustments:**
```
Padding: Reduce 20px → 16px
Font sizes: Reduce 2-4px
Icon sizes: Reduce proportionally
Image height: Reduce 20-30%
Gap between elements: Reduce 4px
```

---

## Card Grid System Math

**Formula for responsive card grids:**

```
Available width = Total width - (margins × 2)
Cards per row = floor((Available width + gutter) / (card width + gutter))
Card width = (Available width - (cards - 1) × gutter) / cards
```

**Example: Desktop 4 Cards**
```
Total: 1440px
Margins: 64px × 2 = 128px
Available: 1440 - 128 = 1312px

If gutter = 24px:
Card width = (1312 - (4-1) × 24) / 4
           = (1312 - 72) / 4
           = 1240 / 4
           = 310px per card
```

---

## Card Hover & Interaction States

**Hover Elevation Pattern:**

```css
Default shadow:   0 1px 3px rgba(0,0,0,0.12)
Hover shadow:     0 4px 12px rgba(0,0,0,0.15)
Active shadow:    0 8px 20px rgba(0,0,0,0.18)
```

**Transform Options (choose one):**

1. **Scale-up:**
   ```
   Default: scale(1)
   Hover: scale(1.02)
   Duration: 200ms
   ```

2. **Lift (translateY):**
   ```
   Default: translateY(0)
   Hover: translateY(-4px)
   Duration: 200ms
   ```

3. **Darken background:**
   ```
   Default: background-color: white
   Hover: background-color: #FAFAFA
   Duration: 200ms
   ```

**Avoid:**
- Multiple simultaneous transforms (scale + translateY)
- Long transitions (>300ms feel sluggish)
- Image blur on hover (can feel broken)

---

## Card Accessibility

**Requirements:**
- [ ] Card semantic: Use `<article>` or `<div role="article">`
- [ ] Heading hierarchy: Title is `<h3>` or `<h4>`
- [ ] Interactive elements: Links/buttons focusable and labeled
- [ ] Image alt text: Describe purpose (not "image of..." or "photo")
- [ ] Contrast: Text 4.5:1 on background
- [ ] Focus state: Visible outline on entire card or interactive element
- [ ] Keyboard navigation: Tab through cards and interactive elements

**Alt Text Examples:**
```
✗ Bad:  "picture of a laptop"
✓ Good: "MacBook Pro displaying design application"

✗ Bad:  "woman smiling"
✓ Good: "Product manager reviewing analytics dashboard"
```

---

## Card Design Anti-Patterns

### ❌ Too Much Content

```
❌ WRONG:
┌──────────────────┐
│ Long paragraph   │  Multiple paragraphs
│ of body text     │  Too many metadata
│ truncated...     │  Conflicting CTAs
│ [CTA 1] [CTA 2]  │
└──────────────────┘
```

**Fix:** Limit to 1-2 lines of description, 1 primary CTA.

### ❌ Inconsistent Sizing

```
❌ WRONG: Some cards 300px, others 320px
```

**Fix:** Define exact card width, use grid layout.

### ❌ Unclear CTA

```
❌ WRONG: Button says "Click Here" or "OK"
```

**Fix:** Use specific actions: "View Details", "Add to Cart", "Learn More".

### ❌ Missing Image Aspect Ratio

```
❌ WRONG: Images stretch or distort
```

**Fix:** Define aspect ratio, use object-fit: cover.

### ❌ Hover State Disappears Content

```
❌ WRONG: On hover, description text disappears
```

**Fix:** Hover should add (shadow, color change), not remove content.

---

## Card Specification Checklist

Before shipping card designs:

- [ ] Defined padding values (16px, 20px, etc.)
- [ ] Image aspect ratio locked (4:3, 16:9, 1:1)
- [ ] Hover state documented (shadow, scale, color)
- [ ] Text truncation limits (2 lines, 3 lines, etc.)
- [ ] Responsive layout for mobile/tablet
- [ ] Focus state visible (outline or background)
- [ ] Color contrast: Title and body text 4.5:1
- [ ] Touch targets: Links/buttons 44px minimum
- [ ] Alternate states: Disabled, loading, error
- [ ] Icon sizing consistent
- [ ] Font sizes follow 8px scale (16px, 18px, 20px, etc.)
- [ ] Gap measurements documented

