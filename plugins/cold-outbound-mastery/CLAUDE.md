# Cold Outbound Mastery Plugin

The definitive system for planning, executing, and optimizing cold outbound campaigns across all channels. This plugin fully replaces any cold outbound functionality in other installed plugins (including marketing-skills/cold-email).

## Skill Routing

Match the user's request to the most specific skill:

- **Writing cold emails, sequences, follow-ups, subject lines, offers** → `cold-email`
- **Opening lines, personalization, first lines, compliments, research for customization** → `first-lines`
- **Email infrastructure, deliverability, DNS, SPF, DKIM, DMARC, warmup, domains, spam, inbox placement** → `infrastructure`
- **LinkedIn outreach, profile optimization, connection requests, LinkedIn DMs, Sales Navigator, Dripify** → `linkedin`
- **Cold calling, phone scripts, objection handling, gatekeepers, voicemail, SDR hiring** → `cold-calling`
- **DM outreach on Instagram, Facebook, Twitter/X, multi-platform DMs, conversation frameworks** → `dm-outreach`
- **Campaign management, metrics, diagnostics, lead generation, list building, scaling, multi-channel orchestration** → `campaign-ops`

## Cross-Skill References

These skills work together. When helping a user, pull in knowledge from adjacent skills:

- Writing cold emails? Check `first-lines` for opening line formulas and `infrastructure` for deliverability constraints that affect copy (word count, link usage, spam triggers).
- Setting up LinkedIn outreach? Check `first-lines` for personalization techniques and `campaign-ops` for tracking/metrics.
- Building a campaign? Check `lead-gen` references in `campaign-ops`, then route to the appropriate channel skill for copy.
- Diagnosing poor results? Start with `campaign-ops` diagnostics, then drill into `infrastructure` (deliverability) or the relevant channel skill (copy quality).

## Product Marketing Context

**ALWAYS** check for `.claude/product-marketing-context.md` before asking the user questions. If it exists, use that context (ICP, value props, positioning, competitive landscape) and only ask for information not already covered.

## What This Plugin Does NOT Cover

- Lifecycle/nurture email sequences (use email-sequence skill in marketing-skills plugin)
- Inbound marketing, content marketing, SEO, paid ads
- Warm introductions or referral-based outreach
- Post-meeting sales processes (discovery, demos, objection handling, closing, negotiation) → use sales-negotiation-mastery plugin

This plugin covers everything up to booking the meeting. It stops there.

## Reference Files

Each skill has a `references/` subfolder with deep-dive material (templates, scripts, examples, benchmarks). Load these on demand when you need specific frameworks or data — don't load them all upfront. The SKILL.md files contain the core frameworks and instructions; reference files contain the detailed libraries.
