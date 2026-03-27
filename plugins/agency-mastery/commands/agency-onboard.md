---
name: Agency Client Onboard
description: Generate a complete onboarding package for a new client including internal KO email, client welcome email, KO meeting agenda, deck outline, post-KO actions, communication setup, and first-30-days milestone plan. Activates client-onboarding and client-management.
---

# /agency-onboard

## Purpose
Generate a complete onboarding package for a newly signed client.

## Skills Required
Load in order:
- `skills/client-onboarding/SKILL.md` and `skills/client-onboarding/references/ref_client_onboarding.md`
- `skills/client-management/SKILL.md` (for ongoing cadence setup)

## Step-by-Step Execution

### Step 1: Gather Client Details
Ask the user:
1. **Client name:** Company or individual name
2. **Service signed:** What service will you deliver?
3. **Agreed fee:** Monthly retainer amount (and any performance components)
4. **Contract term:** Duration (month-to-month, 3 months, 6 months, etc.)
5. **Team members:** Who from your agency will work on this client? (names and roles)
6. **Account manager:** Who is the primary point of contact?
7. **Agency name:** Your agency name (for email templates)
8. **Client contact:** Name and email of the client-side decision maker
9. **Key deliverables promised:** What results did you commit to during the sales process?
10. **Start date:** When does the engagement begin? (or use today)

If the user does not have all details, proceed with what is available and mark gaps with [TBD].

### Step 2: Generate Internal KO Email
Use the template from ref_client_onboarding.md. Customize fully with:
- Client overview (name, social links, website, location)
- Partnership overview (service, signing date, fee, term, client email)
- Agreement mention
- Next steps with specific team member name assignments and deadlines

### Step 3: Generate Client Welcome Email
Use the template from ref_client_onboarding.md. Customize with:
- Welcome message referencing the SPECIFIC results committed to during the sales process
- Full KO meeting agenda preview (7 items: services clarity, team intros, communication, planning, strategy, deliverables needed, timelines)
- 3 proposed meeting dates/times (within 5 business days of signing)
- Mention of onboarding form (attached or linked)
- Invoice/deposit reminder if applicable

### Step 4: Generate Onboarding Form
List the recommended onboarding form fields from ref_client_onboarding.md, customized to the service type:
- Business information
- Goals and KPIs
- Brand assets
- Account access (specific to their service -- e.g., ad accounts for paid ads, CMS for web)
- Stakeholders and communication preferences
- Competitive landscape

### Step 5: Generate KO Meeting Agenda
**Internal KO meeting checklist** (team pre-meeting, 30-45 min):
Walk through the 10-item internal KO agenda from ref_client_onboarding.md.

**Client KO deck outline** (12 slides, customized):
1. Client name + kick-off date
2. Agenda
3. Core team (photos, names, titles) -- use provided team members
4. Partnership overview -- specific services and deliverables for THIS client
5. Client's role/obligations
6. Communication & approvals (Slack for daily, email for formal)
7. Communication cadence (daily/weekly/monthly -- from client-management cadence framework)
8. Initial strategy outline -- ask user for their high-level approach, or scaffold based on service type
9. Deliverables needed from client -- specific assets and access for THIS service
10. Timelines -- week-by-week milestones for first 30-60 days
11. Next steps (Slack setup, form completion, account access grants, first call date)
12. Closing

### Step 6: Post-KO Action Checklist
Generate customized checklist:
- [ ] Send follow-up email (meeting summary, actions, owners, deadlines, attached deck)
- [ ] Set up client Slack channel: #client-[name] and #client-[name]-internal
- [ ] Create client folder (subfolders: Assets, Deliverables, Reports, Meeting Notes, Strategy)
- [ ] Add weekly call to calendar + send invite
- [ ] Create client delivery board (Backlog | In Progress | Review | Client Approval | Done)
- [ ] Verify all account access granted
- [ ] Begin first deliverables per timeline
- [ ] Schedule internal check-in for end of week 1

### Step 7: Communication Setup
Specify for this client:
- **Daily channel:** Slack (SLA: 2-hour response during business hours)
- **Formal channel:** Email (SLA: 24-hour response)
- **Weekly call:** [Suggest day/time], recorded with permission
- **Monthly review:** End of each month, 60-minute strategy meeting + written report
- **Emergency protocol:** Define what constitutes an emergency and the 1-hour SLA

### Step 8: First-30-Days Milestone Plan
Generate date-specific milestones based on start date:
- **Day 0:** Contract signed, internal KO email sent
- **Day 1:** Welcome email + onboarding form sent
- **Days 2-3:** Form returned, assets/access gathered
- **Days 3-5:** Internal KO meeting
- **Days 5-7:** Client KO call, post-KO setup complete
- **Days 7-10:** First deliverables in progress
- **Days 10-14:** First weekly status update
- **Day 14:** Check-in on access gaps, alignment issues
- **Days 14-21:** First deliverables completed or major progress
- **Day 21:** Second weekly update, early metrics shared
- **Days 28-30:** First month review, feedback collection, month 2 goals set

End with: "The first 30 days set the tone for the entire relationship. Over-invest in this period."

### Step 9: Output
Compile everything into a structured, copy-ready document:
1. **Internal KO Email** (ready to send to team)
2. **Client Welcome Email** (ready to send to client)
3. **Onboarding Form Fields** (ready to build in Google Forms/Typeform)
4. **Internal KO Meeting Agenda** (for team pre-meeting)
5. **Client KO Deck Outline** (12 slides customized)
6. **Post-KO Action Checklist** (with owners assigned)
7. **Communication Setup** (channels, naming, SLAs, cadence)
8. **First-30-Days Milestone Plan** (with specific dates)
