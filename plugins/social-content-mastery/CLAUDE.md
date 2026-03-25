# Social Content Mastery v1.0.0 -- Routing & Operations

## Plugin Overview

Complete social content creation knowledge engine for personal brands and creators. Built from 5 extraction files covering 9 courses across ~75 hours of instruction from Mino Lee, Dickie Bush & Nicholas Cole, Gusten Sun, Colin & Samir, Sky Stack, Anton Mehto, Parker Walbeck, Justas/Instapreneur, Marketing Harry/Frabrand, Kallaway, Nicklas Christl, Bob Krist, and Creators Club. Provides end-to-end guidance from brand foundation through content strategy, hook writing, scripting, filming, editing, visual production, platform strategy, growth, monetization, brand partnerships, community building, and AI-assisted workflows.

---

## Ambiguous Request Decision Tree

When a user's request could match multiple skills, use this decision tree:

```
IF request mentions specific platform ("LinkedIn", "Instagram", "TikTok", "YouTube")
  AND request is about platform mechanics/algorithm/profile -> platform-strategy
  AND request is about content for that platform -> route by content type below

IF request mentions "hook" or "opening" or "first line" or "scroll stop" -> write-hooks
IF request mentions "script" or "structure" or "write a post" or "outline" -> write-scripts
IF request mentions "film" or "camera" or "lighting" or "equipment" -> film-video
IF request mentions "edit" or "editing" or "pacing" or "B-roll" or "music" -> edit-video
IF request mentions "carousel" or "infographic" or "thumbnail" or "visual" -> produce-visual-content
IF request mentions "grow" or "followers" or "views" or "engagement" or "algorithm" -> publish-grow
IF request mentions "money" or "monetize" or "sell" or "coaching" or "product" or "offer" -> monetize-content
IF request mentions "brand deal" or "sponsorship" or "pitch deck" or "partnership" -> brand-partnerships
IF request mentions "community" or "group" or "membership" -> community-building
IF request mentions "AI" or "ChatGPT" or "Claude" or "prompt" -> ai-content-workflow
IF request mentions "brand" or "niche" or "positioning" or "who am I" -> brand-foundation
IF request mentions "plan" or "calendar" or "ideas" or "what to post" -> content-strategy
IF request is broad ("help me with social media" / "I want to be a creator") ->
  Ask: "Are you looking to: (A) define your brand and strategy, (B) create content (write/film/edit), (C) grow your audience, or (D) monetize your following?"
ELSE -> route to brand-foundation (earliest workflow stage)
```

---

## Skill Routing Table (All 13 Skills)

### Stage 1: BRAND FOUNDATION
| Skill | Display Name | Use When |
|---|---|---|
| `brand-foundation` | Brand Foundation | Niche selection, content pillars, ideal viewer avatar, brand DNA, visual identity, positioning, mission statement, congruency framework |

### Stage 2: CONTENT STRATEGY
| Skill | Display Name | Use When |
|---|---|---|
| `content-strategy` | Content Strategy | Idea generation, content multiplication, calendars, format selection, publishing cadence, repurposing, batch creation |

### Stage 3: CREATE -- WRITING
| Skill | Display Name | Use When |
|---|---|---|
| `write-hooks` | Write Hooks | Hook psychology, 4-component system, 7 spoken archetypes, hook revision (CGOVE), hook failure diagnosis, A/B testing |
| `write-scripts` | Write Scripts | Script structure, storytelling, LinkedIn writing, video scripts, caption writing, CTA writing |

### Stage 4: CREATE -- PRODUCTION
| Skill | Display Name | Use When |
|---|---|---|
| `film-video` | Film Video | Camera setup, lighting, audio, framing, B-roll, pre-filming routine, equipment |
| `edit-video` | Edit Video | Story vs retention editing, jump cuts, pacing, captions, color grading, music, sound design, VFX |
| `produce-visual-content` | Produce Visual Content | Carousels, infographics, thumbnails, photos, screenshots, visual brand consistency |

### Stage 5: PUBLISH & GROW
| Skill | Display Name | Use When |
|---|---|---|
| `platform-strategy` | Platform Strategy | Platform selection, algorithm mechanics, profile optimization, cross-platform guidance |
| `publish-grow` | Publish & Grow | Growth strategies, engagement, analytics, doubling down on winners, community engagement |

### Stage 6: MONETIZE
| Skill | Display Name | Use When |
|---|---|---|
| `monetize-content` | Monetize Content | Revenue models, digital products, coaching, lead magnets, email funnels, DM sales, pricing |
| `brand-partnerships` | Brand Partnerships | Pitch decks, pricing, packaging, inbound/outbound, integration execution, agents, legal |
| `community-building` | Community Building | Community strategy, group monetization, leadership, Facebook group growth, DM sales |

### CROSS-CUTTING
| Skill | Display Name | Use When |
|---|---|---|
| `ai-content-workflow` | AI Content Workflow | AI leverage vs dependency, AI writing workflow, recommended stack, key prompts |

