# Internal Linking Checklist

Master internal linking strategy to distribute authority throughout your site, guide Google's crawl path, and create topical signals that improve rankings across your content.

## Why Internal Linking Matters

**Ranking Factor**: Yes - one of top 3 ranking factors (along with content quality and backlinks)
**Authority Flow**: Links flow PageRank through your site, strengthening target pages
**Crawl Efficiency**: Guides Google's crawler to important pages, ensuring they're indexed and refreshed
**Topic Signals**: Clustered internal links signal topical authority to Google

## The Three Purposes of Internal Linking

### 1. Authority Distribution
- Home page has highest authority (most backlinks)
- Internal links pass authority from high-authority pages to important target pages
- Target pages: Money pages (products, main services), pages you want to rank

### 2. Topical Clustering
- Linking related articles together signals they're part of same topic
- Google recognizes topic clusters and ranks entire cluster higher
- Example: Link all "retirement" articles to each other + to main retirement buying guide

### 3. Navigation
- Help users discover related content
- Reduce bounce rate by keeping visitors on site longer
- Improve engagement signals

## Internal Linking Fundamentals

### Link Juice & PageRank Flow

**How It Works**:
```
Homepage (high authority)
  → About page (moderate authority)
    → Blog post (receives authority from internal link)
      → Money page (receives authority from blog link)
```

**Key Principle**: Number of links out + relevance of linked pages determines authority passed

**Example**:
```
Homepage has 100 units of authority
- Links to 5 pages equally = 20 units each
- Links to 1 page = 100 units to that page

Better: Link to money pages from home, less to secondary pages
```

### Anchor Text Strategy

**What Anchor Text Is**: The visible text of a link (the words you click)

**Example**:
```html
<a href="/sunscreen-buying-guide/">best sunscreen for sensitive skin</a>
              ↑ URL                  ↑ Anchor text (visible, clickable)
```

**Anchor Text Signals What Page Is About**:
- Link with anchor "natural sunscreen" tells Google target page is about natural sunscreen
- Link with anchor "click here" tells Google nothing
- Link with exact keyword is strongest signal

**Best Practices**:
- **Descriptive**: Tells user what they'll find ("best running shoes" not "read more")
- **Relevant**: Anchor text matches target page topic
- **Concise**: 3-5 words maximum (not 10-word sentences)
- **Varied**: Don't use same anchor text for every link to same page

**Examples**:

For page about "natural sunscreen":
```
✓ GOOD: "best natural sunscreen for sensitive skin"
✓ GOOD: "reef-safe sunscreen options"
✓ GOOD: "non-nano zinc oxide benefits"
✓ OKAY: "our sunscreen guide"
✗ BAD: "click here"
✗ BAD: "sunscreen sunscreen sunscreen" (keyword stuffing)
```

### Link Placement Best Practices

**In Context**: Link should appear naturally within related content
```html
✓ GOOD:
"While mineral sunscreen works well, you might also consider
<a href="/natural-sunscreen-guide/">natural sunscreen options</a> that don't use chemicals."

✗ BAD:
[Entirely unrelated paragraph]
<a href="/natural-sunscreen-guide/">Click here for sunscreen</a>
```

**Multiple Locations**: Link same page from multiple relevant pages
```
Money page: "Natural Sunscreen SPF 30"
  ← Blog post 1: "Best Sunscreen for Sensitive Skin"
  ← Blog post 2: "Reef-Safe Sunscreen Guide"
  ← Blog post 3: "Chemical-Free Skincare"
  ← Category/pillar page: "Natural Skincare"
```

**Depth**: Link from 2-5 different pages (not just homepage)
- Homepage link is strongest
- Secondary pages still pass authority
- Multiple sources = stronger signal

**Timing**: Add internal links naturally as you create new content
- Don't add links that feel forced
- Link to pages that genuinely help reader
- Better to have no link than irrelevant link

## Internal Linking Audit Workflow

