# Custom Sections with JSON Schema: Complete Reference

## Section Schema Basics

**Schema defines what settings appear in Shopify editor**

**Basic schema structure:**

```json
{% schema %}
{
  "name": "Section Name",
  "settings": [
    {
      "type": "text",
      "id": "unique_id",
      "label": "Label that appears in editor",
      "default": "Default value"
    }
  ]
}
{% endschema %}
```

## Common Setting Types

| Type | Purpose | Example |
|---|---|---|
| `text` | Single line text | Heading, product title |
| `textarea` | Multi-line text | Description, body copy |
| `richtext` | Rich text editor | Formatted paragraphs, links |
| `image_picker` | Choose image from library | Hero image, section background |
| `url` | Link input | Button destination, external link |
| `color` | Color picker | Background color, text color |
| `range` | Number slider | Padding, width, gap |
| `select` | Dropdown menu | Layout option, alignment |
| `checkbox` | Boolean toggle | Show/hide feature |
| `product` | Pick a product | Featured product selector |
| `collection` | Pick a collection | Collection display |
| `page` | Pick a page | Link to page |

## Complete Section Schema Example

```liquid
{% schema %}
{
  "name": "Hero Section",
  "settings": [
    {
      "type": "image_picker",
      "id": "hero_image",
      "label": "Background Image",
      "info": "1920x600px recommended"
    },
    {
      "type": "text",
      "id": "heading",
      "label": "Heading Text",
      "default": "Welcome to Our Store"
    },
    {
      "type": "textarea",
      "id": "subheading",
      "label": "Subheading",
      "default": "Shop our collection"
    },
    {
      "type": "text",
      "id": "button_text",
      "label": "Button Text",
      "default": "Shop Now"
    },
    {
      "type": "url",
      "id": "button_url",
      "label": "Button Link"
    },
    {
      "type": "color",
      "id": "text_color",
      "label": "Text Color",
      "default": "#ffffff"
    },
    {
      "type": "color",
      "id": "button_color",
      "label": "Button Color",
      "default": "#000000"
    },
    {
      "type": "range",
      "id": "height",
      "label": "Hero Height",
      "min": 200,
      "max": 800,
      "default": 400,
      "unit": "px"
    },
    {
      "type": "select",
      "id": "text_alignment",
      "label": "Text Alignment",
      "options": [
        {
          "value": "left",
          "label": "Left"
        },
        {
          "value": "center",
          "label": "Center"
        },
        {
          "value": "right",
          "label": "Right"
        }
      ],
      "default": "center"
    }
  ]
}
{% endschema %}
```

## Using Schema Settings in Liquid

**Reference settings with `section.settings.setting_id`:**

```liquid
<div class="hero"
     style="
       height: {{ section.settings.height }}px;
       background-image: url('{{ section.settings.hero_image | image_url: width: 1920 }}');
       color: {{ section.settings.text_color }};
       text-align: {{ section.settings.text_alignment }};
     "
>
  <h1>{{ section.settings.heading }}</h1>
  <p>{{ section.settings.subheading }}</p>
  <a
    href="{{ section.settings.button_url }}"
    class="button"
    style="background-color: {{ section.settings.button_color }};"
  >
    {{ section.settings.button_text }}
  </a>
</div>
```

## Block Structure Example

**Structure of a section file with blocks:**

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
