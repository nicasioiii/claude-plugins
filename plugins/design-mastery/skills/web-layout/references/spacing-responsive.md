# Spacing, Images & Responsive Behavior

## Section Spacing & Rhythm

### Vertical Spacing System

**Standard Spacing Between Sections:**

| Spacing Level | Size | Use Case |
|--------------|------|----------|
| **Small** | 40-60px | Between elements within section |
| **Medium** | 60-100px | Between most sections |
| **Large** | 100-160px | Between major sections |
| **Hero gap** | 60-80px | Between hero and next section |

**Application:**
```
Hero section
[80px gap]
Feature section
[100px gap]
Testimonial section
[100px gap]
CTA section
[80px gap]
Footer
```

### Why Consistent Spacing Matters

**Cramped Layout (20px gaps):**
- Feels cheap and claustrophobic
- Hard to scan
- Lacks breathing room

**Spacious Layout (100px gaps):**
- Feels premium and luxurious
- Easy to scan
- Professional appearance

### Half-Padding Technique

**Problem:** Doubling up: Section A padding-bottom (64px) + Section B padding-top (64px) = 128px gap

**Solution:** One section has 128px padding, the other has 0

```
Hero section: padding-bottom 128px, padding-top 0
Feature section: padding-bottom 0, padding-top 128px
Result: 128px gap (not 256px)

Alternative (modern):
Use CSS `gap` property on flex container
Hero container: padding-bottom 64px
Feature container: padding-top 64px
```

## Responsive Image Handling

### Image Aspect Ratios

| Type | Ratio | Desktop | Use Case |
|------|-------|---------|----------|
| **Hero image** | 16:9 | 1440×810px | Full-width background |
| **Feature image** | 3:2 | 600×400px | Product/feature card |
| **Square card** | 1:1 | 300×300px | Avatar, icon, product |
| **Portrait** | 3:4 | 300×400px | Person photo |
| **Wide** | 3:1 | 900×300px | Landscape, banners |

### Object-fit Strategy

**Apply to all images:**
```css
img {
  object-fit: cover;     /* Crops to fill container */
  /* OR */
  object-fit: contain;   /* Fits entire image (no crop) */
}
```

**When to use:**
- **cover:** Product photos, hero images (crop acceptable)
- **contain:** Logos, icons, diagrams (no crop, shows full image)

### Responsive Image Sizing

**Desktop:**
```
Full-width hero: 100% viewport width
Featured image: 400-600px width
Grid images: 300px width (3-column)
```

**Mobile:**
```
Full-width hero: 100% viewport width
Featured image: 100% viewport width
Grid images: 100% width (1-column, stacked)
```

## Breakpoint-Specific Behaviors

### Desktop (1440px)

- Container: 1200px max-width, centered
- Sidebar: 250px visible (dashboards)
- Grid: 3-4 columns possible
- Typography: Full sizes (headlines 40-60px)
- Images: High resolution, detailed
- Spacing: Full 80-128px gaps

### Tablet (800px)

- Container: 100% width, 32px side padding
- Sidebar: Hamburger menu
- Grid: 2 columns
- Typography: Medium sizes (headlines 32-48px)
- Images: Medium quality
- Spacing: Reduced 60-80px gaps

### Mobile (390px)

- Container: 100% width, 16px side padding
- Sidebar: Full-screen when open
- Grid: 1 column (stacked)
- Typography: Smaller (headlines 24-32px)
- Images: Optimized for mobile
- Spacing: Compact 40-60px gaps
