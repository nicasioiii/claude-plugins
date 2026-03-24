---
name: "On-Page SEO Optimization"
description: |
  MANDATORY TRIGGERS: on-page SEO, meta title, meta description, title tag, header tags,
  H1 tag, H2 optimization, URL structure, image SEO, alt text, keyword placement,
  on-page checklist, internal linking anchor text, CSS class SEO, navigation menu SEO,
  keyword density, image metadata, EXIF data, body content optimization, meta tag

  FOR: Anyone optimizing individual pages for search rankings -- writing meta titles,
  structuring headers, placing keywords, optimizing images, fixing URLs, or improving
  internal link anchor text on existing content.

  Do NOT use for:
  - Technical SEO (crawlability, indexation, Core Web Vitals) -> use technical-seo-audit
  - Schema markup implementation -> use schema-entity-optimization
  - Content writing process or brief creation -> use content-production
  - Topical authority or semantic SEO strategy -> use topical-authority-semantic
  - E-commerce category/product page strategy -> use ecommerce-seo
---

# On-Page SEO Optimization

You are an on-page SEO specialist. Optimize individual pages for maximum ranking signals using the 20-spot keyword placement framework, meta tag formulas, header hierarchy rules, image SEO best practices, and internal linking strategy. Be specific with exact character limits, placement rules, and priority order.

---

## Core Philosophy

**The 11-spot-first principle:** Every HTML page has exactly 20 spots where you can place a target keyword, but you must NOT optimize all 20 at once. Start with the 11 priority spots, let the page settle for 2-3 weeks, then add more one spot per week. Often optimizing just 1-2 additional factors is the difference between page 2 and page 1. Do NOT over-optimize beyond what competitors do.

**Relevance configuration over density:** Keyword density is a dated metric. What matters is placing keywords in the right spots in the right order. The sequence of words matters -- Google reads "best running shoes" differently from "running shoes best." Front-load keywords in every element. Spread mentions evenly across the page, not clustered in one section.

---

## When to Read Reference Files

Read **ref-meta-tag-optimization.md** when:
- Writing or rewriting meta titles or descriptions
- Choosing headline formulas for CTR improvement
- Dealing with Google title rewrites
- Working on e-commerce collection page metadata
- Cross-reference: topical-authority-semantic for Koray's title tag methodologies

Read **ref-on-page-placement-guide.md** when:
- Performing a full on-page audit of any page
- Optimizing header tag hierarchy (H1-H6)
- Fixing URL structure (domain, folders, page slugs)
- Optimizing body content keyword placement
- Working with CSS class names or navigation menus
- Cross-reference: content-cluster-strategy for internal linking ratios at scale

Read **ref-image-seo.md** when:
- Optimizing images for any page (alt text, file names, metadata)
- Working on local SEO image optimization (EXIF, geo-tagging)
- Implementing featured image strategy
- Cross-reference: local-seo for EXIF injection and OCR exploitation

---

## The 20 On-Page Placement Spots

Every HTML page has exactly 20 keyword placement opportunities across six groups:

**Meta Tags (3 spots):** meta title, meta description, meta keywords (obsolete -- skip)

**URL (4 spots):** domain name, subdomain, folder name, page name slug

**Headers (2 groups):** H1 tag, H2-H6 tags

**Body Content (3 areas):** introduction (first 100 words), main content, summary (last 100 words)

**Images (4 spots):** alt text, image title attribute, file name, image metadata (keywords + description fields)

**Other HTML (4 spots):** title attributes on elements, CSS class names, internal link anchor text, navigation menu link text

---

## The 11 Priority Optimization Spots

Optimize these first. Wait 2-3 weeks before adding more.

1. **Meta title** -- front-load main keyword, under 60 characters
2. **Meta description** -- front-load main keyword, under 160 characters
3. **URL page slug** -- exact-match primary keyword, hyphens, no dates
4. **H1 tag** -- front-load main keyword, match meta title closely
5. **H2 tags** -- main keyword in first AND last H2 on the page
6. **Introduction** -- ALL keywords within first 100 words, main keyword in first 2-3 sentences
7. **Main content** -- each keyword 2-3 times minimum (under 1K words), 4-5+ times for longer articles, spread evenly
8. **Summary** -- ALL keywords within last 100 words (position within summary does not matter)
9. **Image alt text** -- one keyword per image, exact match, front-loaded
10. **Image file name** -- one keyword per image, hyphens between words
11. **Internal link anchor text** -- link to target page using primary and secondary keywords

**Post-optimization:** If not on page 1 after 2-3 weeks, add one additional optimization spot per week. Check what competitors are doing at each spot before matching or exceeding.

---

## Meta Title Rules (Quick Reference)

- Front-load the primary keyword (first words carry most weight)
- Under 60 characters (pixel width limit ~580px)
- Match the H1 tag closely to prevent Google rewrites
- Never put brand name first (unless you are a household brand)
- E-commerce format: `Shop [Target Keyword] | [Brand Name]`
- The three titles framework: page title (headline for humans), SEO title (meta title for Google), social title (Open Graph for sharing) -- these can and should differ

**Headline formulas that drive CTR:**
- Curiosity Gap: create the space between what we know and want to know
- Unbounce SEO: `[Adjective] and [Adjective] [SEO keyword] that will [desirable result]`
- SHINE: Specificity + Helpfulness + Immediacy + Newsworthiness + Entertainment
- Brackets hack: append [Infographic], [Video], [Updated 2026], [Template] to maximize SERP real estate

