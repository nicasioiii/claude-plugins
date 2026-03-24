---
name: LinkedIn Outreach
description: Build a LinkedIn outreach campaign or optimize your LinkedIn presence
argument-hint: "<ICP, campaign goal, or 'profile audit'>"
---

# LinkedIn Outreach

Build LinkedIn outreach campaigns: profile optimization, connection strategies, DM sequences, Sales Navigator targeting, voice messages, and follow-up systems. Synthesized from LinkedIn Client Lab (Ty Frankel), LinkedInbox (Alex Berman), and Cold Email Wizard.

## Trigger

User runs `/linkedin-outreach` or asks about LinkedIn prospecting, connection requests, LinkedIn DMs, Sales Navigator, profile optimization, voice messages, or LinkedIn campaign design.

## Gather Context

Before building, collect:

1. **What's the goal?** Profile audit, DM campaign, connection strategy, or full LinkedIn system?
2. **Who's the ICP?** Industry, company size, job titles, geography.
3. **What's the offer?** Service, price point, delivery model.
4. **Do they have case studies?** Specific client results to reference.
5. **Current LinkedIn status?** Connections count, posting frequency, Sales Navigator access.

Check `.claude/product-marketing-context.md` first -- skip questions already answered there.

## Execution Flow

### If Profile Audit
Load `linkedin-outreach` SKILL.md + `references/linkedin-profile-optimization.md`. Walk through every section: photo, banner, tagline, about, featured, experience. Score against the 8-point checklist for 50%+ acceptance. Provide specific rewrite suggestions for each section.

### If DM Campaign
Load `linkedin-outreach` SKILL.md + `references/linkedin-dm-frameworks.md`. Build:
1. **Connection request strategy** (empty requests, timing, targeting)
2. **Initial DM framework** using the 6-step multi-thread approach (greeting, restrained compliment, rephrase offer, business question, personal connection, WIIFM)
3. **3 example DM sequences** tailored to their ICP at different warmth levels
4. **Voice message script** for follow-up (if applicable)
5. **Weekly activity targets** with specific KPIs

Also load `first-lines` skill for personalization research if writing specific DMs for named prospects.

### If Full LinkedIn System
Combine both flows above, plus load `references/linkedin-follow-up-and-systems.md` for:
- 2-bucket follow-up system setup
- Content strategy (posting cadence, engagement strategy, lead magnets)
- Sales systems (pre-call, day-of text, post-call drips)
- Tool recommendations

## Output Format

Deliver a structured LinkedIn outreach plan:

1. **Profile Optimization** (if needed) -- Section-by-section recommendations
2. **Targeting Strategy** -- Sales Navigator filters, Boolean search setup, warmth level priorities
3. **DM Sequences** -- Multi-thread framework examples for 2-3 prospect types
4. **Follow-Up System** -- Bucket 1 (throw rope) and Bucket 2 (friendly check-in) cadences
5. **Voice Message Template** -- Structure and tone guidance
6. **Weekly Activity Plan** -- Daily/weekly targets with time blocks
7. **Content Strategy** -- Posting cadence and engagement plan
8. **Tools** -- Recommended stack with costs

## Quality Checks

- [ ] Every DM example uses restrained compliments (4-6/10 enthusiasm), not over-enthusiasm
- [ ] No copy-paste scripts -- framework examples that must be adapted per prospect
- [ ] Multi-threading present (personal + business threads)
- [ ] WIIFM answered in every initial outreach example
- [ ] Connection requests default to empty (no note)
- [ ] Voice message examples convey outcome independence and friendly helper mindset
- [ ] Follow-up system uses 2-bucket approach with correct timing
