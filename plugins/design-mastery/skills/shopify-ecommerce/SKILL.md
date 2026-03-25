---
name: Shopify E-Commerce
description: "Shopify theme architecture, Liquid templating, custom sections with JSON schema, e-commerce UX and conversion optimization, metafields, product detail pages, mobile design, CSS customization, SEO, and store launch workflow. Based on Design Freedom on Shopify (Luna Templates) methodology. MANDATORY TRIGGERS: Shopify, Liquid, theme, custom section, e-commerce, product page, PDP, collection, metafield, Shopify launch, Shopify SEO, Shopify CSS, checkout, conversion, store design, Online Store 2.0, section schema, Shopify theme architecture. FOR: Designing and building Shopify stores, customizing themes with Liquid code, creating custom sections, optimizing e-commerce conversion, Shopify launch workflow, metafield setup, platform selection advisory. Do NOT use for general web design — use web-layout instead. Do NOT use for Webflow builds — use webflow-build instead. Do NOT use for brand identity/logo — use logo-brand-identity instead."
---

# Shopify E-Commerce

Design and build conversion-optimized Shopify stores. This skill covers platform selection, theme architecture, Liquid templating, custom sections, e-commerce UX, metafields, mobile design, SEO, and the complete client workflow from scoping through launch.

---

## CORE PHILOSOPHY: FUNCTION OVER FORM

**Function always wins for e-commerce** -- but functional does not mean boring.

[CONTRARIAN -- Design Freedom] Standard layouts with great branding beat experimental layouts. The branding (typography, color, photography) makes standard layouts feel exciting, not the layout itself. Back up every design decision with a reason -- leads to fewer revisions and positions you as an expert.

---

## PLATFORM SELECTION

### The 60% Rule
If selling products will make up more than 60% of the website content, Shopify is the right choice.

### When Shopify Wins
- E-commerce is primary business function
- Client needs POS (point of sale) for in-person selling
- International selling (currency, tax, fulfillment)
- 10+ SKUs
- Advanced payment options (40+ gateways including Apple Pay, Klarna, installments)
- Familiar, trusted checkout (increases conversion)

### When Shopify Loses
- Service-based businesses (<60% e-commerce)
- Advanced blogging needs (Shopify blog is basic -- images and text only)
- Heavy information architecture, scheduling, or portfolio needs

### Shopify Lite Hybrid
Build site on Squarespace/Webflow + add Shopify Lite for e-commerce backend. Client gets Shopify's product tools, payment processing, and trusted checkout at ~$32/mo combined.

### Platform Decision Questions
1. Will selling products make up more than 60% of content?
2. Does client need POS?
3. Will store sell internationally?
4. Need fulfillment center integration?
5. More than 10 SKUs?
6. Need advanced blogging?
7. Ask about NOW and FUTURE needs -- migration is painful

For the complete decision framework, see `references/01-platform-selection.md`.

---

## THEME ARCHITECTURE: THE 5-LAYER SYSTEM

```
Layout (theme.liquid)
  -> Templates (.json)
    -> Sections (.liquid)
      -> Blocks (inside sections)
        -> Snippets (.liquid, via render tag)
```

### Layer 1: Layout (theme.liquid)
The master template wrapping ALL pages. Contains HTML document structure, header, footer, CSS/JS includes, and Shopify-required code (`{{ content_for_header }}`, `{{ content_for_layout }}`).

### Layer 2: Templates (.json)
Control which sections appear on each page type. Standard types: product, collection, blog, article, page, index (homepage). JSON templates store section lists and settings -- NOT HTML code.

### Layer 3: Sections (.liquid)
Building blocks of pages. Contain HTML, CSS, Liquid, JSON schema, and optional JavaScript. Each section has its own theme editor settings.

### Layer 4: Blocks
Smaller reusable units inside sections. Added/removed/reordered by the merchant in the theme editor.

### Layer 5: Snippets (.liquid)
Reusable code chunks via `{% render 'snippet-name' %}`. Common: product card, social icons, breadcrumbs, pagination. DRY principle: change once, updates everywhere.

### Online Store 2.0 vs. Vintage
- **2.0 themes:** Templates are `.json` -- freely add/remove sections on any page via editor
- **Vintage themes:** Templates are `.liquid` -- sections hard-coded, can't freely add/remove
- Released mid-2021; some clients still on vintage themes

For full architecture details, see `references/02-theme-architecture.md`.

---

## STORE DATA vs. THEME DATA

