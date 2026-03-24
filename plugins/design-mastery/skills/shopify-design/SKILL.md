---
name: Shopify Design & Theme Architecture
description: "Complete Shopify theme customization, Liquid templating, custom sections with JSON schema, e-commerce design for conversion, theme architecture, and store launch workflow. MANDATORY TRIGGERS: Shopify theme design, Liquid code, custom sections, Shopify customization, e-commerce design, theme development, section schema, store launch, conversion optimization Shopify. Do NOT use for general web design—use web-layout instead."
---

# Shopify Design & Theme Architecture Skill

## When You Need This Skill

Use this skill when:
- Customizing a Shopify theme (appearance, layout, functionality)
- Building custom sections with Liquid templating
- Understanding Shopify's hierarchical file structure
- Designing for e-commerce conversion
- Planning a Shopify store launch
- Scoping/pricing Shopify customization projects
- Troubleshooting Liquid code issues
- Optimizing theme for performance and UX

**This is a technical design skill.** You should understand how Shopify's code structure works and how to create custom sections. It's not purely visual design—it requires understanding templating and configuration.

---

## Shopify Theme Architecture: The 5-Layer System

Shopify themes are organized hierarchically. Understanding this structure is essential.

### Layer 1: Layout (theme.liquid)

**What it is:** The master template that wraps ALL pages

**Contains:**
- HTML document structure (`<html>`, `<head>`, `<body>`)
- Header and navigation
- Footer (usually)
- CSS and JavaScript includes
- Shopify-required code (`{{ content_for_header }}`)

**Critical code that MUST exist:**

```liquid
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    {{ content_for_header }}
    <!-- CSS, analytics, fonts go here -->
  </head>
  <body>
    {% section 'header' %}

    {{ content_for_layout }}

    {% section 'footer' %}
  </body>
</html>
```

**Key tag:** `{{ content_for_layout }}` — This is where page-specific content renders

**What CAN'T be in layout:**
- Page-specific content (products, blog posts, collections)
- Section-specific Liquid code
- Only shared elements (header, footer, global styles)

### Layer 2: Templates (Page Type Definitions)

**What they are:** Define which sections appear on specific page types

**Template types:**
- `product.liquid` — Single product page
- `collection.liquid` — Collection/category page
- `index.liquid` — Homepage
- `page.liquid` — Static pages
- `blog.liquid` — Blog listing page
- `article.liquid` — Single blog post
- `cart.liquid` — Shopping cart
- `checkout.liquid` — Checkout page (limited customization)

**How templates work:**

```liquid
{%- render 'breadcrumbs' -%}

{% section 'product-hero' %}
{% section 'product-details' %}
{% section 'related-products' %}
{% section 'testimonials' %}
```

**Key principle:** Template defines which sections appear and in what order. Sections are reusable, template is page-specific.

**Shopify 2.0 IMPORTANT:** Modern themes use JSON template structure:
```json
{
  "sections": {
    "main": { "type": "main-product" },
    "product-gallery": { "type": "product-gallery" },
    "related": { "type": "related-products" }
  },
  "order": ["main", "product-gallery", "related"]
}
```

### Layer 3: Sections (Reusable Building Blocks)

**What they are:** Self-contained components with HTML, CSS, Liquid, and JSON schema

**Each section contains:**
1. **HTML/Liquid** — Markup and content logic
2. **CSS** — Styling (scoped to section)
3. **Liquid schema** — Settings that appear in Shopify editor
4. **JavaScript** — Interactivity (optional)

**Structure of a section file:**

```liquid
<div class="section-name">
  <!-- HTML/LIQUID MARKUP -->
  <h2>{{ section.settings.heading }}</h2>
  <p>{{ section.settings.description }}</p>
</div>

<style>
  .section-name {
    padding: {{ section.settings.padding }}px;
  }
</style>

{% schema %}
{
  "name": "Section Display Name",
  "settings": [
    {
      "type": "text",
      "id": "heading",
      "label": "Heading Text"
    },
    {
      "type": "range",
      "id": "padding",
      "label": "Padding",
      "min": 10,
      "max": 50,
      "default": 20,
      "unit": "px"
    }
  ]
}
{% endschema %}
```

**Key advantage:** Sections are:
- Draggable in Shopify theme editor (no code knowledge required)
- Fully customizable with JSON schema
- Reusable across multiple pages
- Can have blocks (smaller pieces within sections)

### Layer 4: Blocks (Repeatable Elements Within Sections)

**What they are:** Smaller reusable pieces within a section (can be added/removed/reordered)

