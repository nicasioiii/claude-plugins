# Cold Outbound Mastery v2.0 -- Routing & Operations

## Plugin Overview

Complete cold outbound knowledge engine covering 11 skills across 6 workflow layers. Built from 8 extraction files covering 500+ expert-level training transcriptions across 8 courses. Provides end-to-end guidance from email infrastructure setup through campaign optimization, covering all outbound channels: cold email, cold calling, LinkedIn, DMs, and multichannel sequencing.

---

## Ambiguous Request Decision Tree

When a user's request could match multiple skills, use this decision tree:

```
Is the user asking about EMAIL SETUP/DELIVERABILITY/DNS?
  YES -> email-infrastructure
  NO -> Continue

Is the user asking about FINDING/SOURCING/QUALIFYING LEADS?
  YES -> list-building
  NO -> Continue

Is the user asking about RESEARCH FOR MESSAGING (triggers, matrix, VOC)?
  YES -> prospect-research
  NO -> Continue

Is the user asking about WRITING FIRST LINES or PERSONALIZATION?
  YES -> first-lines
  NO -> Continue

Is the user asking about WRITING COLD EMAILS (body, subject, CTA)?
  YES -> cold-email-copy
  NO -> Continue

Is the user asking about COLD CALLING?
  YES -> cold-calling
  NO -> Continue

Is the user asking about LINKEDIN (DMs, profile, connection requests)?
  YES -> linkedin-outreach
  NO -> Continue

Is the user asking about DMs on FACEBOOK/INSTAGRAM/TWITTER?
  YES -> dm-outreach
  NO -> Continue

Is the user asking about FOLLOW-UP SEQUENCES or MEETING BOOKING?
  YES -> follow-up-sequences
  NO -> Continue

Is the user asking about CAMPAIGN METRICS, TESTING, or SCALING?
  YES -> campaign-ops
  NO -> Continue

Is the user expressing FEAR, IMPOSTER SYNDROME, or REJECTION?
  YES -> outbound-psychology
  NO -> Ask clarifying questions
```

---

## Skill Routing Table (All 11 Skills)

### Layer 1: Infrastructure

| Skill | Triggers | Status |
|-------|----------|--------|
| `email-infrastructure` | DNS, SPF, DKIM, DMARC, warmup, deliverability, domain setup, spam, inbox placement, Maildoso, custom tracking domain, signature rules, bounce rate, blacklist, Mail-Tester, postmaster tools | BUILT |

### Layer 2: List Building + Research

| Skill | Triggers | Status |
|-------|----------|--------|
| `list-building` | ICP, lead sourcing, prospect list, lead database, UpLead, Apollo, Sales Navigator, NeverBounce, email verification, list cleaning, RB2B, Buska, Reddit prospecting, Golden Goose, Upwork lead gen | BUILT |
| `prospect-research` | Messaging matrix, trigger research, VOC mining, AI research workflow, hard/soft triggers, persona mapping | BUILT |
| `first-lines` | First line, opening line, personalization, God-Level framework, research hierarchy, first line formulas, outsourcing first lines, AI personalization | BUILT |

### Layer 3: Writing (Channel-Specific)

| Skill | Triggers | Status |
|-------|----------|--------|
| `cold-email-copy` | Cold email body, subject line, CTA, case study sentence, email scripts, REPLY Method, 3-C framework, spintax, objection handling email | BUILT |
| `cold-calling` | Cold call script, opener, problem proposition, objection handling phone, gatekeeper, voicemail, Mr. Miyagi, AREQ, SDR hiring, tone mastery | BUILT |
| `linkedin-outreach` | LinkedIn DM, profile optimization, connection request, Sales Navigator, voice message, multi-thread DM, warmth levels | BUILT |
| `dm-outreach` | Facebook DM, Instagram DM, Twitter DM, conversation framework, 3 levels of pain, daily DM SOP, Inflact | BUILT |

### Layer 4: Sequencing

| Skill | Triggers | Status |
|-------|----------|--------|
| `follow-up-sequences` | Follow-up, sequence, bump email, breakup email, no-show prevention, multichannel sequence, meeting booking | BUILT |

### Layer 5: Operations

| Skill | Triggers | Status |
|-------|----------|--------|
| `campaign-ops` | Campaign metrics, benchmarks, A/B testing, diagnostics, scaling, tool stack, send timing, multichannel orchestration | BUILT |

### Layer 6: Psychology (Cross-Cutting)

| Skill | Triggers | Status |
|-------|----------|--------|
| `outbound-psychology` | Fear, imposter syndrome, rejection, mindset, frame control, persuasion, friendly helper, emotional state | BUILT |

---

## Cross-Reference Map

