# Paid Ads Mastery Plugin - Routing & Operations

## Plugin Overview

This is a complete paid advertising knowledge engine for Meta and Google Ads, built from 616 expert-level training transcriptions across 6 comprehensive courses. It provides end-to-end guidance from account setup through advanced scaling, covering pixel/conversion infrastructure, creative research and development, strategic account architecture, ad production workflows, and campaign optimization methodologies.

---

## Skill Routing Logic

Route user requests to the appropriate skill based on workflow stage and question type:

### SETUP STAGE
**When user asks about:** Account setup, pixel/conversion infrastructure, feed management, tracking implementation

| User Intent | Skill | Notes |
|---|---|---|
| Google Ads account setup, Google Merchant Center, product feed creation, conversion tracking, Tag Manager | **setup-google-ads** | Start here for any Google Ads infrastructure |
| Meta Pixel setup, Conversions API, pixel training, account quality, value events | **setup-meta-pixel** | Start here for Meta/Facebook infrastructure |

### RESEARCH STAGE
**When user asks about:** Creative direction, audience insights, messaging strategy, creative frameworks

| User Intent | Skill | Notes |
|---|---|---|
| Creative research process, code banks, persona development, awareness level mapping, ICE scoring, creative briefs | **research-creative** | Always precedes creative development — captures the 4-step research methodology |

### STRATEGY STAGE
**When user asks about:** Campaign structure, bidding strategy, account architecture, scaling approaches

| User Intent | Skill | Notes |
|---|---|---|
| Meta/Facebook campaign structure, budget rules, CBO vs ABO, ASC, cost cap optimization, scaling logic, Simple/Crazy/MOB/Blender methods | **strategy-meta-ads** | Meta-specific strategic decisions |
| Google campaign structure, Shopping/Search/PMax/YouTube strategy, 30-30 rule, Quality Score optimization, GTC scaling | **strategy-google-ads** | Google-specific strategic decisions |

### CREATE STAGE
**When user asks about:** Ad production, copy writing, video scripts, asset creation

| User Intent | Skill | Notes |
|---|---|---|
| Meta ad hooks, video scripts, copy templates, UGC integration, VSL/mini-VSL workflows, iteration methods | **create-meta-ads-traditional** | Traditional creative production for Meta |
| AI-powered Meta creative: Midjourney prompts, Flux images, Arcads, ElevenLabs voiceovers, Kling videos, CapCut workflows | **create-meta-ads-ai** | AI tools and automation for Meta creative |
| Google product titles/descriptions, RSA copy optimization, YouTube scripts, PMax asset groups | **create-google-ads** | Google-specific ad production |

### OPTIMIZE STAGE
**When user asks about:** Campaign monitoring, testing, scaling decisions, performance diagnostics

| User Intent | Skill | Notes |
|---|---|---|
| Campaign monitoring, testing methodologies (A/B, holdout, sequential, ACOS, budget scaling, etc.), kill/scale decisions, performance benchmarks, diagnostics, retargeting, naming conventions | **optimize-campaigns** | Always revisit after launch or when troubleshooting |

---

## Command Routing

Commands provide interactive, structured workflows. Route based on user intent:

| Command | When to Use | Calls Which Skills |
|---|---|---|
| `/build-campaign` | User wants to design a campaign from scratch | strategy-meta-ads, strategy-google-ads, research-creative |
| `/audit-campaign` | User wants diagnostic analysis of existing campaign | optimize-campaigns |
| `/write-ad` | User wants to generate ad copy/creative | create-meta-ads-traditional, create-meta-ads-ai, create-google-ads |
| `/test-plan` | User wants to plan creative or strategy tests | optimize-campaigns, research-creative |
| `/scale-plan` | User wants a scaling roadmap | strategy-meta-ads, strategy-google-ads, optimize-campaigns |
| `/brief-media-buyer` | User wants an SOP for team execution | All relevant skills (builds comprehensive brief) |
| `/research-brief` | User wants a creative research framework | research-creative |

---

## Cross-Skill Workflow Chains

These skills frequently chain together in real workflows:

**Complete Campaign Launch Chain:**
1. research-creative (develop creative direction & code bank)
2. strategy-meta-ads OR strategy-google-ads (define account structure)
3. create-meta-ads-traditional/ai OR create-google-ads (produce assets)
4. optimize-campaigns (launch, monitor, test)

**Setup → Strategy Chain:**
1. setup-google-ads or setup-meta-pixel (establish infrastructure)
2. strategy-meta-ads or strategy-google-ads (configure account/campaigns)

**Creative Iteration Chain:**
1. optimize-campaigns (identify underperforming creative)
2. research-creative (analyze why & develop new direction)
3. create-meta-ads-traditional/ai or create-google-ads (produce new assets)
4. optimize-campaigns (test & measure)

**Scaling Chain:**
1. strategy-meta-ads or strategy-google-ads (review current structure)
2. optimize-campaigns (run scaling tests)
3. strategy-meta-ads or strategy-google-ads (adjust budget rules/structure)
4. optimize-campaigns (monitor scaled performance)

---

## Product Marketing Context

Before invoking any skill, check for `product-marketing-context.md` from the marketing-skills plugin (if available). If it exists, load it and reference:

- Brand voice & messaging guidelines
- Target audience definitions & segments
- Product/service positioning
- Value proposition & key differentiators
- Competitive landscape context
- Campaign goals & KPIs

This ensures all creative and strategic recommendations align with the user's brand identity and marketing objectives.

---

## Plugin Overlap & Priority

**This plugin FULLY REPLACES any paid ads functionality in other installed plugins**, specifically:
- `marketing-skills/paid-ads`
- `marketing-skills/ad-creative`

If those skills remain installed alongside paid-ads-mastery, **paid-ads-mastery takes priority**. Do not invoke the older skills; route all paid advertising requests to this plugin's 9 skills instead.

---

## Reference Files Pattern

Each skill may contain a `references/` subfolder with deep-dive content, templates, frameworks, and case studies. When a user needs tactical details beyond the SKILL.md summary:

1. Check if the skill's references/ folder exists
2. Load relevant reference files (e.g., `references/hooks.md`, `references/bidding-strategies.md`)
3. Use reference content to provide specific, actionable guidance
4. Cite the reference file in responses for traceability

Example: If user asks for "a list of proven Meta ad hooks," load `create-meta-ads-traditional/references/hooks.md`.

---

## Implementation Notes

- **Decision Tree First**: Use the routing tables above to determine which skill(s) to invoke.
- **Cross-Reference When Needed**: Acknowledge when multiple skills contribute (e.g., "This combines strategy and creative; let me pull from both").
- **Skill SKILL.md First, Then References**: Always start with the skill's SKILL.md for high-level guidance, then deep-dive into references/ for specifics.
- **User Stage Awareness**: Ask clarifying questions if unclear (e.g., "Are you setting up a new campaign or optimizing an existing one?").
- **Tool Availability**: Some skills may recommend external tools (Midjourney, ElevenLabs, etc.). Guide users on setup but don't simulate tool outputs.
