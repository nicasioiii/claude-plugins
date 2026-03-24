---
name: Cold Call Script
description: Generate cold calling scripts, openers, and objection handling frameworks
argument-hint: "<offer, persona, or industry>"
---

# Cold Call Script

Build cold call frameworks: openers, problem propositions, objection handling scripts, gatekeeper bypass, voicemails, and call metrics targets. Synthesized from 30MPC (Armand Farrokh & Nick Cegelski) and Sean Longden's Conquer Cold Calling.

## Trigger

User runs `/cold-call` or asks about cold calling scripts, call openers, phone objection handling, gatekeeper bypass, voicemail scripts, SDR playbooks, or cold call frameworks.

## Gather Context

Before building, collect:

1. **Who's the prospect?** Title, seniority (below/at/above the line), industry.
2. **What's the offer?** Service/product, key differentiator, price point.
3. **What problem do you solve?** The specific, visceral problem (not a generic value prop).
4. **Do you have case studies?** Specific results with named clients.
5. **Who's calling?** The founder themselves, an SDR, or an appointment setter for a client?
6. **What competitors do prospects currently use?** For competitor-specific objection scripts.
7. **Gatekeepers?** Are they calling direct lines/mobiles or going through receptionists?

Check `.claude/product-marketing-context.md` first -- skip questions already answered there.

Also load `prospect-research` skill if user needs help identifying the triggering problem or building a messaging matrix.

## Execution Flow

### Step 1: Build the Problem Proposition
Load `cold-calling` SKILL.md + `references/cold-call-frameworks.md`. This is the most critical step.

1. **Identify the triggering problem** -- Must pass the Hairy Lollipop Test (visceral, visual, specific). Layer: persona + annoyances + scenery + emotion.
2. **Write the one-sentence solution** -- "We do [biggest differentiator] so that [problem goes away]"
3. **Craft the interest-based CTA** -- Validate interest only, never ask for time

If prospect is senior (VP/C-suite), Chunk Up: attach a business problem to the process problem.

### Step 2: Build 2 Opener Variants
From the 30MPC framework:

**Variant A: Heard the Name Tossed Around**
- Identify the context (competitors, investors, regional peers, industry cohort)
- Write the opener with context -> intro -> assumptive question
- Write the "No" response ("Ha! Guess I'm not as popular as I thought...")
- Write the permission pivot

**Variant B: Tailored Permission Opener**
- Identify prospect-specific context connected to the problem you solve
- Write the opener with context -> own the cold call -> ask for 30 seconds
- Write the "No" recovery (get to real objection, then pivot back)

### Step 3: Build Objection Scripts (Top 5)
Load `references/objection-handling-phone.md`. For each objection:

Using Mr. Miyagi framework:
1. **Agree** -- Specific agreement phrasing
2. **Incentivize** -- Multiple choice question to get them talking
3. **Test Drive** -- What they'll get from a meeting even if they never buy

Build scripts for the 5 most likely objections based on their offer and industry. Common ones:
- No budget
- Not interested / already have something
- Using a competitor (build trap question if known competitor)
- Send me information (include Dart technique)
- Not a priority / call in 6 months

### Step 4: Build Supporting Elements
- **Gatekeeper bypass** (if needed) -- Load `references/gatekeeper-voicemail-metrics.md`
- **Voicemail scripts** -- Double Tap method (context-only VM #1, context + social proof VM #2)
- **Metric targets** -- Connect rate, set rate, show rate goals based on Golden 3 data

### Step 5: Call Plan
- Recommended dial volume and time blocks
- Account tiering (A/B/C) based on buying triggers
- Who to call (above/at/below the line priorities)
- No-show protocol

## Output Format

Deliver a complete cold call playbook:

1. **Problem Proposition** -- Triggering problem + one-sentence solution + interest CTA
2. **Opener A** (Heard the Name) -- Full script with Yes/No branches
3. **Opener B** (Tailored Permission) -- Full script with No recovery
4. **Objection Scripts** (Top 5) -- Agree/Incentivize/Test Drive for each
5. **Gatekeeper Bypass** -- 3-attempt sequence
6. **Voicemail Scripts** -- VM #1 (15 sec) + VM #2 (30 sec)
7. **Metric Targets** -- Connect/set/show rate goals
8. **Call Plan** -- Weekly dial targets, time blocks, account tiers

## Quality Checks

- [ ] Problem proposition passes the Hairy Lollipop Test (can you SEE the problem?)
- [ ] Openers lead with context about the PROSPECT, not about you
- [ ] Interest-based CTA used (never asks for time directly)
- [ ] Objection scripts use agree/incentivize/test drive structure (not counter-pitching)
- [ ] No banned openers ("Did I catch you at a bad time?", "How's your day going?", "Is this [Name]?")
- [ ] Tone guidance included (slow down, kill uptones, laugh, human voice)
- [ ] If senior persona, problem proposition is Chunked Up to business-level impact
- [ ] Gatekeeper scripts share context, not product
- [ ] Voicemails direct to email, never ask for callback
