# Quality Signals: E-E-A-T

Master Google's E-E-A-T framework to signal expertise and trustworthiness in your content.

## What is E-E-A-T?

E-E-A-T = Expertise, Experience, Authoritativeness, Trustworthiness

Google uses this framework to evaluate content quality, especially for YMYL (Your Money or Your Life) topics.

## The Four Components

### 1. Expertise (First E)

**Definition**: Knowledge and skill in the specific topic

**How to Signal**:
- Author credentials and certifications
- Years of experience in field
- Professional affiliations
- Education (degree, program)
- Author bio with clear expertise

**Not Expertise**:
- Random person reviewing product without background
- Author has unrelated expertise

**Examples**:

✓ Good:
"Written by Dr. Sarah Johnson, MD, Board-Certified Dermatologist with 15 years of clinical experience."

✗ Bad:
"Written by John (generic, no credentials)"

### 2. Experience (Second E)

**Definition**: First-hand, direct experience with topic

**How to Signal**:
- "I tested this product for 90 days..."
- "When I used this approach..."
- "In my experience working with clients..."
- "During my research, I discovered..."
- Real case studies and examples
- Personal anecdotes that show deep knowledge

**Importance**: Google heavily weights experience (2024 update emphasis)

**Examples**:

✓ Good:
"I tested 20 sunscreens on my own sensitive skin over three months. Here's what actually worked."

✗ Bad:
"This sunscreen has good reviews" (no personal experience)

### 3. Authoritativeness

**Definition**: Recognition of credibility by other experts and institutions

**How to Signal**:
- Backlinks from reputable sites (votes of confidence)
- Author credentials and profile links
- Institutional affiliations
- Quotes from or features in major publications
- Professional memberships
- Speaking engagements
- Citations by other experts

