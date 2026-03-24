# Meta Title & Description Optimization

## Meta Title Rules (Complete)

### Ranking Impact
The meta title is the single most important on-page ranking factor you can control (Hockman). It also directly affects CTR in SERPs.

### Character & Pixel Limits
- **Desktop:** ~60 characters or ~580px pixel width before Google truncates with ellipsis
- **Mobile:** Slightly more forgiving on character count but varies by device
- **Best practice:** Write titles to 55-58 characters to leave a pixel safety margin
- **Pipe vs. dash separators:** Both work; dash (–) is slightly wider in pixels, pipe (|) saves space
- Test pixel width with SERP preview tools (Mangools, Portent, SEOmofo)

### Optimization Checklist
1. **Include main keyword** as exact-match phrase
2. **Front-load the keyword** -- closer to beginning = more SEO weight. Google reads left to right
3. **Add secondary keywords** after main keyword to capture broader queries
4. **Under 60 characters** (pixel width ~580px) -- Google truncates with ellipsis
5. **Match the H1 tag** -- near-identical meta title + H1 prevents Google rewrites (confirmed by Cyrus Shepard case study, late 2021 onward)
6. **Never brand name first** -- unless household brand (Amazon, Nike). Front-load the keyword

### E-Commerce Meta Title Format
- Format: `Shop [Target Keyword] | [Brand Name]` or `Shop [Target Keyword] - [Brand Name]`
- Never put brand name first for e-commerce
- Google rewrites over 50% of meta descriptions -- for bulk collection pages, use ChatGPT or leave blank and let Shopify auto-source from collection description (Cromwell)

### The Three Titles Framework (Authority Hacker)
Pages have three distinct titles that should differ:
1. **Page title (headline)** -- communicates value to human readers on the page
2. **SEO title (meta title)** -- optimized for Google with primary keyword
3. **Social title (OG title)** -- optimized for social sharing and engagement

The page title does NOT have to include SEO keywords. The SEO title SHOULD include primary keyword. They can and arguably should be different (Maddy Osman).

**Why three titles matter:**
- The page title hooks the reader who is already on the page -- it can be creative, emotional, provocative
- The SEO title must include the keyword because it competes for clicks in the SERP
- The OG title needs to work in a social feed where context is limited and attention is scarce
- Using the same title for all three sacrifices optimization on at least two surfaces

### Preventing Google Title Rewrites
Google rewrites titles at an increasing rate. Prevention tactics:
1. **Match meta title and H1 closely** -- the strongest prevention signal (Shepard)
2. **Keep within character limits** -- truncated titles are rewrite candidates
3. **Include the site name** -- Google appends it if missing, which may cause truncation
4. **Ensure title matches page content** -- topical mismatch triggers rewrites
5. **Avoid keyword stuffing** -- over-optimized titles get rewritten to be more user-friendly
6. **Use proper title case** -- ALL CAPS or all-lowercase titles are rewrite candidates

### A/B Testing Titles
- **Google Search Console method:** Change title, wait 2-4 weeks, compare CTR in GSC Performance report
- **ClickFlow / SearchPilot:** Dedicated SEO split-testing tools (paid)
- **Manual rotation:** Change title every 30 days, track CTR per period in GSC
- **When to test:** High-impression, low-CTR pages are the best candidates for title testing
- **Warning:** Changes take 1-2 weeks to reflect in SERPs; do not change titles more frequently than every 3-4 weeks

### Measuring Title Effectiveness
- Track CTR via Google Search Console
- Even if page and meta titles differ, they should communicate a similar core message
- Compare your CTR to expected CTR for your average position (position 1 ~28%, position 3 ~11%, position 10 ~2.5%)

---

## Meta Description Optimization

### Ranking Status
Meta descriptions are NOT a direct ranking factor in Google. But they have significant indirect value.

### Why They Still Matter
- Keywords get **bolded** in search results, signaling relevance
- Controls (partially) your SERP listing display
- Functions as a mini sales tool impacting CTR
- AI search (ChatGPT) reads meta descriptions via WebGPT to decide whether to fetch the page

### Character Limits & Display Rules
- **Standard limit:** ~155-160 characters on desktop
- **Mobile:** Often truncated shorter (~120 characters)
- **Experimental:** Google sometimes shows up to 250+ characters for certain queries
- **Best practice:** Front-load the most important information within the first 120 characters
- **Rich snippets override:** If structured data is present, Google may replace your meta description with review stars, price, availability

