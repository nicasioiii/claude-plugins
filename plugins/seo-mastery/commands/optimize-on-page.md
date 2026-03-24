---
name: "Optimize On-Page"
description: |
  Audit and optimize a single page for its target keyword. Activates on-page-optimization
  and schema-entity-optimization skills. Outputs optimized meta tags, headers, schema JSON-LD,
  image alt text, and internal link suggestions.
---

# /optimize-on-page -- On-Page SEO Optimization Workflow

## Skills Activated
- **on-page-optimization** (primary) -- 20-spot placement framework, meta tags, headers, image SEO
- **schema-entity-optimization** (secondary) -- schema JSON-LD generation and validation

## Invocation
```
/optimize-on-page [article URL or pasted content]
```

## Required Input
Ask the user for:
1. **Article URL or content** -- the page to optimize
2. **Target keyword** -- primary keyword (auto-detect if not provided)
3. **Secondary keywords** -- 2-3 additional keywords (optional)
4. **Business type** -- e-commerce, content site, local service, SaaS (affects recommendations)

---

## Step 1: Audit Current State (5 minutes)

Analyze the page against the 11 priority optimization spots:

| Spot | Current State | Recommendation |
|------|--------------|----------------|
| Meta title | [Extract current] | [Rewrite with keyword front-loaded, <60 chars] |
| Meta description | [Extract current] | [Rewrite with keyword, <160 chars, answer-spoiling for AI] |
| URL slug | [Extract current] | [Clean slug with exact-match keyword, 5-7 words] |
| H1 tag | [Extract current] | [Match meta title closely, front-load keyword] |
| H2 tags (first/last) | [Check keyword presence] | [Add keyword to first and last H2] |
| Introduction | [Check first 100 words for keywords] | [All keywords in first 100 words] |
| Main content | [Check keyword frequency and spread] | [Optimal placement recommendations] |
| Summary | [Check last 100 words] | [All keywords in last 100 words] |
| Image alt text | [Check all images] | [One keyword per image, descriptive] |
| Image file names | [Check naming convention] | [Keyword-hyphens.jpg format] |
| Internal links | [Count and assess anchor text] | [Anchor text ratio recommendations] |

---

## Step 2: Generate Optimized Meta Tags (5 minutes)

### Meta Title (3 options)
Provide three options using different headline formulas:
1. **Direct keyword** -- front-loaded, benefit-driven
2. **Curiosity gap** -- creates information gap
3. **Brackets hack** -- keyword + [Updated 2026] or [Template] or [Checklist]

Rules: under 60 characters, keyword front-loaded, matches H1.

### Meta Description (2 options)
1. **Standard** -- keyword front-loaded, benefit statement, under 160 characters
2. **Answer-spoiling** -- put the answer directly in the meta description for AI citation boost

---

## Step 3: Optimize Header Structure (5 minutes)

Provide recommended header hierarchy:
```
H1: [Primary keyword + compelling modifier]
  H2: [Primary keyword - first section]
  H2: [Secondary keyword 1]
    H3: [Variation/synonym]
    H3: [Variation/synonym]
  H2: [Secondary keyword 2]
  H2: [Question-style for AI extraction (40-60 word answer block)]
  H2: [Primary keyword - summary section (last H2)]
```

Flag any headers that are missing keywords or misordered.

---

## Step 4: Image SEO Recommendations (5 minutes)

For each image on the page:
| Image | Current Alt | Recommended Alt | File Name |
|-------|------------|----------------|-----------|
| Hero | [current] | [keyword, descriptive, <125 chars] | [keyword-hyphens.jpg] |
| Image 2 | [current] | [secondary keyword variation] | [variation-hyphens.jpg] |

Additional: recommend featured image strategy (unique image, text overlay, brand mark).

---

## Step 5: Internal Link Suggestions (5 minutes)

Suggest 3-5 internal links to add:
| Source Location in Article | Link To | Anchor Text | Type |
|---------------------------|---------|-------------|------|
| [Section/paragraph] | [Target page] | [Exact match or filler] | Exact / Partial |

Follow anchor text ratio: ~30% exact, ~60% exact+filler, ~10% partial.

---

## Step 6: Schema Markup (5 minutes)

Generate JSON-LD schema appropriate for the page type:
- **Blog post** -- Article schema with author, datePublished, dateModified
- **Product page** -- Product schema with price, availability, reviews
- **Service page** -- Service or LocalBusiness schema
- **FAQ content** -- FAQPage schema

Provide ready-to-paste JSON-LD code. Include validation instruction: test at schema.org validator + Google Rich Results Test.

---

## Step 7: Priority Fix Checklist

Output a prioritized action list:

### Quick Wins (implement in 30 minutes)
- [ ] Update meta title to: [recommendation]
- [ ] Update meta description to: [recommendation]
- [ ] Fix H1 to: [recommendation]
- [ ] Add missing image alt text

### Medium Priority (implement this week)
- [ ] Restructure headers per recommended hierarchy
- [ ] Add 3-5 internal links with optimized anchor text
- [ ] Add/update schema markup
- [ ] Optimize URL slug (if feasible -- 301 redirect needed)

### Ongoing Monitoring
- [ ] Track rankings in Search Console for 2-3 weeks
- [ ] If not on page 1, add one additional optimization spot per week
- [ ] Do NOT over-optimize beyond competitor level

---

## Expected Results
- Ranking improvement: 1-5 positions typical for pages ranking 5-30
- CTR improvement: 10-30% from meta tag updates
- Rich snippet eligibility from schema implementation
- Time to results: 2-4 weeks for ranking changes
- Total implementation time: 40-60 minutes
