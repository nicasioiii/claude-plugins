---
name: Discovery & Direction
description: "Project discovery, scoping, understanding client needs, information architecture, complexity assessment. MANDATORY TRIGGERS: new project, client needs, discovery questions, scoping, information architecture, sitemaps, user flows, wireframing, complexity assessment, stakeholder interviews, brand questionnaire. Do NOT use for — use visual-foundations for design rules, figma-workflows for file organization."
---

# Discovery & Direction

Before designing anything, you must understand what you're solving. This is where 80% of project problems are prevented—by asking the right questions upfront.

## The 8-Step Design Process

Every project follows this sequence. The first three steps are discovery; skipping them guarantees rework.

### Step 1: Understanding the Problem (Priority #1)

**What you're doing:** Interviewing stakeholders, reading briefs, asking "why" repeatedly

**Key principle:** More complex problems require deeper understanding before visual design. Non-visual problems exist that require situational awareness.

**Output:** Problem statement (one sentence that summarizes what you're solving)

**Questions to ask:**
- What problem are we solving?
- Who is experiencing this problem?
- What does success look like?
- What constraints exist (budget, timeline, technical)?

### Step 2: Determining Project Complexity

Complexity determines your workflow. Do this assessment immediately—it drives all downstream decisions.

**High Complexity Project:**
- Multiple user types with conflicting needs
- Complex workflows or data relationships
- Regulatory/accessibility requirements
- Unclear requirements from stakeholders
- **Workflow:** 30min-1hr+ of sketching/discovery required
- **Wireframe:** ESSENTIAL before visual design
- **Example:** Banking app, medical SaaS, government portal

**Medium Complexity Project:**
- Clear use case but multiple features
- Some user flow uncertainty
- Multiple pages/sections
- **Workflow:** Create wireframes/low-fidelity designs to confirm functionality
- **Purpose:** Separates functional conversations (does this flow make sense?) from visual conversations (colors, typography)
- **Example:** E-commerce site, SaaS dashboard, content site

**Low Complexity Project:**
- Simple, agreed-upon functionality
- Few features or pages
- Clear stakeholder alignment
- **Workflow:** Jump straight to visual design if everyone agrees on requirements
- **Wireframe:** Optional; use "low-fidelity explorations" if sketching helps
- **Example:** Marketing website, landing page, portfolio

### Step 3: Create Flows & Maps

Document information architecture before designing screens.

**Content Maps:** Show hierarchical relationship of information
- Example: E-commerce has categories > subcategories > products > product details
- Helps identify missing functionality or unclear organization

**User Flows:** Show how users achieve goals step-by-step
- Include decision points (if user is logged in, show X; if not, show Y)
- Identify error states and edge cases
- Clarify before designing

**Feature Spreadsheet:** Document every feature with acceptance criteria
- Owner: Who's responsible?
- Status: Not started, in progress, complete
- Requirements: What does this feature do?

### Step 4: Wireframe Decision

- **High/Medium complexity:** Wireframe required. Invest 4-8 hours now vs. 40 hours reworking visual design later.
- **Low complexity:** Skip formal wireframes if everyone agrees. Use sketches if helpful for exploration.
- **Key rule:** If you don't fully understand functionality, wireframe before visual design.

### Step 5: Set Design Direction

Define creative style before creating components.
- Visual aesthetic: Modern, playful, sophisticated, minimal?
- Brand personality: What emotion do we want?
- Reference inspiration: 3-5 websites with the right direction

### Step 6: Present Early & Often

Get stakeholder feedback before investing heavily in polish.

### Step 7: Iterate & Refine

Explore multiple directions in color, style, interactions.

### Step 8: Create & Expand the System

Build reusable components once direction is locked.

---

## Determining Complexity: Decision Tree

```
Is there stakeholder disagreement about requirements?
├─ YES → High Complexity
└─ NO → Continue

Are there multiple user types with different goals?
├─ YES → High Complexity
└─ NO → Continue

Is the feature set larger than 5-8 distinct features?
├─ YES → Medium Complexity
└─ NO → Continue

Is the workflow straightforward and linear?
├─ YES → Low Complexity
└─ NO → Medium Complexity
```

---

## Discovery Questions Framework

Ask these during initial client calls. Document answers—they become your project foundation.

### Company Identity & Brand

- What's the company name and origin story?
- What's your vision? (Where do you want to be in 5 years?)
- What's your mission? (Why do you exist?)
- One-sentence company description?
- Brand values (5 words): What do you stand for?

### Brand Personality

- How would you describe your brand? (5 descriptive words)
- What emotions should customers feel when using your product?
- What's your brand voice? (How do you speak to customers?)
- What are you NOT? (Define the opposite to clarify boundaries)
- Celebrity equivalent: If your brand were a famous person, who?

### Target Audience

- **Demographics:** Age range, income, occupation, location
- **Psychographics:** Values, interests, lifestyle, shopping habits
- **Pain points:** What problems do they have?
- **Where do they spend time:** Online (communities, social media), offline (stores, events)

### Competitor Analysis

- Who are your direct competitors?
- Who are indirect competitors (alternative solutions)?
- What do you do better than them?
- What do they do better than you?

### Technical & Business Requirements

- What's the primary goal of this project?
- Secondary goals?
- Success metrics: How do you measure success?
- Timeline and budget?
- Technical constraints or requirements?

### Visual Direction

- Do you have an existing color palette? Open to changes?
- Brand archetype (12 universal archetypes—explorer, sage, innocent, etc.)?
- Reference websites you admire?
- Reference imagery style (photography, illustration, 3D)?
- Imagery preferences: Real people, lifestyle, abstract?

---

## Information Architecture Basics

IA is the blueprint before you design.

### Sitemap

A hierarchical diagram showing:
- All pages in the project
- Parent-child relationships
- Number of levels (typically 2-3 levels max)

**Example: Restaurant website**
```
Home
├── About (team, story, values)
├── Menu (categories → items → details)
├── Reservations
├── Blog
│   └── Individual posts
├── Contact
└── Account (login → profile, order history)
```

**Rule:** If your sitemap has 5+ levels, it's too deep. Flatten it.

### User Flow

Step-by-step journey showing decisions and actions.

**Example: Booking a reservation**
```
Home → Click "Reserve" → Sign in?
├─ New user → Sign up → Enter preferences → Select date/time → Confirm
└─ Existing user → Select date/time → Confirm
→ Confirmation page
```

Identify:
- Decision points (if/then branches)
- Error states (invalid email, date unavailable)
- Success states (confirmation, next steps)

---

## Project Scoping Checklist

Before moving to visual design, confirm:

- [ ] Problem statement defined (one sentence)
- [ ] Complexity assessed (high/medium/low)
- [ ] Stakeholder alignment confirmed (no major disagreements)
- [ ] Information architecture mapped (sitemap + key flows)
- [ ] Content inventory complete (copy deck provided)
- [ ] Success metrics defined (how do we measure success?)
- [ ] Timeline agreed (when is this needed?)
- [ ] Budget approved (can we afford this quality?)
- [ ] Brand direction identified (if new brand) or provided (if existing)
- [ ] Deliverables listed (what are you getting? Figma? Prototype? Webflow site?)

---

## When to Use References

Load these reference files when:

- **01-discovery-questionnaire.md** — Preparing for discovery call with client; writing detailed questionnaire
- **02-information-architecture.md** — Creating sitemaps and user flows for medium/high complexity projects
- **03-complexity-assessment.md** — Determining whether this project needs wireframes or can skip to design
- **04-competitive-analysis.md** — Auditing competitors; identifying positioning opportunities

---

## Common Discovery Mistakes

1. **Skipping the questions:** Jumping straight to design. Result: Complete rework when stakeholders disagree.
2. **Too much scope:** Trying to solve everything. Result: Project paralysis, feature creep.
3. **Unclear success metrics:** "Make it better" has no definition. Result: Infinite revisions.
4. **No stakeholder alignment:** Each person has different vision. Result: Design disapproval surprises.
5. **Insufficient user research:** Designing for yourself, not the user. Result: Low adoption/engagement.

---

## After Discovery: Next Steps

Once discovery is complete:

1. **If High/Medium Complexity:** Move to `figma-workflows` to set up your Figma file, then create wireframes
2. **If Low Complexity:** Move to `visual-foundations` to understand design rules, then `figma-workflows` to set up
3. **All paths:** Eventually hand off to `ui-components` and `web-layout` for detailed design

---

## Key Metrics from Discovery

**Timeline expectations:**
- Discovery call: 1 hour
- Research & competitive analysis: 2-4 hours
- Sitemap & flows: 2-3 hours
- Wireframes (if medium/high complexity): 4-8 hours

**Total discovery investment:** 9-16 hours before first visual design

**ROI:** Saves 20-40 hours on rework during design/development phases. Worth every minute.

---

## Cross-References

- **visual-foundations** — Design principles you'll apply once discovery is done
- **figma-workflows** — How to organize your design file for this project
- **ui-components** — Specific component patterns for your use case
- **web-layout** — Layout structures for web-based projects
