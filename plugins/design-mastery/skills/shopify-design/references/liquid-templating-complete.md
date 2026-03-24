# Liquid Templating: Complete Guide with Real Examples

This reference provides comprehensive Liquid syntax and patterns for Shopify theme development.

---

## LIQUID FUNDAMENTALS

### Three Types of Liquid Syntax

#### 1. Output Tags (Display Values)

```liquid
{{ variable }}
{{ product.title }}
{{ section.settings.heading }}
{{ product.price | money }}
```

**Rules:**
- Double curly braces `{{ }}`
- Outputs the value directly to HTML
- Can use filters to transform output

#### 2. Logic Tags (Control Flow)

```liquid
{% if product.available %}
  <p>In stock</p>
{% endif %}

{% for product in collection.products %}
  <h3>{{ product.title }}</h3>
{% endfor %}

{% unless product.available %}
  <p>Out of stock</p>
{% endunless %}
```

**Rules:**
- Curly brace + percent `{% %}`
- Don't output anything themselves
- Control how page renders
- Always close with `{% endif %}`, `{% endfor %}`, etc.

#### 3. Comment Tags (Non-displayed Notes)

```liquid
{% comment %}
This is a comment that doesn't appear in HTML
{% endcomment %}

{# Short comment syntax #}
```

---

## ESSENTIAL SHOPIFY VARIABLES

### Product Variables

```liquid
{{ product.id }}              → Product ID (e.g., 12345678)
{{ product.title }}           → "Blue Cotton T-Shirt"
{{ product.description }}     → Full product description (HTML)
{{ product.price }}           → 2999 (in cents)
{{ product.price | money }}   → "$29.99"
{{ product.compare_at_price | money }} → "$39.99" (original price)
{{ product.available }}       → true/false
{{ product.handle }}          → URL-friendly name
{{ product.url }}             → /products/blue-tshirt
{{ product.featured_image }} → Image object
{{ product.created_at }}      → Product creation date
{{ product.options }}         → Size, color, etc.
{{ product.variants }}        → All product variants
{{ product.collections }}     → Collections this product is in
{{ product.vendor }}          → Manufacturer/brand
{{ product.tags }}            → Array of product tags
```

### Collection Variables

```liquid
{{ collection.id }}           → Collection ID
{{ collection.title }}        → Collection name
{{ collection.description }}  → Collection description
{{ collection.handle }}       → URL-friendly slug
{{ collection.url }}          → /collections/shoes
{{ collection.image }}        → Collection image
{{ collection.products }}     → Array of products in collection
{{ collection.products_count }} → Number of products
```

### Shop Variables

```liquid
{{ shop.name }}               → "My Store"
{{ shop.currency }}           → "USD"
{{ shop.money_format }}       → Format string for money
{{ shop.email }}              → Shop support email
{{ shop.phone }}              → Shop phone number
{{ shop.description }}        → Shop description
{{ shop.url }}                → Shop domain URL
```

### Cart Variables

```liquid
{{ cart.items }}              → Array of items in cart
{{ cart.item_count }}         → Number of items
{{ cart.total_price }}        → Total price in cents
{{ cart.total_price | money }}→ "$99.99"
{{ cart.empty? }}             → true if no items
```

---

## FILTERS (Transform Output)

### Money Filters

```liquid
{{ 2999 | money }}            → "$29.99"
{{ product.price | money }}   → "$29.99"
{{ product.price | money_with_currency }} → "$29.99 USD"
{{ product.price | money_without_currency }} → "29.99"
```

### String Filters

```liquid
{{ "hello world" | capitalize }}           → "Hello world"
{{ "HELLO" | downcase }}                   → "hello"
{{ "hello" | upcase }}                     → "HELLO"
{{ "hello world" | replace: "world", "universe" }} → "hello universe"
{{ "hello" | prepend: "say " }}            → "say hello"
{{ "hello" | append: " world" }}           → "hello world"
{{ "hello world" | split: " " }}           → ["hello", "world"]
{{ "hello world" | size }}                 → 11
{{ "the quick brown fox" | truncate: 10 }} → "the quick..."
{{ "hello" | remove: "l" }}                → "heo"
{{ "HELLO" | lstrip }}                     → "HELLO" (left trim)
```

