# Web Layout Patterns — Common Combinations

## Layout Pattern 1: Hero + 3-Column Features + CTA + Footer

**Flow:**
```
[Full-viewport hero, left-aligned text + right image]
↓ 128px gap
[3 feature cards with icons]
↓ 128px gap
[CTA section, centered]
↓
[Multi-column footer]
```

**When to use:** B2B SaaS, service-based businesses, most websites
**Example sites:** Slack, Figma, Webflow (home pages)

**Desktop layout:**
- Hero: Text (50%) + Image (50%)
- Features: 3 cards (4-col each)
- CTA: Centered text + button
- Footer: 5 columns

**Mobile layout:**
- Hero: Text full-width above image
- Features: 1 card per row, stacked
- CTA: Centered, full-width button
- Footer: 1 column, stacked

---

## Layout Pattern 2: Split-Screen (Image + Text, Alternating)

**Flow:**
```
[Image left, text right]
↓ 100px gap
[Text left, image right]
↓ 100px gap
[Image left, text right]
```

**When to use:** Product narratives, brand stories, detailed explanations
**Example sites:** Apple product pages, design-focused sites

**Desktop layout:**
- Section 1: Image (50%) + Text (50%), left image
- Section 2: Text (50%) + Image (50%), left text
- Alternates for visual interest

**Mobile layout:**
- All sections: Image top, text bottom (single column)

**Spacing:**
- Image aspect ratio: 3:2 or 16:9
- Gap between image and text: 48px (desktop), 32px (mobile)
- Section padding: 100px vertical
- Text max-width: 500px

---

## Layout Pattern 3: Grid of 6 Tiles (2x3 or 3x2)

**Flow:**
```
[Tile 1] [Tile 2] [Tile 3]
[Tile 4] [Tile 5] [Tile 6]
```

**When to use:** Case studies, portfolio, team members, product variations
**Example sites:** Creative agencies, portfolio sites

**Desktop:**
- 3 columns, 2 rows
- Tile width: 4-column width each
- Gap: 24px

**Tablet:**
- 2 columns, 3 rows
- Tile width: 3-column width each
- Gap: 20px

**Mobile:**
- 1 column, 6 rows
- Full width
- Gap: 16px

**Tile content:** Image + text overlay, or card with title

---

## Layout Pattern 4: Bento Box (Varied Sizes)

**Flow:**
```
[Large tile (2x2)]  [Tile 1] [Tile 2]
                    [Tile 3] [Tile 4]
[Tile 5] [Tile 6]   [Large tile (2x2)]
```

**When to use:** Dashboard home, portfolio showcase, feature overview
**Example sites:** Modern SaaS dashboards

**Implementation:**
- Large tile: 6-column width (or more)
- Regular tile: 3-column width
- Gap: 24px consistent
- Aspect ratios: Varied (allow flexibility)

**Desktop:** Full bento layout with varied sizes
**Mobile:** All tiles 1 column, full-width, standard aspect ratio

---

## Layout Pattern 5: Left Sidebar + Main Content

**Flow:**
```
┌──────┬──────────────────┐
│ Nav  │ Main content     │
│ Side │ with multiple    │
│ bar  │ sections         │
│      │                  │
└──────┴──────────────────┘
```

**When to use:** Documentation, blog with sidebar, settings pages
**Example sites:** Docs sites, internal tools

**Desktop:**
- Sidebar: 250-300px fixed or sticky
- Content: Remaining width, max-width 900px
- Layout: Flexbox or grid

**Tablet/Mobile:**
- Sidebar: Collapses to hamburger menu
- Content: Full width

**Sidebar content:** Navigation, filters, related links
**Main content:** Article, documentation, settings form

---

## Layout Pattern 6: Masonry Grid (Pinterest-style)

**Flow:**
```
[Tall image 1] [Image 2] [Tall image 3]
               [Image 4]
[Image 5]      [Image 6] [Image 7]
```

