# Homepage Section Anatomy — Quick Reference

## SECTION-BY-SECTION HOMEPAGE BLUEPRINT

### 1. NAVIGATION BAR
**Purpose**: Site-wide wayfinding and primary CTA access

**Desktop Structure** [Arash]:
```
┌─────────────────────────────────────────────────────────────┐
│ [Logo]       [Home] [Features] [Pricing] [About]      [CTA] │
└─────────────────────────────────────────────────────────────┘
```
- Auto Layout: horizontal, Space Between
- Height: 56-72px
- Logo: 32-40px height, left-aligned
- Nav items: center-grouped, 24-32px gap
- CTA button: right-aligned, filled style

**States**: transparent landing > solid on scroll > dropdown open

---

### 2. HERO SECTION
**Purpose**: Communicate core value proposition and primary action

**Split Hero (Most Common for SaaS):**
```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│  [Eyebrow / Badge]              ┌─────────────────┐    │
│                                 │                 │    │
│  Main Headline                  │   Product       │    │
│  Goes Here                      │   Screenshot    │    │
│                                 │   or Visual     │    │
│  Supporting description         │                 │    │
│  text 2-3 lines max            │                 │    │
│                                 └─────────────────┘    │
│  [Primary CTA]  [Secondary]                            │
│                                                         │
│  "Trusted by 10,000+ companies"                        │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

**Centered Hero:**
```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│              [Eyebrow / Badge]                          │
│                                                         │
│           Main Headline Goes                            │
│             Here Centered                               │
│                                                         │
│     Supporting description text aligned center          │
│         max-width 600-700px for readability             │
│                                                         │
│          [Primary CTA]  [Secondary]                     │
│                                                         │
│          [Product screenshot below]                     │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

**Hero Sizing Reference:**
| Element | Desktop | Tablet | Mobile |
|---------|---------|--------|--------|
| Headline | 48-72px | 36-48px | 28-40px |
| Subheadline | 18-20px | 16-18px | 16px |
| CTA button | Large (48px) | Large (48px) | Large, full-width |
| Section height | 80-100vh | auto or 70vh | auto |
| Content max-width | 560-680px | 480px | full (minus padding) |

---

### 3. SOCIAL PROOF / LOGO BAR
**Purpose**: Build trust immediately after hero promise

**Layout Options:**
- Horizontal logo row (5-8 logos, grayscale, evenly spaced)
- Scrolling marquee (for many logos)
- Quote + attribution with company logo

**Sizing:**
- Logo height: 24-40px (all same height, width varies naturally)
- Vertical padding: 32-48px
- Background: same as hero or subtle change (light gray)
- Text above logos: "Trusted by" or "Used by teams at" -- 14px, uppercase, lighter color

---

### 4. FEATURES / SERVICES
**Purpose**: Show what the product/service does

**Pattern A: Icon + Title + Description Grid**
```
┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│ [Icon]       │  │ [Icon]       │  │ [Icon]       │
│ Feature 1    │  │ Feature 2    │  │ Feature 3    │
│ Description  │  │ Description  │  │ Description  │
└──────────────┘  └──────────────┘  └──────────────┘
```
- 3 or 4 columns, 24px gap
- Icon: 32-48px, brand color
- Title: 18-20px, semi-bold
- Description: 14-16px, lighter color
- Card padding: 24px all sides

**Pattern B: Alternating Image + Text Rows**
```
[Image left]  [Content right: Title, description, bullet list]
[Content left]  [Image right]
[Image left]  [Content right]
```
- Image: 50% width, screenshot or illustration
- Content: 50% width, left-aligned
- Gap between halves: 48-64px
- Alternate sides per row for visual rhythm

**Pattern C: Large Feature Showcase**
- Section heading + subheading centered
- Large product screenshot below
- 3-4 callout annotations pointing to features
- Best for flagship feature sections

---

### 5. HOW IT WORKS / PROCESS
**Purpose**: Reduce complexity, show simplicity of getting started

