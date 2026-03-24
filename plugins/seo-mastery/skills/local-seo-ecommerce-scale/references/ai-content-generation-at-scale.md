# AI Content Generation at Scale: Workflows & Quality Control

**Length:** ~300 lines
**Purpose:** Practical AI workflows for generating content at 100+ page scale

---

## Part 1: When AI Content Works (& When It Doesn't)

### AI Content SUCCESS Cases

✅ **Use AI for:**
- Location page variations (rewrite city intro 100 times)
- Product description variations (update 500 product descriptions)
- FAQ generation (create location-specific Q&A)
- Content expansion (turn outline into full article)
- Rewriting for tone (change academic → casual voice)

### AI Content FAILURE Cases

❌ **Don't use AI for:**
- Complex original research (needs human investigation)
- Competitive analysis (requires judgment calls)
- Brand positioning (needs strategic input)
- Sensitive topics (medical, legal—needs expert review)
- Pure content (no human edit or unique angle)

**Key principle:** AI works best for **variation + expansion**, not **creation from scratch**.

---

## Part 2: AI Content Quality Framework

### Three-Tier Quality System

**Tier 1: Premium (Human-Written, AI-Enhanced)**
- Human writes original outline
- AI fills sections
- Human edits heavily
- Multiple rounds of review
- Typical: Blog posts, thought leadership
- Cost: $200-500 per article
- Quality: 95%+ publishable rate

**Tier 2: Standard (AI-Written, Human-Edited)**
- AI generates initial draft
- Human does light editing (grammar, clarity)
- Fact-checking on sample set
- Single review pass
- Typical: Category pages, location pages
- Cost: $20-50 per article
- Quality: 80-90% publishable rate

**Tier 3: Volume (AI-Generated, Template-Based)**
- AI generates variation from template
- Spot-check QA (1 in 10 pages reviewed)
- No human editing (structural guarantee)
- Typical: 50+ page variations
- Cost: $2-10 per article
- Quality: 60-80% publishable rate

**Strategy:** Start with Tier 2. Scale to Tier 3 once you prove quality.

---

## Part 3: AI Workflows (Step-by-Step)

### Workflow 1: Location Page Variations (Tier 3)

**Task:** Write 50 unique location page intros (different cities, same business).

**Setup:**
```
Input spreadsheet:
City | State | Population | Main Competitor | Key Problem
Madison | WI | 260,000 | [Competitor A] | [Problem X]
Milwaukee | WI | 600,000 | [Competitor B] | [Problem Y]
...
```

**Prompt template (for Claude):**
```
You are a copywriter for [Business Type] company.
Write a unique 200-word intro for a location page.

Location: [City], [State]
Population: [Pop]
Local competitors: [Competitors]
Common problem in this city: [Problem]
Business name: [Name]
Unique service: [Service]

Requirements:
- Include city name 3+ times
- Mention local context/problem specific to [City]
- Reference competitor differentiation
- Conversational tone (not corporate)
- Include CTA ("Free consultation")
- No keyword stuffing

Write ONLY the intro paragraph, no other text.
```

**Execution:**
1. Create spreadsheet with city data
2. Use API integration (Claude API) or copy-paste workflow
3. Generate all 50 intros (10 minutes with API)
4. Spot-check 5 random intros for quality
5. If >80% quality, approve all
6. If <80%, adjust prompt and regenerate failing batch

**Expected quality:** 85-90% of intros publishable with zero edits.

### Workflow 2: Product Description Rewriting (Tier 2)

**Task:** Rewrite 200 product descriptions in 3 different styles (casual, formal, excited).

**Setup:**
```
Input: Product specs from CSV
- Product name
- Category
- Price
- Key features (bulleted)
- Current description (100 words)
```

**Prompt template:**
```
You are rewriting product descriptions for [Industry].

Original description:
[Current 100-word description]

Product specs:
- Name: [Name]
- Category: [Category]
- Price: [Price]
- Key features: [Features]

Rewrite the description in [TONE] voice:
- [TONE] = "Casual" | "Professional" | "Excited"
- Target audience: [Audience]
- Include benefit statement (not just features)
- Length: 150-200 words
- Include keyword: [Primary keyword]
- One CTA: [CTA]

Write ONLY the new description.
```

