---
name: Amazon SEO Tools & Keyword Research Guide
description: >
  Helium 10 tool guide (X-ray, Cerebro, Magnet, Frankenstein, Scribbles, Listing
  Analyzer), listing image best practices, Search Query Performance Report analysis
  (Brian Johnson method), keyword research workflow, backend keyword optimization
  process, pattern field hack, flat file image URL automation, imagecheck.com
  for AI image interpretation, and Data Dive/Growth Opportunity Explorer usage.
---

# Amazon SEO Tools & Keyword Research Guide

---

## Helium 10 Tool Guide

### X-Ray (Product Research)
- **Purpose:** Analyze competitor products on Amazon search results page
- **Key metrics:** Revenue estimates, BSR, price, review count, review velocity
- **Usage:** Install Chrome extension; activate on any Amazon search results page
- **Limitation:** Per-variation sales data is unreliable (see variation strategy in SKILL.md)

### Cerebro (Reverse ASIN Lookup)
- **Purpose:** Find all keywords a competitor ranks for
- **Process:** Enter competitor ASIN -> get full keyword list with search volume and rank
- **Advanced:** Load top 20 competing ASINs for comprehensive keyword universe
- **Spanish keyword hack:** Export all keywords -> import to Google Sheets -> add detect language formula -> sort by "ES" for Spanish keywords

### Magnet (Keyword Research)
- **Purpose:** Find keywords from a seed term with search volume data
- **Process:** Enter seed keyword -> get related keywords with monthly search volume
- **Use with:** Ritu Java's ChatGPT Seed Keyword Generator for initial seed terms

### Frankenstein (Keyword Processor)
- **Purpose:** Remove duplicate words and compress keyword lists
- **Use for:** Processing backend search terms to fit within 250-byte limit
- **Process:** Paste large keyword list -> tool removes duplicates and unnecessary words

### Scribbles (Listing Builder)
- **Purpose:** Write listing copy while tracking keyword usage in real-time
- **Shows:** Character/byte count, used vs. unused keywords
- **Use:** Build title, bullets, description, and backend while ensuring no keyword is missed

### Listing Analyzer (Competitive Analysis)
- **Purpose:** Analyze competitor listings side-by-side
- **"Media Comparison" feature:** See all competitor image strategies at once
- **Use:** Identify niche image patterns (what's every competitor's 3rd, 4th, last image?)

### Review Insights (Chrome Extension)
- **Purpose:** Extract and analyze competitor reviews
- **Use:** Filter by star rating, extract top complaint phrases
- **Export:** CSV export for analysis or review importing pipeline

### Follow-Up (Automation)
- **Purpose:** Automate "Request a Review" button clicks
- **Trigger:** Set to fire 7 days after delivery
- **100% TOS-safe:** Uses Amazon's built-in review request mechanism

---

## Keyword Research Workflow

### Step 1: Seed Keyword Generation
- **Option A (Manual):** Brainstorm 5-10 seed keywords from product knowledge
- **Option B (ChatGPT -- Ritu Java method):** Ask ChatGPT for top 10 audiences for your product + what keywords each audience uses to search. Plug results into Helium 10 Magnet for volume validation.

### Step 2: Competitor Keyword Mining
- Load top 10-20 competitor ASINs into Helium 10 Cerebro
- Download complete keyword lists with search volume and rank data
- Combine into master spreadsheet

### Step 3: Keyword Sorting (Ritu Java -- ChatGPT Method)
Sort keywords into 4 buckets by search volume x word count:
1. **Generic** (high volume, 1-2 words) -> broad match campaigns, low bid
2. **Broad modifier** (medium volume, 2-3 words) -> moderate bid
3. **Long-tail high volume** (3+ words, >1000 searches) -> exact match campaigns
4. **Long-tail low volume** (3+ words, <1000 searches) -> phrase match campaigns

### Step 4: Semantic Relevance Filtering
Run keyword list through ChatGPT semantic relevance audit (see SKILL.md for exact prompts). Remove keywords that dilute your central topic.

