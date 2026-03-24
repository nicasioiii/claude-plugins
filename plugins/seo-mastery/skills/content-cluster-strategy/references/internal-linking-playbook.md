# Internal Linking Playbook

Strategic system for distributing link authority throughout your cluster and guiding user journey.

## Internal Linking Fundamentals

**Definition:** A link from one page on your site to another page on your site.

**Why it matters:**
- Distributes authority (link juice) from strong pages to weak pages
- Helps Google understand content hierarchy
- Guides users through content
- Keeps users on your site longer

**Authority flow principle:**
- Links PASS authority from linking page to linked page
- Every link costs the linking page a small amount of authority
- Link juice spreads across ALL outgoing links equally
- Strategic interlinking = strategic authority distribution

**Example:**
```
Page A has 100 authority points
Page A links to 5 pages
Each page receives 20 authority points
(Simplified model, actual algorithm more complex)
```

## Cluster Interlinking Architecture

### Hub-and-Spoke Model (Most Effective)

**Structure:**
```
          Pillar (Hub)
           /    |    \
         S1    S2    S3
        / \    / \    / \
       S1  S2 S2 S3 S3 S1
```

**Rules:**
1. **Pillar links to all satellites**
   - Pillar receives all internal link authority
   - Pillar distributes authority downward

2. **Satellites link back to pillar**
   - Reinforce pillar authority
   - Create cycle of authority flow

3. **Satellites link to related satellites**
   - Only topically related pages
   - Creates secondary authority distribution

### Authority Flow Direction

**Hierarchy (authority flows downward):**
```
Level 1: Pillar (highest authority = most links received)
Level 2: Satellites (medium authority = some links received)
Level 3: Sub-satellites (optional, lower authority)
```

**Strategic implication:**
- Pillar gets 20-30 internal links (from satellites + homepage)
- Each satellite gets 3-5 internal links (from pillar + related satellites)
- Result: Pillar ranks for main keyword; satellites rank for long-tail

## Internal Linking Implementation (Step-by-Step)

### Step 1: Map the Cluster

Create visual map of all links:

**Example (Dog Nutrition cluster):**

**Pillar:** "Dog Nutrition Complete Guide"
- S1: "Best Dog Food for Sensitive Stomach"
- S2: "Limited Ingredient Dog Food"
- S3: "How to Calculate Dog Portions"
- S4: "Dog Food Ingredients Glossary"
- S5: "Feeding Dogs by Life Stage"

**Interlinking map:**

```
PILLAR
├─ [Link to S1] Best dog food for sensitive stomach section
├─ [Link to S2] Limited ingredient food section
├─ [Link to S3] Portion sizing section
├─ [Link to S4] Understanding ingredients section
└─ [Link to S5] Feeding by age section

S1 (Sensitive Stomach)
├─ [Link to PILLAR] Back to nutrition guide
├─ [Link to S3] How to portion sensitive-stomach food
└─ [Link to S5] Feeding puppies/seniors with sensitivities

S2 (Limited Ingredient)
├─ [Link to PILLAR] Back to nutrition guide
├─ [Link to S1] Overlap: allergies vs sensitivities
└─ [Link to S4] Understanding ingredient lists

S3 (Portions)
├─ [Link to PILLAR] Back to nutrition guide
└─ [Link to S5] Age-based portion recommendations

S4 (Ingredients)
├─ [Link to PILLAR] Back to nutrition guide
└─ [Link to S2] Understanding limited ingredient foods

S5 (Life Stage)
├─ [Link to PILLAR] Back to nutrition guide
├─ [Link to S3] Puppy/senior portion guide
└─ [Link to S1] Senior dogs with sensitivities
```

### Step 2: Draft Anchor Text

**Define what text will be linked:**

**Rule 1: Anchor text should describe linked content**
- Bad: "click here," "read more," "article"
- Good: "best dog food for sensitive stomach"
- Better: "complete guide to feeding dogs with sensitivities"

**Rule 2: Include keywords naturally**
- Goal: Help users and search engines understand link target
- Don't force keywords unnaturally

**Rule 3: Variety in anchor text**
- Don't use identical anchor text every time
- Varies: exact match, partial match, branded, generic
- Helps avoid over-optimization signals

**Anchor text variations (for S1: "Best Dog Food for Sensitive Stomach"):**
- Exact match: "best dog food for sensitive stomach"
- Partial match: "sensitive stomach dog food," "food for sensitive stomachs"
- Descriptive: "complete guide to feeding dogs with stomach issues"
- Branded: "our sensitive stomach guide"
- Generic: "read our feeding guide" (occasional, not primary)

