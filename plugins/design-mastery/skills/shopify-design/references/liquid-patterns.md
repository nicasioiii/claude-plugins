# Liquid Templating: Complete Patterns Reference

## Core Liquid Syntax

**Liquid has three types of syntax:**

1. **Output tags** — Display variables
```liquid
{{ product.title }}          <!-- Outputs: "Blue T-Shirt" -->
{{ product.price | money }}  <!-- Outputs: "$29.99" -->
```

2. **Logic tags** — Control flow (if/for/unless)
```liquid
{% if product.available %}
  <p>In Stock</p>
{% else %}
  <p>Out of Stock</p>
{% endif %}

{% for product in collection.products %}
  <h3>{{ product.title }}</h3>
{% endfor %}
```

3. **Filters** — Transform output
```liquid
{{ "hello" | capitalize }}        <!-- Outputs: "Hello" -->
{{ product.price | money }}       <!-- Outputs: "$29.99" -->
{{ product.created_at | date: "%B %d, %Y" }}  <!-- Outputs: "March 12, 2026" -->
```

## Essential Liquid Filters for E-Commerce

| Filter | Purpose | Example |
|---|---|---|
| `money` | Format price | `{{ product.price \| money }}` → `$29.99` |
| `image_url` | Generate image URLs | `{{ image \| image_url: width: 300 }}` |
| `img_tag` | Create `<img>` tags | `{{ image \| img_tag: alt: product.title }}` |
| `capitalize` | Capitalize first letter | `{{ "hello" \| capitalize }}` → `Hello` |
| `upcase` / `downcase` | Convert case | `{{ "Hello" \| upcase }}` → `HELLO` |
| `date` | Format dates | `{{ product.created_at \| date: "%B %d, %Y" }}` |
| `truncate` | Shorten text | `{{ product.description \| truncate: 100 }}` |
| `json` | Convert to JSON | `{{ product \| json }}` |
| `url_param_escape` | URL encode | `{{ text \| url_param_escape }}` |

## Common Liquid Patterns for E-Commerce

**Pattern 1: Loop through products**

```liquid
{% for product in collection.products %}
  <div class="product">
    <h3>{{ product.title }}</h3>
    <p>{{ product.price | money }}</p>
  </div>
{% endfor %}
```

**Pattern 2: Conditional availability**

```liquid
{% if product.available %}
  <button>Add to Cart</button>
{% else %}
  <p>Sold Out</p>
{% endif %}
```

**Pattern 3: Loop with counter/index**

```liquid
{% for product in collection.products limit: 4 %}
  <div class="product-card">
    <span class="number">{{ forloop.index }}</span>
    {{ product.title }}
  </div>
{% endfor %}
```

**Pattern 4: Section settings**

```liquid
<div class="hero" style="padding: {{ section.settings.padding }}px;">
  <h1>{{ section.settings.heading }}</h1>
  <p>{{ section.settings.description }}</p>
</div>
```

**Pattern 5: Block iteration**

```liquid
{% for block in section.blocks %}
  <div class="feature-item" {{ block.shopify_attributes }}>
    <h3>{{ block.settings.title }}</h3>
  </div>
{% endfor %}
```
