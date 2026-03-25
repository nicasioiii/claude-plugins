# Sales & Negotiation Mastery Plugin v2

The definitive system for everything that happens AFTER a meeting is booked -- from opening the conversation through closing the deal and managing pipeline. Synthesized from 629,000+ lines of practitioner-taught course material across Chris Voss (Never Split The Difference), Cole Gordon (30 Day Closer), Luke Alexander (Closer Cartel Remote Protocol), and Ryan Serhant (Mastering CODO).

## Scope

**Starts at:** The booked meeting (prospect has agreed to a call/demo)
**Ends at:** Deal closed + post-close follow-up + pipeline reactivation

This plugin does NOT cover:
- Cold outreach, prospecting, or list building --> use `cold-outbound-mastery`
- Marketing, content, SEO, or paid ads --> use marketing plugins
- Customer success or post-sale account management
- Career advice for closers (LLC, taxes, offer hunting)

## Skill Routing (12 Skills)

Match the user's request to the most specific skill. When multiple skills apply, load the primary skill first, then cross-reference supporting skills.

### Pre-Call Layer
- **Pre-call mindset, identity, conviction, frames, fear management, energy, flow state, ramp-up** --> `sales-mindset-prep`
- **Voice types, inflection, pacing, silence, rapport levels, subcommunication, body language on video** --> `tonality-delivery`

### Core Call Flow
- **Discovery calls, qualification, building the gap, probing questions, Belief Ladder** --> `discovery-qualification`
- **Mirroring, labeling, accusation audits, "That's Right," power of "no," calibrated questions** --> `tactical-empathy`
- **Structuring and delivering the pitch, Pitch Codex, transitions, two sales in every call** --> `pitch-presentation`
- **Diagnosing objections, isolation, INTAI handling, money/spouse/uncertainty objections** --> `objection-handling`
- **Getting commitment, investment drop, trial closes, urgency, Rule of Three** --> `closing-techniques`

### Negotiation and Deal Structuring
- **Price negotiation, Ackerman model, bargaining, concessions, negotiator types, Black Swans** --> `negotiation-tactics`

### Post-Call and Support
- **Follow-up sequences, pipeline management, re-offers, CRM, reactivation, anti-ghosting** --> `pipeline-followup`
- **Appointment setting, DM/phone setting, triage calls, booking, show rates** --> `appointment-setting`

### Foundational / Cross-Cutting
- **Psychological principles, loss aversion, framing, Six Human Needs, consistency bias, buyer types** --> `sales-psychology`
- **In-person presence, first impressions, body language, setting manipulation, power dynamics** --> `presence-power`

## Decision Tree

```
User Request
    |
    +--> About mindset, prep, fear, conviction, energy? --> sales-mindset-prep
    +--> About how to SOUND (voice, tone, silence)? --> tonality-delivery
    +--> About asking questions, qualifying, discovery? --> discovery-qualification
    +--> About empathy, mirroring, labeling, "that's right"? --> tactical-empathy
    +--> About presenting the offer, pitch structure? --> pitch-presentation
    +--> About handling objections or rebuttals? --> objection-handling
    +--> About getting the commitment, closing? --> closing-techniques
    +--> About price negotiation, bargaining, deal terms? --> negotiation-tactics
    +--> About follow-up, pipeline, ghosted prospects? --> pipeline-followup
    +--> About setting appointments, booking calls? --> appointment-setting
    +--> About WHY people buy (theory, psychology)? --> sales-psychology
    +--> About in-person presence, body language, meetings? --> presence-power
    +--> About reviewing a sales call? --> /callreview command
    +--> About a psychological principle? --> /psychology command
```

## Commands (8 Total)

| Command | Maps To | Purpose |
|---------|---------|---------|
| `/discovery` | discovery-qualification, tactical-empathy | Prepare or review a discovery call |
| `/pitch` | pitch-presentation, sales-psychology | Build or refine a pitch/offer presentation |
| `/objection` | objection-handling, tactical-empathy | Diagnose and resolve a specific objection |
| `/close` | closing-techniques, negotiation-tactics | Plan or execute a closing strategy |
| `/negotiate` | negotiation-tactics, tactical-empathy, presence-power | Prepare for or debrief a negotiation |
| `/followup` | pipeline-followup, appointment-setting | Create follow-up sequence or re-engagement plan |
| `/callreview` | ALL (route by diagnosis) | Review a call and diagnose issues |
| `/psychology` | sales-psychology, sales-mindset-prep | Explain or apply a psychological principle |

## Cross-Reference Map

### Common Multi-Skill Scenarios

| User Request | Primary Skill | Supporting Skills |
|---|---|---|
| "Prospect says too expensive" | objection-handling | negotiation-tactics, sales-psychology (loss aversion), tactical-empathy (labeling) |
| "How do I run better discovery?" | discovery-qualification | tactical-empathy (mirroring/labeling), tonality-delivery |
| "Prospect went dark" | pipeline-followup | tactical-empathy ("have you given up?"), objection-handling |
| "Preparing for a big negotiation" | negotiation-tactics | presence-power, tactical-empathy, sales-mindset-prep |
| "I keep losing deals at the close" | closing-techniques | objection-handling, discovery-qualification, tonality-delivery |
| "Review my sales call" | /callreview | ALL (diagnose which phase broke down) |
| "Help me train a setter" | appointment-setting | tonality-delivery, discovery-qualification |
| "Spouse objection" | objection-handling | tactical-empathy, closing-techniques (deposit close) |
| "I freeze under pressure" | sales-mindset-prep | tonality-delivery, tactical-empathy |
| "Presenting to a committee" | pitch-presentation | negotiation-tactics, closing-techniques, presence-power |

## Product Marketing Context

**ALWAYS** check for `.claude/product-marketing-context.md` before asking the user about their product/service. If it exists, use that context to tailor advice. Only ask for information not already covered.

## How This Plugin Relates to Others

- **cold-outbound-mastery**: Everything PRE-meeting. This plugin picks up where cold-outbound-mastery stops.
- **marketing plugins**: Marketing systems (content, SEO, ads). Separate domain.
- **cro-copywriting-system**: Written copy optimization. Separate from live sales conversations.

## Reference Files

Each skill has a `references/` subfolder with deep-dive material. SKILL.md files contain core frameworks and decision logic. Load reference files on demand when you need specific scripts, templates, or detailed examples.

## Source Material

Synthesized from 4 expert courses:
- **Chris Voss (Black Swan Group)** -- Tactical empathy, mirroring, labeling, Ackerman model, calibrated questions, negotiator types
- **Cole Gordon (30 Day Closer)** -- Belief Ladder, Pitch Codex, Three Frames, discovery syntax, objection diagnosis, follow-up systems
- **Luke Alexander (Closer Cartel)** -- Belgian Malinois identity, 5-step objection process, appointment setting, pipeline management, selling to affluent
- **Ryan Serhant (Mastering CODO)** -- CODO method, Six Power Plays, Game Theory, Interests vs. Positions, improv, stealth negotiation
