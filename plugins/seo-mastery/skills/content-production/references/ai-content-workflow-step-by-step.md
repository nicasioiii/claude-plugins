# AI Content Workflow: Step-by-Step

Master the Perplexity → Claude → publish pipeline to generate SEO-optimized articles in hours.

## The Three-Step Pipeline

```
Step 1: Perplexity AI (Research & Outline)
  ↓ (Copy outline)
Step 2: Claude (Generate Full Article)
  ↓ (Copy article content)
Step 3: Publish & Optimize
```

## Step 1: Perplexity AI - Data-Driven Outline Generation

### Why Perplexity?

Perplexity provides what Google expects to see on a ranking page:
- Target word count
- Header structure (H1-H3)
- Key phrases to target
- Content elements (tables, lists, FAQs)
- Exact order elements should appear

### Perplexity Prompt (Copy-Paste Ready)

```
Act as an SEO expert and analyze the keyword "[YOUR KEYWORD]".

Provide:
1. Target word count needed to rank #1 in Google for this keyword
2. Complete page outline with elements in exact order they should appear

Page Structure (in sequential order):
- SEO Title (50-60 characters, include primary keyword)
- SEO Meta Description (150-160 characters)
- H1 Title (include primary keyword)
- Introduction paragraph with primary keyword in first 100 words
- Next H2 section heading (include secondary keyword if natural)
  - H3 subsection (if applicable)
  - H3 subsection (if applicable)
- Continue with each additional H2
- H2: FAQ section
- H2: Conclusion

For each section, specify:
- What to cover (details, topics, angles)
- Approximate word count
- Key phrases to naturally target
- Any special formatting (lists, tables, comparisons)

Format as numbered list showing exact page flow from top to bottom.
```

### How to Use Perplexity

1. Go to Perplexity.ai (free account)
2. Paste prompt with your keyword
3. Wait for response (30-60 seconds)
4. Copy entire response
5. Paste into document or send to Claude

### Example Perplexity Output

```
TARGET WORD COUNT: 2,500-3,000 words

PAGE STRUCTURE:

1. SEO Title: "How to Choose the Best Natural Sunscreen | SPF Guide 2024"
2. SEO Meta Description: "Learn how to choose natural sunscreen that works. Compare SPF levels, reef-safe ingredients, and best brands for sensitive skin. Expert guide."
3. H1 Title: "How to Choose the Best Natural Sunscreen"
4. Introduction (150-200 words): Explain sunscreen importance, natural vs chemical, hint at what guide covers
5. H2: "Understanding SPF and UV Protection" (300 words)
   H3: "What SPF Numbers Mean"
   H3: "UVA vs UVB: What's the Difference"
6. H2: "Natural vs Chemical Sunscreen: Key Differences" (400 words)
   H3: "Mineral/Physical Sunscreens"
   H3: "How They Protect Your Skin"
7. H2: "Reef-Safe Ingredients to Look For" (350 words)
   H3: "Approved vs Banned Ingredients"
   H3: "Why Reef Safety Matters"
8. H2: "Best Natural Sunscreens by Use Case" (600 words)
   H3: "For Sensitive Skin"
   H3: "For Water/Beach Activities"
   H3: "For Daily Face Use"
9. H2: "How to Apply for Maximum Protection" (250 words)
10. H2: "Common Mistakes People Make" (200 words)
11. H2: "FAQ" (300 words)
    - What's the best natural sunscreen?
    - Is natural sunscreen as effective?
    - Can I use sunscreen with other skincare?
12. Conclusion (150 words): Recap key points, call to action

KEY PHRASES TO TARGET:
- natural sunscreen (primary)
- reef-safe sunscreen (secondary)
- best sunscreen for sensitive skin (long-tail)
- SPF protection (supporting)
- mineral sunscreen (secondary)
```

## Step 2: Claude - Full Article Generation

### Claude Setup

1. Use Claude 3.5 Sonnet (most cost-effective)
2. Desktop app preferred (better for uploads)
3. Or web version (claude.ai) works fine

### Claude Prompt Structure

