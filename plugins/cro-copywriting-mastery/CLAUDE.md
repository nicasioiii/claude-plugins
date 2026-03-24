# CRO Copywriting Mastery: Plugin Routing & Execution Guide

**Plugin Name:** `cro-copywriting-mastery`
**Status:** Complete Implementation
**Date:** March 11, 2026
**Skills:** 11 core + 8-10 slash commands

---

## Plugin Overview

This plugin provides a complete CRO and copywriting system organized by workflow stage. Users enter at any skill but achieve best results following the progression: Understand → Discover → Structure → Write → Persuade → Optimize.

The plugin is based on 13 expert courses (David Deutsch, Copy Hackers, Eddie Shleyner, Glenn Fisher, Todd Brown, Adil Amarsi, Ryan Deiss, and others) synthesizing 1M+ words of field-tested frameworks.

---

## THE 11 CORE SKILLS (Execution Order)

### FOUNDATION LAYER (Skills 1-3)
**User starts here for new projects or audience understanding.**

1. **customer-avatar-research** — Customer Avatar & Audience Research
   - Trigger: "Who am I writing to?" "I need to understand my audience"
   - Output: Detailed customer avatar, before-after grid, audience lifecycle

2. **benefit-discovery** — Benefit Discovery & Problem Translation
   - Trigger: "How do I turn features into benefits?" "What problems do I solve?"
   - Output: Benefit map, emotional benefits, FAB charts

3. **big-idea-positioning** — Big Idea & Unique Positioning
   - Trigger: "What's my unique angle?" "How do I differentiate?"
   - Output: Big Idea framework, primary promise, unique mechanism articulation

### STRUCTURE LAYER (Skills 4-6)
**User has foundation; now needs page architecture.**

4. **page-structure-templates** — Page Structure & Template Selection
   - Trigger: "What page type should I use?" "How do I structure this page?"
   - Output: Chosen template, wireframe, page architecture

5. **headline-hook-engine** — Headlines, Hooks & Attention-Grabbers
   - Trigger: "How do I write a great headline?" "What makes a good hook?"
   - Output: 10+ headline variations, tested winners

6. **copy-flow-organization** — Copy Flow & Organization Frameworks
   - Trigger: "How do I organize my copy?" "What goes where in the page?"
   - Output: Outlined structure (7-step or 10-step), section-by-section framework

### WRITING LAYER (Skills 7-8)
**User has structure; now writes core content.**

7. **story-narrative-copywriting** — Story, Narrative & Emotional Copywriting
   - Trigger: "How do I tell a story that converts?" "How do I make copy emotional?"
   - Output: Story framework, narrative structure, story beats

8. **email-sequence-architecture** — Email Sequences & Multi-Touch Campaigns
   - Trigger: "How do I write email sequences?" "What should my email flow look like?"
   - Output: 7-email welcome sequence template, broadcast email flows

### PERSUASION LAYER (Skills 9-10)
**User has copy; now makes it bulletproof.**

9. **objection-psychology-framework** — Objection Handling & Persuasion Psychology
   - Trigger: "How do I handle objections?" "What objections might readers have?"
   - Output: Objection map, proof hierarchy, FAQ framework, guarantee copy

10. **call-to-action-mastery** — Call-to-Action Design & Conversion
    - Trigger: "How do I design a high-converting CTA?" "What makes people click?"
    - Output: CTA copy formulas, placement strategy, form friction audit

### OPTIMIZATION LAYER (Skill 11)
**User has complete page; now improves it.**

11. **testing-audit-optimization** — Testing, Auditing & CRO Optimization
    - Trigger: "How do I test my page?" "What should I audit?" "How do I improve?"
    - Output: Test plan, audit scores, prioritized improvements

---

## SKILL ROUTING TABLE (User Intent → Skill)

### User Says... → Route To...

**"I don't know who I'm writing to"**
→ customer-avatar-research `/avatar-brief` or `/before-after-grid`

