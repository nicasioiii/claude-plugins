# Design Mastery Plugin: Routing & Operations

**Plugin:** design-mastery
**Version:** 1.0.0
**Last Updated:** March 12, 2026

---

## PLUGIN OVERVIEW

Design Mastery is a comprehensive design knowledge system covering the complete visual design lifecycle:

- **Visual design fundamentals** (typography, color, spacing, layout, hierarchy)
- **UI component patterns** (buttons, cards, forms, navigation, modals)
- **Web & responsive design** (layouts, sections, mobile strategy)
- **SaaS & dashboard design** (app interfaces, data visualization)
- **Design systems & Figma workflows** (file organization, components, tokens)
- **Design critique & improvement** (systematic review, common mistakes)
- **Animation & interactions** (micro-interactions, scroll animations, timing)
- **Implementation platforms** (Webflow, Shopify)
- **Logo design & branding** (logo process, brand systems, visual identity)

The plugin contains **11 interconnected skills** organized by **workflow stage** (discovery → design → implementation), enabling users to start anywhere in their process and find the right guidance.

---

## THE 11 SKILLS

| Skill | When Users Need It | Primary Output |
|-------|-------------------|-----------------|
| **discovery-direction** | Starting a new project, understanding client needs, scoping | Discovery framework, questionnaire, complexity assessment |
| **visual-foundations** | Learning design rules, fixing visual issues, understanding hierarchy | Typography/color/spacing reference, design principles |
| **figma-workflows** | Setting up design files, creating design systems, team organization | File structure, component setup, design tokens |
| **ui-components** | Designing buttons, cards, forms, navigation, modals | Component patterns, state variations, sizing guidelines |
| **web-layout** | Structuring websites, responsive design, homepage design | Layout patterns, responsive breakpoints, section spacing |
| **dashboard-systems** | Designing SaaS interfaces, data visualization, app dashboards | Dashboard structure, navigation patterns, data display |
| **web-design-audit** | Reviewing designs, identifying issues, systematic critique | Critique checklist, specific fixes, before/after examples |
| **animation-interactions** | Adding animations, designing micro-interactions, scroll effects | Animation patterns, timing, implementation approach |
| **webflow-implementation** | Building in Webflow, responsive patterns, client handoff | Layout techniques, animations, CMS setup |
| **shopify-design** | Designing Shopify stores, customizing themes, Liquid templating | Store structure, product display, theme customization |
| **logo-branding** | Logo design, brand identity systems, style guides | Logo process framework, brand system templates |

---

## SKILL ROUTING LOGIC

### How to Route User Intent to Skills

**IF user asks about...**

| User Intent | → Skill | TRIGGER CONDITIONS |
|-------------|--------|-------------------|
| New project, client discovery, understanding needs | **discovery-direction** | Keywords: "start project," "client brief," "understand needs," "scope," "project plan," "discovery" |
| Design fundamentals, typography, color, spacing rules | **visual-foundations** | Keywords: "why doesn't this look good," "design rules," "hierarchy," "typography," "color," "spacing," "layout basics" |
| Figma setup, file organization, design systems, components | **figma-workflows** | Keywords: "Figma," "design system," "components," "organize," "file structure," "design tokens," "variants" |
| Button, card, form, navigation, modal design patterns | **ui-components** | Keywords: "button," "card," "form," "navigation," "modal," "component," "pattern," specific component type |
| Website structure, homepage, sections, responsive design | **web-layout** | Keywords: "website," "homepage," "layout," "section," "responsive," "mobile," "desktop," "hero," "footer," "web design" |
| SaaS dashboard, app interface, data tables, metrics | **dashboard-systems** | Keywords: "dashboard," "SaaS," "app," "data," "metrics," "table," "analytics," "admin panel," "application interface" |
| Design review, critique, improving existing design, mistakes | **web-design-audit** | Keywords: "review," "critique," "audit," "what's wrong," "improve," "feedback," "mistakes," "check," "feedback" |
| Animation, micro-interactions, scroll animations, motion | **animation-interactions** | Keywords: "animation," "animate," "interaction," "scroll," "motion," "hover," "loading," "transitions," "easing" |
| Building in Webflow, Webflow techniques, Webflow interaction | **webflow-implementation** | Keywords: "Webflow," "build," "layout," "flexbox," "grid," "responsive," "CMS," "interaction in Webflow" |
| Shopify store design, theme customization, product pages | **shopify-design** | Keywords: "Shopify," "e-commerce," "store," "product page," "theme," "Liquid," "shop design" |
| Logo design, branding, brand identity, style guide | **logo-branding** | Keywords: "logo," "brand," "identity," "branding," "style guide," "brand system," "logo design," "visual identity" |

---

## AMBIGUOUS REQUEST DECISION TREE

When a user request could match multiple skills, use this decision tree:

```
USER ASKS: "How do I design [X]?"

├─ Is it a specific UI component (button, card, form)?
│  └─ YES → ui-components
│  └─ NO → continue
│
├─ Is it a full layout/page structure?
│  ├─ Website? → web-layout
│  ├─ App/Dashboard? → dashboard-systems
│  └─ NO → continue
│
├─ Is it about motion/animation?
│  └─ YES → animation-interactions (or pair with web-layout/ui-components)
│
├─ Is it about critique/improvement?
│  └─ YES → web-design-audit (then recommend specific skill to fix)
│
├─ Is it about organization/setup?
│  ├─ Figma? → figma-workflows
│  ├─ Project? → discovery-direction
│  └─ NO → continue
│
├─ Is it about implementation/building?
│  ├─ Webflow? → webflow-implementation
│  ├─ Shopify? → shopify-design
│  └─ NO → continue
│
├─ Is it about logo/branding?
│  └─ YES → logo-branding
│
└─ Is user confused about fundamentals?
   └─ YES → visual-foundations (with referral to other skills)
```

---

## EXECUTION PRIORITY ORDER

When multiple skills could apply, execute them in this order (workflow sequence):

1. **discovery-direction** — Understand the project first
2. **visual-foundations** — Establish design rules & principles
3. **figma-workflows** — Set up the design workspace
4. **ui-components** — Design reusable pieces
5. **web-layout** OR **dashboard-systems** — Assemble into full layout
6. **animation-interactions** — Enhance with motion (optional)
7. **web-design-audit** — Review and improve
8. **webflow-implementation** OR **shopify-design** — Build & deploy
9. **logo-branding** — Parallel track for brand identity

**Example workflow:**
- User: "Help me design a website"
- Response path: discovery-direction (understand goals) → visual-foundations (establish style) → figma-workflows (organize file) → web-layout (design structure) → ui-components (design pieces) → webflow-implementation (build)

---

## CROSS-SKILL REFERENCES & TRIGGER CONDITIONS

### discovery-direction → visual-foundations
**Trigger:** "Now that we've scoped the project, let's define the visual style"
**Connection:** Scoping reveals design constraints → visual-foundations applies them

### visual-foundations → figma-workflows
**Trigger:** "Now let's set up a Figma file to apply these visual rules"
**Connection:** Visual principles need organization → figma-workflows structures the workspace

### figma-workflows → ui-components
**Trigger:** "Now we'll create reusable components based on these visual rules"
**Connection:** Design system foundation → component library implementation

### ui-components → web-layout
**Trigger:** "Now we'll assemble components into a full page layout"
**Connection:** Components are building blocks → layouts assemble them

### web-layout → dashboard-systems (if applicable)
**Trigger:** "If this is a SaaS/app project, let's design the dashboard structure"
**Connection:** Layout principles apply to dashboards; specific patterns for data-heavy UIs

### web-layout → animation-interactions
**Trigger:** "Now we'll enhance the design with scroll and hover animations"
**Connection:** Base layout is set → animations add polish

### animation-interactions → webflow-implementation
**Trigger:** "Let's implement these animations in Webflow"
**Connection:** Animation design → animation code

### web-layout → web-design-audit
**Trigger:** "Before we build, let's audit the design for quality"
**Connection:** Design ready for review → systematic critique

### web-design-audit → [any skill for fixes]
**Trigger:** "To fix this typography issue, let's reference visual-foundations"
**Connection:** Audit identifies problem → specific skill provides solution

### webflow-implementation → shopify-design (for e-commerce)
**Trigger:** "If this is an e-commerce site, use Shopify-specific patterns"
**Connection:** Implementation platform choice determines specific techniques

### logo-branding (parallel track)
**Trigger:** "Before designing the website, let's create the brand identity"
**Connection:** Brand identity → brand application in web design

---

## SCOPE BOUNDARIES

### IN SCOPE (What Design Mastery Covers)

✅ Visual design fundamentals (typography, color, spacing, layout, hierarchy)
✅ UI component design patterns (buttons, cards, forms, navigation, modals)
✅ Web layout and responsive design
✅ SaaS dashboard and app interface design
✅ Design systems in Figma
✅ Animation and micro-interactions
✅ Design critique and systematic improvement
✅ Logo design and brand identity systems
✅ Implementation in Webflow and Shopify

### OUT OF SCOPE (What Design Mastery Does NOT Cover)

❌ **Copywriting & CRO** (Handled by `cro-copywriting-mastery` plugin)
   - Headline writing, persuasive messaging, call-to-action copy optimization, conversion psychology
   - ✓ IN: Microcopy in forms, error messages, button labels from design perspective

❌ **SEO & Content Strategy** (Handled by `seo-mastery` plugin)
   - Keyword research, metadata, content hierarchy for SEO, link strategy
   - ✓ IN: Information architecture for UX (not SEO)