```
Act as an SEO and copywriting expert. Write a comprehensive article based on the following outline:

[PASTE PERPLEXITY OUTLINE HERE]

IMPORTANT INSTRUCTIONS:
1. Follow the outline structure exactly (don't reorder sections)
2. Maintain word counts specified for each section
3. Write naturally for humans - don't force keywords
4. Naturally integrate these target keywords throughout:
   - Primary: [keyword]
   - Secondary: [keyword], [keyword], [keyword]
5. Include 2-3 practical examples or case studies
6. Use conversational tone (not robotic)
7. Make headers compelling and specific
8. Create smooth transitions between sections
9. Include actionable takeaways readers can implement
10. For FAQ section, answer concisely (1-2 sentences max per answer)

TONE & VOICE:
- Write in [TONE: expert/friendly/conversational/authoritative]
- Use [VOICE: first-person if relevant], practical examples
- Show expertise through specific details
- Address reader pain points directly

OUTPUT:
Generate the complete article ready to publish. Start with H1 title and continue through conclusion.
```

### Example Claude Prompt (Copy-Paste Ready)

```
Act as an SEO and copywriting expert. Write a comprehensive 2,500-word article based on the following outline:

H1: How to Choose the Best Natural Sunscreen
Intro (150-200 words): Explain sunscreen importance, natural vs chemical, hint at what guide covers
H2: Understanding SPF and UV Protection (300 words)
  H3: What SPF Numbers Mean
  H3: UVA vs UVB: What's the Difference
H2: Natural vs Chemical Sunscreen: Key Differences (400 words)
  H3: Mineral/Physical Sunscreens
  H3: How They Protect Your Skin
H2: Reef-Safe Ingredients to Look For (350 words)
  H3: Approved vs Banned Ingredients
  H3: Why Reef Safety Matters
H2: Best Natural Sunscreens by Use Case (600 words)
  H3: For Sensitive Skin
  H3: For Water/Beach Activities
  H3: For Daily Face Use
H2: How to Apply for Maximum Protection (250 words)
H2: Common Mistakes People Make (200 words)
H2: FAQ (300 words)
  - What's the best natural sunscreen?
  - Is natural sunscreen as effective?
  - Can I use sunscreen with other skincare?
Conclusion (150 words): Recap key points, CTA

TARGET KEYWORDS TO NATURALLY INTEGRATE:
- Primary: natural sunscreen
- Secondary: reef-safe sunscreen, sunscreen for sensitive skin, mineral sunscreen, SPF

INSTRUCTIONS:
1. Follow the structure exactly
2. Write naturally - don't keyword stuff
3. Include real examples (brand names, situations)
4. Use conversational tone (friendly expert, not robotic)
5. Create compelling headers specific to content
6. Smooth transitions between sections
7. Make it actionable (readers should know how to apply tips)
8. Keep FAQ answers concise (1-2 sentences each)
9. End conclusion with clear call to action

Write the complete article ready to publish.
```

### Advanced: Feeding Voice/Tone Examples

To match your brand voice, include writing sample:

```
Reference Writing Sample:
[Paste 2-3 paragraphs from your best existing article]

Write the article above using the same tone, vocabulary, and style as the reference sample.
```

### Handling Claude Refusals or Poor Output

**If Claude refuses (says "I can't write marketing content"):**
- Rephrase: "Write an informational article..."
- Remove affiliate link requests (add manually later)
- Focus on educational angle

**If output is generic or weak:**
- Run again with more specific instructions
- Add "unique angle" instruction
- Include more detailed section descriptions

## Step 3: Publish & Optimize

### Pre-Publication Checklist

Before copying article to website:

- [ ] Plagiarism check (Copyscape.com) - paste article, verify original
- [ ] Readability review (Hemingway Editor) - aim for grade 8-10
- [ ] Keyword verification - primary keyword 2-3 times, secondaries 1-2 times
- [ ] Link review - 3-5 internal links, 3-5 external links to high-authority
- [ ] Header hierarchy - one H1, 3-5 H2s, logical H3 structure
- [ ] Word count - matches Perplexity target (within 10%)
- [ ] Author info - author name, credentials, photo ready
- [ ] Images - feature image + 2-3 supporting images ready

### Content Optimization on Website

1. **Set Meta Title**
   - From Perplexity output
   - 50-60 characters
   - Keyword first

2. **Set Meta Description**
   - From Perplexity output
   - 160 characters
   - Benefit statement

3. **Set H1 Tag**
   - Should match meta title (or very similar)
   - Paste from article

4. **Add Featured Image**
   - At least 1200x630px
   - Optimized (WebP format)
   - Alt text: Include primary keyword naturally

5. **Add Internal Links**
   - 3-5 links to related content
   - Descriptive anchor text
   - Links within natural context

6. **Add External Links**
   - 3-5 authoritative sources
   - Government, academic, well-known brands preferred
   - Never reciprocal links

7. **Add Author Bio**
   - Author name
   - Credentials/expertise
   - Photo (optional but recommended)
   - Link to profile/LinkedIn

