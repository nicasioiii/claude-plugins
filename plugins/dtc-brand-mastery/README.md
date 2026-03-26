# DTC Brand Mastery v1.0.0

Complete DTC e-commerce knowledge engine for building, launching, and scaling product brands across Shopify/DTC, Amazon FBA, and TikTok Shop.

## What This Plugin Covers

End-to-end guidance from product ideation through exit, organized into 15 skills covering the full brand lifecycle:

1. **Product Ideation & Validation** -- PSSP, Four Criteria, PRIME, TikTokability, MVP frameworks
2. **Customer Personas & Brand Strategy** -- MVB Pyramid, SAVE framework, naming, archetypes, designer briefs
3. **Sourcing & Supplier Management** -- Alibaba, 10-3-1 method, negotiation scripts, import records, domestic manufacturing
4. **Product Development & Prototyping** -- Prototyping workflow, spec sheets, 3-stage sampling, regulatory compliance, packaging
5. **Quality Control & Inspections** -- AQL 2.5, third-party inspection, failed inspection plans, payment leverage
6. **Shipping, Logistics & Fulfillment** -- Ocean/air freight, 3PL, Amazon MCF, TikTok fulfillment
7. **Shopify Store & DTC Setup** -- Store build, PASTOR framework, landing pages, upsells, conversion optimization
8. **Amazon Listing Optimization** -- A9 ranking, semantic relevance, title density, Rufus/Cosmo, A+ content
9. **Amazon PPC & Advertising** -- Campaign structure, bid optimization, DSP, Sponsored Brands/Display
10. **TikTok Shop Setup & Operations** -- Registration, creator outreach, GMV Max ads, 22-step launch sequence
11. **Launch & Reviews Strategy** -- Platform-specific launches, Vine strategy, review generation, social proof
12. **Pricing, Unit Economics & Finance** -- Markup rules, COGS breakdown, CCC, LTV, break-even CPA, valuation
13. **Influencer & Content Marketing** -- Creator outreach, 3 C's of Community, content territories, UGC, spark codes
14. **Operations, Scaling & Team Building** -- Demand forecasting, hiring framework, Escala systemization, omnichannel
15. **Legal, IP & Exit Strategy** -- Trademarks, patents, entity types, exit valuation, deal structures

## Sources

Built from 9 extraction files covering expert-level training:

| Instructor | Expertise |
|---|---|
| Gretta Van Riel | 5 multimillion-dollar DTC brands (SkinnyMeTea, Dropbottle, The Fifth, Hey Influencers, Drop for Drop) |
| Jason Wong | Doe Lashes founder; prototyping, sourcing, finance, hiring frameworks |
| Matt Clark | LifeBoost Coffee ($30M/year); omnichannel machine, supplier templates, ad scaling |
| Melisa Vong | Amazon FBA; PRIME method, 10-step validation, review strategy, exit planning |
| Kian Golzari | 2,000+ products sourced; 10-3-1 method, spec sheets, feature innovation, packaging |
| Kevin King + 20 speakers | BDSS Summits; A9 ranking, PPC triangulation, semantic relevance, listing optimization |
| Incrementum Digital | Amazon PPC; campaign structures, DSP, bid optimization, bulksheet operations |
| Escala Academy | Business systemization; process hierarchy, ClickUp, sprint methodology |
| Michelle | TikTok Shop; 100+ brands onboarded, creator outreach, GMV Max, fulfillment sync |

## Commands (14)

| Command | Purpose |
|---|---|
| `/audit-operations` | Operations efficiency audit with scored report and prioritized improvements |
| `/build-brand` | Generate brand pyramid, name options, persona drafts, and designer brief |
| `/dtc-audit` | Full business audit across all 15 skills with scored report card |
| `/exit-prep` | Exit preparation checklist and valuation estimate |
| `/find-supplier` | Guided Alibaba or domestic supplier search with vetting checklist |
| `/influencer-outreach` | Plan influencer/creator outreach campaign with tier selection and templates |
| `/optimize-listing` | Audit Amazon listing against A9 ranking factors and conversion best practices |
| `/plan-launch` | Generate platform-specific launch checklist and timeline |
| `/price-product` | Calculate unit economics, markup, break-even CPA, and recommended pricing |
| `/scale-business` | Scaling strategy planner with omnichannel roadmap and hiring plan |
| `/setup-shopify` | Shopify store setup wizard with 14-step build process |
| `/setup-tiktok-shop` | Step-by-step TikTok Shop setup wizard |
| `/spec-sheet` | Generate product specification sheet from user inputs |
| `/validate-product` | Run product through all validation frameworks |

## Structure

```
dtc-brand-mastery/
  .claude-plugin/plugin.json
  CLAUDE.md                    # Full routing for all 15 skills
  README.md
  settings.json                # Points to dtc-brand-advisor agent
  agents/dtc-brand-advisor.md  # Agent persona with routing rules
  commands/                    # Slash command wizards
  skills/
    01-product-ideation/       # SKILL.md + references/
    02-brand-strategy/
    03-sourcing-suppliers/
    04-product-development/
    05-quality-control/
    06-logistics-fulfillment/
    07-shopify-dtc/
    08-amazon-listing/
    09-amazon-ppc/
    10-tiktok-shop/
    11-launch-reviews/
    12-pricing-finance/
    13-influencer-content/
    14-operations-scaling/
    15-legal-exit/
```

Each skill directory contains a `SKILL.md` (under 500 lines) with core frameworks and a `references/` directory with detailed reference files (200-400 lines each).