**When to use:** Image gallery, portfolio, inspiration showcase
**Example sites:** Pinterest, Dribbble, photo galleries

**Implementation:**
- CSS Grid with auto-flow (dense)
- Variable tile heights (content-based)
- Gap: 16-24px consistent
- Use aspect-ratio CSS property

**Desktop:** 3-4 columns
**Tablet:** 2 columns
**Mobile:** 1 column

---

## Layout Pattern 7: Asymmetric (Large + Small Content Mix)

**Flow:**
```
[Large content area]     [Small 1]
                         [Small 2]
[Medium content area]    [Small 3]
```

**When to use:** Blog post with sidebar ads, product with related items
**Example sites:** Medium, news sites with sidebars

**Desktop:**
- Large: 8 columns
- Small: 4 columns (right sidebar)
- Ratio: 2:1 content to sidebar

**Mobile:**
- All content: Full width, single column
- Sidebar moves below content

---

## Layout Pattern 8: Full-Width Sections with Varied Containers

**Flow:**
```
[Full-width dark hero section]
[100% viewport width, centered content max-width 1312px]
↓
[Full-width light section]
[100% viewport width, centered content]
↓
[Full-width white section]
[100% viewport width]
```

**When to use:** Modern websites with color blocks, SaaS homepages
**Example sites:** Vercel, Stripe, modern design-focused sites

**Implementation:**
```css
.section {
  width: 100%;
  padding: 100px 0;
  background-color: #F5F5F5;
}

.section-content {
  max-width: 1312px;
  margin: 0 auto;
  padding: 0 64px;
}
```

**Desktop:** Full-width background, centered content
**Mobile:** Same approach, narrower margins (16px)

---

## Layout Pattern 9: Two-Column with Full-Width Sections

**Flow:**
```
[Full-width hero]
↓
[2-column content + sidebar]
[Left 8 cols, Right 4 cols]
↓
[Full-width CTA]
↓
[Single column content]
```

**When to use:** Blog/docs with mixed content types
**Example sites:** Documentation, long-form content sites

**Responsive:**
- Desktop: 8+4 column split
- Tablet: Stack to 6+6 or single column
- Mobile: Full-width single column

---

## Layout Pattern 10: Card Grid with Pagination

**Flow:**
```
[Search/filter bar]
↓
[Card 1] [Card 2] [Card 3]
[Card 4] [Card 5] [Card 6]
↓
[Pagination: Previous] [1] [2] [3] [Next]
```

**When to use:** E-commerce, product listing, content discovery
**Example sites:** Shopify, Amazon, product marketplaces

**Desktop:**
- 3-4 cards per row
- Card width: Responsive columns
- Filter bar: Top, full-width

**Mobile:**
- 1-2 cards per row
- Filter bar: Collapsible hamburger
- Pagination: Below or infinite scroll

**Card content:** Image, title, price/description, CTA

---

## Decision Tree: Choosing a Layout Pattern

```
What type of content are you displaying?

→ Product/Service homepage?
  └─ Use Pattern 1 (Hero + Features + CTA)

→ Detailed narrative/story?
  └─ Use Pattern 2 (Alternating split-screen)

→ Portfolio/cases/team?
  └─ Use Pattern 3 (6-tile grid)

→ Varied feature showcase?
  └─ Use Pattern 4 (Bento box)

→ Documentation/blog with sidebar?
  └─ Use Pattern 5 (Sidebar nav)

→ Image gallery/inspiration?
  └─ Use Pattern 6 (Masonry)

→ Mixed content sizes?
  └─ Use Pattern 7 (Asymmetric)

→ Brand-focused with color blocks?
  └─ Use Pattern 8 (Full-width sections)

→ Complex content mix?
  └─ Use Pattern 9 (2-col + full-width)

→ Products/items to browse?
  └─ Use Pattern 10 (Card grid + pagination)
```

