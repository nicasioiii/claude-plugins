---
name: "Write Content"
description: |
  Create SEO-optimized content from brief to final draft. Activates content-production
  and ai-seo-content-automation skills. Outputs a complete article with SEO optimization,
  internal link suggestions, and schema recommendations.
---

# /write-content -- SEO Content Production Workflow

## Skills Activated
- **content-production** (primary) -- 4-stage writing process, content briefs, templates, editing
- **ai-seo-content-automation** (secondary) -- AI-assisted writing, quality guardrails

## Invocation
```
/write-content [keyword or topic]
```

## Required Input
Ask the user for:
1. **Target keyword** -- primary keyword to rank for
2. **Content type** -- info post, review, roundup, vs post, alternatives, how-to, listicle
3. **Target audience** -- who is reading this and what problem are they solving
4. **Word count target** -- or ask "what are top-ranking articles doing?"
5. **Tone** -- formal/casual, funny/serious, enthusiastic/matter-of-fact
6. **First-hand experience** -- does the user have personal experience to inject? (critical for E-E-A-T)
7. **Internal linking targets** -- what existing pages should this article link to?

---

## Phase 1: Content Brief (10 minutes)

Generate a complete content brief:

### Brief Output
```
TARGET KEYWORD: [keyword]
SECONDARY KEYWORDS: [2-5 related keywords]
SEARCH INTENT: [informational / commercial / transactional]
BUYER'S JOURNEY: [TOFU / MOFU / BOFU]

CONTENT TYPE: [info post / review / roundup / vs / alternatives / how-to / listicle]
WORD COUNT TARGET: [X words]
UNIQUE ANGLE: [What makes this piece different from what already ranks]

COMPETITOR ANALYSIS:
- Top result: [URL] -- [Strengths] -- [Weaknesses/Gaps]
- Runner-up: [URL] -- [Strengths] -- [Weaknesses/Gaps]
- Gap opportunity: [What no one is covering]

ON-PAGE SEO TARGETS:
- SEO title: [draft, <60 chars, keyword front-loaded]
- Meta description: [draft, <160 chars, answer-spoiling]
- URL slug: [keyword-with-hyphens]
- H1: [near-identical to SEO title]
```

---

## Phase 2: Research & Outline (10 minutes)

### Subtopic Research (Nat Eliason 3-Step Process)
1. Check "also rank for" data for target keyword
2. SERP analysis of top 3-5 results for missed subtopics
3. Identify terms/topics competitors cover that you should include

### Generate Outline
```
H1: [Title with primary keyword]

Introduction (Problem > Solution > Reveal structure)
- Problem: [pain point]
- Solution: [approach]
- Reveal: [hook to continue reading]

H2: [Primary keyword -- first section]
  H3: [Subtopic 1]
  H3: [Subtopic 2]

H2: [Secondary keyword 1]
  H3: [Detail point]
  H3: [Detail point]

H2: [Secondary keyword 2 or question-style for AI extraction]
  [40-60 word answer block]

H2: [Additional sections as needed]

H2: FAQ
  H3: [Question from People Also Ask]
  H3: [Question from Reddit/forums]
  H3: [Question from keyword research]

H2: [Primary keyword -- summary section (last H2)]

Conclusion (Restate problem + Key takeaways + CTA)
```

---

## Phase 3: Draft Content

### Writing Guidelines

**Introduction (First 100 Words)**
- ALL target keywords must appear
- Main keyword in first 2-3 sentences
- Follow Problem > Solution > Reveal structure
- Hook the reader within first paragraph

**Body Content**
- Each keyword appears 2-3x minimum (under 1K words), 4-5x for longer articles
- Spread keywords evenly across beginning, middle, end
- One subheading per ~300 words
- Use keyword variations in H3s (synonyms, related terms)
- Include at least one image per keyword with optimized alt text

**For Commercial Content (Reviews/Roundups/Vs/Alternatives)**
- Apply feature-to-benefit translation for every product feature
- Include comparison tables
- Honest pros AND cons (trust converts better than hype)
- Inverted pyramid: best recommendation first
- Affiliate link placement: comparison table, detailed review section, final recommendation

**For Info Content (How-To/Listicle/Question Posts)**
- Answer the question directly in first paragraph (targets featured snippets)
- Provide depth, context, and supporting evidence after the answer
- Link to authoritative external sources
- Include actionable steps the reader can follow

**AI-Optimized Elements**
- 50-60 word summary snippet at top of article
- Question-style H2s with 40-60 word answer blocks
- FAQ section mirroring key facts
- Natural phrasing throughout (AI systems prefer it)
- Year reference in title/H1 for recency signal

**Last 100 Words**
- ALL target keywords must appear
- Restate key points
- Clear CTA based on content goal

---

## Phase 4: Self-Editing (6 Passes)

Walk the user through the editing process:

1. **Content pass** -- any sections incomplete? Word choice improvements? Missing research?
2. **Grammar pass** -- spelling, grammar, formatting consistency
3. **Read aloud pass** -- does it flow naturally? Any awkward phrasing?
4. **Audience pass** -- would the target reader find this valuable?
5. **Plagiarism pass** -- run through Copyscape or similar
6. **SEO pass** -- final checklist:
   - [ ] Primary keyword in meta title (front-loaded, <60 chars)
   - [ ] Primary keyword in meta description (<160 chars)
   - [ ] Primary keyword in URL slug
   - [ ] Primary keyword in H1 (matches meta title)
   - [ ] Primary keyword in first and last H2
   - [ ] All keywords in first 100 words
   - [ ] All keywords in last 100 words
   - [ ] Keywords spread evenly through body
   - [ ] 2+ internal links per 500 words
   - [ ] 2+ external links to authoritative sources per 500 words
   - [ ] Every image has optimized alt text
   - [ ] Only one H1 on the page

---

## Phase 5: Post-Publication

### Internal Linking (After Publishing)
- Go back to existing articles related to the new content
- Add links FROM old articles TO the new one
- Use keyword-optimized anchor text
- Search your CMS for the new article's topic to find linking opportunities

### Promotion Checklist
- [ ] Share on social channels (automated via Zapier if set up)
- [ ] Republish on Medium (wait 2+ days, use Import feature for canonical)
- [ ] Republish on LinkedIn as article
- [ ] Post to relevant subreddits (if appropriate)
- [ ] Tag mentioned brands/influencers in social posts
- [ ] Add to automated re-sharing library (MeetEdgar)

### Schema Recommendation
Based on content type, suggest appropriate schema:
- Blog post -> Article schema with author, dates
- Product review -> Review schema with rating
- How-to -> HowTo schema with steps
- FAQ -> FAQPage schema
- Comparison -> Article schema (no specific comparison schema)

---

## Output Summary

Deliver to user:
1. Complete content brief
2. Full article outline with header hierarchy
3. Draft article (or guidelines for drafting)
4. SEO optimization checklist (completed)
5. Internal link suggestions (3-5)
6. Schema JSON-LD code (ready to paste)
7. Promotion checklist
8. Post-publication internal linking recommendations