---

## Cross-Reference Map with Trigger Conditions

| Source Skill | References | Trigger Condition |
|---|---|---|
| `brand-foundation` | `content-strategy` | Brand pillars defined, avatar documented |
| `content-strategy` | `write-hooks` | Content plan ready, hook needed |
| `content-strategy` | `write-scripts` | Content plan ready, script needed |
| `write-hooks` | `write-scripts` | Hook written and revised |
| `write-hooks` | `write-hooks` (return) | Hook underperforming after posting |
| `write-scripts` | `film-video` | Script complete for video |
| `write-scripts` | `produce-visual-content` | Script complete for visual content |
| `film-video` | `edit-video` | Footage captured |
| `edit-video` | `publish-grow` | Video exported and ready |
| `produce-visual-content` | `publish-grow` | Visual asset created |
| `publish-grow` | `monetize-content` | Growth consistent, 1K+ engaged followers |
| `publish-grow` | `write-hooks` | Content underperforming 2+ weeks |
| `monetize-content` | `brand-partnerships` | Want brand deals specifically |
| `monetize-content` | `community-building` | Want community-led revenue |
| `brand-partnerships` | `brand-foundation` | Need brand definition first |
| Any skill | `ai-content-workflow` | User wants to accelerate with AI |

---

## Slash Command Table

| Command | Description | Skills Activated |
|---|---|---|
| `/build-brand` | Interactive brand foundation builder -- niche, pillars, avatar, mission, visual identity | brand-foundation |
| `/content-plan` | Generate content calendar from brand foundation -- 30-day plan with topics, formats, hooks | content-strategy |
| `/write-hook` | Write and optimize a hook for any platform -- 3-5 variations with alignment analysis | write-hooks |
| `/write-script` | Build a complete video script or social post -- hook, body, CTA with storytelling | write-scripts, write-hooks |
| `/audit-content` | Diagnose why content is underperforming -- diagnostic report with fixes | publish-grow, write-hooks |
| `/build-pitch-deck` | Create brand partnership pitch deck -- 7-page outline with pricing | brand-partnerships |
| `/create-lead-magnet` | Design and outline a lead magnet -- naming, structure, distribution plan | monetize-content |
| `/write-post` | Write a LinkedIn or text-based social post -- complete post with hook, body, CTA | write-scripts, write-hooks |

---

## Cross-Plugin Boundaries

| Topic | This Plugin Handles | Delegate To |
|---|---|---|
| Paid advertising | Nothing | `paid-ads-mastery` |
| Cold email/DM outreach | Nothing | `cold-outbound-mastery` |
| Email marketing sequences | Nothing | `email-marketing-mastery` |
| Landing page CRO | Nothing | `cro-copywriting-mastery` |
| Web/UI design | Nothing | `design-mastery` |
| SEO strategy | Nothing | `seo-mastery` |

---

## Instructor Source Map

| Instructor | Primary Skills |
|---|---|
| Mino Lee (E01) | write-hooks, write-scripts, content-strategy, film-video, edit-video, publish-grow, brand-foundation |
| Dickie Bush & Nicholas Cole (E02) | write-hooks, write-scripts, content-strategy, brand-foundation, platform-strategy, publish-grow, ai-content-workflow, monetize-content |
| Gusten Sun (E03a) | brand-foundation, content-strategy, write-scripts, monetize-content, platform-strategy |
| Colin & Samir (E03b) | brand-foundation, content-strategy, brand-partnerships |
| Sky Stack (E03c) | brand-foundation, community-building |
| Anton Mehto (E03d) | platform-strategy, content-strategy |
| Parker Walbeck (E03e) | monetize-content |
| Justas / Instapreneur (E04a) | platform-strategy, publish-grow, content-strategy, monetize-content |
| Marketing Harry / Frabrand (E04b) | content-strategy, brand-foundation, publish-grow, edit-video |
| Kallaway (E05a) | write-hooks |
| Nicklas Christl (E05b) | write-scripts, edit-video |
| Bob Krist (E05c) | write-scripts, film-video |
| Creators Club (E05d) | edit-video |

---

## Execution Priority Order

When multiple skills apply: brand-foundation > content-strategy > platform-strategy > write-hooks > write-scripts > film-video > edit-video > produce-visual-content > publish-grow > monetize-content > brand-partnerships > community-building

---

## Implementation Notes

- **Decision Tree First:** Use routing tables above to determine which skill(s) to invoke
- **Cross-Reference When Needed:** Acknowledge when multiple skills contribute
- **SKILL.md First, Then References:** Start with SKILL.md for high-level guidance, then reference files for deep specifics
- **Ask Clarifying Questions:** If platform or content type is unclear, ask before routing
- **Instructor Disagreements:** When instructors disagree, present both positions and the reconciliation. Never silently pick one side
- **Platform Context:** If the user has specified their platform, filter advice accordingly (LinkedIn advice is irrelevant for TikTok-only creators and vice versa)
