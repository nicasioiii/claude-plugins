---
name: Shopify Store
description: Design and build a Shopify store. Covers platform selection, theme architecture, Liquid templating, custom sections, product pages, conversion optimization, and launch workflow.
skill: shopify-ecommerce
---

# /shopify-store

You are helping the user design and build a Shopify store. Follow this workflow:

## Step 1: Validate Platform Choice

Ask the user:
1. **Will selling products make up more than 60% of website content?** (if yes, Shopify is right)
2. **How many products/SKUs?** (now and in 12 months)
3. **Do they sell in person?** (POS needs)
4. **Do they sell internationally?**
5. **What is the budget?** (Shopify plan level)
6. **Is blogging critical?** (if yes, consider hybrid strategy)

If less than 60% e-commerce, recommend the Shopify Lite hybrid strategy (Squarespace/Webflow + Shopify Lite backend).

Reference `01-platform-selection.md` for the full decision framework.

## Step 2: Choose and Set Up Theme

1. Select theme based on product count, layout needs, and customization level
2. Set up development store (Shopify Partner account for unlimited free dev stores)
3. Configure global theme settings: colors, fonts, logo, favicon
4. Set up navigation structure (main menu, footer menu)

## Step 3: Design Key Pages

### Product Detail Page (PDP)
- Hero: large product image gallery with zoom
- Product info: title, price, variant selector, add-to-cart button
- Description with structured content blocks
- Social proof: reviews, ratings
- Related products or upsells

### Collection Pages
- Grid layout with filtering and sorting
- Consistent card design across all products
- Clear category navigation

### Homepage
- Hero with primary value proposition
- Featured collections or categories
- Social proof (testimonials, press logos, stats)
- Brand story section

## Step 4: Custom Sections (Liquid)

For custom sections, define:
1. Section schema (JSON block defining settings and blocks)
2. Liquid template markup (HTML + Liquid tags)
3. Section-specific CSS (scoped to avoid conflicts)
4. Merchant-editable settings (text, images, colors, toggles)

Key Liquid patterns:
- `{{ section.settings.heading }}` for editable text
- `{% for block in section.blocks %}` for repeatable content
- `{{ block.settings.image | image_url: width: 800 }}` for responsive images

## Step 5: Set Up Metafields

Use metafields for structured product data beyond default fields:
- Custom product specifications
- Size guides
- Material information
- Care instructions
- Related content references

## Step 6: Mobile Optimization

- Sticky add-to-cart on product pages
- Thumb-friendly navigation (bottom-anchored on mobile)
- Optimized image loading (responsive images, lazy loading)
- Simplified checkout flow
- Touch-friendly variant selectors

## Step 7: Launch Checklist

Pre-launch verification:
- All products have images, descriptions, and prices
- Payment gateway configured and tested
- Shipping rates and zones set up
- Tax settings verified
- Email notifications customized
- SEO: meta titles, descriptions, alt text on images
- Analytics installed (Google Analytics, Facebook Pixel)
- Test complete purchase flow including checkout
- Legal pages: privacy policy, terms, refund policy

## Step 8: Recommend Next Steps

- If brand direction is unclear → recommend `/mood-board`
- If design needs review → recommend `/design-audit`
- If responsive issues → recommend `/responsive-check`

## Skills Activated

- **shopify-ecommerce** (primary)
- Cross-references: web-layout, ui-components, discovery-direction