### Step 3: Place Links Contextually

**Best placement:**
- In body text where relevant (most natural)
- At end of section "Learn more" (clear CTA)
- In paragraph transitions (contextual)
- In lists or tables (when applicable)

**Example placement (in article body):**

```
Different foods work for different dogs. The best choice depends on your dog's
age, health, and budget.

→ [Link: "Best dog food for sensitive stomach"] if your dog has digestion issues
→ [Link: "Limited ingredient dog food guide"] if your dog has allergies
→ [Link: "How to calculate dog portions"] to determine how much to feed
→ [Link: "Understanding dog food ingredients"] for deeper ingredient analysis
```

**Bad placement (avoid):**
- Random links not related to text
- Too many links in single paragraph (link density >3%)
- Keyword-stuffed anchor text looking unnatural
- Links that don't help user journey

### Step 4: Implement in Content Management System

**WordPress implementation:**

1. **Highlight text** you want to link
2. **Click link button** (chain icon)
3. **Search for target page** (start typing page title)
4. **Paste URL** of target page
5. **Open in new tab?** YES (better UX)
6. **Update/Publish** post

**Other CMS (Webflow, Squarespace, etc.):**
- Similar process: highlight → link → insert URL
- Most have link management tools in editor

### Step 5: Create Link Distribution Matrix

Track all links systematically:

**Matrix template:**

| Source Page | Target Page | Anchor Text | Location | Context |
|---|---|---|---|---|
| PILLAR | S1 | best dog food for sensitive stomach | Section 2 | Introduction |
| PILLAR | S2 | limited ingredient dog food | Section 3 | Benefits section |
| PILLAR | S3 | how to calculate dog portions | Section 4 | Feeding guidelines |
| PILLAR | S4 | understanding ingredients | Section 5 | Label reading |
| PILLAR | S5 | feeding dogs by life stage | Section 6 | Age variations |
| S1 | PILLAR | back to dog nutrition guide | Conclusion | Summary |
| S1 | S3 | detailed portion guide | Body | Transition help |
| S2 | PILLAR | return to nutrition overview | Conclusion | Next steps |
| S2 | S4 | ingredient analysis | Body | Understanding labels |
| S3 | PILLAR | full nutrition guide | Conclusion | Further reading |
| S3 | S5 | adjust for puppy/senior needs | Body | Age adjustments |
| S4 | PILLAR | nutrition fundamentals | Conclusion | Background |
| S4 | S2 | limited ingredient options | Body | Application |
| S5 | PILLAR | general feeding guidelines | Conclusion | Overview |
| S5 | S1 | senior dog sensitivities | Body | Specific needs |
| S5 | S3 | age-appropriate portions | Body | Portions by age |

**Use this matrix when:**
- Creating content (know exactly where to link)
- Reviewing content (ensure all links present)
- Updating site (track existing link structure)

## Advanced Interlinking Strategies

### Strategy 1: Content Gap Linking

**Concept:** Link to satellite pages from related articles OUTSIDE the cluster

**Example:**
- Article: "5 Common Dog Health Problems"
- Mentions: "digestive issues"
- Link to: "Best dog food for sensitive stomach" (S1)

**Benefit:** Drives traffic from broader articles to cluster

**Implementation:**
- Review all existing content
- Identify places you mention cluster topics
- Add contextual links to cluster pages
- Creates "topic gravity" pulling traffic inward

### Strategy 2: Pillar Hub Links

**Concept:** Make pillar link hub for topical authority

**Structure:**
- Pillar links to ALL satellites (8-10 links)
- Pillar links to ALL related clusters (if applicable)
- Pillar becomes "table of contents" for topic

**Example (pillar links):**
```
## Dog Nutrition Overview

In this complete guide, you'll learn:

→ [How to choose the best dog food]
→ [Best foods for specific health conditions]
→ [Understanding dog food ingredients]
→ [Calculating proper portions]
→ [Feeding dogs by life stage]
→ [Cost-saving feeding strategies]
```

**Benefit:** Pillar becomes "go-to" hub for topic; high internal link authority

### Strategy 3: Breadcrumb Navigation

**Concept:** Visual hierarchy showing where user is in cluster

**Example:**
```
Home > Dog Nutrition > Best Foods > Sensitive Stomach Guide

[Back to: Dog Nutrition Guide]
[Related: Limited Ingredient Foods] [Portion Calculator]
```

**Benefit:** Clear navigation; helps users understand relationships; improves UX

