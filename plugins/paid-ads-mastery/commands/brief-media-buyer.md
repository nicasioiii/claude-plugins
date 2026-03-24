---
name: Brief Media Buyer
description: Media buyer brief generator that asks campaign type, platform, budget, team structure. Outputs naming conventions, daily checklist, reporting template, escalation criteria.
---

# Media Buyer Brief & SOP Generator

## Step 1: Campaign Overview

**Campaign Name:** [_____________]
**Brand:** [_____________]
**Platform:** [Meta / Google / Both]
**Campaign Type:** [Cold / Warm / Hot / Testing / Scale]
**Daily Budget:** $[_____________]
**Start Date:** [Date]
**Target ROAS:** [__]x
**Target CPA:** $[__]

---

## Step 2: Team Structure

**Who is this brief for?**

A) **Solo Media Buyer** (You managing alone)
   → Simplified daily SOP, focus on critical metrics
   → Reporting: Weekly email to self/stakeholders

B) **Freelance Media Buyer** (External contractor)
   → Detailed SOP, clear escalation criteria
   → Reporting: Daily check-in + weekly deep dive

C) **In-House Team** (2-3 people)
   → Role clarity, handoff procedures
   → Reporting: Daily standup + weekly analysis

D) **Agency Team** (4+ people, specialized roles)
   → Granular workflows, approval chains
   → Reporting: Real-time dashboard + client reporting

→ Go to Step 3[Selected]

---

## Step 3a: Solo Media Buyer Brief

### Daily Routine (20 minutes)

**Morning (8am):**
1. Open Ads Manager / Google Ads Dashboard
2. Check spend vs. budget: Is today 1/7 of weekly budget?
3. Check ROAS: Compare yesterday to 7-day average (alert if ±0.3)
4. Check CPA: Alert if >target by 20%+
5. Pixel health check: Any tracking errors?
6. Top 5 creatives: Which are above account average?
7. Any campaigns showing red flags?
8. Logged: 5 minutes

**During Day (No actions needed)**
- Platform continues running
- Budget depleting normally

**Evening (5pm):**
1. Final spend check: Did we hit daily budget target?
2. Final ROAS check: Any surprises?
3. Prepare next day notes
4. Document any alerts in tracking sheet
5. Logged: 5 minutes

**Weekly (Friday):**
1. 30-minute deep review
2. Plot 4-week ROAS trend
3. Identify top 3 winning creatives
4. Identify 2-3 underperformers (kill candidates)
5. Plan next week's testing
6. Update stakeholder report

### Kill/Scale Decision Thresholds (Your Rules):

```
SCALE NOW: ROAS >1.5x target for 3+ days
  → Increase budget 10%
  → Repeat every 3-5 days if conditions met

PAUSE 48H: ROAS <1.3x breakeven for 2 days
  → Investigate issue
  → Refresh creative or audience
  → Relaunch at 50% budget

KILL: ROAS <breakeven for 3+ consecutive days
  → Stop campaign immediately
  → Reallocate budget to winners
  → Post-mortem: What failed?

CRITICAL: CPA >2x target OR Account Quality "Poor"
  → Pause all scaling immediately
  → Investigate before resuming
```

### Naming Convention (Campaign Level):

```
[BRAND]_[FUNNEL]_[TYPE]_[VARIABLE]_[OPTIMIZATION]_[DATE]

Example:
  BLS_COLD_VID_HOOK_ABO_03_2026

Rules:
- ALL CAPS
- Use underscores only
- Concise but specific
- Easy to scan in long lists
```

### Reporting Template (Weekly Email):

```
SUBJECT: Weekly Ad Report [Campaign Name] - [Week]

THIS WEEK'S RESULTS:
Spend: $[X] (Budget: $[Y] - On track? ✅/❌)
Revenue: $[X]
ROAS: [X]x (Target: [Y]x - Hit? ✅/❌)
Conversions: [X]
Average CPA: $[X] (Target: $[Y] - On track? ✅/❌)

TOP 3 CREATIVES:
1. [Creative ID] - ROAS [X]x, Spend $[X]
2. [Creative ID] - ROAS [X]x, Spend $[X]
3. [Creative ID] - ROAS [X]x, Spend $[X]

ACTION THIS WEEK:
✅ [Action taken]
✅ [Action taken]
❌ [Issue encountered]

NEXT WEEK PLAN:
→ [Test new creative]
→ [Scale campaign X by 10%]
→ [Monitor campaign Y for fatigue]
```

