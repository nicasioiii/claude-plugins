# Programmatic SEO: 12 Playbooks for Scaling Content

**Length:** ~450 lines
**Purpose:** Framework for automating content generation while maintaining unique value

---

## Core Definition

**Programmatic SEO** = Creating hundreds or thousands of pages using templates + data + AI, while maintaining unique value per page.

**Key principle:** Template structure + unique data = rankable content (not "thin" content).

---

## The 12 Playbooks

### Playbook 1: Template Pages (Keyword Variations)

**Use case:** Multiple keywords describing similar concepts.

**Example:** Blog post templates
- "How to [action] in [city]"
- "Best [product] for [use case]"
- "Complete guide to [topic] in [industry]"

**Template formula:**
```
H1: "[Keyword]"

Intro (100 words):
[Hook about topic]
[Why this matters]
[What we'll cover]

H2: "What is [Keyword]?"
[150 words explaining concept + variations]

H2: "[Keyword] vs. Alternatives"
[200 words comparing to similar concepts]

H2: "How to [Action]"
[Step-by-step guide specific to keyword]

H2: "FAQ: [Keyword]"
[5-8 questions specific to keyword]

CTA: "[Book demo / Learn more]"
```

**Data variations (makes each page unique):**
- City names
- Product names
- Use cases
- Industry-specific examples

**Tools:**
- Template CMS (Webflow, custom build)
- AI content generation (Claude, ChatGPT)
- Spreadsheet with keyword variations

**Example output:** 50 keywords → 50 unique pages (same structure, different data).

---

### Playbook 2: Curation Pages

**Use case:** Aggregate content from multiple sources + add unique angle.

**Example:** "Best [product] for [use case]"
- "Best laptops for video editing"
- "Best ecommerce platforms for dropshipping"

**Structure:**
```
H1: "Best [Product] for [Use Case] (2026)"

Intro (150 words):
[Why this category matters]
[How we evaluated products]
[Key criteria]

[For each top product]
H2: "[Product Name]"
- Image
- Price
- Specs
- Link to product
- Why we chose it (100 words, ORIGINAL OPINION)

H2: "Comparison Table"
[Feature matrix comparing all products]

H2: "Buyer's Guide"
[Criteria for choosing within category]

H2: "FAQ"
[Q&A about category]

CTA: [Shop best choice]
```

**Unique value (not just copy-paste):**
- Original testing/opinions (not regurgitated reviews)
- Comparison data (table you built)
- Specific use case angle (not generic "best")
- Updated evaluation criteria (you decided what matters)

**Output:** Each curation page is unique because YOUR opinions/evaluations differ.

---

### Playbook 3: Comparison Pages

**Use case:** Head-to-head product comparisons.

**Example:** "Shopify vs. WooCommerce," "HubSpot vs. Salesforce"

**Structure:**
```
H1: "[Product A] vs. [Product B]"

Executive Summary (100 words):
[When to choose A]
[When to choose B]
[Winner for specific use case]

Comparison Table:
| Feature | [Product A] | [Product B] |
|---------|-----------|-----------|
| Price | | |
| Ease of use | | |
| Support | | |
| Integrations | | |

H2: "[Product A] Overview"
[200 words about A, with pros/cons]

H2: "[Product B] Overview"
[200 words about B, with pros/cons]

H2: "Detailed Comparison"
[Feature-by-feature analysis]

H2: "When to Choose [Product A]"
[Specific use cases favoring A]

H2: "When to Choose [Product B]"
[Specific use cases favoring B]

H2: "Verdict"
[Final recommendation]

CTA: [Try Product A] [Try Product B]
```

**Unique value:**
- Original comparison table (based on actual feature research)
- Use-case analysis (not generic "A is better")
- Recent updates (pricing, features change; your page reflects reality)

---

### Playbook 4: List Pages (Ranked Lists)

**Use case:** Aggregating best-of within category.

**Example:** "Top 10 Python libraries for data science," "Best wedding venues in [city]"

**Structure:**
```
H1: "Top 10 [Category] for [Use Case]"

Intro (150 words):
[Why this category matters]
[Evaluation criteria]
[Quick overview]

[For each item, 1-10]
H2: "#[Number]. [Item Name]"
- Why it ranked [#]
- Key features (100-150 words)
- Best for [specific case]
- Link / CTA

H2: "Honorable Mentions"
[3-5 items that didn't make top 10, why]

H2: "Comparison Table"
[All 10 items compared on key criteria]

H2: "FAQ"
[10-15 questions about category]

H2: "Final Verdict"
[Key takeaways + summary]

CTA: [Explore these options]
```

