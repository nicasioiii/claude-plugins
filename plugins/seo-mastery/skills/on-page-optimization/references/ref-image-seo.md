# Image SEO Optimization Guide

## Core Principle
Include at least **one image per keyword** you are targeting on the page. This allows one image optimized per keyword for maximum SEO value (Hockman).

---

## Alt Text Rules

1. Use target keyword as exact-match phrase
2. Describe the image accurately (screen readers need useful descriptions)
3. Front-load the keyword when possible
4. Max 125 characters -- no SEO value in maxing it out
5. Do NOT prefix with "image of" or "picture of"
6. For multiple images, vary alt text -- never repeat identical alt text
   - Good: "organic shea butter lotion", "natural shea butter lotion", "body lotion with shea butter"
7. Be descriptive enough that someone reading only the alt text understands the image

---

## Image Title Attribute
Copy the alt text directly into the image title attribute. Simple and effective.

---

## Image File Naming

1. Use target keyword as exact-match phrase with hyphens (e.g., `best-seo-books.jpeg`)
2. Match file name to corresponding alt text keyword
3. 100% exact match with alt text not required -- you can omit extra descriptive words
4. **Use JPEG format, not PNG** -- only JPEG allows metadata editing via file properties
5. Always hyphens between words (search engines read hyphens as spaces)
6. Avoid underscores (Google historically treated underscores as word joiners, not separators)
7. Keep filenames descriptive but concise -- under 5-6 words is ideal

### File Naming Convention Examples
| Bad | Good |
|-----|------|
| IMG_4782.jpg | waterproof-hiking-boots.jpg |
| photo1.png | organic-face-cream-review.jpg |
| screenshot-2026-03-24.jpg | ga4-dashboard-setup-guide.jpg |
| product_image_v2.png | mens-leather-crossbody-bag.jpg |

---

## Image Metadata (Hidden SEO)

Two key metadata fields:
- **Keywords field** -- exact-match target keyword
- **Description field** -- 1-2 sentences describing the image, include keyword naturally

Optional fields:
- **Document Title** -- keyword variations
- **Author** -- your name/business (builds entity connections)
- **Copyright** -- brand name for entity association

### How to Edit Image Metadata

**Method 1: File Properties (Windows)**
1. Right-click image file > Properties > Details tab
2. Fill in Title, Subject, Tags, Comments with target keyword and variations
3. Fill in Authors with brand or person name
4. Click Apply > OK

**Method 2: File Properties (Mac)**
1. Open image in Preview > Tools > Show Inspector > Exif tab
2. Limited editing -- use a third-party tool for full control

**Method 3: Online Tools**
- **TheExifer.com** -- best for EXIF data injection including GPS coordinates
- **thexifer.net** -- free alternative for basic metadata editing
- **GIMP** -- open source, full metadata editing in File > Export As > Advanced Options

**Method 4: Photoshop**
- File > File Info > fill in Description, Keywords, Copyright fields
- Most comprehensive metadata editing available

---

## EXIF Data Injection for SEO (Step-by-Step)

EXIF data is the hidden "DNA" of images -- GPS coordinates, timestamps, camera info, and custom fields that validate authenticity and location.

### Complete EXIF Injection Workflow
1. **Prepare image** -- save as JPEG (PNG strips EXIF data)
2. **Open TheExifer.com** and upload the image
3. **Description/Caption field:** Enter target keyword + NAP + website URL
4. **Artist/Author field:** Enter owner name or brand representative
5. **Copyright field:** Enter brand name and year
6. **GPS Coordinates:** Hardcode exact latitude/longitude of business location
   - Find coordinates: Google Maps > right-click location > copy coordinates
7. **Date/Time fields:** Set to a recent, realistic date (validates freshness)
8. **Rating field:** Set to 5 stars as a trust signal
9. **Download** the EXIF-injected image
10. **Verify** by re-uploading to TheExifer and checking fields persisted

### GPS Coordinate Sources
- Google Maps: right-click any location to copy lat/long
- GeoSetter (desktop tool): visual map-based coordinate selection
- LatLong.net: address-to-coordinate converter

### Batch EXIF Processing
For sites with 50+ images, use GeoSetter (free desktop tool):
1. Open folder of images in GeoSetter
2. Select all images
3. Navigate map to business location
4. Click to set coordinates for all selected images
5. Edit metadata fields in batch
6. Save all at once

---

## OCR Exploitation for SEO

Google uses Optical Character Recognition to read text within images. Most competitors overlook this entirely.