---

## Step 3b: Freelance Media Buyer Brief

### Responsibility Matrix

**Your Role:**
- Daily monitoring (15-20 min/day)
- Creative optimization decisions
- Audience expansion decisions
- Escalation of red flags to manager

**Manager/Client Role:**
- Final approval on major scaling (>20% daily increase)
- Final approval on budget allocation
- Creative brief and design
- Conversion tracking setup

### Daily Monitoring SOP

**Required: 7am, 1pm, 5pm Check-ins**

**7am Standup:**
```
MESSAGE: "[Campaign] - spend $X (on pace), ROAS X.Xx vs target Y.Xx"

Format: 1 message per campaign
Include: Status emoji (🟢 OK / 🟡 Warning / 🔴 Alert)
Action items: Any decisions needed today?
```

**1pm Mid-Day:**
```
Quick check if any campaigns underperforming
Alert if: ROAS dropped >0.2, CPA spiked >20%
```

**5pm Close-Out:**
```
Full metrics update
Document: Spend, ROAS, CPA, Top 3 creatives
Decisions made: Any pauses, scales, kills?
Tomorrow plan: Any changes scheduled?
```

### Escalation Criteria

**INFORM (via message, no action needed):**
- ROAS within ±0.2 of target
- CPA within ±10% of target
- Frequency stable <3.0x
- "Everything nominal"

**DISCUSS (requires conversation):**
- ROAS 0.2-0.3 below target for 2 days
- CPA inflating 10-20%
- Frequency 3.0-3.5x with stable ROAS
- Creative fatigue detected
- Need approval to test new audience

**ESCALATE IMMEDIATELY (decision needed ASAP):**
- ROAS >0.3 below target for 2+ days
- CPA >target by 30%+
- Campaign approaching/in Learning Phase unexpectedly
- Frequency >3.5x with declining conversions
- Account quality score dropped
- Pixel tracking failures
- Disapproved ads (Google)

### Weekly Reporting to Client/Manager

```
WEEKLY PERFORMANCE SUMMARY

📊 Results:
- Spend: $[X] (Budget: $[Y]) — [On pace / Behind / Ahead]
- Revenue: $[X]
- ROAS: [X]x (Target: [Y]x) — [Hit / Missed by X%]
- CPA: $[X] (Target: $[Y]) — [On target / X% above]
- Conversions: [X]

🎯 Top Performers:
1. [Campaign]: ROAS [X]x, Status: Scaling
2. [Campaign]: ROAS [X]x, Status: Holding
3. [Creative]: Hook rate [X]%, Status: Winner

⚠️ Areas of Concern:
1. [Campaign]: ROAS [X]x (below target) - Plan: [Action]
2. [Audience]: Frequency [X]x (monitoring) - Plan: [Action]

✅ Actions Completed This Week:
→ [Action and result]
→ [Action and result]
→ [Action and result]

📅 Next Week:
→ [Test new creative / audience]
→ [Scale campaign from $X to $Y]
→ [Monitor fatigue on campaign X]
→ [Need approval for: ...]
```

### Communication Preferences

**Response Time Expectations:**
- Red flags: Response within 2 hours
- Decisions: Response within 24 hours
- Non-urgent updates: Weekly review

**Communication Channel:**
- Urgent: [Slack / SMS / Phone call]
- Updates: [Daily message]
- Analysis: [Weekly email + Slack]

---

## Step 3c: In-House Team Brief (2-3 People)

### Role Division

**Media Buyer #1: Daily Operations**
- Morning monitoring (30 min)
- Creative kill/scale decisions
- Audience optimization
- Real-time troubleshooting
- Daily reporting (10 min)