**Unique value:**
- Ranking methodology (you decided criteria + weighting)
- Original evaluations (not copied from other lists)
- Updated data (previous top 10 may have changed)

---

### Playbook 5: Example / Case Study Pages

**Use case:** Demonstrating concepts through real-world examples.

**Example:** "How [Brand] uses [tactic]," "Real-world examples of [concept]"

**Structure:**
```
H1: "[Number] Real-World Examples of [Concept]"

Intro (150 words):
[What is concept]
[Why examples matter]
[Overview of cases]

[For each example]
H2: "Example [#]: [Company/Product Name]"
- Context (what they were trying to do)
- How they applied [concept]
- Results (metrics, outcomes)
- Lessons learned
- Link to original case study / source

H2: "Common Patterns Across Examples"
[150 words analyzing what worked]

H2: "How to Apply These Examples"
[Actionable guidance based on patterns]

H2: "FAQ"
[Frequently asked questions about examples]

CTA: [Try these strategies]
```

**Unique value:**
- Original case research (you analyzed cases)
- Pattern discovery (commonalities across cases)
- Application guidance (not just "here are examples")

---

### Playbook 6: Location Pages (Already Covered)

See `location-page-templates.md` for full details.

**Quick summary:**
- Unique per location (city-specific intro, keywords, services)
- Template structure (consistent layout, unique data)
- Scalable to 100+ locations

---

### Playbook 7: Persona Pages

**Use case:** Content tailored to specific user personas.

**Example:** "Guide for beginners," "Advanced user guide," "Enterprise setup guide"

**Structure:**
```
H1: "[Topic] for [Persona]"

Intro (100 words):
[Assumptions about this persona]
[What this guide covers]
[Prerequisites]

H2: "Getting Started (For [Persona])"
[Simplified/advanced steps depending on persona]

H2: "Common Challenges for [Persona]"
[Problems specific to this persona]

H2: "[Persona]-Specific Best Practices"
[Tips/strategies for this persona]

H2: "FAQ from [Persona] Users"
[Q&A relevant to this persona]

H2: "Next Steps for [Persona]"
[Progression path specific to persona]

CTA: [Start your [persona] journey]
```

**Unique value:**
- Persona-specific content (different from generic guide)
- Tailored examples (beginners get beginner examples; experts get advanced)
- Persona progression (where to go next)

**Example output:** 1 topic × 3 personas (beginner, intermediate, advanced) = 3 unique pages.

---

### Playbook 8: Integration Pages

**Use case:** How-to guides for tool combinations.

**Example:** "Zapier + HubSpot integration," "Shopify + Mailchimp automation"

**Structure:**
```
H1: "How to Connect [Tool A] + [Tool B]"

Overview (100 words):
[What this integration does]
[Benefits of connecting these tools]
[Use cases]

Step-by-Step Setup (300 words):
[Prerequisites]
[Step 1: Set up in Tool A]
[Step 2: Set up in Tool B]
[Step 3: Test integration]
[Step 4: Verify data flow]

Automation Examples (200 words):
[Example use case 1]
[Example use case 2]
[Example use case 3]

Troubleshooting (150 words):
[Common errors + fixes]
[How to debug]

H2: "Alternative Integrations"
[Other tools that connect A + B]

CTA: [Try this integration now]
```

**Unique value:**
- Original step-by-step (based on actual testing)
- Current screenshots (tools change; your guide updates)
- Use case examples (specific, not generic)

---

### Playbook 9: Glossary Pages

**Use case:** Define niche-specific terminology.

**Example:** "Glossary of SEO terms," "Medical terminology guide," "Crypto terms explained"

**Structure:**
```
H1: "[Industry] Glossary"

Intro (100 words):
[Why terminology matters]
[How to use this glossary]
[Scope of terms covered]

[For each term, alphabetically]
H3: "[Term]"
- Definition (50-100 words)
- Example usage (sentence using term)
- Related terms (internal links)
- External source link

Optional: Grouping
H2: "Category: [Terminology Group]"
[10-15 related terms grouped]
```

**Unique value:**
- Original definitions (written in your voice)
- Examples (specific to your industry)
- Related terms (internal linking structure)

**Output:** 50 terms → 50 internal-linked pages.

---

### Playbook 10: Translation Pages (Multi-Language)

**Use case:** Expanding to new language markets.