| From Skill | To Skill | Trigger Condition |
|-----------|----------|-------------------|
| `email-infrastructure` | `cold-email-copy` | When writing cold emails, share deliverability constraints (150 words, no links, plain text) |
| `email-infrastructure` | `campaign-ops` | When planning campaign volume or diagnosing deliverability |
| `list-building` | `prospect-research` | When building a list, define messaging matrix first |
| `list-building` | `campaign-ops` | When planning campaign or diagnosing bounce rates |
| `first-lines` | `cold-email-copy` | Always when writing a cold email (first line is the opening) |
| `first-lines` | `linkedin-outreach` | When writing LinkedIn DMs (restrained compliment uses same research) |
| `first-lines` | `cold-calling` | When personalizing cold calls (used after interest, not upfront) |
| `prospect-research` | `cold-email-copy` | Messaging matrix drives email problem/value lines |
| `prospect-research` | `cold-calling` | Triggers inform opener context and problem proposition |
| `prospect-research` | `first-lines` | Research hierarchy is the input for first lines |
| `cold-email-copy` | `follow-up-sequences` | Initial email feeds into follow-up sequence |
| `cold-calling` | `follow-up-sequences` | Voicemail + email integration (Double Tap method) |
| `linkedin-outreach` | `follow-up-sequences` | LinkedIn touches integrate with email sequences |
| `campaign-ops` | ALL SKILLS | Diagnostics route to specific skill for fixes |
| `outbound-psychology` | ALL SKILLS | Mindset blocks surface in any channel |

---

## Slash Command Table (All 14 Commands)

| Command | Description | Skills Activated | Status |
|---------|-------------|-----------------|--------|
| `/build-list` | Create a lead list strategy: ICP definition, tool recommendations, qualification criteria, sourcing plan, verification workflow, and list size targets | `list-building`, `prospect-research` | BUILT |
| `/campaign-audit` | Diagnose an underperforming outbound campaign using diagnostic decision trees | `campaign-ops`, `email-infrastructure` | BUILT |
| `/campaign-sequence` | Design a complete multi-touch follow-up sequence with timing, channels, and templates | `cold-email-copy`, `follow-up-sequences` | BUILT |
| `/cold-call` | Generate cold calling scripts, openers, and objection handling frameworks | `cold-calling`, `prospect-research` | BUILT |
| `/cold-email` | Write a cold email (body, subject, CTA) for a specific ICP and offer, with 2-3 follow-up variants | `cold-email-copy`, `first-lines` | BUILT |
| `/diagnose-campaign` | Quick diagnostic for a specific metric issue with targeted root cause analysis and fix | `campaign-ops` | BUILT |
| `/dm-outreach` | Create DM outreach sequences for Facebook, Instagram, or Twitter | `dm-outreach` | BUILT |
| `/first-line` | Write personalized first lines for cold outreach given prospect details, using the God-Level framework and 6 formulas | `first-lines`, `prospect-research` | BUILT |
| `/linkedin-outreach` | Build a LinkedIn outreach campaign or optimize your LinkedIn presence | `linkedin-outreach`, `first-lines` | BUILT |
| `/objection-handle` | Handle a specific outreach objection across any channel (phone, email, LinkedIn DM, Facebook/Instagram DM) | `cold-calling`, `cold-email-copy`, `linkedin-outreach`, `outbound-psychology` | BUILT |
| `/pitch-craft` | Craft a cold pitch for a specific prospect combining research, messaging psychology, and channel-specific copy | `prospect-research`, `outbound-psychology` | BUILT |
| `/research-prospect` | Research a specific prospect or account to build outreach angles | `prospect-research` | BUILT |
| `/scale-outbound` | Create a scaling plan for outbound operations: volume, domains, SDR hiring, multichannel orchestration, and tool stack | `campaign-ops`, `list-building`, `follow-up-sequences` | BUILT |
| `/setup-infrastructure` | Walk through cold email infrastructure setup: domains, DNS authentication, warmup, tracking, and deliverability benchmarks | `email-infrastructure` | BUILT |

---

## Execution Flow for a New Campaign

1. `email-infrastructure` -- Set up domains, DNS, warmup
2. `list-building` -- Define ICP, source leads, verify emails
3. `prospect-research` -- Build messaging matrix, identify triggers
4. `first-lines` -- Write personalized openers
5. `cold-email-copy` / `cold-calling` / `linkedin-outreach` / `dm-outreach` -- Write channel-specific outreach
6. `follow-up-sequences` -- Build multi-touch follow-up cadence
7. `campaign-ops` -- Launch, measure, diagnose, optimize
8. `outbound-psychology` -- Referenced throughout when user faces fear, rejection, or mindset blocks

---

## Product Marketing Context

**ALWAYS** check for `.claude/product-marketing-context.md` before asking the user questions. If it exists, use that context (ICP, value props, positioning, competitive landscape) and only ask for information not already covered.

---

## What This Plugin Does NOT Cover

- Lifecycle/nurture email sequences (use email-sequence skill in marketing-skills plugin)
- Inbound marketing, content marketing, SEO, paid ads
- Warm introductions or referral-based outreach
- Post-meeting sales processes (discovery, demos, closing, negotiation) -- use sales-negotiation-mastery plugin
- CRO / landing page copywriting -- use CRO plugin
- Warm email deliverability for marketing -- overlap with email-infrastructure for DNS/authentication, but sending strategy for warm email is out of scope

This plugin covers everything up to booking the meeting. It stops there.

---

## Reference Files

Each skill has a `references/` subfolder with deep-dive material (templates, scripts, examples, benchmarks). Load these on demand when you need specific frameworks or data. The SKILL.md files contain the core frameworks and instructions; reference files contain the detailed libraries and checklists.
