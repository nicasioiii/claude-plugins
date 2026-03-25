# Design Mastery Plugin: Routing & Operations

**Plugin:** design-mastery
**Version:** 2.0.0
**Last Updated:** March 24, 2026

---

## PLUGIN OVERVIEW

Design Mastery is a comprehensive design knowledge system covering the complete visual design lifecycle. Built from 10+ expert courses (Shift Nudge, Webflow Masterclass, Figma UI Design, LogoCore, Shopify Ecommerce, Typography & Layout, Mood Board Method, Design Career Kickstarter, and more).

The plugin contains **14 interconnected skills** organized across **7 workflow layers**, enabling users to start anywhere in their process and find the right guidance.

---

## THE 14 SKILLS

### Layer 1: Discovery & Direction
| Skill | When Users Need It | Primary Output |
|-------|-------------------|-----------------|
| **discovery-direction** | Starting a project, scoping work, running discovery calls, writing proposals, pricing, client acquisition | Discovery framework, complexity assessment, proposal structure, pricing guide |
| **mood-board-brand-vibe** | Creating mood boards, establishing brand direction, AI brand imagery, finding inspiration, visual direction | Brand Vibe Report, mood board, visual guidelines, inspiration workflow |

### Layer 2: Visual Foundations
| Skill | When Users Need It | Primary Output |
|-------|-------------------|-----------------|
| **typography-systems** | Font selection, sizing, pairing, hierarchy, line-height, weight, tracking, callouts, truncation | Type scale, font pairings, hierarchy checklist, text style system |
| **color-systems** | Color palette, HSB method, WCAG contrast, dark UI, gradients, 60-30-10, grays, color psychology | Color system document, contrast-checked palette, gray tinting |
| **layout-spacing** | Grid setup, spacing tokens, alignment, density, breakpoints, negative space, composition | Grid specification, spacing scale, breakpoint rules |

### Layer 3: Components & Systems
| Skill | When Users Need It | Primary Output |
|-------|-------------------|-----------------|
| **ui-components** | Buttons, cards, forms, navigation, modals, tables, tabs, inputs | Component patterns, state variations, sizing guidelines |
| **design-systems** | Figma components, variants, variables, tokens, atomic design, style guides | Design system setup, component library, token definitions |

### Layer 4: Page-Level Design
| Skill | When Users Need It | Primary Output |
|-------|-------------------|-----------------|
| **web-layout** | Homepage structure, section anatomy, hero design, responsive web, footer, navigation | Page structure, section patterns, responsive strategy |
| **dashboard-app-design** | SaaS dashboards, data tables, metrics, app navigation, UX laws | Dashboard structure, data display patterns, UX law application |

### Layer 5: Implementation
| Skill | When Users Need It | Primary Output |
|-------|-------------------|-----------------|
| **webflow-build** | Webflow HTML/CSS, flexbox, CMS, responsive build, QA, starter projects | Build order, layout techniques, CMS setup, QA checklist |
| **webflow-animations** | Scroll animations, Lottie, Spline, GSAP, hover states, preloaders | Animation patterns, tool selection, implementation approach |
| **shopify-ecommerce** | Shopify themes, Liquid, sections, metafields, PDP, conversion, launch | Theme architecture, section schemas, launch checklist |

### Layer 6: Brand & Identity
| Skill | When Users Need It | Primary Output |
|-------|-------------------|-----------------|
| **logo-brand-identity** | Logo process, sketching, vectorization, logo typography, grids, style guides | Logo workflow, sketch-to-vector, brand style guide |

### Layer 7: Review & Iterate
| Skill | When Users Need It | Primary Output |
|-------|-------------------|-----------------|
| **design-critique** | Design audit, common mistakes, typography/color/layout critique, iteration, taste development | Audit checklist, mistake patterns, improvement recommendations |

---

## SKILL ROUTING LOGIC

### Primary Routing Table