### Image Filters

```liquid
{{ image | image_url: width: 300 }}
→ https://cdn.shopify.com/s/files/1/...&width=300

{{ image | image_url: width: 300, height: 300 }}
→ Square image URL

{{ image | img_tag }}
→ <img src="..." alt="..." />

{{ image | img_tag: alt: "Custom alt text" }}
→ <img src="..." alt="Custom alt text" />

{{ product.featured_image | image_url: width: 600 }}
→ Shopify-hosted image at 600px width
```

### Array Filters

```liquid
{{ array | join: ", " }}      → Join array with delimiter
{{ array | first }}            → First item
{{ array | last }}             → Last item
{{ array | size }}             → Length of array
{{ array | map: "title" }}     → Extract property from each item
```

### Date Filters

```liquid
{{ "now" | date: "%Y-%m-%d" }}           → "2026-03-12"
{{ "now" | date: "%B %d, %Y" }}          → "March 12, 2026"
{{ product.created_at | date: "%A" }}    → "Wednesday"
{{ product.created_at | date: "%I:%M %p" }} → "02:30 PM"
```

### URL Filters

```liquid
{{ "hello world" | url_param_escape }}   → "hello%20world"
{{ text | url_encode }}                   → URL-safe string
{{ product.url | link_to: product.title }} → <a href="...">title</a>
```

---

## CONTROL FLOW LOGIC

### If/Elsif/Else

```liquid
{% if product.available %}
  <p>In Stock</p>
{% elsif product.coming_soon %}
  <p>Coming Soon</p>
{% else %}
  <p>Out of Stock</p>
{% endif %}
```

### Unless (Inverse of If)

```liquid
{% unless product.available %}
  <p>This product is out of stock</p>
{% endunless %}

<!-- Equivalent to: -->
{% if product.available == false %}
  <p>This product is out of stock</p>
{% endif %}
```

### Logical Operators

```liquid
{% if product.available and product.price < 100 %}
  <p>In stock and under $100</p>
{% endif %}

{% if product.price > 100 or product.rating > 4 %}
  <p>Premium or highly rated</p>
{% endif %}

{% if product.tags contains "sale" %}
  <p>On sale!</p>
{% endif %}

{% unless product.available or product.coming_soon %}
  <p>Not available</p>
{% endunless %}
```

### Case Statements

```liquid
{% case product.vendor %}
  {% when "Nike" %}
    <p>Premium athletic brand</p>
  {% when "Adidas" %}
    <p>Classic sportswear</p>
  {% else %}
    <p>Other brand</p>
{% endcase %}
```

---

## LOOPS

### For Loops

```liquid
{% for product in collection.products %}
  <h3>{{ product.title }}</h3>
  <p>{{ product.price | money }}</p>
{% endfor %}
```

### For Loop with Limit

```liquid
{% for product in collection.products limit: 4 %}
  <h3>{{ product.title }}</h3>
{% endfor %}
<!-- Shows only first 4 products -->
```

### For Loop with Offset

```liquid
{% for product in collection.products offset: 4 limit: 4 %}
  <h3>{{ product.title }}</h3>
{% endfor %}
<!-- Shows products 5-8 (skip first 4) -->
```

### For Loop with Reversed

```liquid
{% for product in collection.products reversed %}
  <h3>{{ product.title }}</h3>
{% endfor %}
<!-- Shows products in reverse order -->
```

### For Loop with Counter (forloop)

```liquid
{% for product in collection.products %}
  <div class="item">
    <span class="number">{{ forloop.index }}</span>
    <!-- 1, 2, 3... -->
    <h3>{{ product.title }}</h3>
  </div>
{% endfor %}
```

**forloop variables:**
- `{{ forloop.index }}` — Current iteration (1-based)
- `{{ forloop.index0 }}` — Current iteration (0-based)
- `{{ forloop.length }}` — Total iterations
- `{{ forloop.first }}` — true on first iteration
- `{{ forloop.last }}` — true on last iteration
- `{{ forloop.rindex }}` — Reverse index (from end)
- `{{ forloop.rindex0 }}` — Reverse index (0-based)