### Step 1: Map Your Content Hierarchy

**Create Spreadsheet Columns**:
- Page URL
- Page Type (money/blog/pillar)
- Primary Keyword
- Related Pages (topics that naturally connect)

**Example**:
```
URL: /best-sunscreen-for-sensitive-skin
Type: Money Page (Commercial)
Keyword: best sunscreen for sensitive skin
Related Pages:
  - /natural-sunscreen-guide/ (pillar)
  - /reef-safe-sunscreen/ (topic)
  - /ingredients-to-avoid/ (supporting)
```

### Step 2: Identify Linking Opportunities

**Use Site: Search in Google**:
1. Search: `site:yourdomain.com [keyword/topic]`
2. Find all pages mentioning that topic
3. Identify which should link to which

**Example for "natural sunscreen"**:
```
site:yourdomain.com natural sunscreen
Results:
- /natural-sunscreen-guide/ (pillar page - should receive multiple links)
- /best-sunscreen-for-sensitive-skin/ (money page - should link out to pillar)
- /reef-safe-sunscreen-benefits/ (blog - should link to pillar and money page)
- /ingredient-deep-dive/ (blog - supporting, should link to pillar)
```

**Use Ahrefs Site Audit → Link Opportunities**:
1. Run site audit
2. Filter for pages in "50-100" ranking positions
3. See which internal page could link to boost ranking
4. Example: Page ranking #47 for keyword, boost with homepage + 2 blog links = move to #15-20

### Step 3: Create Linking Map

**Visual Hierarchy**:
```
Homepage (links to all top-level pages)
  ├─ Pillar Page: Natural Skincare
  │   ├─ Money Page 1: Natural Sunscreen SPF 30
  │   │   ← Blog Post: Reef-Safe Benefits
  │   │   ← Blog Post: Sensitive Skin Solutions
  │   ├─ Money Page 2: Natural Moisturizer
  │   │   ← Blog Post: Benefits of Natural Ingredients
  │   └─ Supporting Blog: Ingredient Deep Dive
  └─ Blog Hub: Skincare Tips
      ├─ Blog Post: Anti-Aging Routine
      └─ Blog Post: Budget Skincare
```

**Linking Rules**:
- Homepage links to pillar pages only (high-level categories)
- Pillar pages link to money pages + related blog
- Money pages link to pillar (parent) + supporting blogs
- Blog posts link to pillar + money pages (authority flow upward)

### Step 4: Implementation Checklist

**For Each Money Page**:
- [ ] Homepage links to it (highest priority)
- [ ] 3-5 related blog posts link to it
- [ ] Uses strong keyword anchor text
- [ ] Links appear naturally in content
- [ ] 15-30% of internal links are to money pages (rest to supporting content)

**For Each Blog Post**:
- [ ] Links to pillar/category page (parent)
- [ ] Links to 2-3 money pages contextually
- [ ] Links to 1-2 other blogs (related topics)
- [ ] Anchor text is descriptive and varies

**For Pillar/Category Pages**:
- [ ] Linked from homepage
- [ ] Receives links from all money pages (internal links back up)
- [ ] Receives links from supporting blog content
- [ ] Has internal navigation/menu linking to subtopics

## Internal Linking Strategies by Content Type

### Strategy 1: Hub & Spoke (Topic Clusters)

**Structure**: Pillar page (hub) linked to by multiple blog posts (spokes)

```
Pillar Page: "Complete Guide to Natural Skincare"
  ← Blog 1: "10 Natural Skincare Ingredients to Know"
  ← Blog 2: "DIY Natural Face Masks"
  ← Blog 3: "Budget Natural Skincare Routine"
  ← Blog 4: "Natural Skincare for Acne"
```

**Why It Works**:
- Google recognizes topic authority (pillar + 4 supporting articles)
- All related articles link back to pillar, boosting its ranking
- Pillar becomes primary page for broad keyword
- Spokes rank for specific long-tail variations