**Execution:**
1. Extract product data (name, specs, current description)
2. Generate 3 versions per product (API batch call)
3. Human review: Pick best version for each product (5 seconds per pick)
4. Update database with chosen version
5. Publish

**Expected quality:** 100% publishable after human selection.

### Workflow 3: FAQ Generation per Location (Tier 3)

**Task:** Generate 50 location-specific FAQ sets.

**Setup:**
```
Input:
City | Service | Local Problem | Common Question 1 | Common Question 2
Madison | Carpet cleaning | Pet odor issues | Cost range? | Timeline?
```

**Prompt template:**
```
Generate 8 FAQ questions and answers for [Service] in [City].

Context:
- City: [City]
- State: [State]
- Service: [Service]
- Local challenge: [Problem]
- Population: [Pop]

Generate questions that [City] residents would ask:
- 3 questions about [Service] specific to [City]
- 2 questions about pricing
- 2 questions about process
- 1 question about timeline/availability

Format: Q: [Question]\nA: [Answer 100-200 words]

Answer each question including:
- References to [City] neighborhoods or context
- Address [Local challenge]
- Include [City] name in answer
- Professional but friendly tone

Output ONLY questions and answers.
```

**Execution:**
1. Batch generate FAQ for 50 cities
2. Spot-check 5 random FAQs
3. If >85% quality, approve all
4. Publish to location pages

**Expected quality:** 80-85% directly publishable.

---

## Part 4: Fact-Checking & QA Protocol

### Tier 1 QA (Premium Content)

Fact-check 100% of content:
- Verify claims against sources
- Check statistics (cite sources)
- Verify dates/timelines
- Review for bias/accuracy
- Human expert review

**Time:** 30-60 minutes per 1000 words

### Tier 2 QA (Standard Content)

Spot-check 20% of content:
- Random sample 20% of batch
- Check 3-5 major claims per sample
- Verify no hallucinations (made-up stats)
- Grammar/clarity check

**Time:** 5 minutes per 1000 words

### Tier 3 QA (Volume Content)

Spot-check 10% of content:
- Random sample 1 in 10 pages
- Check basic structure (headers present, length OK)
- Check no obvious errors
- Trust template + AI consistency

**Time:** 2 minutes per 1000 words

### Common AI Hallucinations (Watch For)