**Implementation:** Add at top and/or bottom of articles

### Strategy 4: "See Also" Section

**Concept:** List related articles at bottom of each page

**Example (at bottom of S1 article):**
```
## Related Articles You Might Find Helpful

- [Complete Dog Nutrition Guide] (our main resource)
- [Limited Ingredient Dog Food Guide] (similar health focus)
- [How to Calculate Dog Portions] (feeding guidance)
- [Dog Food Ingredients Explained] (understanding labels)
```

**Benefit:** Increases internal traffic; encourages content consumption

**Implementation:** Section at end of article with bulleted links

### Strategy 5: Contextual In-Content Links

**Concept:** Link naturally within body text as you write

**Example:**
```
"Many dogs with sensitivities actually have [allergies], not sensitivities.
Learn the difference in our [allergies vs sensitivities guide].

If your dog has sensitivities, the best approach is feeding [limited ingredient dog food].
See our [complete limited ingredient guide] for options and recommendations."
```

**Benefit:** Most natural; helps readers; best for SEO

**Implementation:** Write naturally, then add links where text mentions related topics

## Link Velocity & Interlinking

**Link velocity principle:** Regular new links show freshness

**Strategy:**
- When you publish new article, interlink from existing articles
- When you update old article, add links to new related articles
- Creates ongoing internal linking momentum

**Timeline example:**
```
Week 1: Publish pillar + 2 satellites, interlink them
Week 2: Publish satellite 3, add links from S1 and S2
Week 3: Publish satellite 4, update pillar with new link
Week 4: Publish satellite 5, add links from all previous
Result: Continuous freshness + internal link growth
```

## Internal Linking Best Practices

**Do:**
- ✓ Use descriptive anchor text (keyword-rich but natural)
- ✓ Link contextually (where mentioned in text)
- ✓ Link to relevant pages only (not random)
- ✓ Use varied anchor text (avoid repetition)
- ✓ Open in new tab (for UX)
- ✓ Review monthly (are links still current?)
- ✓ Add links when content is updated (refresh signals)

**Don't:**
- ✗ Link to every page from every page (dilutes authority)
- ✗ Use generic anchor text ("click here")
- ✗ Over-optimize with keyword stuffing in anchors
- ✗ Link to unrelated pages (confuses both users and Google)
- ✗ Use hidden links or cloaked links (black hat)
- ✗ Link to duplicate content (choose canonical version)
- ✗ Create link schemes (linking just for links)

## Internal Linking Tools

**WordPress:**
- Yoast SEO (plugin with internal link suggestions)
- Rank Math (plugin with link tracking)
- Manual: WordPress default link feature

**Other CMS:**
- Webflow: Built-in link tools
- Squarespace: Built-in linking
- Custom CMS: Depends on platform

**Analysis Tools:**
- Ahrefs (see internal link structure)
- Screaming Frog (crawl your site, see all internal links)
- Google Search Console (see Google's view of site structure)

## Common Linking Mistakes

**Mistake 1: Too many links per page**
- More than 4-5 links per paragraph dilutes authority
- 20+ links on page spreads authority too thin
- Solution: Limit to 3-5 relevant links

**Mistake 2: Linking to wrong page**
- Linking to homepage when should link to relevant article
- Authority spreads incorrectly
- Solution: Create specific landing page, link there

**Mistake 3: Broken internal links**
- Links point to deleted pages
- Users hit 404; bad UX
- Solution: Redirect old pages before deleting

**Mistake 4: Missing obvious internal links**
- Pillar mentions satellite but doesn't link to it
- Authority stays on pillar
- Solution: Map and implement ALL intended links

**Mistake 5: Over-optimization**
- Using exact match keyword in EVERY link
- Looks unnatural; can trigger optimization penalties
- Solution: Vary anchor text (80% descriptive, 20% branded/generic)

## Internal Linking Checklist (Before Publishing)

- [ ] Pillar page created with links to all satellites
- [ ] All satellites created and drafted
- [ ] Satellite-to-satellite links planned (topically related only)
- [ ] All links use natural, descriptive anchor text
- [ ] Links open in new tab
- [ ] No broken links (all target pages exist)
- [ ] Link density reasonable (3-5% max)
- [ ] Breadcrumb navigation created (if applicable)
- [ ] "See also" sections added to satellites
- [ ] Internal link matrix documented
- [ ] Links tested before final publish
- [ ] Interlinking monitored for effectiveness (rankings improve?)

---

*Synthesis from: Ahrefs internal linking research, Yoast linking best practices, Real cluster ranking data*
