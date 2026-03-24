# Sales & Negotiation Mastery Plugin

The definitive system for everything that happens AFTER a meeting is booked — from opening the conversation through closing the deal. Synthesized from 629,000+ lines of practitioner-taught course material across Chris Voss (Never Split The Difference), Cole Gordon (30 Day Closer), Luke Alexander (Closer Cartel Remote Protocol), and Ryan Serhant (Mastering CODO).

## Scope

**Starts at:** The booked meeting (prospect has agreed to a call/demo)
**Ends at:** Deal closed + immediate post-close follow-up

This plugin does NOT cover:
- Cold outreach, prospecting, or appointment setting → use `cold-outbound-mastery`
- Marketing, content, SEO, or paid ads → use `marketing-skills`
- Customer success or post-sale account management
- Sales team hiring/management (unless frameworks from courses apply directly)

## Skill Routing

Match the user's request to the most specific skill:

- **Discovery calls, needs analysis, qualification, asking better questions, understanding the prospect** → `discovery-qualification`
- **Presenting the offer, running demos, structuring pitches, articulating value** → `pitch-presentation`
- **Handling objections, rebuttals, "I need to think about it", "too expensive", spouse/partner objections** → `objection-handling`
- **Pricing negotiation, defending price, deal terms, concessions, bargaining, Ackerman model** → `negotiation-tactics`
- **Closing the deal, getting commitment, deposit handling, assumptive closes, trial closes** → `closing-techniques`
- **Sales psychology, persuasion principles, tonality, mental models, framing, loss aversion** → `sales-psychology`
- **Follow-up strategy, pipeline management, re-offer techniques, CRM, nurture sequences** → `pipeline-followup`

## Cross-Skill References

These skills work together. Common combinations:

- **"Prospect says it's too expensive"** → Start with `objection-handling` (diagnose the real objection), then `negotiation-tactics` (if it's genuinely a pricing negotiation), reference `sales-psychology` (loss aversion framing)
- **"How do I run a better discovery call?"** → Primary: `discovery-qualification`, support: `sales-psychology` (question psychology), `pitch-presentation` (transition to pitch)
- **"Prospect went dark after demo"** → Start with `pipeline-followup` (re-engagement strategy), reference `objection-handling` (what objection did you miss?)
- **"I need to present to a committee"** → Primary: `pitch-presentation`, support: `negotiation-tactics` (multi-stakeholder dynamics), `closing-techniques` (champion building)
- **"How do I handle a prospect who keeps stalling?"** → Primary: `closing-techniques` (urgency creation), support: `objection-handling` (diagnosing the real blocker), `sales-psychology` (commitment psychology)

## Product Marketing Context

**ALWAYS** check for `.claude/product-marketing-context.md` before asking the user questions about their product/service. If it exists, use that context (ICP, value props, positioning, competitive landscape) to tailor advice. Only ask for information not already covered.

## How This Plugin Relates to Others

- **cold-outbound-mastery**: Handles everything PRE-meeting (cold email, LinkedIn, DMs, cold calling for appointment setting, list building). This plugin picks up where cold-outbound-mastery stops.
- **sales (knowledge-work plugin)**: Provides CRM-integrated sales enablement (account research, competitive intelligence, call summaries). Complementary — use both together.
- **marketing-skills**: Marketing systems (content, SEO, ads, copywriting). Separate domain, but `marketing-psychology` shares foundational principles with `sales-psychology`.
- **cro-copywriting-system**: Written copy optimization. Separate from live sales conversations.

## Reference Files

Each skill has a `references/` subfolder with deep-dive material (scripts, templates, frameworks, benchmarks). The SKILL.md files contain core frameworks and decision logic. Load reference files on demand when you need specific scripts or detailed examples.

## Source Material

Knowledge synthesized from 4 expert courses:
- **Chris Voss (Black Swan)** — Never Split The Difference: FBI-trained negotiation (tactical empathy, mirroring, labeling, Ackerman model, calibrated questions)
- **Cole Gordon** — 30 Day Closer: High-ticket closing system (Belief Ladder, Pitch Codex, discovery syntax, objection diagnosis)
- **Luke Alexander** — Closer Cartel Remote Protocol: Remote closing mastery (Doctor Frame, 7-step objection process, setter/closer frameworks, live call coaching)
- **Ryan Serhant** — Mastering CODO: Closing & negotiation (CODO Method, Funnel Technique, Stealth Negotiator, urgency creation, negotiation styles)
