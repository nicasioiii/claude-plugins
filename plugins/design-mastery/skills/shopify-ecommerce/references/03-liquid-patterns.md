---
name: Liquid Patterns & Custom Section Code
description: "Liquid fundamentals, output/logic syntax, essential filters, section schema anatomy, custom section starter code templates."
---

# Liquid Patterns & Custom Section Code

Practical Liquid reference with starter code for custom Shopify sections.

---

## LIQUID FUNDAMENTALS

### Output Tags `{{ }}`
Display information from Shopify data:
```liquid
{{ product.title }}
{{ product.price | money_with_currency }}
{{ shop.name }}
{{ article.author }}
```

### Logic Tags `{% %}`
Control flow and logic:
```liquid
{% if product.available %}
  <button>Add to Cart</button>
{% else %}
  <button disabled>Sold Out</button>
{% endif %}
```

### Dot Syntax
Objects have properties accessed via dots:
```liquid
{{ product.title }}           → "Blue Widget"
{{ product.price }}           → 1999 (in cents)
{{ product.images.first }}    → first image object
{{ product.vendor }}          → "Acme Co"
```

### Object Scope
| Scope | Objects | Available In |
|-------|---------|-------------|
| Global | shop, settings, request, routes, all_products | Any .liquid file |
| Template | product, collection, article, blog, page | Matching template only |
| Section | section.settings, section.blocks | Within section file |
| Block | block.settings, block.type, block.id | Inside block loop |

---

## ESSENTIAL FILTERS

### Text Filters
```liquid
{{ "hello world" | upcase }}              → "HELLO WORLD"
{{ "Hello World" | downcase }}            → "hello world"
{{ "hello world" | capitalize }}          → "Hello world"
{{ product.title | truncate: 50 }}        → "Blue Widget..." (if longer)
{{ product.title | escape }}              → HTML-safe text
{{ product.description | strip_html }}    → Remove all HTML tags
{{ product.title | newline_to_br }}       → Enable line breaks
```

### Money Filters
```liquid
{{ product.price | money }}                    → $19.99
{{ product.price | money_with_currency }}      → $19.99 USD
{{ product.price | money_without_currency }}   → 19.99
```

### Image Filters
```liquid
{{ product.featured_image | image_url: width: 400 }}
{{ product.featured_image | image_url: width: 800, height: 800, crop: 'center' }}
{{ product.featured_image | image_tag }}
```

**Important:** `image_url` controls LOAD size (bandwidth). CSS controls DISPLAY size.

### Translation Filter
```liquid
{{ 'general.search.title' | t }}  → Looks up translation in locale file
```

### Date Filters
```liquid
{{ article.published_at | date: "%B %d, %Y" }}  → "March 24, 2026"
```

---

## CONTROL FLOW

### Conditionals
```liquid
{% if product.available %}
  In Stock
{% elsif product.compare_at_price %}
  On Sale
{% else %}
  Sold Out
{% endif %}

{% unless product.title == blank %}
  {{ product.title }}
{% endunless %}
```

### Loops
```liquid
{% for product in collection.products %}
  {% render 'product-card', product: product %}
{% endfor %}

{% for block in section.blocks %}
  <div {{ block.shopify_attributes }}>
    {{ block.settings.text }}
  </div>
{% endfor %}
```

### Case / When
```liquid
{%- case block.type -%}
  {%- when 'heading' -%}
    <h2>{{ block.settings.heading }}</h2>
  {%- when 'text' -%}
    <div>{{ block.settings.text }}</div>
  {%- when 'button' -%}
    <a href="{{ block.settings.url }}">{{ block.settings.label }}</a>
{%- endcase -%}
```

### Assign
```liquid
{% assign title = section.settings.title %}
{% assign products = collection.products | limit: 4 %}
```

---

## WHITE SPACE CONTROL

Add hyphens to remove blank lines in output:
```liquid
{%- if condition -%}
  content
{%- endif -%}
```

Good practice to always use hyphens in production code.

---

## SECTION SCHEMA REFERENCE

### Setting Types
| Type | Purpose | Example |
|------|---------|---------|
| text | Single line text | Title, label |
| textarea | Multi-line text | Description |
| richtext | Rich text with formatting | Content blocks |
| image_picker | Image upload/selection | Hero image |
| url | URL input | Button link |
| select | Dropdown with options | Alignment choice |
| checkbox | Boolean toggle | Show/hide element |
| color | Color picker | Background color |
| color_scheme | Theme color scheme | Section theming |
| range | Numeric slider | Padding, opacity |
| number | Number input | Count, limit |
| product | Product picker | Featured product |
| collection | Collection picker | Featured collection |
| blog | Blog picker | Blog reference |
| page | Page picker | Page link |
| video_url | Video URL | YouTube/Vimeo embed |

### Setting Structure
```json
{
  "type": "text",
  "id": "title",
  "label": "Heading",
  "default": "Featured Products"
}
```

```json
{
  "type": "select",
  "id": "heading_size",
  "label": "Heading size",
  "options": [
    { "value": "h2", "label": "Medium" },
    { "value": "h1", "label": "Large" }
  ],
  "default": "h2"
}
```

```json
{
  "type": "range",
  "id": "padding_top",
  "label": "Top padding",
  "min": 0,
  "max": 100,
  "step": 4,
  "unit": "px",
  "default": 36
}
```