### Step 5: Allocation to Listing Fields
- **Title:** Highest-volume, most relevant keyword (beginning of title)
- **Bullets:** Secondary keywords woven into benefit-focused copy
- **Backend:** Everything that doesn't fit naturally in visible listing
- **Use Scribbles** to build listing while tracking keyword coverage

---

## Backend Keyword Optimization Process

1. Start with master keyword list from Cerebro + Magnet
2. Run through Frankenstein to remove duplicates
3. Remove all keywords already used in title and bullets (saves bytes)
4. Run semantic relevance check (remove irrelevant keywords)
5. Add: misspellings, alternate names, related terms, Spanish translations
6. Check byte count (250 bytes max, not 250 characters)
7. No commas needed between keywords (spaces are sufficient)
8. No need to repeat singular/plural forms

---

## Listing Image Best Practices

### Slot Allocation (7-9 images)
1. **Main image:** White background, product-only, high resolution (Amazon requirement)
2. **Lifestyle image:** Product in real-world use
3. **Infographic:** Key features/benefits with callout text
4. **Size/dimensions:** Scale reference or comparison
5. **Benefits breakdown:** One benefit per section
6. **Social proof:** Review quotes overlaid on product image
7. **Packaging/what's included:** Box contents layout
8-9. **Additional lifestyle or use-case images**

### Image SEO (Leo Sgovio)
- Add target keywords in image text (on infographics)
- Add Photoshop metadata: document title, description, keywords, copyright
- Save filenames with target keywords
- Applies to all images including A+ content

### imagecheck.com
- Shows how Amazon's AI interprets your images
- Reveals what demographics, items, text, and context the algorithm detects
- Use to verify your images communicate what you intend

---

## Search Query Performance Report (Brian Johnson -- BDSS 2025)

### How to Access
Brand Analytics -> Search Query Performance -> Pull ASIN report

### Three Metrics to Track Per Keyword
1. **ASIN impression share %** (pre-calculated by Amazon)
2. **Click-through rate:** ASIN click count / total click count
3. **Relative conversion rate:** (ASIN purchases / ASIN clicks) - (total purchases / total clicks)

### Interpretation
- **Positive delta** on relative conversion = you have an advantage on that keyword -> invest more PPC
- **Negative delta** = fix listing/product for that keyword or abandon it
- About 30 additional ranking factors exist beyond these three

---

## Pattern Field Hack (Bradley Sutton)

- Put main keyword in the backend "pattern" field
- Result: keyword appears in bold in search results
- Easy to implement; gives slight visual edge on SERP
- Access via flat file upload or Listing Fields in Seller Central

---

## Flat File Image URL Automation

For bulk listing updates:
1. Host images on external URL (e.g., S3, Cloudflare)
2. Reference image URLs in flat file columns (main_image_url, other_image_url1, etc.)
3. Upload flat file to bulk update all listing images
4. Useful for seasonal image updates or new image rollouts across multiple ASINs

---

## Amazon Data Tools

### Data Dive
- Available in Seller Central
- Deep product analytics and search term data
- Use for identifying keyword opportunities and gaps

### Growth Opportunity Explorer
- Amazon's built-in niche analysis tool
- Shows search volume trends, competition level, customer demographics
- Identify emerging niches before they become saturated

### Next Gen Selling Dashboard
- Access at amazon.com/amazonsell
- Customizable conversion rate tracking
- More granular than standard Business Reports

---

## Keyword Density Analysis (Leo Sgovio)

### Tools Required
- SEO Quake Chrome extension
- Custom Blocker Chrome extension

### Process
1. Install both extensions
2. Navigate to competitor listing on Amazon
3. Activate Custom Blocker to remove "frequently bought together," "related products," etc.
4. Run SEO Quake's "density" tab on the listing
5. Result: shows competitor's top keywords by frequency and prominence

**Without Custom Blocker:** Data gets skewed by related product widgets -- you see Amazon's cross-sell keywords instead of the competitor's actual listing keywords.

---

## Opportunity Keywords

- Low competition keywords with high win-rate potential
- Found via Cerebro: filter for keywords where competitors rank but have low impression share
- Also found via Search Query Performance: keywords where your relative conversion is high but impression share is low
- These are keywords where you can rank quickly with targeted PPC spend
