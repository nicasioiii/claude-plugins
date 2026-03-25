---
name: CMS Setup Guide
description: "Collection fields, CMS filtering (native + Finsweet), CMS import, blog setup, and CMS-driven component patterns."
---

# Webflow CMS Setup Guide

Complete reference for planning and building CMS-driven content in Webflow.

---

## CMS PLANNING

**Always plan CMS structure before building.** Define all fields upfront -- changing structure after content is populated creates rework.

### Planning Questions
1. What content types does the site need? (Blog posts, team members, case studies, products, FAQs)
2. What fields does each content type require?
3. What relationships exist between content types? (Author -> Blog Post, Category -> Blog Post)
4. How will content be filtered or sorted on the front end?
5. Who will be adding/editing content? (Inform field labels and help text)

---

## COMMON COLLECTION STRUCTURES

### Blog Posts
| Field | Type | Notes |
|-------|------|-------|
| Name (Title) | Plain text | Auto-generated slug |
| Slug | Auto | URL path segment |
| Thumbnail Image | Image | For card displays |
| Main Image | Image | For post header |
| Author | Reference → Authors | Single author |
| Categories | Multi-Reference → Categories | Multiple categories |
| Publish Date | Date | For sorting |
| Body | Rich Text | Main article content |
| Excerpt | Plain text | For cards and SEO |
| Featured | Switch | Toggle for homepage display |

### Authors
| Field | Type | Notes |
|-------|------|-------|
| Name | Plain text | Author display name |
| Photo | Image | Headshot |
| Bio | Plain text | Short description |
| Role | Plain text | Job title |
| Social Links | Link | Optional |

### Categories
| Field | Type | Notes |
|-------|------|-------|
| Name | Plain text | Category label |
| Slug | Auto | URL path |
| Description | Plain text | Optional for category pages |
| Color | Color | For visual distinction |

### Case Studies / Portfolio
| Field | Type | Notes |
|-------|------|-------|
| Name | Plain text | Project title |
| Client | Plain text | Client name |
| Thumbnail | Image | Card display |
| Gallery | Multi-Image | Project images |
| Description | Rich Text | Full write-up |
| Services | Multi-Reference → Services | Tags |
| Year | Number | For sorting |
| Featured | Switch | Homepage display |
| External URL | Link | Live project link |

### Team Members
| Field | Type | Notes |
|-------|------|-------|
| Name | Plain text | Full name |
| Photo | Image | Headshot |
| Role | Plain text | Job title |
| Bio | Rich Text | Description |
| Social Links | Link | LinkedIn, Twitter |
| Order | Number | Custom sort order |

---

## FIELD TYPES REFERENCE

| Type | Use For | Notes |
|------|---------|-------|
| Plain Text | Short strings | Titles, names, slugs |
| Rich Text | Long-form content | Blog posts, descriptions |
| Image | Single image | Photos, thumbnails |
| Multi-Image | Image galleries | Portfolio, product shots |
| Video | Video embed | URL-based |
| Link | URLs | External links |
| Email | Email addresses | Contact info |
| Phone | Phone numbers | Contact info |
| Number | Quantities, ordering | Sort values, prices |
| Date/Time | Dates | Publish dates, events |
| Switch | Boolean toggle | Featured, active, etc. |
| Color | Hex color values | Category colors, tags |
| Reference | Single relationship | Author → Post |
| Multi-Reference | Multiple relationships | Categories → Post |

---

## CMS FILTERING

### Native Webflow Tabs (Simple)
- Each tab represents a category
- Tab content shows filtered collection list
- Limited to one filter dimension
- Good for: category pages with few categories

### Finsweet CMS Filter (Advanced)
- **Free** and extremely powerful
- Multi-filter (combine multiple filter criteria)
- Search within collection
- Sort by any field
- Pagination
- URL-based filters (shareable filtered views)
- Setup via custom attributes on elements

### Finsweet Filter Setup Pattern
```
Wrapper:     fs-cmsfilter-element="list"
Filter btn:  fs-cmsfilter-field="category"
             fs-cmsfilter-value="Design"
Clear btn:   fs-cmsfilter-element="clear"
Search:      fs-cmsfilter-element="search"
Empty state: fs-cmsfilter-element="empty"
```

### Finsweet CMS Sort
- Add `fs-cmssort-field` attribute to sort trigger elements
- Supports ascending/descending toggle
- Combine with filters for powerful collection views

---

## CMS CONTENT IMPORT

### For Large Datasets (50+ items)
1. Prepare data in Airtable or CSV format
2. Use **CMS Bridge** to import into Webflow
3. Map fields between source and Webflow collection
4. Batch import saves enormous time vs. manual entry

### Image Import Workflow
1. Export ALL images from Figma at 2x resolution
2. Compress using Cloud Convert in one batch
3. Upload to Webflow organized by category
4. Reference in CMS items via image field

---

## CMS SLIDER WORKAROUND

Webflow's native slider does not support CMS binding.

**Solutions:**
1. **Finsweet CMS Slider** -- free, attribute-based, works with collection lists
2. **Custom code** -- JavaScript carousel libraries (Swiper.js, Splide)
3. **Webflow Tabs + CMS** -- use tabs styled as slider (limited to fixed number)

---

## URL STRUCTURE

### Default Patterns
```
Blog posts:     /blog/[slug]
Categories:     /category/[slug]
Authors:        /author/[slug]
Case studies:   /work/[slug]
```

### URL Best Practices
- Keep slugs short and keyword-rich
- Use hyphens between words (not underscores)
- Pre-configure URL structures in starter project
- Verify no "copy-of-" or "-1" artifacts in slugs

---

## CMS PAGE TEMPLATES

### Collection Pages
- Each collection gets a template page
- Template uses dynamic fields from the collection
- Design once, applies to all items

### Multiple Templates Per Collection
- Create alternate templates for different item types
- Example: "Product - Standard" vs "Product - Featured"
- Assign template per item in CMS editor

### Template Design Tips
- Include breadcrumbs for navigation context
- Add "related items" section (prevents dead-end pages)
- Include social sharing links
- Test with items of varying content length (short vs. long descriptions)
