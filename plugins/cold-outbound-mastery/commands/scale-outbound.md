---
name: Scale Outbound
description: Create a scaling plan for outbound operations. Covers volume scaling, domain expansion, SDR hiring, multichannel orchestration, and tool stack recommendations. Activates campaign-ops, list-building, and follow-up-sequences skills.
---

# Scale Outbound Wizard

## Step 1: Assess Current State

Ask the user:

1. **Current channels active:** Which channels are you currently using?
2. **Current volume:** Daily/weekly numbers for each channel (emails, calls, DMs, connections)
3. **Current metrics:** Open rate, reply rate, connect rate, set rate, show rate, call book rate (by channel)
4. **Current tools:** What sending tools, CRM, warmup, lead gen tools are you using?
5. **Current team:** Solo operator, small team, or SDR team?
6. **Target scale:** Where do you want to be? (e.g., "2x meetings," "500 emails/day," "hire SDRs")
7. **Budget for scaling:** What can you invest in tools and people?

---

## Step 2: Verify Scaling Prerequisites

**Load skill:** `campaign-ops` > references/ab-testing-and-scaling.md

Run through the prerequisites checklist:

- [ ] **Metrics healthy for 2+ consecutive weeks** (above all benchmark minimums)
- [ ] **Infrastructure solid** (domains warmed, DNS authenticated, no blacklists)
- [ ] **List quality verified** (<5% bounce, emails validated)
- [ ] **Copy proven** (A/B tested with clear winning variants)
- [ ] **Follow-up sequence built** (minimum 5 touches)
- [ ] **Tracking operational** (can measure all key metrics)
- [ ] **Booking mechanics working** (show rate >70%)
- [ ] **Response capacity** (can reply within minutes)

If ANY prerequisite fails, prescribe the fix before scaling. Scaling amplifies problems -- if metrics are bad at 50 emails/day, they will be catastrophically bad at 500.

---

## Step 3: Design the Scaling Plan

### Email Scaling Plan

**Load skill:** `campaign-ops` > references/ab-testing-and-scaling.md

Calculate domain requirements:
- Current volume: ___ emails/day
- Target volume: ___ emails/day
- Domains needed: target / 30 = ___ domains
- Buffer domains (pre-warming): +20% = ___ additional domains

Build the ramp schedule:
| Week | Domains Active | Volume/Domain | Total Daily | Action |
|---|---|---|---|---|
| Current | ___ | ___ | ___ | Baseline |
| +2 weeks | +___ new domains (warming) | 0 on new | Same | Start warming new domains |
| +4 weeks | All domains active | 5-10 on new | Incremental | Soft launch new domains |
| +6 weeks | All domains ramped | 25-30 | Target volume | Full scale |

### Call Scaling Plan

Options by team size:
- **Solo with more dials:** Optimize call blocks (Wed-Thu 8-10 AM, 4-5 PM), use power dialer (Twilio + GHL)
- **Solo with SDR support:** Hire 1 experienced SDR (Upwork, $5K+ earned, 90%+ success). Provide full enablement. 1-2 week trial.
- **Building an SDR team:** Tiered commission (15-40%), end-of-day reports, weekly call reviews, clear KPIs

### LinkedIn Scaling Plan

- Add Dripify for connection request automation (if not already)
- Start voice messages (1 call per 3-5 voice messages)
- Increase content to 3-5 posts/week (feeds acceptance rate and warmth)
- Add engagement groups (10-15 creators, mutual support)
- Build lead magnets for comment-to-get distribution (dozens of conversations at once)

### Multichannel Scaling

**Load skill:** `follow-up-sequences`

Design the integrated sequence:
- Email as primary channel (highest volume)
- LinkedIn as secondary (connection + DM + voice)
- Phone as conversion accelerator (call people who open emails, engage on LinkedIn)
- Voicemail + email combo (3.24x reply rate increase)

Use K.I.S.S. pattern:
- Day 1: Triple tap (call + voicemail + email + social)
- Day 3: Double tap (call + email)
- Repeat with new problem angle in week 2

---

## Step 4: Tool Stack Recommendations

**Load skill:** `campaign-ops` > references/tool-stack-reference.md

Based on current tools and scaling target, recommend:
- Sending tools needed
- Additional domains to purchase
- Warmup tool capacity
- Lead gen tools for increased list needs
- CRM upgrades if needed
- Calling infrastructure
- LinkedIn tools

Provide cost estimate for the scaling tool stack.

---

## Step 5: Deliver the Scaling Playbook

Output a structured plan:

### Scaling Summary
- Current state: ___ meetings/month from ___ channels
- Target state: ___ meetings/month from ___ channels
- Timeline: ___ weeks to reach target
- Investment required: $___ /month in tools + $___/month in team

### Week-by-Week Action Plan
- Weeks 1-2: Infrastructure prep (new domains, warmup, tools)
- Weeks 3-4: Soft launch at increased volume
- Weeks 5-6: Ramp to target volume
- Weeks 7-8: Optimize and stabilize at scale

### Monitoring Plan
- Daily: Spam rate, bounce rate, reply sentiment
- Weekly: Full metric review against benchmarks
- Monthly: ROI calculation, tool cost review, team performance

### Risk Mitigation
- What to do if spam rate creeps up during scaling
- What to do if reply rate drops as volume increases
- What to do if SDR performance is below benchmark
- When to pause and stabilize vs. continue scaling

### Cross-References
- If list needs to scale: `/build-list` for list strategy
- If copy needs more variants for testing: `/cold-email` for new angles
- If adding cold calls: `/cold-call-script` for framework
- If adding LinkedIn: `/linkedin-dm` for DM sequence
