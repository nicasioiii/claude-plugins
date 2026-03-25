# Design Mastery Plugin

**Version:** 2.0.0
**Skills:** 14
**Commands:** 15
**Reference Files:** 42
**Total Lines:** ~12,400

Complete design knowledge engine covering the full visual design lifecycle from project discovery through implementation and review.

## Source Material

Built from 10+ expert courses across 600+ transcriptions:
- Shift Nudge (MDS) -- Interface design foundations
- Webflow Masterclass (Ran Segall) -- Web design and Webflow build
- Web Design Masterclass (Matt Jumper / Flux) -- Web design process
- Figma UI Design (Arash) -- UI design and Figma mastery
- UX-UI Designership -- UX workflows and laws
- LogoCore (Kirill) -- Logo design process
- Logo Launch (Will Patterson) -- Logo production
- Typography & Layout (Oliver Gareis) -- Typography and grid systems
- Mood Board Method (Andrew Lane) -- AI-powered brand direction
- Design Career Kickstarter (Flux / Ran Segall / Gigi) -- Freelancing and career

## Skills (14)

### Layer 1: Discovery & Direction
| Skill | Files | Description |
|-------|-------|-------------|
| `discovery-direction` | SKILL + 3 refs | Project scoping, discovery calls, proposals, pricing, client acquisition, niche definition |
| `mood-board-brand-vibe` | SKILL + 2 refs | AI-powered Brand Vibe Reports, mood board creation, inspiration workflow, visual direction |

### Layer 2: Visual Foundations
| Skill | Files | Description |
|-------|-------|-------------|
| `typography-systems` | SKILL + 3 refs | Rule of Four, font selection/pairing, type scale, hierarchy, tracking, callouts, truncation |
| `color-systems` | SKILL + 3 refs | HSB method, palette construction, WCAG contrast, structural-interactive spectrum, dark UI, grays |
| `layout-spacing` | SKILL + 3 refs | Column/baseline/modular/hierarchical grids, 8px/4pt systems, density, pacing, breakpoints |

### Layer 3: Components & Systems
| Skill | Files | Description |
|-------|-------|-------------|
| `ui-components` | SKILL + 3 refs | Buttons, cards, forms, inputs, navigation, dialogs, tables, tabs |
| `design-systems` | SKILL + 3 refs | Figma auto layout, components/variants, variables/tokens, atomic design |

### Layer 4: Page-Level Design
| Skill | Files | Description |
|-------|-------|-------------|
| `web-layout` | SKILL + 3 refs | Homepage sections, hero design, responsive patterns, navigation, mega menus |
| `dashboard-app-design` | SKILL + 2 refs | SaaS dashboards, UX laws, data tables, metrics, app navigation |

### Layer 5: Implementation
| Skill | Files | Description |
|-------|-------|-------------|
| `webflow-build` | SKILL + 4 refs | HTML/CSS in Webflow, flexbox, CMS, responsive build, QA, starter projects |
| `webflow-animations` | SKILL + 2 refs | 4 scroll techniques, Lottie, Spline, GSAP, hover states, preloaders |
| `shopify-ecommerce` | SKILL + 4 refs | Theme architecture, Liquid patterns, section schemas, conversion UX, launch |

### Layer 6: Brand & Identity
| Skill | Files | Description |
|-------|-------|-------------|
| `logo-brand-identity` | SKILL + 4 refs | Logo process, sketching, vectorization, typography for logos, style guides |

### Layer 7: Review & Iterate
| Skill | Files | Description |
|-------|-------|-------------|
| `design-critique` | SKILL + 3 refs | Systematic audit, common mistakes vault, taste development, portfolio |

## Commands (15)

| Command | Skill | Purpose |
|---------|-------|---------|
| `/start-project` | discovery-direction | Launch project scoping workflow |
| `/mood-board` | mood-board-brand-vibe | Create brand vibe report and mood board |
| `/type-system` | typography-systems | Design typographic scale and hierarchy |
| `/color-palette` | color-systems | Build accessible color system |
| `/layout-grid` | layout-spacing | Set up grid and spacing tokens |
| `/component-pattern` | ui-components | Quick-reference component patterns |
| `/design-system` | design-systems | Set up Figma design system |
| `/homepage-structure` | web-layout | Design homepage |
| `/dashboard-design` | dashboard-app-design | Design SaaS dashboard |
| `/webflow-build` | webflow-build | Webflow build techniques |
| `/animate` | webflow-animations | Animation patterns |
| `/shopify-store` | shopify-ecommerce | Shopify store design |
| `/logo-process` | logo-brand-identity | Logo design workflow |
| `/design-audit` | design-critique | Systematic design review |
| `/responsive-check` | web-layout + webflow-build | Responsive design audit |

## Infrastructure

| File | Purpose |
|------|---------|
| `CLAUDE.md` | Full routing for 14 skills, decision tree, cross-references, 15 commands |
| `agents/design-mastery-advisor.md` | Agent persona with routing rules and response style |
| `settings.json` | Agent configuration |
| `.claude-plugin/plugin.json` | Plugin metadata (v2.0.0) |

## v2.0.0 Changes from v1.0.0

- **14 skills** (up from 11) -- 3 net new skills
- **Split `visual-foundations`** into 3 focused skills: `typography-systems`, `color-systems`, `layout-spacing`
- **New `mood-board-brand-vibe`** skill from Mood Board Method extraction (AI-powered branding)
- **Renamed** `figma-workflows` to `design-systems` (broader scope)
- **Renamed** `dashboard-systems` to `dashboard-app-design` (includes app interfaces)
- **Renamed** `web-design-audit` to `design-critique` (broader: taste, portfolio, iteration)
- **Split** `animation-interactions` + `webflow-implementation` into `webflow-build` + `webflow-animations`
- **Renamed** `shopify-design` to `shopify-ecommerce`
- **Renamed** `logo-branding` to `logo-brand-identity`
- **15 commands** (up from 8)
- **42 reference files** with cross-references and "When to Read" headers
- **Multi-instructor synthesis** with documented disagreements marked [CONTRARIAN]
- **7 extraction files** as source material (up from partial coverage)
