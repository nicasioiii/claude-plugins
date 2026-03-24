---
name: "Local SEO & Google Business Profile"
description: >
  MANDATORY TRIGGERS: local SEO, Google Business Profile, GBP, GMB, Google My Business,
  citations, NAP consistency, local ranking, map pack, rank and rent, local reviews, GBP posting,
  local citations, location pages, EXIF data, geo-tagging, local link building.
  FOR: Optimizing a Google Business Profile for map pack rankings. Building a local SEO strategy
  for service businesses. Creating a GBP posting calendar and content strategy. Building citations
  and maintaining NAP consistency. Implementing image SEO with EXIF injection and OCR. Setting up
  rank and rent lead generation assets. Building syndication tiers for local authority.
  Do NOT use for: E-commerce product/category optimization (use ecommerce-seo), programmatic
  location pages at scale (use directory-programmatic-seo), general link building tactics
  (use link-authority-building), directory site building (use directory-programmatic-seo),
  GA4 analytics setup (use seo-analytics-reporting).
---

# Local SEO & Google Business Profile

## Core Philosophy

Local SEO is dominated by three building blocks: Name, Address, Phone Number (NAP). Everything else amplifies these signals. The Google Business Profile is the single most important asset for local ranking -- invest more time in GBP optimization than in website-only SEO.

**Contrarian insight (Jacky Chou):** Google is pushing organic local SERP results to page 2 with double map pack layouts. Organic rankings for local keywords are dying. Invest in GBP, not just website SEO.

## Local SEO Ranking Factors (Order of Importance)

1. NAP consistency / citations
2. Location proximity to searcher
3. Reviews (quantity + quality)
4. GBP optimization (posts, photos, categories)
5. CTR signals
6. Organic website SEO (supports but secondary)

## Google Business Profile Optimization

### Primary Keyword Foundation
Formula: **Service Keyword + Location Modifier** (e.g., "Carpet Cleaning Madison WI"). Do not get creative -- match core service to city. The difference between page-two obscurity and top-three map pack often comes down to this alignment.

### Secondary Keyword Engine
Build a list of secondary keywords as your content engine for GBP posts. Target variations like "rug cleaning" or "stain removal" instead of repeating the primary keyword. Develop monthly content silos -- one secondary keyword per post.

**Six sources for secondary keywords:**
1. SEMrush -- filter by relevance not just volume
2. "People Also Search For" on Google
3. Google Search Console -- export CSV, isolate service+location keywords
4. GBP Performance Data -- "How people discovered you" section
5. Google Trends -- input core service WITHOUT location modifier
6. Google Keyword Planner -- sort by Top of Page Bid (high CPC = commercial intent)

### GBP Posting Strategy
**Minimum 5 posts/week (~20/month).**
- "What's New" posts: 3-5/week (daily workhorses, target secondary keywords)
- Event posts: 1 every 1-2 weeks (don't expire if set correctly)
- Offer posts: 1 every 1-2 weeks (drive immediate conversions)

Event and Offer posts must target the same primary service keyword as the current "What's New" silo.

### "What's New" Post Copy Anatomy (6 Elements)
1. Headline with keyword at top
2. Layer secondary terms naturally
3. State brand name explicitly
4. Include owner's name (entity signals)
5. Target location (city + neighborhood/locality)
6. Anchor to Points of Interest (reference nearby landmarks)

Use TopicalRelevance.com for related entities. Google recognizes emojis as valid entities -- use sparingly. Never put phone number in post body (policy violation -- use CTA buttons).

### Umbrella Silo Strategy (Interlinking)
**The Loop (Spokes):** Link Post 1 -> Post 2 -> Post 3 -> ... -> back to Post 1.
**The Money Link (Hub):** Every post links to the SAME target service page via CTA button. CTA button is the only do-follow link.
Do NOT interlink Event or Offer posts -- treat as standalone signals.

> See `ref-gbp-optimization.md` for complete GBP optimization details.

## Image SEO for Local

### OCR Exploitation
Google uses OCR to read text within images -- most competitors overlook this. Add keyword overlays using bold, clear sans-serif fonts. Inject primary service keyword + location directly onto image.

### EXIF Data Injection
EXIF data is the hidden "DNA" -- GPS coordinates and timestamps validate physical location. Use TheExifer.com to populate target keyword, NAP, persona name, website URL, and hardcode GPS coordinates.

### File Metadata & Geo-tagging
Right-click > Properties > Details: populate Title, Subject, Tags with primary keywords, NAP, persona name. For AI/web-sourced images: use GeoSetter tool to add latitude/longitude, city, neighborhood.

### File Naming Rules
- Never upload "IMG1234.jpeg"
- Rename to keyword (e.g., carpet-cleaning-madison-wi.jpg)
- Use hyphens (read as spaces); avoid underscores

## Citations & NAP Consistency

### Citation Building Process (Jacky Chou)
1. Buy 50 citations for $5 (Fiverr). Index via Telegram indexer (SpeedyIndexBot).
2. Wait 2 weeks.
3. ~50% of local SEO campaigns need only citations.
4. Optional: 200 PBN citations per batch (90%+ indexation rate).
5. Optional: Guest posts (only for highly competitive terms).

**PBN citations:** Include NAP + naked URL + description matching GMB + AI-generated content. Never point PBNs directly to money site -- use only for tiering citations.

**Citation URL risk levels:** Low = naked URLs. Medium = nofollow links. High = dofollow (not recommended for organic side).

### Location Proximity
Direct correlation between GMB location and searcher distance. Options: own office, co-working space, purchased GMB location ($200-$400, risky). In low-competition niches, you can rank from 40+ km away.

> See `ref-local-ranking-factors.md` for reviews, CTR manipulation, rank and rent, and monthly workflow.

## Reviews Strategy

**White hat:** Always prompt clients. Use review funneler (QR code -> landing page; 4+ stars -> Google review, 3 or fewer -> contact form). Always follow up with low-star reviewers.

**Gray hat:** Offer gift/incentive for 5-star review (comp drinks, keychain, raffle entry).

**Value of a 5-star review: approximately $10-$20.**

## Rank and Rent Model

### Setup
- EMD domains work best (e.g., vancouverrealtor.com)
- WordPress only. CTA above fold on mobile and desktop.
- Buy 50 citations for $5. DO NOTHING for 4 weeks.
- Expected: position ~20 or top 10 within 4 weeks for non-competitive keywords.
- Only buy backlinks if not top 10 after 8 weeks.

### Pricing Formula
Search Volume x CTR x Form Fill Rate x Lead-to-Client Ratio x AOV x Margin x Your Cut

### Cold Email Pitching
Use burner domain (not main). Short copy: "I rank on the front page for [keyword]. Would you be interested in position one?" 2% reply rate typical.

## Cross-References

- For e-commerce product/category optimization -> `ecommerce-seo`
- For programmatic location pages at scale -> `directory-programmatic-seo`
- For general link building tactics -> `link-authority-building`
- For PBN citations -> `pbn-advanced-link-strategy`
- For Casey Keith's local internal link trick -> `topical-authority-semantic`
- For Google Stacking entity reinforcement -> `schema-entity-optimization`

## Reference Files

- `ref-gbp-optimization.md` -- GBP primary/secondary keywords, posting strategy, post copy anatomy, umbrella silo, image SEO, Google ecosystem linking, external property syndication
- `ref-local-ranking-factors.md` -- NAP consistency, citation building, proximity, reviews, CTR manipulation, rank and rent, ranking factors hierarchy, syndication tiers, monthly workflow
