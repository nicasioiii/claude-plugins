# Site Speed Optimization: Complete Implementation Guide

## Why Site Speed Matters
1. **Ranking factor**: Google confirms speed influences rankings
2. **Conversion impact**: 1 second delay = 7% conversion decrease
3. **User experience**: Slow sites have higher bounce rates
4. **Mobile first**: Mobile speed weighted more than desktop

---

## Part 1: Understanding Key Metrics

### Three Important Measurements
1. **TTFB (Time to First Byte)** — Server response time (target: <600ms)
2. **FCP (First Contentful Paint)** — First visible content (target: <1.8s)
3. **LCP (Largest Contentful Paint)** — Main content loads (target: <2.5s)

### Where to Check
- **Google PageSpeed Insights**: Lab + real-world data
- **GTmetrics**: Detailed waterfall (what loads first, what's slow)
- **Google Search Console**: Core Web Vitals real-world data

---

## Part 2: Image Optimization (Biggest Impact)

### Why Images Matter
Images typically make up 50-80% of page weight. Optimizing images = biggest speed win.

### Step 1: Audit Current Images
1. Open GTmetrics
2. Enter site URL
3. Look for section: "Serve images in modern formats"
4. Check image file sizes
5. Note: Which images are largest?

### Step 2: Convert to WebP Format

**WebP**: Google's modern image format (30-50% smaller than JPEG/PNG)

**Conversion Method A: Online Tool**
1. Visit `convertio.co` or `cloudconvert.com`
2. Upload image
3. Convert to WebP
4. Download

**Conversion Method B: WordPress Plugin**
1. Install: "Smush" or "Ewww Image Optimizer"
2. Bulk convert all images to WebP
3. Plugin automatically serves correct format

**Conversion Method C: ImageMagick (Command Line)**
```bash
convert image.jpg -quality 80 image.webp
```

### Step 3: Compress Further
1. Upload WebP image to `tinypng.com`
2. Download compressed version
3. Typical reduction: WebP 200KB → TinyPNG 50KB

### Step 4: Implement Responsive Images
Serve different image sizes to different devices:

```html
<img
  src="image-large.webp"
  srcset="image-small.webp 480w, image-medium.webp 768w, image-large.webp 1200w"
  sizes="(max-width: 768px) 100vw, 50vw"
  alt="Description"
  loading="lazy"
/>
```

**What This Does**:
- Mobile (480w): Gets smallest image (~30KB)
- Tablet (768w): Gets medium image (~60KB)
- Desktop (1200w): Gets large image (~100KB)

### Step 5: Implement Lazy Loading
```html
<img src="image.webp" loading="lazy" alt="Description"/>
```

Lazy loading = only load images when user scrolls near them.

**WordPress Implementation**:
- Plugin "Lazy Load by WP Rocket" handles this automatically
- Or use native WordPress lazy loading (newer versions)

### Image Optimization Checklist
- [ ] All images converted to WebP
- [ ] Images compressed with TinyPNG
- [ ] Responsive images implemented (different sizes for mobile/desktop)
- [ ] Lazy loading enabled
- [ ] Image alt text descriptive
- [ ] Largest image <200KB

### Expected Impact
- Typical site: 30-40% page speed improvement
- LCP improvement: 1-2 seconds faster

---

## Part 3: Eliminate Render-Blocking Resources

### What Render-Blocking Means
Browser waits for CSS/JavaScript to download before showing content.

### Identify Render-Blocking Resources
1. Open Google PageSpeed Insights
2. Look for: "Eliminate render-blocking resources"
3. Lists CSS and JS files blocking render
4. Sort by file size

### Fix Render-Blocking CSS

**Option 1: Inline Critical CSS**
```html
<head>
  <!-- Critical CSS inline (for above-the-fold content) -->
  <style>
    body { margin: 0; padding: 0; }
    header { background: #333; }
    h1 { font-size: 32px; }
  </style>

  <!-- Non-critical CSS loaded async -->
  <link rel="preload" as="style" href="styles.css" onload="this.onload=null;this.rel='stylesheet'">
</head>
```

**Option 2: Defer CSS**
```html
<link rel="preload" href="styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
```

**Option 3: Remove Unused CSS**
Use DevTools Coverage tab to find unused CSS:
1. Open DevTools
2. Ctrl+Shift+P (Cmd+Shift+P on Mac)
3. Type "Coverage"
4. Run coverage
5. Red sections = unused CSS
6. Delete those rules

### Fix Render-Blocking JavaScript

**Option 1: Defer JavaScript**
```html
<script src="script.js" defer></script>
```
`defer` = load script after page renders (doesn't block)

**Option 2: Async JavaScript**
```html
<script src="script.js" async></script>
```
`async` = load script in parallel (doesn't block, but may execute out of order)

**Option 3: Move Scripts to End**
```html
<body>
  <content here>

  <!-- Scripts at end of body load last -->
  <script src="script.js"></script>
</body>
```

### WordPress Implementation
1. Install: "WP Rocket" or "Autoptimize"
2. Enable "Defer JavaScript"
3. Enable "Inline Critical CSS"
4. Plugin handles rest automatically

### Render-Blocking Checklist
- [ ] Critical CSS inlined or preloaded
- [ ] Non-critical CSS deferred
- [ ] Unused CSS removed
- [ ] JavaScript deferred or async
- [ ] No render-blocking resources in PageSpeed report

### Expected Impact
- Typical site: 20-30% improvement
- FCP improvement: 1-2 seconds faster

---

## Part 4: Third-Party Scripts Management

### The Problem
Analytics, ads, chat widgets load synchronously and block page.

### Identify Culprits
1. Open GTmetrics
2. Look at "Waterfall" chart
3. Find third-party domains (google.com, facebook.com, etc.)
4. Note which take longest time

### Defer Third-Party Scripts

**Google Analytics**
```html
<!-- BAD: Blocks page -->
<script async src="https://www.google-analytics.com/analytics.js"></script>

<!-- GOOD: Load after 3 seconds -->
<script>
  setTimeout(() => {
    const script = document.createElement('script');
    script.src = 'https://www.google-analytics.com/analytics.js';
    script.async = true;
    document.head.appendChild(script);
  }, 3000);
</script>
```

**Chat Widget**
```html
<!-- Load only after user interaction -->
<script>
  document.addEventListener('click', () => {
    const script = document.createElement('script');
    script.src = 'https://chat.example.com/widget.js';
    document.head.appendChild(script);
  });
</script>
```

**Ads**
```html
<!-- Load ads only when visible -->
<img src="ad.jpg" loading="lazy" />

<!-- Or use lazy-loaded iframe -->
<iframe src="ad.html" loading="lazy"></iframe>
```

### DNS Prefetch for Third-Party Domains
```html
<link rel="dns-prefetch" href="https://analytics.google.com">
```
Starts DNS lookup early so script loads faster.

### Third-Party Script Checklist
- [ ] Analytics deferred or loaded last
- [ ] Chat widget loads after 3+ seconds
- [ ] Ads lazy-loaded
- [ ] DNS prefetch for critical third-parties
- [ ] Non-essential scripts removed

### Expected Impact
- Typical site with many ads: 15-25% improvement
- LCP improvement: 0.5-1 second

---

## Part 5: Caching Strategy

### Browser Caching (Users' Devices)
Users' browsers cache CSS, JavaScript, images. Repeat visitors get fast loads.

**Set Cache Headers**:
```
Cache-Control: max-age=31536000 (1 year for static assets)
Cache-Control: max-age=3600 (1 hour for HTML)
```

**WordPress Plugin**: "WP Super Cache" or "Autoptimize" handles this

### Server-Side Caching
Cache generated pages on server so database doesn't re-generate.

**WordPress Plugin**: "W3 Total Cache"
1. Install plugin
2. Enable "Page Cache"
3. Enable "Database Cache"
4. Plugin caches pages for repeat visitors

### CDN (Content Delivery Network)
Serve content from servers nearest to user's location.

**Free CDN**: Cloudflare
1. Sign up at `cloudflare.com`
2. Change nameservers to Cloudflare
3. Content served from global network

**Paid CDN**: Bunny CDN ($0.01/GB)
- More affordable than Cloudflare Pro
- Good for high-traffic sites

### Caching Checklist
- [ ] Browser caching enabled (Cache-Control headers)
- [ ] Page caching enabled on server
- [ ] Database caching enabled
- [ ] CDN implemented
- [ ] Cache busting on updates (plugin handles this)

### Expected Impact
- Typical site: 20-50% improvement for repeat visitors
- First-time visitors: Little change (they don't have cache)

---

## Part 6: Hosting & Server Optimization

### TTFB (Time to First Byte) Optimization
TTFB = time for server to respond. Should be <600ms.

### Check Current TTFB
1. Open GTmetrics
2. Look at waterfall
3. Note "DNS" + "Connecting" + "Waiting" times
4. Should total <600ms

### If TTFB Too Slow

**Option 1: Upgrade Hosting**
Compare hosting providers:
- SiteGround: Good for WordPress (~$6-15/month)
- WP Engine: Managed WordPress (~$20-115/month)
- Kinsta: Premium WordPress (~$35-1000+/month)

**Option 2: Optimize Database**
```sql
-- Clean up WordPress database
DELETE FROM wp_comments WHERE comment_approved = 'spam';
OPTIMIZE TABLE wp_posts;
OPTIMIZE TABLE wp_postmeta;
```

**Option 3: Use PHP 8+**
Newer PHP versions are faster.
- Contact hosting provider about PHP version
- Should be 8.0+

### Hosting Optimization Checklist
- [ ] TTFB <600ms
- [ ] PHP 8.0+ installed
- [ ] Database optimized
- [ ] Hosting supports HTTP/2
- [ ] Hosting supports gzip compression

### Expected Impact
- Typical site: 10-20% improvement
- LCP improvement: 0.5-1 second

---

## Part 7: Advanced Optimization (Optional)

### Code Splitting
Load only JavaScript needed for each page.

### Service Workers
Cache assets for offline access + repeat visits.

### Server-Side Rendering
Pre-render pages on server instead of browser.

**Note**: These require developer expertise. Start with basic optimizations first.

---

## Implementation Roadmap (Priority Order)

### Week 1: Quick Wins (Biggest Impact)
1. **Convert images to WebP** — 30-40% improvement
2. **Implement lazy loading** — 15-20% improvement
3. **Defer JavaScript** — 20-30% improvement
4. **Enable caching** — 20-50% for repeat visitors

**Total Expected**: 30-50 point PageSpeed boost

### Week 2-3: Medium Effort
1. **Inline critical CSS**
2. **Remove unused CSS/JS**
3. **Defer third-party scripts**
4. **Compress images further (TinyPNG)**

**Total Expected**: Additional 20-30 point boost

### Month 2: Long-Term
1. **Upgrade hosting** (if TTFB still slow)
2. **Implement CDN**
3. **Advanced caching strategies**
4. **Consider code splitting**

**Total Expected**: Additional 10-20 point boost

---

## Tools You'll Use

### Free Tools
- **Google PageSpeed Insights**: Main testing tool
- **GTmetrics**: Waterfall analysis
- **TinyPNG**: Image compression
- **DevTools**: Coverage analysis
- **Chrome Lighthouse**: Automated audits

### Paid Tools (Optional)
- **WP Rocket**: WordPress caching + optimization ($39-399/year)
- **Cloudflare Pro**: Advanced CDN ($200+/year)
- **Kinsta/WP Engine**: Premium hosting ($35+/month)

### Monitoring
Track speed metrics weekly:
- Create spreadsheet
- Weekly PageSpeed score
- LCP/CLS/INP trends
- Monitor for regressions

---

## Common Mistakes to Avoid

1. **Over-optimizing images**: Don't compress too much (quality suffers)
2. **Deferring critical scripts**: Some scripts must load synchronously
3. **Removing too much CSS**: Verify before deleting
4. **Setting cache too long**: Users see outdated content
5. **Ignoring mobile**: Desktop speed less important than mobile