### How to Leverage OCR
1. **Add keyword text overlays** to images using bold, clear sans-serif fonts
2. **Font choice matters:** Arial, Helvetica, Open Sans are easily read by OCR. Fancy scripts and handwriting fonts confuse OCR engines
3. **Contrast matters:** White text on dark background or dark text on light background -- high contrast = better OCR accuracy
4. **Placement:** Bottom or top banner overlay works best; text over busy image backgrounds reduces OCR accuracy
5. **Content to overlay:** Primary keyword + location (for local), brand name, key data points

### OCR for Local SEO
- Overlay service keyword + city name directly onto service images
- Google reads this text and associates it with local search intent
- Example: Banner reading "Professional Plumbing Melbourne" on a service photo
- Google also reads logos via OCR -- brand logos reinforce keyword-brand association

### OCR for E-Commerce
- Product images with text overlays ("Free Shipping", "Best Seller") get read by Google
- Sale/discount text on product images can appear in Google Shopping results
- Size/dimension text overlaid on product images adds structured data signals

---

## Featured Image Strategy (Koray)

For every article's featured/hero image:
1. Use a **unique image** (not generic stock photos)
2. Add **text overlay** with the topic/keyword
3. Include your **brand mark** (logo or consistent visual element)
4. One featured image per article -- make it distinctive

This builds visual brand recognition and provides additional keyword signals via OCR.

### Featured Image Best Practices
- Dimensions: 1200x630px minimum (optimal for social sharing and Google Discover)
- File size: compress to under 150KB without visible quality loss
- Format: JPEG for photos, WebP for modern browsers (with JPEG fallback)
- Unique images rank better in Google Image Search than stock photos used on multiple sites

---

## Image Compression & Performance

### Compression Tools
- **ShortPixel** -- WordPress plugin, batch compression, WebP conversion
- **TinyPNG/TinyJPG** -- free online compression (up to 20 images at once)
- **Squoosh** (by Google) -- advanced compression with quality preview
- **ImageOptim** (Mac) -- free desktop tool for batch optimization

### Target File Sizes
- Hero/featured images: under 150KB
- In-content images: under 100KB
- Thumbnails: under 30KB
- Product images: under 200KB (higher quality needed for zoom)

### Format Selection Guide
| Format | Best For | Notes |
|--------|----------|-------|
| JPEG | Photos, complex images | Best compression ratio, supports EXIF |
| WebP | Modern browsers | 25-35% smaller than JPEG, limited EXIF support |
| PNG | Screenshots, logos, transparency | Large files, no EXIF support |
| SVG | Icons, simple graphics | Infinitely scalable, tiny file size |
| AVIF | Next-gen browsers | Best compression, limited browser support |

---

## Local SEO Image Optimization

### EXIF Data Injection (Mayank/LSC)
- Inject GPS coordinates into image EXIF data (geo-tagging)
- Tools: EXIF editors, Photoshop, dedicated geo-tagging tools
- Adds location relevance signals for local search

### OCR Exploitation
- Google reads text on images via Optical Character Recognition
- Add keyword text overlays to images (e.g., service name + city on hero images)
- Google recognizes logos -- adding brand logo reinforces keyword-brand association

### File Naming for Local
- Include location in image file names: `plumber-melbourne-bathroom-renovation.jpg`
- Each image gets location-specific alt text

---

## Image SEO for Parasite Campaigns

### File Format
- Save as JPEG (not PNG) for metadata editing
- Name file as target keyword: `georadius-schema-generator.jpg`

### JPEG Metadata
- Right-click > Properties > Details
- Add target keyword to Title/Subject field
- Add brand name to Author field

### Image Variety
- Google only shows the same image once in image search
- Create multiple different images with keyword text overlay + brand logo
- Use Canva/Crello for quick creation

---

## Per-500-Words Image Checklist (Maddy Osman)

For every ~500 words of content:
- At least 1 relevant image
- Image title optimized with primary keyword
- Alt tag with primary keyword (descriptive)
- File name with primary keyword (hyphens)
- Image compressed for page speed

---

## AI Search Considerations

- LLMs do NOT process images even though technically capable -- too computationally expensive (brightonSEO/Surfer)
- Always duplicate infographic/image content as text or in meta descriptions
- AI crawlers cannot interact with JavaScript -- if image content is rendered via JS, duplicate as HTML tables
- Text overlays on images are readable by Google but not by LLMs directly
- For AI search: the alt text and surrounding paragraph text matter more than the image itself
