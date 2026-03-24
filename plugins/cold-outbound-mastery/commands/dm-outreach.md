---
name: DM Outreach
description: Create DM outreach sequences for Facebook, Instagram, or Twitter
argument-hint: "<platform, ICP, or offer>"
---

# DM Outreach

Create DM outreach plans for Facebook, Instagram, Twitter/X, and other social platforms (NOT LinkedIn -- use `/linkedin-outreach` for that). Includes platform-specific scripts, conversation frameworks, daily SOPs, and KPI targets. Built from Jason C Fox's Ultimate DM Course.

## Trigger

User runs `/dm-outreach` or asks about Facebook DMs, Instagram DMs, Twitter DMs, social media outreach, appointment setting via DMs, or DM scripts for non-LinkedIn platforms.

## Gather Context

Before building, collect:

1. **Which platform(s)?** Facebook, Instagram, Twitter, or multi-platform?
2. **Warm or cold outreach?** Do they have a Facebook group, existing audience, or starting from scratch?
3. **Who's the ICP?** Industry, role, follower range (for IG), group membership (for FB).
4. **What's the offer?** Service, price point, delivery model.
5. **Do they have a Facebook group?** If yes, membership questions and welcome post system.
6. **What resources exist?** Lead magnets, free trainings, case studies to share.

Check `.claude/product-marketing-context.md` first -- skip questions already answered there.

## Execution Flow

### If Facebook DM Campaign
Load `dm-outreach` SKILL.md + `references/facebook-dm-scripts.md` + `references/dm-conversation-framework.md`. Build:
1. **Lead categorization** -- Warm sources (group members, story responders, action post engagers) vs cold sources (old members, older friends, similar groups)
2. **DM openers** for each lead type (minimum 3 warm + 2 cold scripts)
3. **Conversation flow** using the 4-step consulting framework (Awareness > Cold > Warm > Hot)
4. **Pain discovery questions** -- Surface, Level 2, Level 3
5. **Call booking scripts** with triage call framing
6. **Daily SOP** with specific time allocations
7. **KPI targets** (20-50 new conversations, 100+ follow-ups, 3 qualified calls/day)

If they have a Facebook group, include group onboarding flow with 3 membership questions.

### If Instagram DM Campaign
Load `dm-outreach` SKILL.md + `references/instagram-dm-strategy.md` + `references/dm-conversation-framework.md`. Build:
1. **Lead sourcing** -- Inflact setup, follower range targeting (500-4K sweet spot)
2. **Profile optimization** -- 3 pinned posts, bio structure, bio link strategy
3. **Cold DM process** (7 steps: find, review, like, follow, comment, DM, pivot)
4. **Warm DM openers** for followers, story engagers, content likers
5. **Volume benchmarks** -- 100 new cold/day across 3 accounts, 50-100 follow-ups
6. **Conversation framework** for progressing from cold to call booking
7. **Content strategy** -- Belief-shifting carousels, hashtag testing

### If Multi-Platform
Combine relevant sections from both flows. Add platform selection guidance based on their situation.

## Output Format

Deliver a structured DM outreach plan:

1. **Platform Strategy** -- Why this platform, targeting approach
2. **Profile/Presence Setup** -- Platform-specific optimization
3. **Lead Sources** -- Warm and cold lead types with prioritization
4. **DM Scripts** -- Openers for each lead type + conversation progression
5. **Conversation Framework** -- 4-step flow with pain discovery questions
6. **Call Booking Scripts** -- Triage framing, booking follow-up
7. **Daily SOP** -- Time-blocked daily action plan
8. **KPI Dashboard** -- Daily and weekly targets
9. **Show-Up Rate System** -- Reminder sequence, pre-call funnel, post-booking sequence
10. **Tools** -- Platform-specific tool recommendations

## Quality Checks

- [ ] Every script asks a question (no dead-end messages)
- [ ] Pain discovery progresses through 3 levels (surface -> Level 2 -> Level 3)
- [ ] Call is not proposed until Level 2 pain is identified
- [ ] Triage call framing used ("not a sales call")
- [ ] Daily SOP includes both new outreach AND follow-up time
- [ ] Volume targets are realistic for the platform
- [ ] Show-up rate optimization system included (reminders, pre-call funnel)
- [ ] Resources are used as conversation starters, not deliverables