**How It's Measured**:
- Domain authority (your site's overall authority)
- Topical authority (expertise in specific topic)
- Author authority (individual's credentials)
- Backlink quality (who links to you)

**Examples**:

✓ Good:
- "Dr. Jones is quoted in WebMD, Mayo Clinic, and Harvard Health"
- "Our company has been featured in Forbes, Wall Street Journal"
- "Certified by the American Academy of Dermatology"

✗ Bad:
- No credentials displayed
- No external validation

### 4. Trustworthiness

**Definition**: Honesty, transparency, and accuracy

**How to Signal**:
- Clear author and company information
- Privacy policy and terms visible
- About page with company background
- Author bio with photo
- Transparency about conflicts of interest
- Affiliate disclosure ("We earn from qualifying purchases")
- Accurate citations of sources
- No exaggerated claims
- Honest cons (balanced reviews)

**Critical**: Any financial relationship must be disclosed

**Examples**:

✓ Good:
"This article contains affiliate links. We earn a small commission if you buy through our links, at no extra cost to you."

✗ Bad:
Hidden affiliate links with no disclosure

## Implementation: Author Credibility

### Author Bio Requirements

**Include**:
- Full name (not generic "John")
- Professional title
- Credentials/certifications
- Years of experience
- Organization/company affiliation
- Photo (humanizes, increases trust)
- Link to profile (LinkedIn, personal site, Twitter)

**Example**:
```
Dr. Sarah Johnson
Board-Certified Dermatologist, MD
15+ years of clinical practice at Stanford Medical
Founder of SkinHealth Institute
Featured in: WebMD, Mayo Clinic, Allure Magazine
→ LinkedIn: linkedin.com/in/sarahjohnson
```

### For Non-Expert Writers

**If you're not the expert**:
- Hire expert as author (better credibility)
- Have expert review and approve
- Expert reviews content before publishing

**Alternative**:
- Research extensively and cite experts
- Include expert interviews
- Quote authoritative sources
- Make expertise clear: "Based on research from..."

## Implementation: Source Citation

### How to Cite Sources

**Medical/Scientific Claims**:
Must cite peer-reviewed sources

✓ Good:
"According to a 2023 study published in the Journal of Dermatology, mineral sunscreen provides superior UVA protection. [Link to study]"

✗ Bad:
"Mineral sunscreen is better" (no source)

### Source Quality Hierarchy

**Tier 1 (Best)**: Academic/peer-reviewed
- PubMed, Google Scholar
- University research
- Government agencies (.gov)
- Scientific journals

**Tier 2 (Good)**: Established authority
- Well-known publications (NYT, BBC)
- Professional organizations (American Academy of Dermatology)
- Major institutions

**Tier 3 (Acceptable)**: Industry experts
- Established blogs by credentialed authors
- Professional associations
- Government databases

**Tier 4 (Weak)**: Generic sources
- Low-authority blogs
- Syndication sites
- Unverified sources
- Competitor blogs

### Citing Best Practices

1. **For statistics**: Always link to original source
2. **For claims**: Cite authoritative source
3. **For definitions**: Can cite dictionary or reputable source
4. **For images**: Credit photographer/source

## Review Schema Implementation

### AggregateRating Schema

Signals trust through reviews and ratings

```json
{
  "@type": "AggregateRating",
  "ratingValue": "4.8",
  "ratingCount": "247",
  "bestRating": "5",
  "worstRating": "1"
}
```

**Requirements**:
- Only include if you have real customer reviews
- Rating must be accurate (don't fake)
- Include review count (shows volume = trust)

### Individual Review Display

**Best Practice**: Show actual customer reviews with:
- Reviewer name
- Reviewer title/affiliation (if relevant)
- Star rating
- Review text
- Date

**Example**:
```
⭐⭐⭐⭐⭐ (5 stars)
"This sunscreen is amazing! I have super sensitive skin and no reaction."
- Jennifer M., Verified Buyer, March 2024
```

## E-E-A-T by Content Type

### Product Reviews

**Critical E-E-A-T Elements**:
- ✓ Personal testing (experience)
- ✓ Expert credentials (expertise)
- ✓ Honest pros AND cons (trustworthiness)
- ✓ Real customer reviews (authoritativeness)
- ✓ Product images/videos (authenticity)
- ✓ Clear affiliation disclosure (trustworthiness)

### Educational/Guide Content

**Critical E-E-A-T Elements**:
- ✓ Expert author or reviewer (expertise)
- ✓ Cited sources (trustworthiness)
- ✓ Recent publication date (freshness)
- ✓ Author credentials visible (expertise)
- ✓ No sensational claims (trustworthiness)

### Medical/Health Content

**Critical E-E-A-T Elements**:
- ✓ Author is licensed medical professional (expertise)
- ✓ All claims cited to medical sources (trustworthiness)
- ✓ No medical advice given (trustworthiness)
- ✓ Updated with recent research (authoritativeness)
- ✓ Disclaimer: "Consult healthcare provider" (trustworthiness)

## Common E-E-A-T Mistakes

**Mistake 1: Anonymous Author**
```
❌ "Article by Staff"
✓ "Written by Dr. Sarah Johnson, Dermatologist"
```

**Mistake 2: No Credentials**
```
❌ "Review by John" (what makes John qualified?)
✓ "Review by John Smith, 20-year skincare chemist"
```

**Mistake 3: Fake Expertise**
```
❌ Finance article written by someone with no financial background
✓ Finance article by CFP or financial advisor
```

**Mistake 4: Undisclosed Affiliate Links**
```
❌ Links to product with no disclosure (FTC violation)
✓ "This article contains affiliate links. We earn a commission."
```

**Mistake 5: Unverified Claims**
```
❌ "This sunscreen prevents cancer" (no source)
✓ "Studies show mineral sunscreen may provide additional protection" [link to study]
```

**Mistake 6: Outdated Information**
```
❌ "2021 study shows..." (article published 2024, no update)
✓ "2024 research indicates..." (up-to-date information)
```

**Mistake 7: No Sources Listed**
```
❌ Article full of claims with no links to sources
✓ Every major claim has link to authoritative source
```

## E-E-A-T Audit Checklist

**Author Credibility**:
- [ ] Author name visible (not anonymous)
- [ ] Author credentials listed
- [ ] Author photo included
- [ ] Author profile link included
- [ ] Expertise is relevant to topic

**Experience**:
- [ ] Article shows first-hand experience
- [ ] Personal testing mentioned (if product review)
- [ ] Real examples or case studies included
- [ ] Not just rewritten competitor content

**Authority**:
- [ ] Site has backlinks from reputable sources
- [ ] Author is recognized expert (mentioning affiliations)
- [ ] Content links are to authoritative sources only
- [ ] Publication date recent (within 1-2 years)
- [ ] Content is comprehensive and deep

**Trustworthiness**:
- [ ] Affiliate/financial disclosures clear
- [ ] No exaggerated claims
- [ ] Cons are mentioned (balanced)
- [ ] Sources are cited for major claims
- [ ] No misleading statements
- [ ] Company/About page visible
- [ ] Contact information available
- [ ] Privacy policy accessible

**Medical/Financial Content (If Applicable)**:
- [ ] Licensed professional as author
- [ ] All claims cited to authoritative sources
- [ ] Clear disclaimer included
- [ ] Medical advice not given (only information)
- [ ] Information is current (not outdated)

## Tools for E-E-A-T Validation

- **Author verification**: LinkedIn, personal website
- **Source checking**: Google Scholar, PubMed, .gov sites
- **Fact-checking**: Snopes.com, FactCheck.org
- **Backlink analysis**: Ahrefs, SEMrush (see who links to you)
- **Schema validation**: Google Rich Results Validator (review schema)
- **Citation tools**: Google Scholar (see who cites your work)

## Expected Impact

- **Ranking Boost**: 10-30% position improvement with strong E-E-A-T
- **CTR Improvement**: 5-15% from trustworthiness signals
- **Reduced Bounce Rate**: Clear expertise keeps readers engaged
- **Google Favor**: More likely to be recommended in AI Overviews
- **Rich Snippets**: Qualified for featured snippets with strong signals