### Practical Example: Alternating Classes

```liquid
<div class="product-grid">
  {% for product in collection.products %}
    <div class="product-card {% if forloop.index is odd %}odd{% else %}even{% endif %}">
      <h3>{{ product.title }}</h3>
    </div>
  {% endfor %}
</div>

<!-- Creates: odd, even, odd, even... -->
```

### Break and Continue

```liquid
{% for product in collection.products %}
  {% if product.price > 100 %}
    {% break %}
    <!-- Stops loop -->
  {% endif %}
  <h3>{{ product.title }}</h3>
{% endfor %}

{% for i in (1..10) %}
  {% if i == 5 %}
    {% continue %}
    <!-- Skips this iteration -->
  {% endif %}
  <p>{{ i }}</p>
{% endfor %}
```

---

## ASSIGN & CAPTURE

### Assign (Store Simple Values)

```liquid
{% assign product_price = product.price | money %}
<p>Price: {{ product_price }}</p>

{% assign collection_title = collection.title %}
<h1>{{ collection_title }}</h1>

{% assign items_in_cart = cart.item_count %}
<span>Cart ({{ items_in_cart }})</span>
```

### Capture (Store Complex Output)

```liquid
{% capture product_description %}
  <h3>{{ product.title }}</h3>
  <p>{{ product.description }}</p>
  <p>{{ product.price | money }}</p>
{% endcapture %}

<div class="product-info">
  {{ product_description }}
</div>
```

---

## INCLUDES & RENDERS (Reusable Components)

### Render (Preferred Method)

```liquid
<!-- In any template or section -->
{% render 'product-card', product: product %}

<!-- In product-card.liquid snippet -->
<div class="product-card">
  <h3>{{ product.title }}</h3>
  <p>{{ product.price | money }}</p>
</div>
```

### Pass Multiple Variables

```liquid
{% render 'product-card',
  product: product,
  show_price: true,
  show_rating: false
%}

<!-- In snippet: -->
<div class="product-card">
  <h3>{{ product.title }}</h3>
  {% if show_price %}
    <p>{{ product.price | money }}</p>
  {% endif %}
</div>
```

### Looping with Renders

```liquid
{% for product in collection.products %}
  {% render 'product-card', product: product %}
{% endfor %}

<!-- Better performance than including snippet in loop -->
```

---

## SHOPIFY-SPECIFIC PATTERNS

### Product Variant Selection

```liquid
<div class="variants">
  {% for option in product.options_with_values %}
    <div class="option">
      <label>{{ option.name }}</label>
      {% case option.name %}
        {% when "Size" %}
          <select name="properties[{{ option.name }}]">
            {% for value in option.values %}
              <option value="{{ value }}">{{ value }}</option>
            {% endfor %}
          </select>
        {% when "Color" %}
          <div class="color-selector">
            {% for value in option.values %}
              <div class="color"
                   data-color="{{ value }}"
                   style="background-color: {{ value }};">
              </div>
            {% endfor %}
          </div>
      {% endcase %}
    </div>
  {% endfor %}
</div>
```

### Conditional Pricing Display

```liquid
{% if product.compare_at_price %}
  <!-- On sale -->
  <div class="sale-price">
    <span class="original">{{ product.compare_at_price | money }}</span>
    <span class="sale">{{ product.price | money }}</span>
    <span class="discount">
      Save {{ product.compare_at_price | minus: product.price | money }}
    </span>
  </div>
{% else %}
  <!-- Regular price -->
  <p class="price">{{ product.price | money }}</p>
{% endif %}
```

### Product Availability Badge

```liquid
<div class="availability">
  {% if product.available %}
    <span class="in-stock">In Stock</span>
  {% elsif product.coming_soon %}
    <span class="coming">Coming Soon</span>
  {% else %}
    <span class="out-stock">Out of Stock</span>
  {% endif %}
</div>
```

### Collection Product Count