### Optimization Rules
1. **Include main keyword** -- gets bolded in SERPs
2. **Front-load main keyword** -- first bolded words under title = maximum relevance signal
3. **Add secondary keywords** -- more bolded words = more clicks
4. **Keep keywords within first 160 characters** -- Google truncates at ~160 (sometimes experiments up to 250)
5. **Analyze competitor meta descriptions** -- note which words Google bolds in top results and include them
6. **Include a call to action** -- "Learn how," "Discover why," "Get the complete guide"
7. **Use active voice** -- more compelling than passive constructions

### Meta Description Spoiling Strategy (brightonSEO/Profound)
Put the answer directly in the meta description. Highly cited pages in AI search do this.
- Example: "The best business credit card is [Brand X]" in the meta
- WebGPT reads URL + title + meta description to decide whether to fetch a page
- Spoiling content in meta = higher citation probability in AI search
- This contradicts traditional SEO advice of "teasing" content to get clicks, but AI search changes the calculus

### E-Commerce Meta Description Strategy (Cromwell)
Google rewrites 50%+ of meta descriptions. If you have many collection pages, do NOT waste time writing unique descriptions for all of them. Shopify auto-sources from the first 1-2 sentences of collection descriptions, which -- if optimized -- already contain the target keyword.

**Priority order for meta description writing:**
1. Homepage and top 5-10 category pages -- write manually
2. High-traffic product pages -- write manually
3. Long-tail category pages -- template-generate or leave blank
4. Individual product pages -- auto-generate from product data

---

## Headline Formulas (Maddy Osman)

### 1. Curiosity Gap (Copyhackers)
The space between what we know and what we want to know.
Example: "The Boston Animal Shelter Volunteers Didn't Expect this Celebrity Guest"

### 2. Copyhackers Formula
"Do [something desirable] like [an expert] without [something expected and undesirable]"
Example: "Make decisions like Starbucks CEO Howard Schultz without Wasting Business Funds"

### 3. Unbounce SEO Formula
"[Adjective] and [Adjective] [What you are/SEO keyword phrase] that will [desirable result]"
Example: "Fast-loading and User-Friendly WordPress Themes That Will Improve Your Rankings"

### 4. SHINE Formula (D Bnonn Tennant/Kissmetrics)
S = Specificity, H = Helpfulness, I = Immediacy, N = Newsworthiness, E = Entertainment value
Example: "The Latest Research from the CDC about Masks That Work Plus Tips to Make Your Own"

### 5. Answer-in-Title Formula (Nat Eliason)
Give the answer right in the title to create curiosity about the reasoning.
Example: "No, Soylent Isn't Healthy. Here's Why" -- increases CTR by sparking curiosity about the why.

### SEO Title Brackets Hack (Maddy Osman)
Append informative brackets to maximize SERP real estate:
- [Infographic], [Video], [Podcast]
- [X% Discount Code]
- [Updated for Month/Year]
- [Template], [Checklist]

### Recency Signals (brightonSEO/Profound)
ChatGPT appends the current year to 20-30% of its fan-out queries. Having the year in your title/H1 significantly increases AI citation probability. Update titles with current year for important pages.

**Implementation rules:**
- Add year to title tags for time-sensitive content (reviews, comparisons, guides)
- Update within the first week of January each year
- Do NOT add year to evergreen content that does not benefit from recency (definitions, how-to basics)
- Consider adding month for rapidly changing topics ("Best CRM Software - March 2026")

---

## Open Graph & Social Meta Tags

### Required OG Tags
- `og:title` -- the social-optimized title (can differ from meta title)
- `og:description` -- social-optimized description (can be more casual/engaging)
- `og:image` -- minimum 1200x630px for optimal display across platforms
- `og:url` -- canonical URL of the page
- `og:type` -- usually "article" or "website"

### Twitter Card Tags
- `twitter:card` -- "summary_large_image" for full-width image display
- `twitter:title` -- can differ from OG title for X/Twitter-specific optimization
- `twitter:description` -- shorter, punchier for Twitter's format

### Cache Clearing After Updates
When updating OG tags, clear platform caches to see changes immediately:
- **Facebook:** Facebook Sharing Debugger (developers.facebook.com/tools/debug/)
- **X/Twitter:** Twitter Card Validator
- **LinkedIn:** LinkedIn Post Inspector

---

## Meta Keywords Tag
**Status: Obsolete.** Google, Yahoo, and Bing no longer use meta keywords for ranking. Skip entirely.

---

## Meta Robots Tag
- `noindex` -- prevents page from appearing in search results
- `nofollow` -- tells Google not to follow links on the page (hint directive)
- `max-snippet:-1` -- allows Google to show any length snippet
- `max-image-preview:large` -- allows large image previews in SERPs
- Default (no tag) = index, follow -- only add meta robots when you need to restrict