**Common uses:**
- Product cards within a grid section
- Testimonial items within testimonials section
- Feature items within features section
- Image + text pairs

**Block example:**

```liquid
<div class="products-grid">
  {% for block in section.blocks %}
    <div class="product-card" {{ block.shopify_attributes }}>
      <img src="{{ block.settings.image | image_url: width: 300 }}" alt="">
      <h3>{{ block.settings.title }}</h3>
    </div>
  {% endfor %}
</div>

{% schema %}
{
  "name": "Product Grid Section",
  "blocks": [
    {
      "type": "product",
      "name": "Product Item",
      "settings": [
        {
          "type": "image_picker",
          "id": "image",
          "label": "Product Image"
        },
        {
          "type": "text",
          "id": "title",
          "label": "Product Title"
        }
      ]
    }
  ]
}
{% endschema %}
```

**Blocks appear in Shopify editor as:**
- "Add block" button
- Each block is removable (X button)
- Blocks are reorderable (drag handle)
- Each block has own settings

### Layer 5: Snippets (Reusable Code Chunks)

**What they are:** Reusable Liquid code fragments included in multiple places

**Common snippets:**
- Product card template (used in collections, related products, search results)
- Price display formatting
- Rating stars component
- Image with fallback
- Social sharing buttons

**Snippet example:**

```liquid
<!-- /snippets/product-card.liquid -->
<div class="product-card">
  {% if product.featured_image %}
    <img src="{{ product.featured_image | image_url: width: 300 }}" alt="{{ product.title }}">
  {% endif %}
  <h3>{{ product.title }}</h3>
  <p class="price">{{ product.price | money }}</p>
  <a href="{{ product.url }}">View Product</a>
</div>
```

**Using a snippet:**

```liquid
<!-- In any template or section -->
{% for product in collection.products %}
  {% render 'product-card', product: product %}
{% endfor %}
```