---

## CUSTOM SECTION TEMPLATES

### Section WITHOUT Blocks
```liquid
<section id="section-{{ section.id }}" class="custom-section">
  {%- if section.settings.title != blank -%}
    <h2>{{ section.settings.title }}</h2>
  {%- endif -%}
  {%- if section.settings.description != blank -%}
    <div class="rte">{{ section.settings.description }}</div>
  {%- endif -%}
</section>

{% style %}
#section-{{ section.id }} {
  padding: {{ section.settings.padding_top }}px 0 {{ section.settings.padding_bottom }}px;
}
{% endstyle %}

{% schema %}
{
  "name": "Custom Section",
  "settings": [
    { "id": "title", "type": "text", "label": "Heading", "default": "Section Title" },
    { "id": "description", "type": "richtext", "label": "Description", "default": "<p>Add your text here</p>" },
    { "id": "padding_top", "type": "range", "label": "Top padding", "min": 0, "max": 100, "step": 4, "unit": "px", "default": 36 },
    { "id": "padding_bottom", "type": "range", "label": "Bottom padding", "min": 0, "max": 100, "step": 4, "unit": "px", "default": 36 }
  ],
  "presets": [{ "name": "Custom Section", "category": "Custom" }]
}
{% endschema %}
```

### Section WITH Single Block Type
```liquid
<section id="section-{{ section.id }}" class="custom-grid">
  {%- if section.settings.title != blank -%}
    <h2>{{ section.settings.title }}</h2>
  {%- endif -%}

  <div class="grid">
    {%- for block in section.blocks -%}
      <div class="grid-item" id="block-{{ block.id }}" {{ block.shopify_attributes }}>
        {%- if block.settings.image != blank -%}
          <img src="{{ block.settings.image | image_url: width: 600 }}" alt="{{ block.settings.title }}">
        {%- endif -%}
        <h3>{{ block.settings.title }}</h3>
        <p>{{ block.settings.text }}</p>
      </div>
    {%- endfor -%}
  </div>
</section>

{% style %}
#section-{{ section.id }} .grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 24px;
}
{% endstyle %}

{% schema %}
{
  "name": "Feature Grid",
  "settings": [
    { "id": "title", "type": "text", "label": "Heading" }
  ],
  "blocks": [
    {
      "type": "item",
      "name": "Feature",
      "limit": 6,
      "settings": [
        { "id": "image", "type": "image_picker", "label": "Image" },
        { "id": "title", "type": "text", "label": "Title", "default": "Feature" },
        { "id": "text", "type": "textarea", "label": "Description", "default": "Describe this feature" }
      ]
    }
  ],
  "presets": [{
    "name": "Feature Grid",
    "category": "Custom",
    "blocks": [
      { "type": "item" },
      { "type": "item" },
      { "type": "item" }
    ]
  }]
}
{% endschema %}
```

### Section WITH Multiple Block Types
```liquid
<section id="section-{{ section.id }}" class="content-section">
  {%- for block in section.blocks -%}
    {%- case block.type -%}
      {%- when 'heading' -%}
        <h2 id="block-{{ block.id }}" {{ block.shopify_attributes }}>
          {{ block.settings.heading }}
        </h2>

      {%- when 'text' -%}
        <div id="block-{{ block.id }}" class="rte" {{ block.shopify_attributes }}>
          {{ block.settings.text }}
        </div>

      {%- when 'button' -%}
        <a id="block-{{ block.id }}" href="{{ block.settings.url }}" class="btn" {{ block.shopify_attributes }}>
          {{ block.settings.label }}
        </a>

      {%- when 'image' -%}
        <div id="block-{{ block.id }}" {{ block.shopify_attributes }}>
          <img src="{{ block.settings.image | image_url: width: 800 }}" alt="{{ block.settings.alt }}">
        </div>
    {%- endcase -%}
  {%- endfor -%}
</section>

{% schema %}
{
  "name": "Content Builder",
  "blocks": [
    {
      "type": "heading",
      "name": "Heading",
      "settings": [
        { "id": "heading", "type": "text", "label": "Heading text", "default": "Heading" }
      ]
    },
    {
      "type": "text",
      "name": "Text",
      "settings": [
        { "id": "text", "type": "richtext", "label": "Text content", "default": "<p>Add text here</p>" }
      ]
    },
    {
      "type": "button",
      "name": "Button",
      "limit": 2,
      "settings": [
        { "id": "label", "type": "text", "label": "Button label", "default": "Learn more" },
        { "id": "url", "type": "url", "label": "Button link" }
      ]
    },
    {
      "type": "image",
      "name": "Image",
      "settings": [
        { "id": "image", "type": "image_picker", "label": "Image" },
        { "id": "alt", "type": "text", "label": "Alt text" }
      ]
    }
  ],
  "presets": [{
    "name": "Content Builder",
    "category": "Custom",
    "blocks": [
      { "type": "heading" },
      { "type": "text" },
      { "type": "button" }
    ]
  }]
}
{% endschema %}
```

---

## KEY RESOURCES

- **Shopify Liquid Cheat Sheet:** Searchable database of all objects, filters, and tags (bookmark this)
- **Shopify Developer Documentation:** Full reference with examples
- **Dawn theme source:** Reference implementation of Online Store 2.0