| User Intent | Route To | Trigger Keywords |
|-------------|---------|-----------------|
| New project, client needs, scoping, proposals, pricing | **discovery-direction** | "start project," "client brief," "scope," "proposal," "discovery call," "pricing," "freelance" |
| Mood board, brand direction, visual inspiration, brand vibe | **mood-board-brand-vibe** | "mood board," "brand vibe," "visual direction," "inspiration," "brand guidelines," "AI branding" |
| Font selection, type hierarchy, sizing, pairing, tracking | **typography-systems** | "font," "typeface," "type scale," "hierarchy," "pairing," "line height," "letter spacing," "heading size" |
| Color palette, contrast, accessibility, dark mode, grays | **color-systems** | "color," "palette," "contrast," "WCAG," "dark mode," "gradient," "60-30-10," "accessibility," "HSB" |
| Grid, spacing, alignment, density, breakpoints, negative space | **layout-spacing** | "grid," "spacing," "8px," "4pt," "alignment," "density," "breakpoint," "negative space," "white space" |
| Button, card, form, navigation, modal, table patterns | **ui-components** | "button," "card," "form," "input," "navigation," "modal," "dialog," "table," "component" |
| Figma components, design tokens, variants, variables, atomic design | **design-systems** | "Figma," "design system," "component," "variant," "variable," "token," "atomic," "style guide" |
| Website structure, homepage, sections, responsive, hero, footer | **web-layout** | "website," "homepage," "hero," "footer," "section," "responsive," "page layout," "web design" |
| Dashboard, SaaS interface, data tables, app navigation, UX laws | **dashboard-app-design** | "dashboard," "SaaS," "app," "data table," "metrics," "analytics," "admin," "UX law" |
| Webflow building, HTML/CSS, flexbox, CMS, responsive build | **webflow-build** | "Webflow," "build," "flexbox," "CMS," "responsive," "HTML," "CSS," "starter project" |
| Scroll animations, Lottie, Spline, GSAP, hover, motion | **webflow-animations** | "animation," "scroll," "Lottie," "Spline," "GSAP," "hover," "motion," "preloader" |
| Shopify store, theme, Liquid, product page, e-commerce | **shopify-ecommerce** | "Shopify," "e-commerce," "store," "product page," "theme," "Liquid," "metafield" |
| Logo design, brand identity, vectorization, style guide | **logo-brand-identity** | "logo," "brand identity," "branding," "style guide," "vectorize," "logotype," "brand mark" |
| Design review, critique, mistakes, improvement, taste, portfolio | **design-critique** | "review," "critique," "audit," "mistakes," "improve," "feedback," "taste," "portfolio" |

---

## AMBIGUOUS REQUEST DECISION TREE

```
USER ASKS: "How do I design [X]?"

├─ Is it about STARTING a new project or client work?
│  └─ YES → discovery-direction
│
├─ Is it about ESTABLISHING visual direction or mood?
│  └─ YES → mood-board-brand-vibe
│
├─ Is it about a SPECIFIC visual property?
│  ├─ Typography/fonts? → typography-systems
│  ├─ Colors/palette? → color-systems
│  ├─ Grids/spacing? → layout-spacing
│  └─ NO → continue
│
├─ Is it a specific UI component (button, card, form)?
│  └─ YES → ui-components
│
├─ Is it about Figma organization or design system setup?
│  └─ YES → design-systems
│
├─ Is it a full layout/page structure?
│  ├─ Website? → web-layout
│  ├─ App/Dashboard? → dashboard-app-design
│  └─ NO → continue
│
├─ Is it about implementation/building?
│  ├─ Webflow layout/CMS? → webflow-build
│  ├─ Webflow animations? → webflow-animations
│  ├─ Shopify? → shopify-ecommerce
│  └─ NO → continue
│
├─ Is it about logo/branding?
│  └─ YES → logo-brand-identity
│
├─ Is it about critique/improvement?
│  └─ YES → design-critique
│
└─ Unclear?
   └─ Ask clarifying question, or route to typography-systems (most universal)
```

---

## EXECUTION PRIORITY ORDER

When multiple skills apply, execute in workflow order:

1. **discovery-direction** — understand the project first
2. **mood-board-brand-vibe** — establish visual direction
3. **typography-systems** / **color-systems** / **layout-spacing** — establish visual foundations
4. **design-systems** — codify foundations into reusable system
5. **ui-components** — design building blocks
6. **web-layout** / **dashboard-app-design** — assemble pages
7. **webflow-animations** — enhance with motion
8. **webflow-build** / **shopify-ecommerce** — implement
9. **design-critique** — review and iterate
10. **logo-brand-identity** — parallel track, any time

---

## CROSS-SKILL REFERENCES & TRIGGER CONDITIONS

| From Skill | To Skill | Trigger |
|------------|----------|---------|
| discovery-direction | mood-board-brand-vibe | "Project scoped; let's establish visual direction" |
| discovery-direction | typography-systems | "Project scoped; let's define the type system" |
| mood-board-brand-vibe | color-systems | "Mood board set; let's formalize the palette" |
| mood-board-brand-vibe | typography-systems | "Direction established; let's select typefaces" |
| typography-systems | design-systems | "Type scale defined; let's create Figma text styles" |
| color-systems | design-systems | "Palette defined; let's create color variables" |
| layout-spacing | design-systems | "Spacing scale set; let's create spacing tokens" |
| design-systems | ui-components | "System ready; let's build component library" |
| ui-components | web-layout | "Components ready; let's assemble the page" |
| ui-components | dashboard-app-design | "Components ready; let's design the app" |
| web-layout | webflow-build | "Design approved; let's build in Webflow" |
| web-layout | shopify-ecommerce | "Design approved; let's build in Shopify" |
| web-layout | webflow-animations | "Layout done; let's add animations" |
| web-layout | design-critique | "Design ready for review before build" |
| design-critique | [any skill] | "Audit found issue X; fix with Y skill" |
| logo-brand-identity | mood-board-brand-vibe | "Logo needs brand direction first" |
| logo-brand-identity | color-systems | "Logo colors feed into brand palette" |