**Three-Step Pattern (Most Common):**
```
    Step 1              Step 2              Step 3
  [Number/Icon]       [Number/Icon]       [Number/Icon]
   Sign Up            Customize           Launch
   Description        Description         Description
```
- Numbered steps (1, 2, 3) or icons
- Connecting line or arrow between steps (optional)
- 3 steps is ideal (Hick's Law: fewer choices = easier decision)
- Vertical stack on mobile

---

### 6. TESTIMONIALS / CASE STUDIES
**Purpose**: Social proof with specific details

**Testimonial Card Layout:**
```
┌─────────────────────────────────────┐
│  "Quote text goes here,            │
│   typically 2-3 lines max."        │
│                                     │
│  [Avatar] Name                      │
│           Title, Company            │
└─────────────────────────────────────┘
```

**Options:**
- 3-column card grid (static)
- Single featured testimonial (large quote)
- Carousel/slider (swipe through)
- Star ratings above quote

**Sizing:**
- Quote text: 16-18px, regular or italic
- Attribution: 14px name (semi-bold) + 14px title (regular, lighter)
- Avatar: 40-48px circle
- Card padding: 24-32px

---

### 7. CTA SECTION
**Purpose**: Mid-page or bottom conversion push

**Full-Width CTA:**
```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│             Ready to get started?                       │
│                                                         │
│      Supporting text about the value proposition        │
│                                                         │
│               [Primary CTA Button]                      │
│                                                         │
└─────────────────────────────────────────────────────────┘
```
- Background: brand color, dark, or gradient
- Text: white or high contrast
- Centered layout
- Padding: 64-96px vertical
- Often placed between content sections AND before footer

---

### 8. FAQ SECTION
**Purpose**: Address objections, reduce support load

**Accordion Pattern:**
```
[Question 1]                                          [+]
[Question 2]                                          [+]
[Question 3 (expanded)]                               [-]
  Answer text goes here with supporting detail...
[Question 4]                                          [+]
```
- 5-8 questions typical
- Accordion expand/collapse (one or multiple open)
- Max-width: 720-800px centered for readability
- Question: 16-18px, semi-bold
- Answer: 14-16px, regular, lighter color

---

### 9. FOOTER
**Purpose**: Secondary navigation, legal, contact

**Multi-Column Footer:**
```
┌─────────────────────────────────────────────────────────┐
│ [Logo]       Product    Resources   Company             │
│              Features   Blog        About               │
│ Brief        Pricing    Help Docs   Careers             │
│ description  Updates    API Docs    Contact             │
│              Status     Guides      Press               │
│                                                         │
│ [Social Icons]                                          │
├─────────────────────────────────────────────────────────┤
│ (c) 2026 Company   |   Privacy   |   Terms   |   Built │
│                         Policy       of Use     by...   │
└─────────────────────────────────────────────────────────┘
```
- 3-5 columns of link groups
- Logo + brief description in first column
- Social icons below or beside logo
- Bottom bar: copyright, legal links, credit
- Background: dark (gray-900 or brand dark)
- Text: gray-400 for links, gray-500 for sub-text

---

## E-COMMERCE HOMEPAGE STRUCTURE

| Section | Purpose | Special Notes |
|---------|---------|---------------|
| Hero | Seasonal promotion or hero product | Carousel optional for multiple promos |
| Category Grid | Product category browsing | 3-6 categories with images |
| Featured Products | Showcase bestsellers | 4-8 product cards |
| Value Props | Shipping, returns, quality | 3-4 icon + text badges |
| Collection Spotlight | Curated collection | Full-width image + CTA |
| Reviews/UGC | Customer photos + reviews | Social proof specific to products |
| Newsletter | Email capture | Incentive: "10% off first order" |
| Footer | Extended with shipping info | Trust badges, payment icons |

---

## PAGE TYPES BEYOND HOMEPAGE

### About Page
- Brand story (narrative format)
- Team section (photo grid + bios)
- Values/mission
- Timeline (optional)

### Pricing Page
- 3-tier pricing cards (Hick's Law: 3 options optimal)
- Feature comparison table below
- FAQ addressing pricing objections
- "Most Popular" badge on recommended tier

### Blog/Resources
- Featured article (large card)
- Article grid (3 columns)
- Category filters
- Sidebar (optional: recent posts, newsletter)
- Pagination

### Contact Page
- Contact form (name, email, message minimum)
- Map or office address
- Alternative contact methods (email, phone, social)
- Hours of operation
