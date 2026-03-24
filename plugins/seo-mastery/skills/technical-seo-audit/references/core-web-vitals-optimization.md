# Core Web Vitals Optimization: Complete Fix Roadmap

## What Are Core Web Vitals?
Google's three metrics measuring user experience:
1. **LCP (Largest Contentful Paint)** — How fast main content loads
2. **INP (Interaction to Next Paint)** — How responsive page is to clicks
3. **CLS (Cumulative Layout Shift)** — How stable layout is (no unexpected movement)

**Target Scores** (mobile first, since that's weighted more):
- LCP: <2.5 seconds
- INP: <200 milliseconds
- CLS: <0.1

**Impact**: Google confirms CWV are ranking factors. Poor scores = ranking penalty. Excellent scores = ranking boost.

---

## Part 1: Measuring Your Current Status

### Step 1: Check Google PageSpeed Insights
1. Go to `pagespeedinsights.web.dev`
2. Enter your homepage URL
3. Review **mobile** score (this matters most)
4. Note the three metrics: LCP, INP, CLS

**What you'll see**:
- Green (90-100): Good
- Yellow (50-89): Needs improvement
- Red (0-49): Poor

### Step 2: Check Real-World CrUX Data
In Google Search Console:
1. Go to "Core Web Vitals" report
2. Check mobile vs. desktop breakdown
3. Note which metric is failing (LCP? CLS? INP?)

**Important**: CrUX = real-world data from actual users. Lab data (PageSpeed) is close but not exact.

### Step 3: Check Affected Pages
GSC report shows which pages have poor CWV:
- Mobile URLs with poor CWV
- Desktop URLs with poor CWV

**Priority**: Fix pages with highest traffic first (usually homepage + top landing pages).

---

## Part 2: Fix LCP (Largest Contentful Paint) — Most Important

**LCP Definition**: Time until main content (largest image or text block) finishes rendering.

**Target**: <2.5 seconds on mobile

### Root Causes of Slow LCP (In Order of Frequency)

#### 1. Unoptimized Images (Causes ~40% of LCP problems)

**Problem**: Large image files slow down download.

**Diagnosis**:
1. Open PageSpeed Insights
2. Look for: "Serve images in modern formats" or "Properly size images"
3. Large image file sizes = culprit

**Fix Workflow**:

**Step 1: Convert to WebP**
- WebP = Google's modern image format (40-50% smaller than JPEG/PNG)
- Use online converter: `convertio.co` or `cloudconvert.com`
- Or use WordPress plugin: "Ewww Image Optimizer" or "ShortPixel"

**Step 2: Compress Further**
- After converting to WebP, use `tinypng.com` to compress
- Typical file reduction: PNG 500KB → WebP 200KB → TinyPNG 50KB

**Step 3: Use Responsive Images**
In HTML, serve different image sizes for different devices:
```html
<img
  src="image-large.webp"
  sizes="(max-width: 768px) 100vw, 50vw"
  srcset="image-small.webp 480w, image-medium.webp 768w, image-large.webp 1200w"
  alt="Description"
/>
```
This ensures mobile users download smaller image.

**Step 4: Implement Lazy Loading**
```html
<img src="image.webp" loading="lazy" alt="Description"/>
```
Only load images when user scrolls near them (not on initial page load).

**WordPress Implementation**:
1. Install plugin: "Lazy Load by WP Rocket" or native "Smush"
2. Enable lazy loading for all images
3. Enable WebP conversion in plugin settings

#### 2. Render-Blocking CSS/JavaScript (Causes ~30% of LCP problems)

**Problem**: Browser waits for CSS/JavaScript to download/execute before showing content.

**Diagnosis**:
- PageSpeed shows: "Eliminate render-blocking resources"
- Google Lighthouse "Performance" tab shows red CSS/JS

**Fix Workflow**:

**Step 1: Defer JavaScript**
Move JavaScript loading to end of page or mark as deferred:
```html
<script src="script.js" defer></script>
```
`defer` = load script but don't block page rendering.

**Step 2: Defer Non-Critical CSS**
Use media queries or JavaScript to load CSS asynchronously:
```html
<!-- Critical CSS inline -->
<style>
  body { margin: 0; padding: 0; }
  h1 { font-size: 24px; }
</style>

<!-- Non-critical CSS loaded async -->
<link rel="preload" as="style" href="styles.css" onload="this.onload=null;this.rel='stylesheet'">
```

**Step 3: Remove Unused CSS**
- Use browser DevTools Coverage tab to find unused CSS
- Use plugin: "Unused CSS" in WordPress
- Delete CSS rules not used on that page

**Step 4: Minify CSS/JavaScript**
Use: `minifier.org` to compress code (removes spaces/comments).

**WordPress Implementation**:
1. Install "WP Rocket" or "Autoptimize"
2. Enable defer JavaScript
3. Enable CSS/JS minification
4. Enable lazy loading

#### 3. Slow Third-Party Scripts (Causes ~20% of LCP problems)

**Problem**: Google Analytics, chat widgets, ads load synchronously and block page.

**Diagnosis**:
- Waterfall in GTmetrics shows third-party domains (facebook.com, google.com, etc.)
- These take up significant portion of LCP time

**Fix Workflow**:

**Step 1: Identify Culprits**
Open GTmetrics waterfall:
1. Look for third-party domains (ads, chat, analytics)
2. Sort by "Time Taken" column
3. Top 3-5 usually account for 50% of LCP delay

**Step 2: Defer Non-Critical Third-Party Scripts**
- Chat widgets: Load after 3 seconds of user interaction
- Analytics: Use GA4 event tracking instead of page-level tracking
- Ads: Load only when visible (lazy load ads)

**Step 3: Use Script Timeouts**
```html
<script async src="analytics.js" type="text/javascript"></script>
```
`async` = load script in background without blocking render.

**Step 4: Load-Time Optimization Tactics**
- Move analytics to footer (loads last)
- Use DNS prefetch for third-party domains: `<link rel="dns-prefetch" href="//api.example.com">`
- Consider removing low-ROI scripts (surveys, heat maps if not critical)

**WordPress Implementation**:
1. Install "WP Disable" to selectively disable unused features
2. Defer analytics scripts
3. Use plugin: "Disable Announcements" to remove WordPress admin scripts affecting frontend

#### 4. Poor Hosting Performance (Causes ~10% of LCP problems)

**Problem**: Server responds slowly (Time to First Byte = TTFB).

**Diagnosis**:
- PageSpeed shows "Reduce server response time (TTFB)"
- GTmetrics waterfall shows long initial DNS lookup or waiting time

**Fix Workflow**:

**Step 1: Check Current TTFB**
- Use GTmetrics: Waterfall → look at DNS + Connecting + Waiting times
- Should total <600ms ideally

**Step 2: Upgrade Hosting**
If TTFB >1 second:
- Contact hosting provider about server specs
- Consider upgrading plan or switching to faster host
- Example providers with good TTFB: SiteGround, WP Engine, Kinsta

**Step 3: Enable Caching**
Use plugin: "WP Super Cache" or "W3 Total Cache"
- Browser caching: Reduce repeat requests
- Server-side caching: Cache database queries

**Step 4: Use CDN (Content Delivery Network)**
- Cloudflare (free tier)
- Bunny CDN (cheap at $0.01/GB)
- Serves content from server nearest to user

---

## Part 3: Fix CLS (Cumulative Layout Shift) — Second Priority

**CLS Definition**: How much layout moves around as page loads (visual instability).

**Target**: <0.1

**Common Causes**:

### 1. Ads Inserting Below Content (Causes ~40% of CLS)

**Problem**:
```
User loads page sees headline + paragraph
Then ads load below headline
Headline + paragraph shift down
User's eye position shifts ("jumping")
```

**Fix**:
- Reserve space for ads BEFORE they load
- Use fixed `height` and `width` on ad containers
```html
<div style="width: 300px; height: 250px;">
  <!-- Ad loads here -->
</div>
```

### 2. Dynamically Loaded Content (Causes ~30% of CLS)

**Problem**: Embedded videos, iframes, images load and push content down.

**Fix**:
- Use aspect ratio CSS to reserve space:
```css
img {
  aspect-ratio: 16/9;
  height: auto;
}
```

- Or use fixed container heights:
```html
<div style="width: 100%; height: 400px;">
  <iframe src="video.html" width="100%" height="100%"></iframe>
</div>
```

### 3. Custom Fonts Loading (Causes ~20% of CLS)

**Problem**: Custom fonts load after page renders; text shifts size/style.

**Fix**:
- Use `font-display: swap` to prevent layout shift:
```css
@font-face {
  font-family: 'CustomFont';
  src: url('font.woff2') format('woff2');
  font-display: swap; /* Show fallback while loading */
}
```

- Or preload fonts:
```html
<link rel="preload" as="font" href="font.woff2" type="font/woff2" crossorigin>
```

### 4. Overlay/Modal Insertions (Causes ~10% of CLS)

**Problem**: Cookie banners, chat widgets, notifications appear and shift content.

**Fix**:
- Don't cover main content; place overlay at bottom
- Animate from outside viewport (don't push existing content)
- Or reserve space with `position: fixed` (doesn't affect normal flow)

---

## Part 4: Fix INP (Interaction to Next Paint) — Third Priority

**INP Definition**: Time between user click and next visual update (responsiveness).

**Target**: <200ms

### Root Causes

#### 1. Long JavaScript Execution (Causes ~50% of INP issues)

**Problem**: Click triggers JavaScript that takes >200ms to run.

**Diagnosis**:
- Open DevTools Performance tab
- Click on an interactive element
- Check "Event listeners" time
- If >200ms = problem

**Fix**:
- Break JavaScript into smaller chunks
- Use `setTimeout` to defer non-critical tasks
- Example:
```javascript
// Bad: Blocks for 500ms
document.getElementById('button').addEventListener('click', () => {
  heavyCalculation(); // Takes 500ms
  updateUI();
});

// Good: Only critical UI updates are synchronous
document.getElementById('button').addEventListener('click', () => {
  updateUI(); // Synchronous (fast)
  setTimeout(() => {
    heavyCalculation(); // Deferred (doesn't block)
  }, 0);
});
```

#### 2. Too Many Event Listeners (Causes ~20% of INP issues)

**Problem**: Page has 500+ event listeners; browser checks them all on every click.

**Diagnosis**:
- DevTools Performance tab
- Check "Event listeners summary"
- If >100 = suspicious

**Fix**:
- Use event delegation (one listener on parent instead of many on children)
- Remove unused event listeners
- Debounce rapid events (search input, scroll listeners)

#### 3. Third-Party Scripts (Causes ~20% of INP issues)

**Problem**: Analytics, chat widgets monitor clicks and interfere with response.

**Fix**:
- Defer analytics tracking
- Use `async` for third-party scripts
- Load chat widget after 5 seconds (not immediately)

---

## Part 5: Implementation Roadmap (Priority Order)

### Quick Wins (Do First, <1 day effort)

1. **Convert images to WebP** — Impacts LCP most
2. **Implement lazy loading** — Reduces initial load
3. **Defer JavaScript** — Unblocks rendering
4. **Reserve space for ads** — Fixes CLS

**Expected impact**: 20-30 point PageSpeed improvement

### Medium Effort (1-2 weeks)

1. **Optimize Core Web Vitals** per specific metric
2. **Implement CDN** — Distribute content globally
3. **Upgrade hosting** — Reduce TTFB
4. **Fix third-party scripts** — Defer non-critical

**Expected impact**: 30-50 point PageSpeed improvement

### Long-Term (1-3 months)

1. **Code splitting** — Load only necessary JavaScript per page
2. **Service Worker** — Cache assets for repeat visits
3. **Server-side rendering** — Pre-render critical content
4. **Database optimization** — Reduce query times

**Expected impact**: 50+ point PageSpeed improvement

---

## Monitoring & Tracking

### Weekly Check
1. Run PageSpeed Insights
2. Note LCP, INP, CLS scores
3. Track improvements in spreadsheet

### Monthly Check
1. Review GSC Core Web Vitals report
2. Check if real-world CrUX data matches lab testing
3. Identify pages with newest CWV problems

### After Each Fix
1. Measure before/after
2. Document what changed
3. Track if change moved needle

---

## Common Pitfalls to Avoid

1. **Obsessing over lab scores**: Real-world CrUX data matters more than lab PageSpeed
2. **Fixing wrong metric first**: Usually LCP is bottleneck; fix that first
3. **Ignoring mobile**: Mobile scores weighted more than desktop
4. **Trying too many fixes at once**: Change one thing, measure, then next
5. **Using low-quality images**: WebP is great but quality matters (don't overshrink)
