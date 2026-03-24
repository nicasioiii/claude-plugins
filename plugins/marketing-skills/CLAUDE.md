# Marketing Skills Plugin

This plugin contains 18 marketing skills for founders and technical marketers. Each skill is a self-contained expert system with frameworks, templates, benchmarks, and reference material.

**Note**: Paid advertising functionality has been moved to the dedicated **paid-ads-mastery** plugin.
**Note**: All SEO functionality (audit, AI SEO, schema, programmatic SEO, content strategy, analytics tracking) has been moved to the dedicated **seo-mastery** plugin.
**Note**: Copywriting and copy-editing functionality has been moved to the dedicated **cro-copywriting-mastery** plugin.

## How Skills Work

Skills are loaded automatically when Claude detects a relevant request. Each skill's `description` field contains trigger phrases that tell Claude when to activate it. You can also invoke any skill manually using its slash command.

## Skill Routing

When a user asks for marketing help, match their request to the most specific skill available:

- **CRO requests**: Route to the specific CRO skill (page-cro, form-cro, signup-flow-cro, onboarding-cro, popup-cro, paywall-upgrade-cro) rather than the general page-cro
- **SEO requests**: Route to the **seo-mastery** plugin. It contains 9 deep skills covering keyword research, competitive analysis, content clusters, on-page optimization, content production, technical SEO, link building, local/ecommerce/programmatic SEO, and analytics/reporting.
- **Email requests**: Route to email-sequence for lifecycle/nurture flows and customer retention. For cold outbound prospecting (cold email, LinkedIn outreach, cold calling, DMs), use the cold-outbound-mastery plugin instead. For emails used in active sales negotiations, use sales-negotiation-mastery plugin
- **Ad requests**: Route to the **paid-ads-mastery** plugin instead. That plugin contains paid-ads and ad-creative skills.
- **Copywriting requests**: For copywriting, CRO, landing pages, sales pages, headlines, story copy, and email copy for sales → use the **cro-copywriting-mastery** plugin. It covers benefit discovery, headline creation, copy flow organization, and testing/audit/optimization.

## Product Marketing Context

If the user has set up `.claude/product-marketing-context.md`, read it before asking questions on any marketing task. This document contains their positioning, ICP, value props, and competitive landscape.

## Psychology Content in This Plugin

The marketing-psychology content covers foundational sales psychology principles. For applied sales psychology in live sales conversations, objection handling during negotiations, and psychological frameworks for closing, see the sales-negotiation-mastery plugin.

## Reference Files

Many skills have a `references/` subfolder with deep-dive material. Load these on demand when you need specific frameworks, templates, or data — don't load them all upfront.
