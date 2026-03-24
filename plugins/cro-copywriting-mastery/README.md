# CRO Copywriting Mastery v2.0.0

A complete conversion copywriting system built from 12+ expert courses, organized into 14 skills with 52 reference files and 12 slash commands.

## What This Plugin Does

This plugin transforms Claude into an expert CRO copywriting advisor. It covers the full conversion copywriting workflow:

1. **Research** your audience and understand their awareness stage
2. **Strategize** your offer, mechanism, and positioning
3. **Structure** the page with proven templates
4. **Write** headlines, body copy, stories, sales pages, and emails
5. **Convert** with proof, objection handling, and optimized CTAs
6. **Optimize** with audits, testing, and data-driven improvements

## Source Courses

Knowledge extracted and synthesized from:

- Todd Brown -- A-Z Copywriting Workshop + 7 Figure Marketing Copy
- Copy Hackers (Joanna Wiebe) -- 10x Landing Pages
- Arman Assadi -- 7-Figure Copywriting (Foundr)
- Ryan Deiss -- Craft A High-Converting Homepage v2
- Eddie Shleyner -- Transformational Landing Pages
- Adil Amarsi -- Encyclopedia of Copy
- Sandy Franks -- Titans of Direct Response (Storytelling)
- OnePeak Creative -- $1M Landing Page Blueprint
- Tom Albrighton -- Copywriting Made Simple
- Traffic & Funnels -- Copywriting Masterclass (Andrew Milligan, Ashton Shanks, Kevin Rogers, David Deutsch)

## 14 Skills by Workflow Stage

### Foundation (Skills 1-3)
| # | Skill | What It Covers |
|---|-------|---------------|
| 1 | `customer-research` | Audience research, VOC mining, avatar frameworks, interviews, surveys |
| 2 | `awareness-sophistication` | 5 Stages of Awareness, Market Sophistication, awareness diagnosis |
| 3 | `offer-engineering` | Offer creation, pricing psychology, value stacking, guarantees |

### Strategy (Skills 4-5)
| # | Skill | What It Covers |
|---|-------|---------------|
| 4 | `big-idea-mechanism` | Unique mechanism, campaign thesis, primary promise, 75/25 rule |
| 5 | `benefit-translation` | Feature-to-benefit translation, FAB charts, dimensionalization |

### Structure (Skills 6-7)
| # | Skill | What It Covers |
|---|-------|---------------|
| 6 | `page-architecture` | Page templates (5 types + homepage), 10/90 rule, message matching |
| 7 | `headline-hook-craft` | Headlines, hooks, fascinations, subject lines, 6 U's framework |

### Writing (Skills 8-11)
| # | Skill | What It Covers |
|---|-------|---------------|
| 8 | `body-copy-craft` | Verb selection, sentence structure, readability, formatting |
| 9 | `story-narrative` | Story frameworks (12-point, Hero's Journey, PAISA), narrative technique |
| 10 | `sales-page-vsl` | Sales pages, VSLs, CPB chunks, marketing argument, spit draft |
| 11 | `email-sequences` | 7-email welcome sequence, subject lines, email strategy |

### Conversion (Skills 12-13)
| # | Skill | What It Covers |
|---|-------|---------------|
| 12 | `objection-proof-psychology` | Proof strategy, objection handling, cognitive biases, framing |
| 13 | `cta-conversion-elements` | CTA formulas, closing techniques, checkout optimization |

### Optimization (Skill 14)
| # | Skill | What It Covers |
|---|-------|---------------|
| 14 | `testing-audit-optimization` | 20-point audit, homepage audit, A/B testing, benchmarks |

## 12 Slash Commands

| Command | What It Does |
|---------|-------------|
| `/research-audience` | Guided audience research worksheet |
| `/diagnose-awareness` | Interactive awareness stage diagnostic |
| `/build-mechanism` | 5-step mechanism interrogation process |
| `/engineer-offer` | 7-dimension offer scorecard |
| `/translate-benefits` | Feature-to-benefit translation (3 tiers) |
| `/write-headline` | Generate 20+ scored headline variations |
| `/build-page` | Page template selection + spit draft outline |
| `/write-email-sequence` | 7-email welcome sequence builder |
| `/write-story` | Story framework selection + narrative draft |
| `/audit-page` | 20-point copy audit with scoring |
| `/audit-homepage` | 7-point homepage audit |
| `/plan-test` | Prioritized test plan with hypotheses |

## File Structure

```
plugin_v2/
├── .claude-plugin/
│   └── plugin.json
├── CLAUDE.md                    # Routing logic and system prompt
├── README.md                    # This file
├── settings.json                # Agent configuration
├── agents/
│   └── cro-copywriting-advisor.md
├── skills/
│   ├── customer-research/
│   ├── awareness-sophistication/
│   ├── offer-engineering/
│   ├── big-idea-mechanism/
│   ├── benefit-translation/
│   ├── page-architecture/
│   ├── headline-hook-craft/
│   ├── body-copy-craft/
│   ├── story-narrative/
│   ├── sales-page-vsl/
│   ├── email-sequences/
│   ├── objection-proof-psychology/
│   ├── cta-conversion-elements/
│   └── testing-audit-optimization/
└── commands/
    ├── build-mechanism.md
    ├── audit-page.md
    ├── audit-homepage.md
    └── plan-test.md
```

## How to Use

1. **Start with a question or task** -- The advisor routes you to the right skill automatically
2. **Use slash commands** for structured workflows (e.g., `/audit-page` for a full copy audit)
3. **Follow the workflow order** when building from scratch: Research -> Strategy -> Structure -> Write -> Convert -> Optimize
4. **Provide context** -- The better you describe your product, audience, and goals, the better the output

## Key Principles

- **Research before writing, always.** The best copywriters spend 60-80% of time on research.
- **Clarity beats cleverness.** Clear, specific copy outperforms clever wordplay every time.
- **One Reader, One Big Idea, One Offer.** Focus is the foundation of conversion.
- **No proof = no campaign.** Every claim needs evidence.
- **Test big before small.** Test offers and headlines before button colors.
- **The offer matters more than the copy.** A great offer with mediocre copy beats mediocre offer with great copy.

## Version History

- **v2.0.0** -- 14 skills (3 new: offer-engineering, body-copy-craft, sales-page-vsl), 52 reference files, 12 commands. Complete rewrite from v1.
- **v1.0.0** -- 11 skills, 18 reference files, 8 commands. Initial release.
