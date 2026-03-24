# Image Handling — Aspect Ratios, Object-Fit, and Responsive Images

## Aspect Ratio Fundamentals

### Common Aspect Ratios

| Ratio | Formula | Use Case | Dimensions |
|-------|---------|----------|-----------|
| **16:9** | Landscape | Hero images, video | 1440×810px (desktop) |
| **4:3** | Landscape | Feature images, cards | 600×450px (desktop) |
| **3:2** | Landscape | Blog thumbnails, gallery | 600×400px (desktop) |
| **1:1** | Square | Avatar, icon, product | 300×300px |
| **3:4** | Portrait | Person photo, mobile | 450×600px |
| **2:3** | Portrait | Book covers, tall photos | 400×600px |
| **9:16** | Portrait | Mobile stories | 360×640px |
| **3:1** | Ultra-wide | Hero banners | 900×300px |

### Aspect Ratio Calculation

```
Aspect ratio = Width ÷ Height

Example: 16:9 = 1.777
If width = 400px, then height = 400 ÷ 1.777 = 225px
If height = 200px, then width = 200 × 1.777 = 355px
```

---

## CSS Aspect Ratio

### Modern Approach: aspect-ratio Property

```css
.image-container {
  aspect-ratio: 16 / 9;  /* or 1.777 */
  width: 100%;
  height: auto;  /* Height calculated from width + ratio */
  overflow: hidden;
  background-color: #F0F0F0;  /* Placeholder while loading */
}

.image-container img {
  width: 100%;
  height: 100%;
  object-fit: cover;  /* Prevents distortion */
}
```

### Older Approach: Padding-Bottom Trick

```css
.image-container {
  position: relative;
  width: 100%;
  padding-bottom: 56.25%;  /* 16:9 = 56.25% */
  overflow: hidden;
}

.image-container img {
  position: absolute;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

---

## Object-Fit Behavior

### object-fit: cover (Most Common)

```css
img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

**Behavior:**
- Image fills container entirely
- Crops to fit aspect ratio
- No empty space
- Best for: Photos, backgrounds, hero images

**Example:** 300×300px container with 16:9 image
- Image scales to 300×169px
- Crops to 300×300px (5.5% off top/bottom)

### object-fit: contain

```css
img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}
```

**Behavior:**
- Entire image visible
- No cropping
- May have empty space (background color shows)
- Best for: Logos, icons, diagrams, full image display

**Example:** 300×300px container with 16:9 image
- Image scales to 300×169px
- Centered in container (65px space top/bottom)

### object-fit: fill

```css
img {
  object-fit: fill;
}
```

**Behavior:**
- Stretches to fill container
- No cropping, but distorts image
- **Rarely use** (causes stretching)

### object-fit: scale-down

```css
img {
  object-fit: scale-down;
}
```

**Behavior:**
- Smaller of contain or original image size
- Preserves aspect ratio
- Good for icons/logos that shouldn't stretch

---

## Responsive Image Sizes

### Hero Image Dimensions

**By Breakpoint:**

| Breakpoint | Width | Height | Aspect Ratio | File Size |
|-----------|-------|--------|----------|-----------|
| **Desktop** | 1440px | 810px | 16:9 | 150-300KB |
| **Tablet** | 800px | 450px | 16:9 | 80-150KB |
| **Mobile** | 390px | 220px | 16:9 | 40-80KB |

**Implementation (HTML):**
```html
<picture>
  <source media="(min-width: 1440px)" srcset="hero-desktop.jpg">
  <source media="(min-width: 800px)" srcset="hero-tablet.jpg">
  <img src="hero-mobile.jpg" alt="Hero image">
</picture>
```

### Feature Image Dimensions

| Context | Desktop | Tablet | Mobile |
|---------|---------|--------|--------|
| Card image (4:3) | 400×300px | 280×210px | 160×120px |
| Card image (3:2) | 400×267px | 280×187px | 160×107px |
| Card image (1:1) | 300×300px | 220×220px | 140×140px |

### Gallery Grid Sizing

**3-column desktop grid:**
```
Total width: 1312px (container max-width)
3 cards × 280px = 840px
Gutters: 2 × 24px = 48px
Total: 888px (fits in 1312px with 424px margin)
```

**Image in card (16:9):**
- Card: 280px wide
- Image: 280×158px (16:9 aspect)
- Padding below image: 16px
- Card height: 158 + 16 + text height