8. **Add Schema Markup**
   - Article schema type
   - Include: headline, image, author, datePublished
   - Validate with Google Rich Results Validator

### Publication Steps

1. Create draft in CMS (WordPress, Shopify, etc.)
2. Add all metadata above
3. Add feature image + internal images with alt text
4. Preview on mobile + desktop
5. Set publishing date/time
6. Publish to live site
7. Verify page loads (test links, images, formatting)
8. Verify indexation in Google Search Console within 24 hours

## Complete Example Workflow

### Input: Target Keyword "how to save for retirement"

**Step 1: Perplexity Prompt**
```
Act as an SEO expert and analyze the keyword "how to save for retirement".

Provide:
1. Target word count needed to rank #1 in Google for this keyword
2. Complete page outline with elements in exact order they should appear on the page

Page Structure (in sequential order):
- SEO Title
- SEO Meta Description
- H1 Title
- Introduction
- Next H2 section
  - H3 subsections
- Continue with each additional H2
- H2: FAQ Section
- H2: Conclusion

For each section, specify what to cover and approximate word count.
```

**Step 2: Claude Prompt (after receiving Perplexity output)**
```
Act as a financial advisor and SEO expert. Write a comprehensive 2,500-word article based on:

[PASTE PERPLEXITY OUTPUT]

Write for someone aged 25-45 interested in retirement planning. Include:
- Specific numbers ($15,000, 7% returns, etc.)
- Real retirement account types (401k, Roth IRA, etc.)
- Actionable steps readers can take today
- Common mistakes to avoid

Write naturally - don't keyword stuff. Use conversational expert tone.
```

**Step 3: Optimize & Publish**
- Add to WordPress
- Set meta title, description
- Add internal links to related retirement content
- Add external links to IRS.gov, Fidelity, etc.
- Add author bio (financial advisor credentials)
- Add Article schema
- Publish and verify

## Advanced: Scaling to Multiple Articles

### Batch Perplexity Analysis

Create 5 keyword outlines at once:

```
Analyze these 5 keywords for SEO potential:
1. "natural sunscreen for sensitive skin"
2. "reef-safe sunscreen brands"
3. "best sunscreen for oily skin"
4. "how to apply sunscreen correctly"
5. "sunscreen vs sunblock: difference"

For each keyword, provide:
- Target word count
- Recommended header structure (H2s and H3s)
- Key secondary keywords to target
```

### Claude Batch Generation

After getting 5 outlines from Perplexity, generate all 5 articles:

```
Generate 5 complete articles based on the outlines provided. Write each to exactly match its outline structure. Use consistent tone throughout all articles.

ARTICLE 1: [Outline 1]
ARTICLE 2: [Outline 2]
[Etc.]

Format output as:
---
ARTICLE 1: [Title]
[Full article]
---
ARTICLE 2: [Title]
[Full article]
---
```

## Troubleshooting Common Issues

**Issue: Claude writes generic content**
- Solution: Add "unique angle" instruction, reference competitive articles to avoid
- Solution: Include brand voice example

**Issue: Article is too short**
- Solution: Ask Claude for "2,500-word version" in new prompt
- Solution: Ask for "more detailed examples and case studies"

**Issue: Keywords feel forced/unnatural**
- Solution: Remove keyword count targets, let Claude integrate naturally
- Solution: Tell Claude "prioritize readability over keyword density"

**Issue: Article ranks well but low CTR**
- Solution: Rewrite meta description (more benefit-focused)
- Solution: Update title to be more compelling

**Issue: Can't get Perplexity to give good outline**
- Solution: Be more specific ("this is for e-commerce site selling X")
- Solution: Reference competitor article structure

## Time Investment

- Perplexity analysis: 5-10 minutes per keyword
- Claude article generation: 10-20 minutes (including refines)
- Optimization + publishing: 20-30 minutes
- **Total per article: 45-60 minutes**

At 4-5 articles/month: 3-5 hours content production time (plus editing/QA)

## Expected Output Quality

- **Plagiarism**: 0% (completely original AI generation)
- **Grammar/Spelling**: 95%+ correct (minimal editing needed)
- **Keyword Integration**: Natural, no stuffing
- **Ranking Potential**: 60%+ chance top 10 within 3-6 months (with backlinks)
- **Publishing Quality**: Ready to publish after on-page optimization

## Next Steps

1. Start with one keyword to test the workflow
2. Get comfortable with both Perplexity and Claude
3. Scale to 4-5 articles/month
4. Monitor Search Console for ranking progress
5. Update low-performing articles at 6-month mark
