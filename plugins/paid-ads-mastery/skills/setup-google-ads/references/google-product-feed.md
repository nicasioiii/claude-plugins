---
name: "Google Product Feed Optimization"
description: "Required and optional feed attributes, SEO title creation, image selection strategy, product description template, feed optimization process, custom labels."
---

# Google Product Feed Optimization

## Feed Attribute Reference

### Required Attributes
| Attribute | Max Length | Notes |
|---|---|---|
| id | 50 chars | Unique product identifier, never change once set |
| title | 150 chars | Most important attribute for Shopping (see SEO Title section) |
| description | 5,000 chars | Use keywords naturally, front-load important info |
| link | - | Product page URL, must work and match product |
| image_link | - | Main product image URL, min 100x100px, ideally 800x800+ |
| price | - | Must match website price exactly (Google checks) |
| availability | - | in_stock, out_of_stock, or preorder |
| brand | 70 chars | Required for branded products, use store name for unbranded |
| gtin | - | Required if product has a UPC/EAN/ISBN |
| condition | - | new, refurbished, or used |
| google_product_category | - | Use Google's taxonomy, be as specific as possible |

### Recommended Attributes (High Impact)
| Attribute | Impact | Notes |
|---|---|---|
| additional_image_link | High | Up to 10 additional images |
| sale_price | High | Shows strikethrough pricing in Shopping ads |
| product_type | Medium | Your own categorization (different from Google category) |
| custom_label_0 through 4 | High | For campaign segmentation (margin, bestseller, season) |
| shipping | Medium | Product-level shipping overrides |
| color | Medium | Required for apparel, helpful for all products |
| size | Medium | Required for apparel |
| material | Low | Helps with long-tail keyword matching |
| age_group | Low | Required for apparel |
| gender | Low | Required for apparel |

---

## SEO Title Creation Process

### The Core Principle
Google Shopping titles are the #1 factor determining which searches your product appears for. Treat titles like SEO optimization, not marketing copy.

### Step-by-Step Process
1. **List all relevant keywords** from Google Keyword Planner
2. **Rank keywords by monthly search volume** (highest first)
3. **Place highest-volume keyword first** in title (left-to-right importance)
4. **Add secondary keywords** that naturally fit
5. **Include differentiating attributes:** material, color, size, use case

### Title Formulas by Category
- **General:** [Primary Keyword] [Material/Feature] [Secondary Keyword] [Use Case]
- **Apparel:** [Product Type] [Material] [Color] [Size] for [Gender/Use]
- **Electronics:** [Brand] [Product Type] [Key Spec] [Model]
- **Home:** [Product Type] [Material] [Key Feature] [Room/Use]

### Title Rules
- Never stuff keywords unnaturally
- Never use ALL CAPS
- Never include promotional text ("Free Shipping", "Best Price", "Sale")
- Never include store name in title (waste of character space)
- Each keyword appears max 3x across title + description combined
- Aim for 80-120 characters (Google shows ~70 in Shopping, full title used for matching)

### Title Examples
**Bad:** "Amazing Blue Storage Container Box Organizer Free Shipping Best Deal"
**Good:** "Large Storage Container with Lid - Stackable Plastic Organizer Bin for Garage"

**Bad:** "Dog Bed"
**Good:** "Orthopedic Dog Bed Large Breeds - Waterproof Memory Foam Pet Bed with Removable Cover"

---

## Product Image Selection Strategy

### The Contrarian Rule
Do the OPPOSITE of what competitors show. If all competitors use white-background product shots, use lifestyle images. If all use lifestyle, use clean white-background shots.

### Image Priority (Main Image)
1. Clean product shot on white/neutral background (safest for Merchant Center approval)
2. Lifestyle image showing product in use (better CTR once approved)
3. Product with scale reference (helps for items where size matters)

### Image Optimization
- Minimum 800x800 pixels (1200x1200+ preferred)
- Square format (1:1 ratio) for consistent Shopping display
- No text, watermarks, or promotional overlays on main image
- Fill 75-90% of frame with the product
- Consistent lighting across all product images
- Additional images: in-use, detail shots, packaging, scale reference

---

## Product Description Template

### Structure
```
[Opening sentence addressing primary pain point or use case]

[2-3 sentences about key features and benefits - use keywords naturally]

Key Features:
- [Feature 1] - [Benefit]
- [Feature 2] - [Benefit]
- [Feature 3] - [Benefit]
- [Feature 4] - [Benefit]

[1-2 sentences about materials/specifications]

[Closing sentence with use case or guarantee]
```

### Description Rules
- 50-200 words (longer descriptions rank better but must be natural)
- Front-load the most important keywords and benefits
- Use customer language from reviews (not marketing jargon)
- Include emotional triggers AND specifications
- Never copy from any other website (Google checks word-for-word)
- Each keyword from your list appears max 3x in description

---

## Custom Labels Strategy

### What Custom Labels Do
Custom labels (0-4) let you segment products in campaigns without changing the feed structure. Essential for campaign architecture.

### Recommended Label Schema
| Label | Segmentation | Values Example |
|---|---|---|
| custom_label_0 | Margin tier | high_margin, medium_margin, low_margin |
| custom_label_1 | Performance tier | bestseller, steady, underperformer, new |
| custom_label_2 | Price tier | under_25, 25_to_50, 50_to_100, over_100 |
| custom_label_3 | Season | evergreen, spring, summer, fall, winter |
| custom_label_4 | Category | your_category_names |

### Using Labels in Campaigns
- Create separate Shopping campaigns by performance tier (bestsellers get more budget)
- Separate campaigns by margin tier (high-margin products can bid more aggressively)
- Seasonal campaigns: only include products labeled for current season
- New product campaigns: isolate new products for testing before mainlining

---

## Feed Optimization Process

### Weekly Tasks
1. Check Merchant Center Diagnostics for any flagged products
2. Fix disapproved products immediately (they hurt account health)
3. Update pricing if it's changed on website (mismatch = disapproval)
4. Update availability for out-of-stock products

### Monthly Tasks
1. Review title performance: Which products get impressions but low clicks? Rewrite titles.
2. Review image performance: Swap main images on low-CTR products
3. Add new products with optimized titles and descriptions
4. Update custom labels based on last 30 days of performance data
5. Check for new keywords in Keyword Planner to incorporate into titles

### Quarterly Tasks
1. Full feed audit: every product reviewed for title, description, image quality
2. Custom label refresh based on seasonal changes
3. Competitor analysis: check competitor Shopping ads for title/image patterns
4. Feed enrichment: add missing recommended attributes
