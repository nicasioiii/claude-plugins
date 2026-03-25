---
name: Conversion Design Reference
description: Seven design principles for higher conversions, design split tests, testimonial visual format, CTA design, and mobile vs desktop optimization.
---

# Conversion Design

## SEVEN DESIGN PRINCIPLES FOR HIGHER CONVERSIONS (GUSTEN)

### 1. Layout
Clear visual hierarchy guides the eye from headline to CTA. Use a Z-pattern or F-pattern layout depending on content type. Headlines at top, supporting content in the middle, CTA at natural stopping points.

Break content into clear sections with distinct visual separation. Each section should have one purpose and one visual focus.

### 2. Size
Important elements should be the largest on the page. Headlines are larger than body text. CTA buttons are larger than surrounding elements. Product images are prominent, not thumbnailed.

**Hierarchy of size:** Headline > Sub-headline > CTA button > Body text > Fine print

### 3. White Space
Do not crowd elements. Breathing room increases readability and perceived quality. A page with generous white space feels more premium and trustworthy.

**Common mistake:** Cramming too much content above the fold. It is better to have a clean, focused above-the-fold section that earns the scroll than a cluttered one that overwhelms.

### 4. Contrast
CTAs must pop against the background. High contrast = higher click rates. The CTA button should be a distinctly different color from everything else on the page.

**Color contrast rules:**
- CTA button should be the ONLY element in that color
- Text on the button must be legible against the button color
- Avoid red buttons on red-themed pages or blue buttons on blue backgrounds
- Test: squint at the page -- the CTA should be the most obvious element

### 5. Numbers
Use specific numbers in headlines and proof sections. "3,000 customers" outperforms "thousands of customers." "Lost 23 pounds in 30 days" outperforms "Lost weight quickly."

Specific numbers create credibility. Round numbers feel estimated. Odd or precise numbers feel measured and real.

### 6. Direction
Visual cues should point toward the CTA. Methods include:
- Arrows (explicit but effective)
- Eye gaze direction (photos of people looking toward the CTA)
- Layout flow (content naturally leads to the CTA as the next action)
- Gradients or visual lines that draw the eye toward the button

### 7. Interactions
Hover effects, animations, and micro-interactions increase engagement. Subtle animations on scroll (fade-in sections) keep attention. Button hover states (color change, grow effect) invite clicking.

**Warning:** Do not overdo animations. They should enhance, not distract. One animation per viewport is usually sufficient.

---

## DESIGN SPLIT TESTS

### Light Mode vs. Dark Mode
- **Dark mode works for:** Design tools, crypto, NFT, tech, gaming, luxury brands, creative agencies
- **Light mode works for:** Text-heavy content, education, health/wellness, info products, professional services
- Test both regardless of assumptions -- results often surprise

### Video vs. Image Hero Section
- **Video hero:** Higher engagement, communicates more information, builds connection faster
- **Image hero:** Faster load time, immediate visual impact, better for mobile on slow connections
- Video converts 2-4x better in most cases but test with your specific audience and traffic

### Embedded Order Form vs. Popup vs. Separate Page
- **Popup:** Least friction for low-ticket, keeps sales page visible
- **Embedded:** Seamless experience, good for e-commerce
- **Separate page:** Fastest load, most trust for mid-to-high ticket

### Long-Form vs. Short-Form Pages
- **Short-form:** Headline, brief benefits, CTA, testimonials, CTA. Works for freebies and warm traffic.
- **Long-form:** Full 10-step sales page framework. Works for cold traffic and complex offers.
- The winner depends entirely on awareness level and price point. Always test.

### Testimonial Placement
- **Above the fold (small):** Short quote + name + photo. Creates immediate social proof.
- **Below the fold (detailed):** Full testimonials with specific results. Builds deep credibility.
- **Best practice:** Both. Small above-the-fold testimonial to earn the scroll, detailed testimonials scattered throughout near CTAs.

---

## TESTIMONIAL VISUAL FORMAT

### Most Effective Combination
Photo of the person + headline quote + short video. This triple format addresses visual proof (photo), scannable impact (headline), and deep engagement (video).

### Screenshot Testimonials
Screenshots from social media (Facebook comments, DMs, text messages) feel authentic because they cannot be easily faked. Include the platform interface elements to reinforce authenticity.

### Video Testimonials
- Keep to 30-60 seconds
- Customer should state: what they were struggling with, what they tried, what they discovered, and the specific result
- Low production value is fine (phone recording) -- it feels more real
- Add subtitles (many people watch without sound)

### Text Testimonials with Photos
- Full name + photo + location (adds credibility)
- Bold the most impactful sentence
- Include specific numbers or timeframes
- Group testimonials that address the same objection together (place near that objection in the copy)

---

## CTA BUTTON DESIGN AND PLACEMENT

### Button Design Principles
- **Color:** High contrast against background. Only one element on the page should be this color.
- **Size:** Large enough to be easily tappable on mobile (minimum 48px height)
- **Text:** Action-oriented first person ("Yes, I want this" / "Get instant access" / "Start my free trial")
- **Micro-copy below button:** Address the biggest objection ("30-day money-back guarantee" / "No credit card required" / "Cancel anytime")