**Why snippets matter:**
- DRY principle (Don't Repeat Yourself)
- Change once, affects everywhere
- Easier to maintain code
- Single source of truth for component

---

## Liquid Templating Fundamentals

Liquid is Shopify's templating language. It uses output tags (`{{ }}`), logic tags (`{% %}`), and filters to manage product data and page rendering.

For comprehensive Liquid patterns, filters, and examples, read `references/liquid-patterns.md`.

---

## Custom Sections with JSON Schema

Sections are self-contained components with Liquid markup, CSS, and JSON schema for editor settings. Each section can have blocks (repeatable items) and customize its appearance through the Shopify theme editor.

For complete schema examples, setting types, and block structures, read `references/custom-sections-schema.md`.

---

## E-Commerce Design for Conversion

### Product Page Structure

**Essential elements on product page:**

1. **Product Images** — Gallery with zoom, thumbnails
2. **Product Title** — Clear, benefit-focused
3. **Price & Availability** — Crystal clear, above fold
4. **Variants** — Size, color, material options
5. **Add to Cart** — Prominent, high contrast
6. **Description** — Benefits, not just features
7. **Social Proof** — Reviews, ratings, "X sold"
8. **Related Products** — Cross-sell, upsell
9. **Trust Signals** — Returns policy, shipping, guarantees
10. **High-Intent CTA** — "Buy now," not "Learn more"

### Conversion-Focused Layouts

**Rule 1: Place price and "Add to Cart" above the fold**
- 60% of people decide to buy or not in first 3 seconds
- If they have to scroll to see price, you lose conversions

**Rule 2: Simplify variant selection**
- Size and color should be OBVIOUS
- Not buried in dropdowns
- Visual representation (show actual colors)

**Rule 3: Reduce friction**
- One-click add to cart
- Minimize form fields
- Clear shipping/return policy visible
- Minimal information hierarchy (don't overwhelm with details)

**Rule 4: Trust and social proof**
- Customer reviews/ratings prominent
- "20 people bought this today" counter
- Money-back guarantee visible
- Professional product photography

**Rule 5: Mobile optimization critical**
- Touch targets minimum 44px × 44px
- Vertical stacking of images
- Simplified variant selection on mobile
- "Add to Cart" fixed at bottom (sticky)

---

## Store Launch Checklist

Use this checklist to verify your store is ready before going live. Key areas: design & UX, content, performance, security, and testing.

For detailed launch checklists with pre-launch verification, launch day prep, and post-launch guides, read `references/store-launch-guide.md`.

---

## Scoping & Pricing Shopify Projects

### Complexity Levels

**Level 1: Simple Store (20-40 hours)**
- Single theme customization
- Basic section edits
- Content updates
- 10-20 products
- Minimal custom code
- **Price range:** $2,000-4,000

**Level 2: Custom Sections (50-80 hours)**
- 3-5 custom sections (built from scratch)
- Product filtering
- Basic animations
- 50-100 products
- Some Liquid customization
- **Price range:** $5,000-8,000

**Level 3: Full Custom Build (100-150 hours)**
- Complete theme from scratch
- 5-10 custom sections with JSON schema
- Advanced product filtering
- Custom checkout customization
- 100+ products with variants
- **Price range:** $10,000-15,000

**Level 4: Enterprise (200+ hours)**
- Completely custom theme
- 10+ complex sections
- Advanced APIs integration
- Custom admin features
- 1000+ products with inventory sync
- **Price range:** $20,000+

### What to Charge For

**Included in project:**
- Theme customization (colors, fonts, layout)
- Content input (product descriptions, images)
- Basic section setup
- Mobile optimization
- Analytics setup
- Basic SEO optimization

**Billable as separate:**
- Product photography
- Product description writing
- Brand strategy/identity
- Marketing consulting
- Advanced integrations (inventory systems, multi-vendor)
- Custom app development
- Ongoing support/maintenance

### Project Scoping Questions

Before quoting, ask:

1. **What's the budget?** (Informs design scope)
2. **How many products?** (Affects complexity)
3. **Product variants?** (Customization needed?)
4. **Custom functionality needed?** (Apps vs. custom code)
5. **Timeline?** (Affects hourly rate?)
6. **Who manages content after launch?** (Support needed?)
7. **Existing design or starting from scratch?** (Time estimation)
8. **What's the business model?** (Affects conversion focus)
9. **Traffic expectations?** (Performance considerations)
10. **Future growth plans?** (Scalability needed?)

---

## When to Read References

The reference files go deeper into specific topics:

- **liquid-templating-complete.md** — Advanced Liquid patterns, loops, conditionals, filters with examples
- **custom-sections-schema.md** — Complete section development, JSON schema deep dive, block management
- **ecommerce-design-conversion.md** — Product page layouts, collection design, checkout optimization

**Read references when:**
- Building complex custom sections
- Troubleshooting Liquid code issues
- Planning e-commerce design strategy
- Preparing for store launch
- Optimizing for specific conversions
- Dealing with performance issues

---

## Quick Reference: Shopify File Structure

```
theme/
├── config/
│   └── settings_schema.json      (Theme-wide settings)
├── layout/
│   └── theme.liquid              (Master template)
├── templates/
│   ├── index.liquid              (Homepage)
│   ├── product.liquid            (Product page)
│   ├── collection.liquid         (Category page)
│   └── cart.liquid               (Cart page)
├── sections/
│   ├── header.liquid             (Header section)
│   ├── footer.liquid             (Footer section)
│   ├── hero.liquid               (Custom hero section)
│   └── featured-products.liquid  (Product grid section)
├── snippets/
│   ├── product-card.liquid       (Reusable product template)
│   └── price.liquid              (Price formatting)
├── assets/
│   ├── style.css
│   ├── script.js
│   └── image.jpg
└── locales/
    └── en.json                    (Multi-language strings)
```

---

## Common Design Decisions

**"Should we use a pre-made section or build custom?"**
- Use pre-made if it matches your needs (saves time)
- Build custom if you need specific functionality or design

**"How many sections per page?"**
- Typical: 5-8 sections per page
- Too many = longer load time, confusing editor
- Too few = repetitive feel

**"Should we use apps or custom code?"**
- Apps: Faster to implement, ongoing updates
- Custom: More control, no monthly fees, requires maintenance

**"Product image sizes?"**
- Minimum: 600px width
- Recommended: 1000px-1500px width
- Aspect ratio: 1:1 for grid, 3:4 for lifestyle

**"Mobile breakpoint?"**
- Typical: 768px (tablet switches to mobile layout)
- Shopify default sections use 750px
- Test on actual mobile devices

---

## This Skill is Specialized

This Shopify Design skill is specific to Shopify theme customization and e-commerce design.

For general website design, web layout, components, or non-e-commerce design patterns, refer to `web-layout`, `ui-components`, or `visual-foundations` skills.

For web implementation in Webflow (not Shopify), use `webflow-implementation` instead.

---

## Skills Referenced

- **web-layout** — General layout patterns and responsive design principles
- **ui-components** — Button, card, form patterns (apply to Shopify design too)
- **visual-foundations** — Color, typography, spacing rules

---

**Next step:** Read liquid-templating-complete.md for advanced Liquid patterns, or dive into custom sections with custom-sections-schema.md.
