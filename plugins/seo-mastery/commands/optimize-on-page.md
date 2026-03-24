---
name: Optimize On-Page
description: "Generate on-page SEO elements for an existing article. Input article URL or content, output meta tags, schema markup, internal link suggestions, and optimization checklist."
---

# Optimize On-Page Command

Generates on-page SEO optimization elements for any existing article.

## Usage

```
/optimize-on-page [article-url-or-content]
```

## Parameters

- `article` (required): Either URL of live article OR paste article content
- `target-keyword` (optional): Primary keyword to optimize for (auto-detected if not provided)
- `include-schema` (optional): true/false - generate schema markup (default: true)
- `include-links` (optional): true/false - suggest internal links (default: true)

## What It Does

1. **Analyzes Existing Content**
   - Reads article structure and content
   - Identifies current optimization level
   - Finds improvement opportunities

2. **Generates Optimization Elements**
   - Meta title (50-60 characters)
   - Meta description (160 characters)
   - H1 tag optimization
   - Header structure review
   - Keyword density analysis
   - Internal link suggestions (3-5)
   - External link audit

3. **Creates Schema Markup**
   - Article schema (JSON-LD format)
   - Organization schema
   - Author schema with credentials
   - FAQ schema (if applicable)

4. **Provides Checklist**
   - What's already optimized
   - What needs improvement
   - Priority fixes (quick wins)
   - Implementation guide

## Example Usage

**Option 1 - Provide URL**:
```
/optimize-on-page https://example.com/blog/best-sunscreen-sensitive-skin/
```

**Option 2 - Paste Content**:
```
/optimize-on-page
[Paste full article text]
```

## Output

Returns complete optimization package:

```
1. METADATA OPTIMIZATION
   Meta Title: [50-60 chars] | [Keyword] | [Benefit]
   Meta Description: [160 chars] | [Benefit] | [CTA]
   H1 Tag: [Recommendation]

2. HEADER STRUCTURE
   Current: [Analysis of H1-H3 hierarchy]
   Recommended: [Improved structure]
   Changes needed: [Specific edits]

3. KEYWORD ANALYSIS
   Primary keyword: [keyword]
   Frequency: [X times per article]
   Recommendation: [Optimal frequency]
   Secondary keywords: [List and placement]

4. INTERNAL LINKS
   Current links: [Count]
   Suggested additions:
   - [Article title] → [Anchor text]
   - [Article title] → [Anchor text]
   - [Article title] → [Anchor text]

5. SCHEMA MARKUP
   Recommended: Article, Organization, FAQ (if applicable)
   [Full JSON-LD code ready to copy-paste]

6. QUICK WINS (Priority Fixes)
   [ ] Update meta title
   [ ] Rewrite meta description
   [ ] Fix H1 tag
   [ ] Add internal links
   [ ] Add schema markup

7. FULL CHECKLIST
   [Comprehensive optimization checklist]
```

## Use Cases

**Scenario 1: New Article Not Ranking**
```
/optimize-on-page [your-new-article-url]
→ Get complete optimization audit
→ Implement all recommendations
→ Article starts ranking within 4 weeks
```

**Scenario 2: Article Ranking 11-30**
```
/optimize-on-page [underperforming-article-url]
→ Get targeted improvements
→ Focus on on-page signals
→ Move to top 3-5 positions
```

**Scenario 3: High-Traffic Article, Low CTR**
```
/optimize-on-page [high-traffic-url]
→ Get meta tag rewrites
→ Improve click-through rate
→ 10-30% CTR improvement typical
```

## Implementation Guide

### Step 1: Copy Meta Tags (5 min)
1. Copy generated meta title
2. Paste into CMS meta title field
3. Copy meta description
4. Paste into CMS meta description field
5. Verify in search results preview

### Step 2: Fix Headers (10 min)
1. Review recommended H1 tag
2. Update H1 if needed
3. Review H2/H3 structure
4. Reorder if recommended
5. Verify page still makes sense

### Step 3: Add Internal Links (10 min)
1. Copy suggested links
2. Find relevant context in article
3. Add links naturally (don't force)
4. Use suggested anchor text
5. Verify links open in new tab

### Step 4: Add Schema (10 min)
1. Copy JSON-LD schema code
2. Paste into CMS header area
3. Test with Google Rich Results Validator
4. Verify no errors
5. Publish and wait 24-48 hours for indexing

### Step 5: Verify (5 min)
1. Check article on live site
2. Verify all links work
3. Check mobile formatting
4. Run plagiarism check if modified significantly

**Total Time: 40 minutes**

## Tips for Success

1. **Start with High-Traffic Articles**: Biggest ROI from optimizing pages getting 500+ monthly visitors
2. **Don't Over-Optimize**: Add keywords naturally, not forced
3. **Verify All Links**: Test every internal/external link before publishing
4. **Use Priority Fixes First**: Start with quick wins, then comprehensive changes
5. **Monitor Results**: Track rankings and CTR changes in Search Console

## Expected Results

- **Ranking Improvement**: 1-3 positions average
- **CTR Improvement**: 10-30% for meta tag updates
- **Rich Snippet Eligibility**: If schema added correctly
- **Time to Results**: 1-4 weeks for ranking changes
- **ROI**: Typically 5-10x return vs. time invested

## Advanced Options

### For Competitive Keywords
- Request competitor analysis alongside optimization
- Get custom keyword strategy recommendations
- Priority on internal linking to money pages

### For YMYL Content
- Enhanced E-E-A-T optimization
- Author credentials emphasis
- Source citation improvement
- Trust signals optimization

### For Multiple Articles
- Batch optimization for content cluster
- Cross-linking strategy for internal authority
- Topical authority recommendations