### Button Placement
- First CTA: above the fold (after headline + brief value prop)
- Second CTA: after the offer stack section
- Third CTA: after the guarantee/risk reversal section
- Final CTA: at the very bottom after FAQ

Do not place only one CTA at the bottom of a long page. Many visitors never scroll that far.

### Sticky CTA
For longer pages, a sticky CTA bar at the bottom of the viewport (mobile) or a floating sidebar (desktop) keeps the buying action always accessible without requiring the visitor to scroll.

---

## MOBILE VS. DESKTOP OPTIMIZATION

### Mobile Priorities
1. **Speed:** Mobile pages must load in under 3 seconds. Compress images, defer non-critical scripts.
2. **Thumb-friendly CTAs:** Large buttons, no small text links for critical actions.
3. **Simplified layout:** Single column. No side-by-side elements that get too small on mobile.
4. **Sticky CTA bar:** Always-visible buy button at bottom of screen.
5. **Reduced form fields:** Fewer fields = higher completion. Use autofill where possible.

### Desktop Priorities
1. **Above-the-fold impact:** More screen real estate = more information visible. Use it wisely.
2. **Side-by-side layouts:** Comparison tables, package displays, and testimonial grids work well.
3. **Video embeds:** Desktop users are more likely to watch embedded videos.
4. **Multi-column navigation:** If applicable, use visual navigation to direct users to different sections.

### When to Segment Tests
If your traffic is 70%+ mobile (common for social media traffic), run mobile-specific tests. The mobile experience likely has more optimization potential than desktop. Conversely, if traffic is search-driven and 60%+ desktop, prioritize desktop optimization.

Always check analytics to understand your traffic split before deciding which device to optimize first.

---

## PAGE SPEED AND CONVERSION

### The Speed-Conversion Relationship
Every additional second of page load time reduces conversion rate. A page that loads in 1 second converts significantly better than one that loads in 5 seconds.

### Quick Wins for Page Speed
- Compress all images (use WebP format where supported)
- Defer non-critical JavaScript (analytics, chat widgets, social embeds)
- Use lazy loading for images below the fold
- Minimize custom fonts (each font file adds load time)
- Use a CDN for static assets
- Remove unused CSS and JavaScript libraries

### Speed Testing
Test page speed with Google PageSpeed Insights and GTmetrix. Target a score of 80+ on mobile. If below 60, page speed is likely hurting conversion.

---

## ABOVE-THE-FOLD OPTIMIZATION

### What Must Be Above the Fold
The first viewport (what the visitor sees without scrolling) must contain:
1. **Headline** with clear outcome
2. **Sub-headline** with timeframe and objection removal
3. **CTA button** (even if there are more CTAs below)
4. **One trust signal** (small testimonial, rating, or guarantee badge)

### What Can Be Below the Fold
- Detailed testimonials and case studies
- Full offer stack and pricing
- FAQ section
- About/authority section
- Comparison tables

### Above-the-Fold Testing Priority
If you can only run one test, test the above-the-fold experience. It determines whether the visitor scrolls or bounces. The headline + hero image/video + first CTA are the highest-leverage elements on any page.

---

## SCARCITY AND URGENCY DESIGN

### Visual Urgency Elements
- **Countdown timers:** Effective when tied to a real deadline. Fake timers that reset on page refresh damage trust permanently.
- **Stock indicators:** "Only 3 left" or "87% claimed." Works for limited-quantity offers.
- **Price change warnings:** "Price goes up in 2 days" or "Early bird ends [date]."
- **Progress bars:** Show how much of a limited offer has been claimed.

### Urgency Placement
Place urgency elements:
- Near the first CTA (above the fold if possible)
- Near the price reveal
- In a sticky bar at the top or bottom of the page
- In the checkout page near the submit button

### When Urgency Backfires
- If the urgency is fake (countdown resets on refresh), visitors lose all trust
- If urgency is too aggressive on a cold audience, it feels like pressure
- If every page has urgency elements, they become invisible (urgency fatigue)
- Urgency works best when the visitor is already interested and needs a reason to act NOW rather than later

---

## FORM DESIGN FOR CONVERSIONS

### Fewer Fields = Higher Conversion
Every additional form field reduces completion rate. Only ask for what is absolutely necessary at each stage.

- **Opt-in pages:** Name + Email (or just Email for maximum conversion)
- **Checkout pages:** Name + Email + Payment info (minimum viable)
- **Application pages:** More fields are acceptable because filtering is the goal

### Field Ordering
Put the easiest fields first (name, email) and the hardest last (payment info). Each completed field creates micro-commitment that makes it harder to abandon.

### Inline Validation
Show green checkmarks as fields are correctly completed. This provides positive reinforcement and reduces form anxiety. Show errors immediately (do not wait for submit).

### Autofill Support
Enable browser autofill for standard fields (name, email, address, card). This dramatically reduces friction on mobile where typing is slower.
