---
name: Write Content
description: "Generate a complete SEO-optimized article using AI workflow. Input keyword and outline preference, output publication-ready article with metadata and optimization checklist."
---

# Write Content Command

Generates a complete SEO-optimized article using the Perplexity → Claude pipeline.

## Usage

```
/write-content [keyword]
```

## Parameters

- `keyword` (required): Target SEO keyword for the article
- `type` (optional): Content type (review, guide, how-to, comparison) - defaults to auto-detect
- `word-count` (optional): Target word count (1000, 1500, 2000, 2500) - defaults to 2000
- `voice` (optional): Writing tone (expert, friendly, conversational) - defaults to friendly-expert

## What It Does

1. **Research Phase** (Perplexity)
   - Analyzes target keyword
   - Generates data-driven outline
   - Identifies optimal word count
   - Proposes header structure
   - Lists key phrases to target

2. **Writing Phase** (Claude)
   - Generates complete article from outline
   - Integrates keywords naturally
   - Includes examples and case studies
   - Matches requested voice/tone
   - Creates compelling structure

3. **Optimization Output**
   - Meta title (50-60 characters)
   - Meta description (160 characters)
   - H1 tag
   - Internal link suggestions
   - External source citations
   - Featured image specifications
   - Article schema skeleton
   - SEO checklist

## Example Usage

```
/write-content "best natural sunscreen for sensitive skin"
```

Output includes:
- Full 2,000+ word article
- Meta tags ready to copy-paste
- Internal link opportunities
- Required citations and sources
- Image alt text templates
- Publication checklist

## Tips for Best Results

1. **Be Specific with Keywords**: "Email marketing tool for nonprofits" > "Email tool"
2. **Choose Content Type**: Commercial (review, comparison) or informational (guide, how-to)
3. **Match Your Voice**: Provide tone preference (expert, friendly, conversational)
4. **Budget Time**: Full process takes 45-60 minutes from research to publication
5. **Use Checklist**: Run final SEO checklist before publishing

## Output Format

The command returns:

1. Perplexity research & outline
2. Complete Claude-generated article
3. SEO metadata (title, description, H1)
4. Publication checklist
5. Link opportunities
6. Fact-checking requirements

## Next Steps After Generation

1. Run plagiarism check (Copyscape)
2. Verify all statistics and claims
3. Add author credentials/bio
4. Optimize images (WebP, compression)
5. Publish and verify indexation
6. Monitor in Search Console