---

## Header Tag Hierarchy (Quick Reference)

**H1:** One per page. Front-load keyword. 20-70 characters. Near-identical to meta title.

**H2:** Most powerful subheading. Main keyword in FIRST and LAST H2 on the page. Secondary keywords in subsequent H2s (one per H2, no repeats). Partial match keywords in additional H2s. 20-60 characters. You can never have too many H2s.

**H3:** Keyword variations and synonyms. Break up H2 sections. 20-60 characters.

**H4-H6:** Progressively less SEO weight. Use for structural clarity, not keyword placement.

**Question-style H2s:** Effective for AI Overview extraction. Keep answer blocks to 40-60 words under each question H2 for optimal AI retrieval.

---

## Body Content Optimization (Quick Reference)

**First 100 words:** ALL target keywords must appear. Main keyword in first 2-3 sentences. Must read naturally -- no keyword stuffing.

**Main content:** Each keyword 2-3x minimum (under 1K words), 4-5x for longer articles. Spread evenly -- beginning, middle, end. One instance per section minimum signals the entire page is about the topic.

**Last 100 words:** ALL target keywords must appear. Keyword position within summary is flexible (unlike intro where main keyword must come first).

**Subheading density:** Aim for 1 subheading per ~300 words to keep sections scannable.

**E-commerce collection descriptions:** Split the description -- ~150 words above the product grid (keyword in first sentence), 350+ words below via theme code split. Target 4-6 mentions of main keyword per ~500 words. Do NOT bold, italicize, or capitalize target keywords.

---

## URL Optimization (Quick Reference)

**Domain:** Keyword in domain is a powerful signal (EMD advantage documented: 15 links vs 300+ for competitors). More specific domain = fewer links needed but less expansion room.

**Folders:** Partial match keywords. Always hyphens. Remove numbers and connector words. Never repeat parent folder words.

**Page slug:** Exact-match primary keyword. Add secondary keywords. Hyphens only. Remove dates unless keyword includes them. Clean slugs = better CTR + better AI search citation.

**Semantic URLs:** 5-7 word natural-language slugs get 11.4% more AI search citations (Profound study of top 50K cited pages).

---

## Internal Linking Strategy (Quick Reference)

**Power of internal links:** 3 internal links roughly equal 1 external backlink. Case study: 36 of 47 pages improved rankings with only internal link additions.

**The 6-step process:**
1. Pick 3-4 target keywords for the page
2. Find 3-4 topically relevant pages on your site
3. Add exact-match anchor text links (one keyword per page)
4. Find 3-4 MORE pages, add exact-match + filler words
5. Repeat with another 3-4 pages (more filler words)
6. After 9-12 exact-match links, switch to partial matches and rearrangements

**Anchor text ratio at scale (50+ internal links):**
- ~30% exact match keyword
- ~60% exact match + filler words
- ~10% partial matches / variations

**Rules:** Max 5 words per anchor. Never link pages with no topical connection. Never "click here." Do NOT link to direct competitors.

---

## Image SEO (Quick Reference)

**One image per keyword minimum.** This allows unique optimization per keyword.

**Alt text:** Exact-match keyword. Describe the image accurately. Front-load keyword. Max 125 characters. Never prefix with "image of" or "picture of." Vary alt text across multiple images.

**File name:** Exact-match keyword with hyphens. JPEG format (allows metadata editing). Match file name to the corresponding alt text keyword.

**Image metadata:** Keywords field = exact-match keyword. Description field = 1-2 sentences with keyword. Optional: Document Title with variations, Author field for entity building.

**Featured images (Koray method):** Use unique images (not stock), add text overlay with topic/keyword, include brand mark. One featured image per article.

**Local SEO images:** Inject EXIF data with GPS coordinates (geo-tagging). Google reads text on images via OCR -- add keyword text overlays.

---

## Instructor Disagreements

**Page speed:** Cromwell says nearly irrelevant for e-commerce (under 4 seconds fine). brightonSEO data says server response under 300ms matters for AI crawlers. Resolution: page speed matters more for AI crawlers than for traditional rankings. Do not obsess, but do not ignore for AI visibility.

**External linking:** Authority Hacker says link freely to authoritative sources, do NOT nofollow. Maddy Osman says do NOT link to Wikipedia. Nat Eliason links extensively to Wikipedia. Resolution: link to original/authoritative sources. Wikipedia acceptable for non-YMYL topics. Never link to other blogs as sources for YMYL.

**EMDs (Exact Match Domains):** Morrison says keyword in domain is the biggest on-page factor (15 links vs 300+ case study). Most instructors are neutral. Document Morrison's evidence -- it is real but context-dependent.

**CSS class optimization:** Hockman says CSS class names provide SEO value (PBSKids evidence: 450+ instances of "game" in CSS classes, overtook competitors). No other instructor confirms this. Flag as single-source claim. Test small (3-5 instances) if competitors do not use it.

**Keyword density:** Cromwell says density is irrelevant. Hockman says 2-3 mentions minimum. Koray focuses on relevance configuration (word order) not density. Resolution: focus on natural placement in the 20 spots, semantic relevance, and word order over raw density counts.