```liquid
<h1>{{ collection.title }} ({{ collection.products_count }} items)</h1>

{% if collection.products_count == 0 %}
  <p>No products in this collection yet.</p>
{% elsif collection.products_count == 1 %}
  <p>1 product available</p>
{% else %}
  <p>{{ collection.products_count }} products available</p>
{% endif %}
```

### Pagination

```liquid
<div class="products">
  {% paginate collection.products by 12 %}
    {% for product in collection.products %}
      <div class="product">{{ product.title }}</div>
    {% endfor %}

    <div class="pagination">
      {{ paginate | default_pagination }}
    </div>
  {% endpaginate %}
</div>
```

### Customer Information (Logged In)

```liquid
{% if customer %}
  <p>Welcome back, {{ customer.first_name }}!</p>
  <p>You have {{ customer.orders_count }} orders</p>
  <p>{{ customer.email }}</p>
{% else %}
  <p>Please log in to see your account</p>
{% endif %}
```

---

## ADVANCED PATTERNS

### Map Filter (Extract Property)

```liquid
{% assign product_titles = collection.products | map: "title" %}
{{ product_titles | join: ", " }}
<!-- Outputs: "Product 1, Product 2, Product 3" -->
```

### Where Filter (Filter Array)

```liquid
{% assign available_products = collection.products | where: "available" %}
{% for product in available_products %}
  <h3>{{ product.title }}</h3>
{% endfor %}
<!-- Only shows available products -->
```

### Math Operations

```liquid
{% assign discount_price = product.price | minus: 500 %}
<!-- $29.99 - 5.00 = $24.99 -->

{% assign markup = product.cost | times: 2 %}
<!-- Double the cost -->

{% assign total = cart.total_price | divided_by: 100 | round: 2 %}
<!-- Convert cents to dollars with 2 decimals -->
```

### String Concatenation

```liquid
{% assign full_name = customer.first_name | append: " " | append: customer.last_name %}
<!-- "John Doe" -->
```

### Conditional Class Application

```liquid
<div class="product {% if product.on_sale %}sale{% endif %} {% if product.featured %}featured{% endif %}">
  {{ product.title }}
</div>

<!-- Alternative: -->
<div class="product {% if product.price > 100 %}premium{% elsif product.price > 50 %}standard{% else %}budget{% endif %}">
  {{ product.title }}
</div>
```

---

## DEBUGGING & TIPS

### Inspect Variables

```liquid
<!-- View what's in a variable -->
{% assign test = product | inspect %}
<pre>{{ test }}</pre>

<!-- Or simpler: -->
<pre>{{ product }}</pre>
```

### Check Variable Existence

```liquid
{% if product %}
  <p>Product exists</p>
{% endif %}

{% if product.reviews %}
  <p>Has reviews</p>
{% else %}
  <p>No reviews yet</p>
{% endif %}
```

### Check Array Is Empty

```liquid
{% if product.reviews.size > 0 %}
  <div class="reviews">
    {% for review in product.reviews %}
      {{ review.text }}
    {% endfor %}
  </div>
{% else %}
  <p>No reviews yet. Be the first!</p>
{% endif %}
```

### Common Shopify Liquid Mistakes

| Mistake | Problem | Fix |
|---|---|---|
| `{{ product.price }}` outputs 2999 | Price in cents | Use `\| money` filter |
| Loop doesn't work | Using wrong variable name | Check exact variable name (case-sensitive) |
| Settings not changing in editor | Typo in setting ID | Match ID exactly in schema |
| Render doesn't work | Typo in snippet name | Check exact filename in /snippets/ |
| Image doesn't show | Missing width parameter | Use `\| image_url: width: 300` |

---

## Summary: Essential Liquid for E-Commerce

**Master these patterns and you can build most Shopify themes:**

1. Output variables with filters: `{{ product.price | money }}`
2. Loop through products: `{% for product in collection.products %}`
3. Conditionals: `{% if product.available %}`
4. Render snippets: `{% render 'product-card', product: product %}`
5. Access product/collection data
6. Apply filters to transform output
7. Use forloop for counters/classes

That's 80% of what you need to know for Shopify theme customization.