**"I have a feature but don't know the benefit"**
→ benefit-discovery `/fab-translator`

**"What makes me different from competitors?"**
→ big-idea-positioning `/big-idea-builder`

**"Should this be a landing page, sales page, or homepage?"**
→ page-structure-templates `/page-type-picker`

**"I need a great headline"**
→ headline-hook-engine `/headline-generator`

**"How should I organize my copy?"**
→ copy-flow-organization `/outline-7-step` or `/outline-10-step`

**"I want to tell a compelling story"**
→ story-narrative-copywriting `/story-builder`

**"How do I write an email sequence?"**
→ email-sequence-architecture `/welcome-sequence-builder`

**"What objections will my reader have?"**
→ objection-psychology-framework `/objection-mapper`

**"How do I design my CTA?"**
→ call-to-action-mastery `/cta-generator`

**"Is my page working? How do I improve it?"**
→ testing-audit-optimization `/audit-copy` or `/test-planner`

---

## AMBIGUOUS REQUEST DECISION TREE

### User Says: "Help me improve my page"

**Ask clarifying questions:**
1. Is this a brand new page or existing page?
2. Do you know your conversion rate? Any baseline?
3. What's your biggest concern about the page?

**Route decision:**
- "I don't have a page yet" → Start with customer-avatar-research (Skill 1)
- "Page exists, conversion is low" → testing-audit-optimization `/audit-copy`
- "Page exists, I know what's wrong" → Route to specific skill
- "Not sure what's wrong" → testing-audit-optimization `/audit-copy` first (diagnose), then other skills

### User Says: "Write my sales page"

**Ask clarifying questions:**
1. Do you have your core message/positioning?
2. Do you know your customer's objections?
3. Is this a digital product, physical product, or service?

**Route decision:**
- No positioning → big-idea-positioning then page-structure-templates
- Have positioning → page-structure-templates then copy-flow-organization
- Ready to write → copy-flow-organization then call-to-action-mastery

### User Says: "I need help with my email"

**Ask clarifying questions:**
1. Is this a welcome sequence or broadcast email?
2. How many emails in the sequence?
3. What's the goal (lead gen, sales, nurture)?

**Route decision:**
- Welcome sequence → email-sequence-architecture `/welcome-sequence-builder`
- Single broadcast email → copy-flow-organization (adapt structure for email)
- Subject line only → headline-hook-engine `/subject-line-crafter`

---

## CROSS-SKILL WORKFLOWS

### Workflow 1: Complete Landing Page from Zero

1. `/avatar-brief` (customer-avatar-research) — Define who you're writing to
2. `/fab-translator` (benefit-discovery) — Turn features into benefits
3. `/big-idea-builder` (big-idea-positioning) — Develop unique positioning
4. `/page-type-picker` (page-structure-templates) — Choose landing page type
5. `/headline-generator` (headline-hook-engine) — Create 10+ headlines
6. `/outline-7-step` (copy-flow-organization) — Structure the copy
7. `/story-builder` (story-narrative-copywriting) — Build story sections
8. `/objection-mapper` (objection-psychology-framework) — Plan proof/FAQ
9. `/cta-generator` (call-to-action-mastery) — Design CTAs
10. `/test-planner` (testing-audit-optimization) — Plan first tests

### Workflow 2: Optimize Existing Page

1. `/audit-copy` (testing-audit-optimization) — Score current page
2. `/headline-generator` (headline-hook-engine) — Test headline variations
3. `/objection-mapper` (objection-psychology-framework) — Add missing proofs
4. `/cta-generator` (call-to-action-mastery) — Test CTA variations
5. `/test-planner` (testing-audit-optimization) — Schedule improvements

### Workflow 3: Build Email Sequence