---

## 15 COMMANDS

| Command | Skill(s) | Purpose |
|---------|----------|---------|
| `/start-project` | discovery-direction | Launch project scoping workflow |
| `/mood-board` | mood-board-brand-vibe | Create brand vibe report and mood board |
| `/type-system` | typography-systems | Design typographic scale and hierarchy |
| `/color-palette` | color-systems | Build accessible color system |
| `/layout-grid` | layout-spacing | Set up grid system and spacing tokens |
| `/component-pattern` | ui-components | Quick-reference component patterns |
| `/design-system` | design-systems | Set up Figma design system with tokens |
| `/homepage-structure` | web-layout | Design conversion-optimized homepage |
| `/dashboard-design` | dashboard-app-design | Design SaaS/app dashboard |
| `/webflow-build` | webflow-build | Webflow build order and techniques |
| `/animate` | webflow-animations | Animation patterns and implementation |
| `/shopify-store` | shopify-ecommerce | Shopify store design and theme work |
| `/logo-process` | logo-brand-identity | End-to-end logo design workflow |
| `/design-audit` | design-critique | Systematic design review checklist |
| `/responsive-check` | web-layout + webflow-build | Cross-skill responsive design audit |

---

## SCOPE BOUNDARIES

### IN SCOPE
- Visual design fundamentals (typography, color, spacing, layout, hierarchy)
- UI component design patterns
- Web layout and responsive design
- SaaS dashboard and app interface design
- Design systems in Figma
- Mood boards and brand direction (manual + AI-powered)
- Animation and micro-interactions
- Design critique and systematic improvement
- Logo design and brand identity systems
- Implementation in Webflow and Shopify
- Client discovery, proposals, pricing, acquisition

### OUT OF SCOPE
- **Copywriting & CRO** — handled by cro-copywriting-mastery plugin
- **SEO & Content Strategy** — handled by seo-mastery plugin
- **Paid Advertising** — handled by other plugins
- **Email Template Design** — not covered in source material
- **Native App Development** — implementation out of scope
- **Advanced 3D Rendering** — code-level Three.js out of scope
- **Full WCAG Compliance** — basic contrast included only
- **After Effects Animation** — out of scope (video editing)

---

## QUICK REFERENCE: USER TYPE PATHS

### "I'm learning to design"
Start: **typography-systems** > **color-systems** > **layout-spacing** > **ui-components** > **web-layout**

### "I'm starting a client project"
Start: **discovery-direction** > **mood-board-brand-vibe** > **typography-systems** > **color-systems** > **layout-spacing** > **design-systems** > **web-layout** > **webflow-build**

### "I need to design a SaaS dashboard"
Start: **dashboard-app-design** > reference **ui-components** > **design-systems**

### "I need to review a design"
Start: **design-critique** > jump to specific skill for fixes

### "I need to design a logo"
Start: **logo-brand-identity** > (optional) **mood-board-brand-vibe** for brand direction

### "I need to design a Shopify store"
Start: **shopify-ecommerce** > reference **web-layout** > reference **ui-components**

### "I want to set up a design system"
Start: **design-systems** > reference **typography-systems** + **color-systems** + **layout-spacing** for tokens

---

## PRODUCT MARKETING CONTEXT CHECK

**Location:** `.claude/product-marketing-context.md`

Before responding to ambiguous requests, check if additional context is available:
- **If file exists:** Use to understand product positioning, target audience, brand voice
- **If not found:** Proceed with generic design guidance

---

## ERROR HANDLING

### If request does not fit any skill
Route to **typography-systems** (most universal) and ask clarifying questions.

### If request spans multiple skills
Identify primary skill, load it first, cross-reference secondary skills as needed.

### If user asks about out-of-scope content
Acknowledge request, explain it is handled by other plugin, offer design aspects.

### If user shows design without context
Suggest **design-critique** (systematic review possible without context).

---

## VERSION HISTORY

- **2.0.0** (March 24, 2026) — Major rebuild: 14 skills (up from 11), 15 commands, split visual-foundations into 3 dedicated skills, added mood-board-brand-vibe, rebuilt from 7 new extractions
- **1.0.0** (March 12, 2026) — Initial release with 11 skills, 8 slash commands
