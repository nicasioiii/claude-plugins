# Social Content Mastery v1.0.0

Complete social content creation knowledge engine for personal brands and creators. Provides end-to-end guidance from brand foundation through content strategy, hook writing, scripting, filming, editing, visual production, platform strategy, growth, monetization, brand partnerships, community building, and AI-assisted workflows.

## Source Material

Built from 5 extraction files covering 9 courses across ~75 hours of instruction:

| ID | Instructor(s) | Course | Focus |
|---|---|---|---|
| E01 | Mino Lee | Content Academy 3.0 | Short-form video, scripting, storytelling, editing, coaching monetization |
| E02 | Dickie Bush & Nicholas Cole | LinkedIn AI | LinkedIn content, positioning, profile optimization, AI writing |
| E03a | Gusten Sun | Personal Brand X | 7-figure personal brand, YouTube, content funnels, monetization |
| E03b | Colin & Samir | Creator Startup | Creator business models, brand partnerships, pitch decks |
| E03c | Sky Stack | (within E03) | Brand DNA, community building, congruency framework |
| E03d | Anton Mehto | (within E03) | Short-form platform selection, competitor analysis |
| E03e | Parker Walbeck | (within E03) | YouTube monetization hierarchy |
| E04a | Justas / Instapreneur | 100K+ Instagram Followers | Instagram growth, algorithm, monetization |
| E04b | Marketing Harry / Frabrand | Content Creation Dojo | Content strategy matrix, brand building, psychology |
| E05a | Kallaway | Short-Form Hooks Workshop | Hook psychology, 4-component system, hook writing |
| E05b | Nicklas Christl | Story Hero Academy | Story vs retention editing, video storytelling |
| E05c | Bob Krist | Art of Video Storytelling | Documentary storytelling, visual grammar, audio |
| E05d | Creators Club | E-Learning VFX | After Effects social VFX, transitions, 3D tracking |

## Plugin Structure

### Skills (13)

| Skill | Display Name | Stage |
|---|---|---|
| `brand-foundation` | Brand Foundation | 1. Brand Foundation |
| `content-strategy` | Content Strategy | 2. Content Strategy |
| `write-hooks` | Write Hooks | 3. Create -- Writing |
| `write-scripts` | Write Scripts | 3. Create -- Writing |
| `film-video` | Film Video | 4. Create -- Production |
| `edit-video` | Edit Video | 4. Create -- Production |
| `produce-visual-content` | Produce Visual Content | 4. Create -- Production |
| `platform-strategy` | Platform Strategy | 5. Publish & Grow |
| `publish-grow` | Publish & Grow | 5. Publish & Grow |
| `monetize-content` | Monetize Content | 6. Monetize |
| `brand-partnerships` | Brand Partnerships | 6. Monetize |
| `community-building` | Community Building | 6. Monetize |
| `ai-content-workflow` | AI Content Workflow | Cross-cutting |

### Reference Files (23)

| Skill | Reference Files |
|---|---|
| brand-foundation | ref-brand-positioning.md, ref-avatar-exercises.md |
| content-strategy | ref-idea-generation.md, ref-content-formats.md |
| write-hooks | ref-hook-templates.md, ref-hook-writing-process.md |
| write-scripts | ref-storytelling-frameworks.md, ref-linkedin-writing.md |
| film-video | ref-filming-techniques.md, ref-equipment-guide.md |
| edit-video | ref-editing-styles.md, ref-social-vfx.md |
| produce-visual-content | ref-visual-templates.md |
| platform-strategy | ref-instagram-algorithm.md, ref-linkedin-profile.md, ref-youtube-strategy.md |
| publish-grow | ref-growth-tactics.md, ref-content-optimization.md |
| monetize-content | ref-lead-magnets.md, ref-offer-design.md |
| brand-partnerships | ref-pitch-deck.md |
| community-building | ref-community-playbook.md |
| ai-content-workflow | ref-ai-prompt-library.md |

### Commands (8)

| Command | Description |
|---|---|
| `/build-brand` | Interactive brand foundation builder -- niche, pillars, avatar, mission, visual identity |
| `/content-plan` | Generate 30-day content calendar from brand foundation |
| `/write-hook` | Write and optimize hooks for any platform (3-5 variations with alignment analysis) |
| `/write-script` | Build complete video script or social post with hook, body, CTA |
| `/audit-content` | Diagnose why content is underperforming -- diagnostic report with fixes |
| `/build-pitch-deck` | Create brand partnership pitch deck -- 7-page outline with pricing |
| `/create-lead-magnet` | Design and outline a lead magnet -- naming, structure, distribution plan |
| `/write-post` | Write a LinkedIn or text-based social post -- complete post with hook, body, CTA |

### Infrastructure

| File | Purpose |
|---|---|
| CLAUDE.md | Routing for all 13 skills, decision tree, cross-references, slash commands |
| agents/social-content-advisor.md | Agent persona with routing rules |
| settings.json | Agent configuration |
| .claude-plugin/plugin.json | Plugin metadata (name, version, description) |

## File Counts

| Component | Count |
|---|---|
| Skills (SKILL.md) | 13 |
| Reference files | 23 |
| Commands | 8 |
| Infrastructure files | 4 |
| Total .md files | 47 |
| Total lines (all .md) | ~9,700 |

## Workflow

```
brand-foundation --> content-strategy --> write-hooks --> write-scripts --> film-video --> edit-video --> publish-grow
                                     \--> produce-visual-content -----------------------------------/       |
                                                                                                           v
platform-strategy (enter at any point)                                                     monetize-content
                                                                                          /       |        \
ai-content-workflow (cross-cutting)                                            brand-partnerships  community-building
```

## Key Instructor Disagreements

| Topic | Positions | Reconciliation |
|---|---|---|
| Niche width | Narrow (E03a, E02) vs. Broad (E04a) | Platform-dependent: LinkedIn = narrow, IG/TikTok = broader |
| Authenticity | Congruency over authenticity (E03c) vs. Authentic vulnerability (E01) | Congruent at brand level, authentic at content level |
| Hook priority | Text hook #1 (E05a) vs. Visual/emotional first (E01) | Text when NOT on camera, visual when on camera |
| Story vs retention editing | Story (E05b) vs. Retention (common) | Adaptive hybrid: retention for hooks, story for strong sections |
| Posting frequency | Daily (E01) vs. 3-5x/week (E02, E04b) | Daily during learning phase, 3-5x once established |
| Reel length | 7-15 seconds (E04a) vs. Up to 60 seconds (E01, E05b) | Shorter for algorithm, longer for trust-building |
| Revenue priority | AdSense (common) vs. Own products (E03e) | Own products first, AdSense is bonus |
| AI content | Cheating (common) vs. Leverage (E02) | AI amplifies expertise, never replaces it |