**Structure:**
```
Same content structure as primary language
WITH proper hreflang tags:

<link rel="alternate" hreflang="en" href="https://example.com/en/" />
<link rel="alternate" hreflang="es" href="https://example.com/es/" />
<link rel="alternate" hreflang="fr" href="https://example.com/fr/" />
```

**Unique value:**
- Localization (not just translation; adapt examples/context)
- Currency/pricing updates (if pricing varies by region)
- Regional differences (different use cases or norms per region)

**Important:** hreflang + proper language tags prevent duplicate content penalty.

---

### Playbook 11: Directory Playbook

**Use case:** Aggregating listings with curation.

**Example:** "Directory of [category] in [region]"

**Structure:** See `programmatic-seo-playbook.md` full section for details.

---

### Playbook 12: Profile Pages

**Use case:** Individual profiles (people, companies, products).

**Example:** "Employee profiles," "Customer profiles," "Product profiles"

**Structure:**
```
H1: "[Profile Name]"

Profile header:
- Photo
- Title/role
- Bio (150 words)

H2: "About [Name]"
[Longer bio + background]

H2: "Expertise"
[Skills/specialties]

H2: "[Name]'s Content"
[Links to articles/projects by this person]

H2: "Connect with [Name]"
[Social links, contact info]

Schema markup: Person or LocalBusiness
```

**Unique value:**
- Original bio/background
- Content aggregation (linking their articles)
- Real profile data (not templated)

---

## Quality Gates (Preventing Thin Content)

Not all programmatic content is created equal. **Google penalizes thin content:**

### Thin Content Signals

❌ **Avoid:**
- Exact template copy-paste (same text per page)
- Zero unique data (only URL parameter changes)
- AI-generated with zero human review
- Keyword stuffing in unique fields
- Duplicate metadata across pages
- No original insights / opinions / research

✅ **Do:**
- Unique intro paragraph per page (even if generated by AI, must be rewritten)
- Unique data per page (city variations, product specs, use-case angles)
- Human review of AI-generated content
- Original analysis / opinions / comparisons
- Unique metadata per page (not templated)
- Original research / statistics / examples

### Quality Checklist Per Page

- [ ] Unique value proposition (not copy-paste from similar page)
- [ ] Minimum word count met (200+ per template)
- [ ] At least ONE data element unique (city name, product name, use case, etc.)
- [ ] At least ONE original opinion/analysis/comparison
- [ ] Human review completed (proof-read, fact-checked)
- [ ] No keyword stuffing
- [ ] Unique H1 and meta description
- [ ] Internal links to related pages (not orphaned)

---

## Implementation Workflow

**Phase 1: Template Design (Week 1)**
- Choose playbook(s) to start with
- Design page structure
- Identify unique data elements
- Create content brief

**Phase 2: Data Gathering (Week 2)**
- Compile keyword list OR location list OR product list
- Organize in spreadsheet
- Identify unique data per page

**Phase 3: Content Generation (Week 3)**
- Generate initial content (manual or AI)
- Set up templated structure
- Batch generate variations

**Phase 4: QA & Review (Week 4)**
- Random sample check (review 5-10 pages)
- Fact-check unique data
- Proof-read
- Verify uniqueness (not duplicates)

**Phase 5: Publishing (Week 5)**
- Batch publish (10-50 pages)
- Monitor indexation
- Track performance

**Phase 6: Iteration (Ongoing)**
- Monitor CTR and rankings
- Update underperforming pages
- Add more pages as you optimize

---

## ROI Expectations

**Typical programmatic SEO campaign:**

| Metric | Timeline | Expectation |
|--------|----------|------------|
| Pages indexed | 2-4 weeks | 60-80% of published pages |
| Traffic (organic) | 2-3 months | 2-5x increase |
| Average ranking position | 3-6 months | Top 20 for 20-30% of keywords |
| Cost per page | One-time | $10-100 (AI) to $500-2000 (custom) |

**Payback:** 50 pages × avg $150 cost = $7,500 investment
Typical = 50 pages × 10 visits/month each = 500 monthly organic visits
@ $30 CPC (ecommerce) = $15,000/month revenue potential
= 2-month payback

---

## Summary

Programmatic SEO works when you:

1. **Choose right playbook** (template, curation, comparison, list, persona, etc.)
2. **Define unique data elements** (city, product, use case, perspective)
3. **Maintain quality gates** (unique intro + data + human review per page)
4. **Scale intelligently** (batch publish, monitor, iterate)
5. **Track performance** (monitor CTR, rankings, traffic lift)

**Result:** 100-500 rankable pages created with 1-2x effort of 10-20 manual pages.