**Implementation**:
1. Create comprehensive pillar page
2. Create 4-8 blog posts on specific angles of topic
3. Have each blog link back to pillar (natural context)
4. Have pillar link to each blog in intro/summary
5. Result: Topic cluster that ranks for entire topic family

### Strategy 2: Money Page Amplification

**Goal**: Push authority to highest-converting pages

```
Homepage → Pillar → Money Page (Product/Service)
                 ↓ (direct link)
           Blog Post 1
                 ↓
           Money Page (receives authority)
                 ↓
           Blog Post 2
                 ↓
           Money Page (receives authority)
```

**Implementation**:
1. Identify top 3-5 money pages (highest revenue potential)
2. Create content that naturally links to them
3. Homepage deep links (not just to pillar)
4. Multiple blogs link using keyword anchor text
5. Result: Concentrated authority flow to revenue pages

**Example - E-commerce Site**:
```
Homepage links to: Best Sunscreen Collections

Blog: "Best Sunscreen for Sensitive Skin"
  → Links to: Best Reef-Safe Sunscreen (money page)
  → Links to: Best Mineral Sunscreen (money page)

Blog: "Reef-Safe Sunscreen Benefits"
  → Links to: Best Reef-Safe Sunscreen (money page)

Result: Money page receives 3-4 contextual links from high-quality blog content
```

### Strategy 3: Supporting Content Network

**Goal**: Create web of internal connections supporting main pages

```
Money Page 1: Product A
  ← Blog: How to Use Product A
  ← Blog: Product A vs. Competitor
  ← Blog: Case Study with Product A

Money Page 2: Product B
  ← Blog: How to Use Product B
  ← Blog: Product B Benefits
  ← Blog: Customer Stories with Product B
```

**Implementation**:
1. For each money page, create 3-4 supporting blog posts
2. Each blog post naturally links to money page
3. Money page links back to all supporting blogs
4. Create topical authority across related content
5. Result: Comprehensive content ecosystem

## Advanced Internal Linking Tactics

### Tactic 1: Contextual Links in Body Text (Highest Value)

**Why It's Best**:
- More valuable than footer/sidebar links
- Appears within relevant context
- Users actually click (higher engagement)
- Google weights contextual links highest

**Implementation**:
```html
WITHIN RELEVANT PARAGRAPH:
"When selecting sunscreen, many people overlook reef-safe options.
In fact, <a href="/reef-safe-sunscreen/">reef-safe sunscreen</a>
is becoming increasingly important for ocean health."
```

### Tactic 2: Breadcrumb Navigation

**Structure**: Home > Category > Subcategory > Page

```html
<nav>
  <a href="/">Home</a> >
  <a href="/natural-skincare/">Natural Skincare</a> >
  <a href="/sunscreen/">Sunscreen</a> >
  <span>Best Sunscreen for Sensitive Skin</span>
</nav>
```

**Benefits**:
- Google understands site hierarchy
- Schema markup for breadcrumbs boosts SERP appearance
- Users can navigate up hierarchy
- Passes authority through path

### Tactic 3: Related Articles / Suggested Reading

**At End of Articles**:
```html
<h3>Related Articles:</h3>
<ul>
  <li><a href="/reef-safe-sunscreen/">Reef-Safe Sunscreen Options</a></li>
  <li><a href="/ingredient-deep-dive/">Common Sunscreen Ingredients</a></li>
  <li><a href="/best-sunscreen-sensitive-skin/">Best Sunscreen for Sensitive Skin</a></li>
</ul>
```

**Benefits**:
- Keeps users on site longer
- Passes authority to related pages
- Improves engagement signals
- Helps Google discover new content

### Tactic 4: Update Old Content with New Links

**Powerful Tactic**:
1. Find old, high-authority pages (get lots of backlinks)
2. Update with links to newer/important pages
3. Authority flows from old content to new
4. Faster ranking for new content