❌ **Fabricated statistics:** "87% of [population] prefer [service]" (made up)
❌ **Fake citations:** "According to XYZ study (no actual link)"
❌ **Outdated info:** "As of 2024..." (when you're in 2026)
❌ **Competitor claims:** "We beat [competitor] because..." (unverified)
❌ **Price claims:** "Average cost is $X" (no source)

### QA Checklist Per Page

- [ ] No fabricated statistics (verify 3+ numeric claims)
- [ ] No fake quotes or citations
- [ ] Current information (no outdated references)
- [ ] No grammatical errors (proofread carefully)
- [ ] Unique value (not just regurgitation)
- [ ] Local context included (city name, neighborhoods, local problems)
- [ ] No keyword stuffing (read naturally)
- [ ] CTA present and clear
- [ ] Links working (if applicable)
- [ ] No competitor name-dropping without context

---

## Part 5: AI Prompt Engineering for Consistency

### Prompt Structure (Template)

```
ROLE: You are a [Role] for [Company/Industry].

TASK: [What to write/rewrite/generate]

INPUT:
[Specific data: name, city, specs, etc.]

REQUIREMENTS:
1. [Style requirement: tone, voice, format]
2. [Audience: beginner, professional, etc.]
3. [Length: 150 words, 300-400 words, etc.]
4. [Keyword inclusion: primary keyword is [Keyword]]
5. [Uniqueness: must vary from template, local context]
6. [Structure: include H2, bullet list, CTA, etc.]

CONSTRAINTS:
- No keyword stuffing
- No fabricated statistics
- Professional tone
- [City name] mentioned 3+ times (for location content)

OUTPUT FORMAT:
[Specify exact format: markdown, HTML, plain text]
[Example output if needed]

Write ONLY [type of content] without intro/explanation.
```

### Consistency Tips

1. **Lock temperature:** temperature=0.5 (consistent but creative)
2. **Test prompt:** Run 3 samples first, adjust before batch
3. **Version control:** Save final prompt in documentation
4. **Feedback loop:** If outputs bad, adjust prompt + regenerate, don't manually fix
5. **Check samples:** Before batch-applying prompt, verify 5 outputs

---

## Part 6: AI Tool Comparison (For Scaling)

| Tool | Cost | Speed | Quality | Best For |
|------|------|-------|---------|----------|
| **Claude API** | $0.003/1k input | Fastest | Highest | Production scale (100+ pages) |
| **ChatGPT API** | $0.0005/1k input | Fast | Good | Budget-friendly scaling |
| **Perplexity API** | $0.003/1k input | Fast | Good | Research-backed content |
| **Custom model** | $$$$ (high) | Variable | Custom | Long-term, 10,000+ pages |
| **Manual ChatGPT** | $20/mo | Slow | Variable | Small projects (<100 pages) |

**Recommendation:** Claude API for quality, ChatGPT API for budget.

---

## Part 7: Scaling Workflow (100+ Pages)

### Phase 1: Pilot (10 pages)

1. Write manual prompt
2. Generate 10 samples
3. QA 100% (ensure quality)
4. Refine prompt based on feedback
5. Adjust tone/structure

### Phase 2: Batch Testing (50 pages)

1. Use refined prompt
2. Generate 50 pages
3. QA 20% (spot-check)
4. Measure quality rate
5. If >85%, proceed; if <85%, adjust prompt

### Phase 3: Scale (200+ pages)

1. Lock prompt
2. Batch generate 200+ pages
3. QA 10% (spot-check)
4. Publish in batches of 50
5. Monitor indexation + CTR

### Phase 4: Monitoring (Ongoing)

- Track indexation rates (should be 90%+ within 2-4 weeks)
- Monitor average CTR (should match control pages)
- Sample QA monthly (verify quality stays consistent)
- Update content quarterly (refresh stats, links, seasonal info)

---

## Part 8: Cost Calculator

**Example: 100 location pages**

| Component | Cost | Notes |
|-----------|------|-------|
| Prompt engineering (2 hours) | $100 | Done once, reused |
| AI generation (100 pages × $0.02) | $2 | Claude API cost |
| QA review (10 pages × $20) | $200 | Spot-check 10% |
| Publishing setup (2 hours) | $100 | Setting up CMSintegration |
| **Total** | **$402** | **~$4 per page** |

**vs. Manual writing:**
- 100 pages × 3 hours = 300 hours
- 300 hours × $100/hr = $30,000
- **Savings:** $29,598 (98% reduction)

---

## Part 9: Red Flags & Troubleshooting

| Problem | Cause | Fix |
|---------|-------|-----|
| 30%+ pages need heavy editing | Prompt too vague | Rewrite prompt, add constraints |
| AI repeating same content | Temperature too low | Increase temperature to 0.7-0.8 |
| Fabricated statistics | Model hallucinating | Add constraint: "No statistics without source" |
| Pages not ranking | Poor quality | Improve QA % (move to Tier 2) |
| Indexation <60% | Thin/duplicate content | Add more unique data per page |
| CTR below control | Quality issue | Random sample QA, identify pattern |

---

## Part 10: Ethical & Quality Considerations

### Transparency

- **Disclose AI generation** if required by platform (Google doesn't require explicit disclosure, but transparency builds trust)
- **Mark AI content** internally (tag in CMS for tracking)
- **Use human reviews** (maintain human oversight at every stage)

### Quality Standards

- **Minimum word count:** 200+ per page (thin content = penalties)
- **Unique data:** Every page must have at least 1 unique data element
- **Human review:** Minimum 10% QA (spot-check, not 0% review)
- **Fact-checking:** 20%+ of content fact-checked monthly
- **Updates:** Refresh AI content quarterly (maintains freshness signal)

---

## Summary

AI content at scale works when you:

1. **Choose right tier** (Premium for important, Tier 3 for variations)
2. **Engineer prompt** (detailed requirements, clear examples, constraints)
3. **Test before scaling** (pilot 10 → test 50 → scale 200+)
4. **QA appropriately** (Tier 1: 100%, Tier 2: 20%, Tier 3: 10%)
5. **Monitor results** (track indexation, CTR, rankings vs. control)
6. **Update regularly** (refresh quarterly, maintain freshness)

**Result:** Generate 100+ pages in days (not months) while maintaining 85-90% quality.