**Media Buyer #2: Strategy & Analysis**
- Weekly deep dives (1 hour)
- Testing plan execution
- Creative strategy
- Scaling roadmap
- Client/stakeholder reporting

**Manager: Oversight**
- Weekly strategy review (30 min)
- Escalation approvals
- Budget allocation
- Team performance review

### Handoff Procedures

**Daily Handoff (Operations → Strategy):**

```
TIME: 4pm Friday
FORMAT: Slack message + spreadsheet

CONTENT:
- This week's results (spend, ROAS, CPA)
- Top 3 winning creatives (IDs + performance)
- Bottom 3 underperformers (kill candidates?)
- Red flags encountered (and resolution)
- Recommendations for next week

Next person: Reviews Friday evening, prepares Monday plan
```

**Weekly Strategy Meeting (Monday 10am):**

```
ATTENDEES: Both media buyers + manager
DURATION: 60 minutes

AGENDA:
1. Review: This week's performance vs. targets
2. Deep dive: ROAS trends, CPA inflation signals
3. Creative: Top performers, refresh plan
4. Testing: What to test this week
5. Scaling: Budget adjustments, new campaigns
6. Blockers: Any issues preventing optimization?
7. Next week: Clear action items assigned

OUTPUT: Shared document with assignments
```

### Naming Convention

**Campaign Level:**
```
[BRAND]_[FUNNEL]_[TYPE]_[VARIABLE]_[OPTIMIZATION]_[QUARTER]_[INITIALS]

Example: BLS_COLD_VID_HOOK_ABO_Q1_JK
```

**Ad Set Level:**
```
[CAMPAIGN]_[AUDIENCE]_[DEMOGRAPHIC]_[VARIATION]

Example: BLS_COLD_VID_HOOK_ABO_Q1_JK_Lookalike1%_25-34_V1
```

### Daily Check-in Template

**Operations Person Posts at 5pm:**
```
DAILY OPERATIONS REPORT [Date]

✅ Spend: $[X] (pace [Y]%) | ROAS: [X]x | CPA: $[X]
🔴 Red flags: [None / List]
👍 Winners: [Creative IDs]
💀 Kill candidates: [Creative IDs or campaigns]
📅 Tomorrow: [Any scheduled actions?]
```

### Weekly Reporting (To Stakeholders)

```
WEEKLY PERFORMANCE DASHBOARD [Week]

KPI SUMMARY:
| Metric | This Week | Target | Status |
|--------|-----------|--------|--------|
| Spend | $X | $Y | ✅/❌ |
| ROAS | X.Xx | Y.Yx | ✅/❌ |
| CPA | $X | $Y | ✅/❌ |
| ACOS | X% | Y% | ✅/❌ |

TOP 3 PERFORMERS:
1. [Campaign] - ROAS [X]x - [Action: Continue scaling]
2. [Campaign] - ROAS [X]x - [Action: Monitor fatigue]
3. [Campaign] - ROAS [X]x - [Action: Test variations]

ISSUES & RESOLUTIONS:
[Issue] - Status: [Resolved / In Progress]
[Issue] - Status: [Resolved / In Progress]

PLAN NEXT WEEK:
→ Test [X new creatives]
→ Scale [Campaign] from $X to $Y
→ Monitor [Campaign] for fatigue
→ Launch [New campaign type]
```

---

## Step 3d: Agency Team Brief (4+ People)

### Full Role Structure

**Account Manager:**
- Client relationship & reporting
- Budget approval & allocation decisions
- Strategic direction

**Lead Media Buyer:**
- Daily operations oversight
- Team supervision
- Major optimization decisions

**Media Buyers (2-3):**
- Campaign management (assign 2-3 per person)
- Daily monitoring & optimizations
- Creative testing

**Creative/Strategist:**
- Creative brief development
- Testing strategy
- Trend analysis

### Workflow & Approvals