1. `/avatar-brief` (customer-avatar-research) — Understand audience
2. `/benefit-brainstorm` (benefit-discovery) — Identify key benefits
3. `/welcome-sequence-builder` (email-sequence-architecture) — Build 7-email template
4. `/subject-line-crafter` (headline-hook-engine) — Write subject lines
5. `/email-outline` (copy-flow-organization) — Outline email body
6. `/cta-generator` (call-to-action-mastery) — Design email CTAs
7. `/test-planner` (testing-audit-optimization) — Plan A/B tests

### Workflow 4: Rebuild Underperforming Page

1. `/audit-homepage` or `/audit-copy` (testing-audit-optimization) — Diagnose problems
2. Jump to specific skill based on audit findings
3. Rebuild weak sections using appropriate skill
4. `/test-planner` (testing-audit-optimization) — Plan tests

---

## SLASH COMMANDS (8-10 Most Important)

### Foundation & Discovery Commands
- `/avatar-brief` — 5-minute customer definition worksheet
- `/before-after-grid` — Interactive before-after builder
- `/benefit-brainstorm` — Emotional benefits worksheet
- `/big-idea-builder` — Big Idea development framework

### Structure & Copy Commands
- `/page-type-picker` — Landing page type decision tree
- `/headline-generator` — 10 headline formulas with examples
- `/outline-7-step` — Quick 7-section structure
- `/outline-10-step` — Detailed 10-section structure

### Persuasion Commands
- `/objection-mapper` — Identify & plan objection responses
- `/cta-generator` — CTA copy formulas & variations
- `/faq-builder` — Generate Q&A from offer

### Optimization Commands
- `/audit-copy` — 20-point copy audit with scoring
- `/audit-homepage` — 7-point homepage audit
- `/test-planner` — A/B testing priority matrix

### Email-Specific Commands
- `/welcome-sequence-builder` — 7-email template
- `/subject-line-crafter` — Email subject lines
- `/email-outline` — Email body structure

---

## EXECUTION PRIORITY ORDER

When user asks for help, use this priority order for routing:

### Priority 1 (New Projects)
Start with Foundation layer (Skills 1-3) unless user already has positioning.

### Priority 2 (Without Structure)
If user has positioning but no page: Structure layer (Skills 4-6).

### Priority 3 (Without Copy)
If user has structure but no copy: Writing layer (Skills 7-8).

### Priority 4 (Weak Page)
If user has full page but it's underperforming: Persuasion layer (Skills 9-10).

### Priority 5 (Optimization)
If user has solid page: Optimization layer (Skill 11).

---

## PRODUCT MARKETING CONTEXT CHECK

### Before Giving Advice, Clarify

**Is the user writing for:**
- **Themselves (bootstrapped)** → Emphasize free/low-cost tools
- **Startup/Early stage** → Emphasize quick wins, testing
- **Mature company** → Emphasize systems, long-term optimization
- **Agency/Freelancer** → Emphasize frameworks for client delivery
- **Personal brand/creator** → Emphasize authenticity, story

**Adjust guidance accordingly:**
- Bootstrapped: Focus on high-ROI tests (headline, offer)
- Startup: Focus on finding product-market fit first
- Mature: Focus on systematic testing program
- Agency: Focus on replicable frameworks
- Creator: Focus on authenticity + persuasion

---

## SCOPE BOUNDARIES

### IN SCOPE (This Plugin)
- Landing page copy (5+ types)
- Homepages
- Sales pages and sales letters
- Opt-in pages
- Email sequences and email copy
- VSL scripts
- Webinar copy
- Ad copy (headlines + body)
- Objection handling and FAQ
- CTA design and copy
- A/B testing strategy
- Copy audits and optimization
- Psychology and persuasion
- Customer research
- Benefit and positioning discovery