### Store Data (Persists Across Theme Changes)
Files, fonts, images, blog posts, pages, products, navigation menus, customers, orders

### Theme Data (Lost When Switching Themes)
Customizer settings, section blocks, page templates, code customizations, language settings, images uploaded in theme editor

**Critical implication:** Working on a live site -- changing store data (navigation, products, blog) affects ALL themes including the published one. Always duplicate theme before changes.

---

## LIQUID TEMPLATING

### Two Syntax Types
- `{{ }}` double curly braces = **output** (display information)
- `{% %}` curly brace + percent = **logic** (conditionals, loops)

### Dot Syntax for Output
`object.property` -- e.g., `product.title`, `article.author`, `shop.name`

### Essential Filters (Pipe Character `|`)
| Filter | Purpose |
|--------|---------|
| `| upcase` | Uppercase text |
| `| money_with_currency` | Format price with currency |
| `| t` | Translation (access locale files) |
| `| escape` | Show HTML as text (DELETE to render HTML) |
| `| strip_html` | Remove all HTML (DELETE to keep styling) |
| `| newline_to_br` | Enable line breaks |
| `| image_url: width: 100` | Image at specific size (load size, not display) |

### White Space Control
Add hyphens: `{%- -%}` to remove extra blank lines in output.

### Object Scope
- **Global:** `shop.name` accessible from any .liquid file
- **Local:** `product.price` only available in product template

For complete Liquid patterns and code examples, see `references/03-liquid-patterns.md`.

---

## SECTION SCHEMA & CUSTOM SECTIONS

### Section Code Structure
1. **HTML** -- skeleton for displayed content
2. **Liquid** -- placeholder code for store data and settings
3. **CSS** -- inside `{% style %}` tags for section-scoped styles
4. **JSON schema** -- creates settings visible in theme editor
5. **JavaScript** (optional)

### Schema Anatomy
```json
{
  "name": "Section Name",
  "settings": [...],
  "blocks": [...],
  "presets": [...]
}
```

### Setting Types
Each setting has: `type`, `id`, `label`, optional `default`. Types: text, richtext, image_picker, select, checkbox, color, url, range.

### Three Ways to Use Setting Values
1. **As content:** `<h2>{{ section.settings.title }}</h2>`
2. **As CSS class:** `class="text-{{ section.settings.heading_size }}"`
3. **In section CSS:** `padding-top: {{ section.settings.padding_top }}px;`

### Section CSS Scoping
Always use `#section-{{ section.id }}` as selector -- ensures styles only apply to that section instance. For blocks: `#block-{{ block.id }}`.

### ID Rules
- IDs must be unique within a block type
- Same ID can exist in section settings AND block settings
- Same ID can exist across different block types
- Cannot have two settings with same ID inside the same block

For starter code templates (with and without blocks), see `references/03-liquid-patterns.md`.

---

## E-COMMERCE UX & CONVERSION

### Conversion Funnel Principles
1. **Make it emotional** -- convey lifestyle, not just product shots
2. **Make it clear** -- effects shouldn't distract from product
3. **Make it fast** -- heavy effects slow load times
4. **Make it easy** -- seamless navigation encourages repeat purchases
5. **Make it scannable** -- users scan, don't read; use visuals for instant impressions

### Where to Get Creative vs. Stay Standard
- **Stay standard:** Homepage product sections, PDP, checkout flow
- **Get creative:** About pages, brand story pages
- **Always creative:** Typography, color, branding, hover effects, micro-animations

### Design Signposts
- All CTAs same color with high contrast (visual wayfinding)
- Consistent navigation and interaction patterns

### Wireframes
[CONTRARIAN -- Design Freedom] Skip wireframes for most e-commerce. Clients find them confusing; layout often changes once branding is applied. USE wireframes for: very large sites, when photography precedes design, or when working with agencies who expect them.

For homepage structure, PDP elements, and mobile rules, see `references/04-ecommerce-ux.md`.

---

## METAFIELDS (CUSTOM FIELDS)

### What They Solve
Store and display extra product-specific information (ingredients, washing instructions, size charts) beyond title/description/price.

### Setup Process
1. Settings > Metafields > Products > Add new
2. Name it (e.g., "Ingredients")
3. Choose content type
4. Go to product editor -- new field appears at bottom
5. In theme editor, use Dynamic Source button to connect