❌ **Paid Advertising** (Handled by other plugins)
   - Ad design, banner specs, ad copy
   - ✓ IN: Design principles that apply universally

❌ **Email Design** (Not yet covered)
   - Email template design, email-specific patterns
   - ✓ IN: Web layout principles that may apply

❌ **Advanced Video/3D** (Minimal coverage)
   - 3D rendering, After Effects compositing, video production
   - ✓ IN: Basic animation timing in web and Webflow

❌ **Accessibility (WCAG Compliance)** (Minimal coverage)
   - Full WCAG testing, accessibility audit, ARIA implementation
   - ✓ IN: Basic contrast standards, form labeling, color-alone information warnings

---

## PRODUCT MARKETING CONTEXT CHECK

**Location:** `.claude/product-marketing-context.md`

Before responding to ambiguous requests, check if additional context is available:

- **If file exists:** Use it to understand product positioning, target audience, brand voice
- **If not found:** Proceed with generic design guidance
- **When to reference:** Ambiguous requests about "brand identity," "messaging," "positioning," "audience"

**Example:** User asks "What should our homepage say?" → Check context.md for brand positioning → Align design with positioning (but refer copywriting to CRO plugin)

---

## QUICK REFERENCE: USER TYPES & BEST SKILL PATHS

### "I'm learning to design"
→ Start: **visual-foundations** → **ui-components** → **web-layout**

### "I'm starting a client project"
→ Start: **discovery-direction** → **visual-foundations** → **figma-workflows** → **ui-components** → **web-layout** → **webflow-implementation**

### "I need to design a SaaS dashboard"
→ Start: **dashboard-systems** → reference **ui-components** → **animation-interactions** → **webflow-implementation**

### "I need to review a design"
→ Start: **web-design-audit** → Jump to specific skill for fixes

### "I need to design a logo"
→ Start: **logo-branding** → (optional) **visual-foundations** for color/typography

### "I need to design a Shopify store"
→ Start: **shopify-design** → reference **web-layout** → reference **ui-components**

### "I want to improve my Figma workflow"
→ Start: **figma-workflows** → reference **visual-foundations** for token setup

---

## PLUGIN OPERATIONS

### Standard Response Pattern

When a user invokes a slash command or mentions a design task:

1. **Clarify ambiguity** (if needed)
2. **Reference relevant skill(s)**
3. **Ask scoping questions** (via AskUserQuestion)
4. **Provide structured output** (e.g., checklist, pattern library, step-by-step guide)
5. **Suggest next step** (which skill/command comes next)
6. **Link to deeper references** (if user wants to dive deeper)

### When to Use Each Command

| User Says | Use Command | Why |
|-----------|------------|-----|
| "I have a new project" | `/start-project` | Launches discovery workflow |
| "Review my design" | `/design-audit` | Systematic critique |
| "Show me button patterns" | `/component-pattern` | Quick component reference |
| "Design a responsive homepage" | `/responsive-layout` | Full layout workflow |
| "Help me design a logo" | `/create-logo` | Logo process guide |
| "Design a dashboard for our SaaS" | `/dashboard-design` | SaaS-specific patterns |
| "How do I animate this?" | `/animation-help` | Animation guidance |
| "Set up our design system" | `/design-system` | Figma system setup |

---

## ERROR HANDLING & EDGE CASES

### If user request doesn't fit any skill
→ Route to **visual-foundations** (most universal) and ask clarifying questions

### If request spans multiple skills with conflicting info
→ Flag the conflict, explain why different skills recommend different approaches, provide decision matrix

### If user asks about out-of-scope content (copywriting, SEO)
→ Acknowledge request, explain it's handled by other plugin, offer to help with design aspects

### If user shows design without context
→ Suggest **web-design-audit** skill (systematic review possible without context)
→ Or ask for context to route to specific skill

---

## METRICS & TESTING

### Coverage Verification

Each skill has been tested against its primary trigger questions:

✅ discovery-direction — "Where do I start a project?"
✅ visual-foundations — "What are the design rules?"
✅ figma-workflows — "How do I organize Figma?"
✅ ui-components — "Show me component patterns"
✅ web-layout — "How do I structure a webpage?"
✅ dashboard-systems — "How do I design a SaaS dashboard?"
✅ web-design-audit — "What's wrong with this design?"
✅ animation-interactions — "How do I add animations?"
✅ webflow-implementation — "How do I build this in Webflow?"
✅ shopify-design — "How do I design a Shopify store?"
✅ logo-branding — "Help me design a logo"

### Success Metrics

- User finds right skill within 2-3 turns
- Response includes actionable next steps
- Cross-references feel natural (not forced)
- No content overlap between skills

---

## VERSION HISTORY

- **1.0.0** (March 12, 2026) — Initial release with 11 skills, 8 slash commands, full routing logic

---

**Generated by:** Claude Code (Agent)
**Next Review:** When new skills are added or user feedback suggests routing changes