### OUT OF SCOPE (Other Plugins)
- **Paid ads strategy** → refer to paid-ads-mastery plugin
- **Cold outreach/email** → refer to cold-outbound-mastery plugin
- **SEO and organic search** → refer to seo-mastery plugin
- **Sales calls and negotiation** → refer to sales-negotiation-mastery plugin
- **Lifecycle email marketing** → refer to marketing-skills plugin
- **Form optimization mechanics** → refer to marketing-skills plugin
- **Affiliate marketing strategy** → out of scope
- **Content marketing strategy** → out of scope (copy tactics OK)
- **Product development** → out of scope

**When user asks out-of-scope question, suggest:**
"This is beyond CRO copywriting. For [topic], check the [plugin-name] plugin."

---

## SKILL TRIGGER KEYWORDS (When to Suggest)

### If User Mentions...

**Customer research, audience, avatar, persona, demographics, frustrations, goals**
→ Suggest customer-avatar-research

**Features, benefits, translation, FAB, dimensionalized, emotional, faux benefits**
→ Suggest benefit-discovery

**Big idea, positioning, unique, differentiation, promise, mechanism, catalyst**
→ Suggest big-idea-positioning

**Page type, template, structure, homepage, landing page, opt-in, wireframe**
→ Suggest page-structure-templates

**Headline, hook, attention, subject line, curiosity, benefit headline**
→ Suggest headline-hook-engine

**Copy flow, organization, structure, hook problem solution, 7-step, 10-step**
→ Suggest copy-flow-organization

**Story, narrative, emotional, transformation, before-after, OMG moments**
→ Suggest story-narrative-copywriting

**Email, sequence, welcome, broadcast, multi-touch, subject line, email body**
→ Suggest email-sequence-architecture

**Objections, psychology, proof, biases, guarantee, FAQ, trust, risk**
→ Suggest objection-psychology-framework

**CTA, button, conversion, click, friction, form fields, urgency**
→ Suggest call-to-action-mastery

**Testing, A/B test, audit, optimization, improve, conversion rate, statistical**
→ Suggest testing-audit-optimization

---

## INTER-SKILL REFERENCE PATTERNS

Skills should cross-reference when appropriate:

- **customer-avatar-research → benefit-discovery:** "Now that you understand the audience, let's translate their frustrations into benefits..."
- **big-idea-positioning → page-structure-templates:** "With your positioning locked, here's which page template works best..."
- **page-structure-templates → copy-flow-organization:** "Here's how to fill each section with compelling copy..."
- **headline-hook-engine → copy-flow-organization:** "Your headline sets the tone for the rest of the copy flow..."
- **copy-flow-organization → objection-psychology-framework:** "Notice how we handle objections in the body copy section..."
- **objection-psychology-framework → call-to-action-mastery:** "After addressing objections, a strong CTA seals the deal..."
- **story-narrative-copywriting → copy-flow-organization:** "Stories typically live in the opening or evidence section..."
- **all skills → testing-audit-optimization:** "After building, always audit and test to improve..."

---

## NOTES FOR SKILL IMPLEMENTATION

### Each Skill Should
- Start with YAML frontmatter (non-negotiable)
- Define ONE clear job
- Keep SKILL.md under 500 lines (major learning in references/)
- Include practical templates and formulas
- Reference when to read deeper in references/
- Include quick checklist at end

### Each Reference File Should
- Deep-dive on one specific subtopic
- Include real examples and templates
- Be immediately usable
- Link back to SKILL.md when context needed

### All Commands Should
- Have YAML frontmatter with name/description
- Provide structured worksheet or framework
- Be completable in 5-30 minutes
- Output usable artifact

---

## FINAL GUIDANCE

**For users who are new to CRO:**
Start with Foundation layer. Don't skip to testing until you understand your customer and positioning.

**For users with existing pages:**
Start with audit (testing-audit-optimization) to diagnose problems, then route to appropriate skill.

**For users in a hurry:**
Start with top 3 Tier 1 testing priorities (headline, offer, message) instead of complete workflow.

**For freelancers/agencies:**
Use the complete 11-skill workflow as a client delivery system.

This plugin is complete, interconnected, and ready for deployment.