### Critical Rules
- Content type MUST match input box type (multi-line text won't appear in single-line options)
- Cannot change content type after creation -- must delete and recreate
- Plan metafields in advance: list needed fields + types before creating
- Collection page metafields require Liquid code changes (not available via theme editor)

---

## THEME SELECTION

[CONTRARIAN -- Design Freedom] Choose the right theme per project, not a go-to theme. Different themes offer different product page layouts, built-in features, and section templates.

### Selection Process (5 Steps)
1. Create feature wish list (now AND future needs)
2. Consider layout options (especially PDP -- hard to change later)
3. Filter and browse themes (70-80 available)
4. Demo the theme (unlimited trial)
5. Purchase ($250-400 one-time, usually included in project cost)

### Key Features to Evaluate
- Mega menu (essential for 20+ products)
- Quick add/quick view (reduces clicks to conversion)
- Color swatches (essential for clothing/beauty)
- Product badges (sale, low stock, best seller)
- Advanced product filtering (must-have for large catalogs)
- Size guide (central for clothing)
- Image rollover on product grid

---

## MOBILE DESIGN

### Key Rules
- Body copy: minimum 14px
- Form input text: minimum 16px (or iPhone auto-zooms on focus)
- Product grid: always 2 columns on mobile (1 column = too much scrolling)
- Buttons: large enough for thumbs with adequate spacing
- Remove decorative elements that obstruct content on mobile
- Sliders useful on mobile for space conservation
- Custom sections: plan mobile stacking (even-number columns work better)

### Checkout Design
Shopify removes all unnecessary UI during checkout to prevent distraction. Customizable: colors, logo, background image only (unless Shopify Plus).

[CONTRARIAN -- Design Freedom] Don't add upsells or extra CTAs to checkout -- creates decision paralysis that increases cart abandonment.

---

## SEO ON SHOPIFY

### Designer-Controlled Factors
1. Text content: incorporate keywords into headings and descriptions
2. Image alt text: add to ALL images (do at END once final)
3. File names: rename descriptively BEFORE uploading
4. Meta descriptions: homepage (most important), all pages, products, blog posts
5. URLs: verify all handles before launch (no "copy-of-" artifacts)
6. HTML heading structure: one H1 per page
7. Blog: suggest to clients for authority and long-tail keywords
8. Submit sitemap to Google Search Console

---

## SHOPIFY CSS CUSTOMIZATION

### Custom CSS Options
- Theme editor's Custom CSS box (available in many themes)
- Directly in section files using `{% style %}` tags
- Assets folder CSS files

### Section-Scoped Pattern
```liquid
{% style %}
#section-{{ section.id }} {
  /* Styles only for this section instance */
}
{% endstyle %}
```

### Block-Scoped Pattern
```html
<style>
#block-{{ block.id }} {
  /* Styles only for this specific block */
}
</style>
```

### Custom Fonts
Upload font files to Assets folder, add @font-face CSS declarations, override theme font variables.

---

## LAUNCH CHECKLIST

### Pre-Launch
- [ ] All meta descriptions added
- [ ] All URL handles verified
- [ ] All image alt text added
- [ ] All images descriptively named
- [ ] Mobile testing on actual devices
- [ ] Form fields minimum 16px
- [ ] Touch targets adequate size
- [ ] Site speed checked
- [ ] Sitemap submitted to Google Search Console
- [ ] Client tutorials delivered
- [ ] Theme backup created (versioned naming)

### Working on Live Stores
- NEVER modify published theme directly
- Duplicate, rename with version (e.g., "Brand 1.0", "Brand 1.1")
- Store data changes (navigation, products, blog) affect live site even on unpublished theme
- Publish only after client approval

---

## ANTI-PATTERNS

- Using one go-to theme for every project
- Experimental layouts that hide products (form over function)
- Hamburger menus on desktop (hide information)
- Sliders in hero section (proven to hide content from shoppers)
- No quantity selector on products rarely bought in multiples
- Generic "Shop" CTA instead of descriptive text
- Adding upsells to checkout flow
- Accepting inquiries via DMs instead of structured forms
- Not planning metafield types before creating them
- Modifying published theme directly

---

## RELATED SKILLS

- **web-layout:** For general web design principles that feed into Shopify page structure
- **typography-systems:** For type hierarchy in Shopify themes
- **color-systems:** For palette and contrast decisions in e-commerce
- **ui-components:** For button, card, and form patterns used in Shopify
- **discovery-direction:** For client scoping, sales calls, and pricing Shopify projects
- **design-critique:** For reviewing store design before launch
- **webflow-build:** If the project is NOT e-commerce, use Webflow instead