---

## Responsive Image Markup

### HTML Picture Element (Best)

```html
<picture>
  <source media="(min-width: 1440px)"
          srcset="large.jpg 1440w, large-2x.jpg 2880w">
  <source media="(min-width: 800px)"
          srcset="medium.jpg 800w, medium-2x.jpg 1600w">
  <img src="small.jpg" alt="Description"
       srcset="small-2x.jpg 2x">
</picture>
```

### Srcset (Width Descriptors)

```html
<img src="small.jpg"
     srcset="small.jpg 390w,
             medium.jpg 800w,
             large.jpg 1440w"
     sizes="(min-width: 1440px) 1312px,
            (min-width: 800px) 720px,
            100vw"
     alt="Description">
```

**Explanation:**
- `390w, 800w, 1440w`: Image sizes available
- `sizes`: How wide image displays at each breakpoint
- Browser selects best match for device

### Webp Format (Modern)

```html
<picture>
  <source type="image/webp" srcset="image.webp">
  <source type="image/jpeg" srcset="image.jpg">
  <img src="image.jpg" alt="Description">
</picture>
```

**Why Webp:** 25-35% smaller file size than JPEG

---

## Image Optimization Best Practices

### File Size Standards

| Image Type | Desktop | Mobile | Format |
|-----------|---------|--------|--------|
| **Hero** | 150-300KB | 40-80KB | WebP or JPEG |
| **Feature card** | 50-100KB | 20-40KB | WebP or JPEG |
| **Thumbnail** | 20-40KB | 10-20KB | WebP or JPEG |
| **Background** | 100-200KB | 40-80KB | WebP or JPEG |

### Compression Tools

**Online:**
- TinyPNG.com (PNG, WebP)
- Compress.com (all formats)
- Squoosh.app (Google, multiple formats)

**Tools:**
- ImageMagick (command-line)
- Figma export (built-in optimization)
- Webpack loaders (automated)

### Best Practices

1. **Export at 2x size for retina displays**
   - Desktop hero: Export at 2880×1620px
   - Mobile image: Export at 780px wide
   - Serve appropriately sized via srcset

2. **Use JPEGs for photos (smaller)**
   - Quality: 70-85% (good balance)
   - Progressive: Enable for better perceived load

3. **Use PNG for graphics with transparency**
   - Optimize with TinyPNG

4. **Use WebP for modern browsers**
   - 25% smaller than JPEG
   - Provide JPEG fallback

5. **Lazy load below-the-fold images**
   ```html
   <img src="image.jpg" loading="lazy">
   ```

---

## Image Aspect Ratio Decision Table

**Choose aspect ratio based on:**

| Content | Ratio | Why |
|---------|-------|-----|
| **Hero/banner** | 16:9 or 3:1 | Wide, cinematic feel |
| **Product photos** | 4:3 or 3:2 | Natural, not squashed |
| **Blog thumbnail** | 16:9 or 3:2 | Video-like format |
| **Avatar/icon** | 1:1 | Square, symmetric |
| **Person portrait** | 3:4 | Headshots are tall |
| **Landscape photo** | 16:9 | Natural landscape |
| **Feature card icon** | 1:1 | Clean, centered |

---

## Responsive Image Anti-Patterns

### ❌ No Aspect Ratio Defined

```html
<img src="image.jpg" alt="">
<!-- Image loads, layout shifts when height determined -->
```

**Fix:** Define aspect-ratio in CSS
```css
img {
  aspect-ratio: 16 / 9;
  width: 100%;
  height: auto;
}
```

### ❌ Same Image for All Devices

```html
<img src="1440px-image.jpg" alt="">
<!-- 1440px image loaded on mobile (150KB+ file) -->
```

**Fix:** Use responsive image markup
```html
<picture>
  <source srcset="mobile.jpg" media="(max-width: 390px)">
  <img src="desktop.jpg" alt="">
</picture>
```

### ❌ object-fit: fill (Stretching)

```css
img {
  object-fit: fill;  /* Distorts image */
}
```

**Fix:** Use cover or contain
```css
img {
  object-fit: cover;  /* Crops cleanly */
}
```

### ❌ Too Many Image Sizes

```
image-small.jpg
image-medium.jpg
image-large.jpg
image-xlarge.jpg
image-2x.jpg
image-2x-small.jpg
... etc
```

**Fix:** Stick to 2-3 sizes per image (small, medium, large)