```
CAMPAIGN SETUP FLOW:
Creative Strategist → Brief Media Buyer → Account Manager → Launch
(Approval at each step)

OPTIMIZATION FLOW (Daily):
Media Buyer → Lead Media Buyer (if >10% budget change) → execute

SCALING APPROVAL FLOW:
Media Buyer → Lead Media Buyer → Account Manager (if >20% daily increase)
```

### Team Daily Standup (9:30am)

```
DURATION: 15 minutes
ATTENDEES: All media buyers + Lead + Account Manager

FORMAT: Each person covers their campaigns:
"Campaign X: $[Y] spend (on pace), ROAS [Z]x, status [OK / WARNING / ALERT]"

Lead highlights: Top performers, red flags, escalations needed
Account Manager: Any client-side decisions blocking optimization?

OUTPUT: Shared document updated for client visibility
```

### Campaign Assignment Template

```
CAMPAIGN: [Campaign Name]
ASSIGNED TO: [Media Buyer Name]
DAILY BUDGET: $[X]
REPORTING: [Weekly to Lead + Client]

OWNER RESPONSIBILITIES:
✓ Daily 7am, 1pm, 5pm monitoring
✓ Kill/scale decisions within authority
✓ Escalate red flags to Lead
✓ Weekly performance summary
✓ Creative testing recommendations

AUTHORITY LIMITS:
✓ Can increase budget up to 10%/day without approval
✗ >10% increase requires Lead approval
✗ Pausing campaign requires Lead + Account Manager approval
✓ Test approval under $X/day goes to Lead only
```

### Client Reporting Dashboard (Weekly/Daily)

```
REAL-TIME DASHBOARD (Updated daily at 6pm):
- Campaign performance (ROAS, CPA, spend)
- Top 3 creatives this week
- Red flags with status
- Projected month-end performance

WEEKLY FORMAL REPORT (Monday morning):
- Executive summary (1 paragraph)
- Performance vs. targets (table)
- Top performers (with insights why)
- Underperformers (with action plan)
- Testing results & recommendations
- Next week plan & any approvals needed
```

---

## Universal Escalation Criteria (All Team Sizes)

### Immediate Escalation (Stop, investigate, decide before action):

- **Pixel/Tracking Issue:** Campaign data unreliable
- **Account Quality:** Dropped to "Fair" or "Poor"
- **Disapproved Ads:** Ad policy violation blocking spend
- **ROAS <Breakeven:** Losing money consistently
- **CPA >2x Target:** Cost inflation critical
- **Frequency >4.0x:** Audience fatigue severe
- **Learning Phase Re-entry:** Unexpected campaign reset

### Weekly Escalation (Monitor, plan response, implement):

- **ROAS 0.2-0.3 Below Target:** Creative fatigue emerging
- **CPA +10-20% Above Target:** Cost inflation trending
- **Frequency Trending Up:** Audience getting saturated
- **New Test Underperforming:** May need refresh
- **Budget Pacing Off:** Ahead/behind pace significantly

### Monthly Escalation (Strategic review, not immediate action):

- **Creative Set Stale:** Running >30 days, need refresh
- **Audience Fatigue Signs:** Visible after 4+ weeks
- **Market Changes:** Seasonal impact, competition shifts
- **Budget Reallocation:** Move budget between campaigns
- **Platform Changes:** New features, policy updates

---

## Final Sign-Off

**Media Buyer [Name] Acknowledges:**
- [ ] I understand the daily monitoring requirements
- [ ] I understand the kill/scale decision thresholds
- [ ] I understand the escalation criteria
- [ ] I will follow the naming conventions
- [ ] I will submit weekly reporting on schedule

**Signed:** _________________ **Date:** _____________

**Manager/Client Acknowledges:**
- [ ] I understand the reporting schedule
- [ ] I understand my approval authority boundaries
- [ ] I am available for escalation decisions
- [ ] I have provided conversion tracking setup

**Signed:** _________________ **Date:** _____________

---

## Next Steps

- **Need testing guidance?** → `/test-plan` command
- **Need scaling roadmap?** → `/scale-plan` command
- **Need campaign audit?** → `/audit-campaign` command
- **Need daily optimization guidance?** → `/optimize-campaigns` skill
