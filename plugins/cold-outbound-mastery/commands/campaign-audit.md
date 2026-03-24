---
name: Campaign Audit
description: Diagnose an underperforming outbound campaign using diagnostic decision trees. Identifies bottlenecks across email, phone, LinkedIn, and DM channels. Activates campaign-ops and email-infrastructure skills. Outputs prioritized fix list with specific actions.
---

# Campaign Audit Wizard

## Step 1: Identify Channel and Gather Metrics

Ask the user:

1. **Which channels are you running?** (cold email, cold calls, LinkedIn DMs, Instagram/Facebook DMs, multichannel)
2. **How long has the campaign been running?** (important for maturity assessment)
3. **Current daily/weekly volume?** (emails sent, calls made, DMs sent, connections requested)

Then ask for channel-specific metrics:

### Cold Email Metrics Needed
- Open rate (%)
- Reply rate (%)
- Positive reply rate (% of total replies that are interested)
- Bounce rate (%)
- Spam complaint rate (% -- check Google Postmaster)
- Number of sending domains
- Emails per domain per day
- Warmup status (running? what tool? how long?)

### Cold Call Metrics Needed
- Total dials per week
- Connect rate (% of dials reaching a human)
- Set rate (% of conversations that book a meeting)
- Show rate (% of meetings that actually happen)
- What opener are they using?
- Are they calling mobile/direct or going through gatekeepers?

### LinkedIn Metrics Needed
- Connection requests sent per week
- Acceptance rate (%)
- Reply rate on initial DMs (%)
- Call book rate (% of conversations that become meetings)
- Are they using voice messages?
- Content posting frequency

### DM Metrics Needed (FB/IG)
- Daily new conversations
- Daily follow-ups
- Conversation to call rate
- Show-up rate
- Which platform(s)?

---

## Step 2: Run Diagnostic

**Load skill:** `campaign-ops` > references/benchmarks-and-diagnostics.md

Compare each metric against benchmarks and run the diagnostic tree:

### For Each Metric Below Benchmark:

1. **Identify the symptom** (e.g., "Open rate is 18% -- below 30% minimum")
2. **Walk the diagnostic tree** (check subject lines -> deliverability -> lead quality -> timing)
3. **Identify the root cause** (not the symptom)
4. **Prescribe the fix** with the specific skill to use

### Priority Framework
- **P0 (Critical):** Spam rate >0.3%, bounce rate >5%, deliverability crisis -> PAUSE campaign, fix infrastructure
- **P1 (High):** Open rate <30%, reply rate <2%, connect rate <5% -> Fix before scaling
- **P2 (Medium):** Set rate low, show rate low, booking friction -> Optimize conversion points
- **P3 (Low):** Suboptimal timing, minor copy improvements -> Iterate over time

---

## Step 3: Deliver the Audit Report

Present a structured audit with:

### Campaign Health Summary
| Channel | Overall Status | Primary Bottleneck |
|---|---|---|
| Email | Red/Yellow/Green | [bottleneck] |
| Phone | Red/Yellow/Green | [bottleneck] |
| LinkedIn | Red/Yellow/Green | [bottleneck] |
| DM | Red/Yellow/Green | [bottleneck] |

### Prioritized Fix List
For each issue found, output:

1. **Issue:** What is wrong (with the metric)
2. **Root Cause:** Why it is happening
3. **Fix:** Specific action to take
4. **Skill to Use:** Which skill provides the detailed fix
5. **Priority:** P0/P1/P2/P3
6. **Expected Impact:** What improvement to expect

### Quick Wins (Implement This Week)
List the 2-3 changes that will have the biggest impact fastest.

### 30-Day Optimization Plan
If multiple issues exist, sequence the fixes:
- Week 1: Fix P0 issues (infrastructure, deliverability)
- Week 2: Fix P1 issues (copy, subject lines, openers)
- Week 3: Fix P2 issues (follow-up, booking, conversion)
- Week 4: Optimize P3 issues (timing, testing, minor improvements)

---

## Cross-References

Direct users to the appropriate skill for each fix:
- Deliverability issues -> `email-infrastructure` + `/deliverability-audit`
- Copy/subject line issues -> `cold-email-copy` + `/cold-email`
- First line issues -> `first-lines` + `/first-line`
- List quality issues -> `list-building` + `/build-list`
- Call framework issues -> `cold-calling` + `/cold-call-script`
- Follow-up issues -> `follow-up-sequences` + `/cold-email-sequence`
- Research/angle issues -> `prospect-research` + `/research-prospect`
- Mindset/fear issues -> `outbound-psychology`