**Example**:
- Your "Natural Skincare Guide" ranks #1 with 50 backlinks
- Create new "Best Sunscreen" page
- Add link to new page from Natural Skincare Guide
- New page gets authority boost from 50 backlinks → ranks faster

### Tactic 5: Keyword-Rich Anchor Text Variation

**Important**: Vary anchor text to avoid over-optimization

**Example - Links to Same Page, Different Anchor Text**:
```
Article 1: "See our guide to <a href="/natural-sunscreen/">natural sunscreen</a>"
Article 2: "Check out our <a href="/natural-sunscreen/">reef-safe sunscreen options</a>"
Article 3: "We also cover <a href="/natural-sunscreen/">sunscreen for sensitive skin</a>"
Article 4: "Related: <a href="/natural-sunscreen/">our sunscreen buying guide</a>"

Result: Page receives signals for multiple keyword variations
```

## Common Internal Linking Mistakes

**Mistake 1: No Internal Links**
```
❌ WRONG: Write article, publish, no internal links at all
✓ CORRECT: 3-5 contextual internal links per article
```

**Mistake 2: All Links Go to Homepage**
```
❌ WRONG: Every link points to home page only
✓ CORRECT: Homepage + 40% to money pages, 30% to category, 30% to other blogs
```

**Mistake 3: Linking to Wrong Pages**
```
❌ WRONG:
Article about "natural sunscreen" links to unrelated "hair care" page

✓ CORRECT:
Article about "natural sunscreen" links to "sunscreen guide", "ingredient guide", "reef-safe options"
```

**Mistake 4: Keyword Stuffing in Anchor Text**
```
❌ WRONG:
"Click here for our natural sunscreen natural sunscreen guide reef safe sunscreen"

✓ CORRECT:
"Check out our <a href="#">reef-safe sunscreen guide</a>"
```

**Mistake 5: Too Many Links in One Article**
```
❌ WRONG: 15-20 internal links per article (looks spammy)
✓ CORRECT: 3-5 internal links per 1000 words (natural, user-focused)
```

**Mistake 6: Linking to Poor Quality Pages**
```
❌ WRONG: Linking to thin, 100-word pages with no value
✓ CORRECT: Only link to pages with substantial content (500+ words) that help reader
```

## Internal Linking Audit Checklist

- [ ] Money pages receive 3-5+ contextual internal links each
- [ ] Money pages receive links from homepage or main navigation
- [ ] Blog posts link to pillar/category pages (parent content)
- [ ] Pillar pages link back to supporting blog content
- [ ] Anchor text is descriptive (not "click here")
- [ ] Anchor text varies (not identical for all links to same page)
- [ ] Links are contextual (appear within relevant content)
- [ ] No over-optimization (not 20 links per page)
- [ ] No links to thin/poor quality pages
- [ ] Breadcrumb navigation implemented (if applicable)
- [ ] Related articles section on key pages
- [ ] No broken internal links (404s)
- [ ] Topical clusters are properly linked
- [ ] 3-5 internal links per 1000 words (typical ratio)

## Tools for Internal Linking Audits

- **Ahrefs Site Audit** - Shows link opportunities, internal link structure
- **Screaming Frog** - Crawl site, visualize internal linking structure
- **Google Search Console** - See how pages are linked internally
- **SEMrush** - Internal linking report
- **Yoast SEO** - Suggests internal linking opportunities within WordPress
- **Google Sheets** - Manual audit spreadsheet for custom linking strategy

## Expected Outcomes

- **Ranking Improvement**: 1-3 positions for money pages with authority concentration
- **Discovery**: Better crawl and indexation of new pages
- **Topical Authority**: Google recognizes topic clusters, ranks entire cluster higher
- **User Engagement**: 15-25% increase in pages per session with good internal navigation
- **Time Investment**: 1-2 hours to audit, 1-2 hours to implement changes across 20-50 pages
