---
name: Theme Architecture Reference
description: "Folder structure, layout/templates/sections/snippets/assets, Online Store 2.0, store vs theme data, config and locales."
---

# Shopify Theme Architecture

Complete reference for Shopify's theme file structure and data model.

---

## FOLDER STRUCTURE HIERARCHY

```
theme/
├── layout/
│   ├── theme.liquid          # Master template for all pages
│   └── password.liquid       # Password-protected store page
├── templates/
│   ├── index.json            # Homepage
│   ├── product.json          # Product pages
│   ├── collection.json       # Collection pages
│   ├── blog.json             # Blog listing
│   ├── article.json          # Blog post
│   ├── page.json             # Static pages
│   ├── cart.json             # Cart page
│   ├── 404.json              # Not found page
│   └── search.json           # Search results
├── sections/
│   ├── header.liquid         # Site header (hard-coded in layout)
│   ├── footer.liquid         # Site footer (hard-coded in layout)
│   ├── featured-collection.liquid
│   ├── hero-banner.liquid
│   └── [custom-sections].liquid
├── snippets/
│   ├── product-card.liquid   # Reusable product card
│   ├── social-icons.liquid
│   ├── breadcrumbs.liquid
│   └── pagination.liquid
├── assets/
│   ├── theme.css             # Main stylesheet
│   ├── theme.js              # Main JavaScript
│   └── [additional CSS/JS files]
├── config/
│   ├── settings_schema.json  # Defines theme setting options
│   └── settings_data.json    # Stores user-selected values
└── locales/
    ├── en.default.json       # English translations
    └── en.default.schema.json # Schema translations
```

---

## LAYOUT FILES

### theme.liquid
Base of every page. Contains the HTML document structure.

**Required elements:**
- `{{ content_for_header }}` in `<head>` -- loads Shopify analytics, app code, Google Analytics
- `{{ content_for_layout }}` in `<body>` -- renders the template for the current URL

**Typically includes:**
- Meta tags, favicon, CSS/JS file references
- Hard-coded sections: `{% section 'header' %}` and `{% section 'footer' %}`
- Body classes for page-type targeting

### password.liquid
Separate layout for password-protected store pages. Minimal styling, no navigation.

---

## TEMPLATES (.json)

### What Templates Do
- Define which sections appear on each page type
- Store section order, settings, and block configurations
- JSON format -- NOT HTML code

### Standard Template Types
| Template | URL Pattern | Purpose |
|----------|-------------|---------|
| index | / | Homepage |
| product | /products/[handle] | Product detail page |
| collection | /collections/[handle] | Collection listing |
| blog | /blogs/[handle] | Blog listing |
| article | /blogs/[handle]/[article] | Blog post |
| page | /pages/[handle] | Static pages |
| cart | /cart | Shopping cart |
| 404 | (any bad URL) | Not found |
| search | /search | Search results |
| list-collections | /collections | All collections |

### Multiple Templates Per Type
- Create alternate templates in theme editor
- Example: "product.featured.json" for hero product pages
- Assign per page in Shopify admin

### Template JSON Structure
```json
{
  "sections": {
    "hero": {
      "type": "hero-banner",
      "settings": { "title": "Welcome" }
    },
    "featured": {
      "type": "featured-collection",
      "settings": { "collection": "best-sellers" }
    }
  },
  "order": ["hero", "featured"]
}
```

---

## SECTIONS (.liquid)

### Anatomy
```liquid
<!-- HTML with Liquid -->
<section id="section-{{ section.id }}">
  <h2>{{ section.settings.title }}</h2>

  {%- for block in section.blocks -%}
    <div {{ block.shopify_attributes }}>
      {{ block.settings.text }}
    </div>
  {%- endfor -%}
</section>

<!-- Scoped CSS -->
{% style %}
#section-{{ section.id }} {
  padding: {{ section.settings.padding }}px 0;
}
{% endstyle %}

<!-- Schema -->
{% schema %}
{
  "name": "Section Name",
  "settings": [...],
  "blocks": [...],
  "presets": [...]
}
{% endschema %}
```

### Hard-Coded vs. Dynamic Sections
- **Hard-coded:** Referenced in layout file (`{% section 'header' %}`). Present on every page. Cannot be removed via editor
- **Dynamic:** Added via theme editor on JSON templates. Can be freely added, removed, reordered

### Block Attributes
Always add `{{ block.shopify_attributes }}` to block wrapper elements -- enables theme editor click-to-select functionality.

---

## SNIPPETS (.liquid)

### Rendering Snippets
```liquid
{% render 'product-card', product: product %}
```

### Common Snippets
| Snippet | Purpose |
|---------|---------|
| product-card | Product grid items across all pages |
| social-icons | Consistent social links |
| breadcrumbs | Navigation trail |
| pagination | Collection page navigation |
| price | Formatted pricing with sale logic |
| badge | Product badges (sale, new, sold out) |

### Variable Passing
```liquid
{% render 'product-card',
  product: product,
  show_badge: true,
  card_style: 'compact'
%}
```

---

## ASSETS FOLDER

- All CSS and JavaScript files
- Dawn (default theme) separates CSS into many individual files
- Most themes consolidate into fewer files
- Custom CSS can go here or in section `{% style %}` tags

---

## CONFIG FOLDER

### settings_schema.json
Defines the theme settings UI that appears in the theme editor. Controls which options merchants can customize (colors, typography, spacing, etc.).

### settings_data.json
Stores the actual selected values. Directly editable (useful for bulk changes). Changes here reflect in theme editor.

---

## LOCALES FOLDER

- Language translation files
- Two files per language: one for theme text, one for schema translations
- Used with the `| t` filter in Liquid
- Dawn uses translation keys (prefixed with `t:`) -- plain English also works

---

## ONLINE STORE 2.0 vs. VINTAGE

| Feature | Online Store 2.0 | Vintage |
|---------|-----------------|---------|
| Template format | .json | .liquid |
| Section flexibility | Add/remove on any page | Hard-coded per template |
| App blocks | Supported | Not supported |
| Metafields in editor | Dynamic source button | Requires code |
| Released | Mid-2021 | Pre-2021 |

### Identifying Theme Version
- Check templates folder: `.json` files = 2.0, `.liquid` files = vintage
- Theme store now only lists 2.0 themes
- Some clients may still be on vintage themes (requires different workflow)

---

## DATA PERSISTENCE

### Store Data (Survives Theme Changes)
- Product information and images
- Customer lists and orders
- Pages and blog posts
- Navigation menus
- Files, fonts, uploaded images
- Domain settings

### Theme Data (Lost on Theme Change)
- Customizer settings
- Section layouts and blocks
- Page templates
- Code customizations
- Language overrides
- Theme editor-uploaded images

### Exportable Data
- Theme files (download as .zip)
- Product list (CSV)
- Customer list (CSV)

### Practical Implications
- Store data changes affect ALL themes (including published)
- Always duplicate theme before major changes
- Version naming: "Brand 1.0", "Brand 1.1", "Brand 2.0"
- Import a theme to another store: store data won't transfer
