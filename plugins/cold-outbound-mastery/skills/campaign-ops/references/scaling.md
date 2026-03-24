# Scaling Cold Outbound Operations: Infrastructure, Domains, Volume, and Hiring

## Scaling Phases Overview

### Phase 1: Foundation (Weeks 1-2) - Single Domain, Single SDR
- Volume: 50-100 emails/day
- Expected meetings: 2-4/week
- Setup: Basic domain, email provider, CRM
- Team: 1 founder or SDR

### Phase 2: Optimization (Weeks 3-4) - Single Domain, Refined Messaging
- Volume: 100-150 emails/day
- Expected meetings: 5-10/week
- Setup: Same domain, improved copy from A/B testing
- Team: 1 SDR + founder managing copy

### Phase 3: Domain Scale (Weeks 5-12) - Multiple Domains
- Volume: 250-500 emails/day
- Expected meetings: 15-30/week
- Setup: 3-5 new domains, distributed volume
- Team: 1-2 SDRs managing volume

### Phase 4: Team Scale (Weeks 13+) - Multi-Domain, Multi-SDR
- Volume: 500-1000+ emails/day
- Expected meetings: 30-60/week
- Setup: 5-10+ domains, specialized team
- Team: 3-10 SDRs with specialized roles

### Phase 5: Operational Scale (3+ months) - Systems and Authority
- Volume: 1000-5000+ emails/day
- Expected meetings: 60-200+/week
- Setup: Automated workflows, content, warm audiences
- Team: 10-50+ team members with content, DM, phone specialists

---

## Phase 1: Foundation Setup (Weeks 1-2)

### Email Infrastructure

**Choosing Email Platform:**

| Platform | Cost | Best For | Email Limit |
|----------|------|----------|------------|
| **MailShake** | $39-149/mo | SMB cold email, tracking | 50-200/day |
| **Lemlist** | $29-99/mo | Personalization + tracking | 100-500/day |
| **Clay + SendGrid** | $99/mo | Advanced personalization | 500-5000/day |
| **HubSpot** | $50-3200/mo | Enterprise, full CRM | Unlimited (usage-based) |
| **Outbound.io** | $99/mo | Calling + email combined | 200-1000/day |

**Recommendation for Phase 1:** MailShake ($39/mo) or Lemlist ($29/mo)
- Affordable
- Built for cold email tracking
- Can send 100-200/day per domain

### Domain Setup

**Initial Domain:**
1. Register domain (GoDaddy, Namecheap)
2. Add to email provider (MailShake/Lemlist)
3. Configure DNS records:
   - SPF record (mail provider provides template)
   - DKIM record (enable in provider settings)
   - DMARC policy (optional, but recommended)
4. Wait 48 hours for DNS propagation
5. Send test emails to Gmail, Yahoo, Outlook accounts
6. Verify emails land in Primary Inbox (not Spam)

**Domain Warmup Schedule (14 days):**
- Days 1-3: 10-20 emails/day (send to warm contacts, clients)
- Days 4-7: 30-50 emails/day
- Days 8-11: 50-100 emails/day
- Days 12-14: 100-150 emails/day
- After 14 days: Can send 150-200 emails/day (sustainable long-term)

### CRM Setup

**Recommendation:** HubSpot Free or Pipedrive Free
- Free tier sufficient for 100s of contacts
- Track opens, replies, meetings
- Basic automation for follow-ups
- Custom fields for segmentation

**Essential fields to track:**
- Contact name, email, company
- Date email sent
- Date email opened (auto-tracked)
- Date replied (auto-tracked)
- Reply content (paste in notes)
- Follow-up email dates
- Meeting booked (yes/no, date/time)
- Meeting attended (yes/no)
- Deal value / outcome

### Initial Campaign (100 leads)

**Week 1:**
1. Build list of 100 leads (Apollo, LinkedIn, manual)
2. Validate in NeverBounce (expect to keep 85-90)
3. Write 5 variations of first line
4. Set up CRM with 100 leads
5. Begin domain warmup (send to 20 warm contacts first)

**Week 2:**
1. Send email #1 to 100 cold leads (across 14-day warmup period)
2. Track opens/replies in CRM
3. A/B test first lines (25 people each variation)
4. Identify winning first line (highest open rate)
5. Monitor replies, respond to everyone
6. Send email #2 follow-ups (Day 3-5)
7. Schedule meetings in CRM

**Expected Week 2 Results:**
- Open rate: 70-80% (if domain warmed, good first line)
- Reply rate: 12-15%
- Meetings booked: 3-5 (from 100 emails)

---

## Phase 2: Optimization (Weeks 3-4)

### A/B Testing System

**Goal:** Identify which first line angle converts best

**Test Structure:**
- Variation A: 25 people (e.g., "recent achievement" angle)
- Variation B: 25 people (e.g., "company signal" angle)
- Variation C: 25 people (e.g., "specific problem" angle)
- Wait 5 days for responses
- Measure: Reply rate per variation
- Winner: The variation with highest reply rate (target 15%+)

**Implementation:**
1. Create variation in email subject line OR first line
2. Manual send to each group (or use tool's A/B feature)
3. Track replies in CRM
4. Calculate reply rate: (Replies / 25) × 100
5. Roll winning variation into next batch

**Next Test (Week 4):**
- Keep winning first line
- Test case study variations (2-3 different proof points)
- Test CTA variations (different ask, different framing)
- Same structure: 25 people per variation

### Segmentation Introduction

**Segment by Job Title:**
- CMO / VP Marketing (different copy)
- Marketing Manager (different copy)
- Demand Gen Manager (different copy)

**Why:** Message resonates better when role-specific

**Example CMO vs. Manager:**
- **CMO copy:** "Helping [company type] improve customer acquisition efficiency + unit economics" (board-level metrics)
- **Manager copy:** "Helping [company type] close more deals from same outreach effort" (tactical execution)

**Implementation:**
1. Segment 100 leads by title in CRM
2. Write version A for CMOs (25 people)
3. Write version B for Managers (75 people)
4. Track reply rate per segment
5. Best-converting segment gets doubled down

### Scale to 150-200 emails/day

**If metrics are good (open 75%+, reply 15%+):**
1. Increase daily volume to 100-150
2. Continue domain warmup schedule
3. Implement follow-up sequence:
   - Day 0: Initial email
   - Day 3: Follow-up 1
   - Day 5: Follow-up 2
   - Day 8: Follow-up 3
4. Measure: meetings per 100 emails (target: 4-8)

**If metrics are struggling (open <70%, reply <10%):**
1. Don't scale yet
2. Go back to Phase 1 diagnostics
3. Fix first line OR subject line
4. Re-test with smaller batch

---

## Phase 3: Domain Scale (Weeks 5-12)

### Why Multiple Domains?

**Email delivery limits per domain:**
- Single domain sustainable: 150-200 emails/day (long-term)
- To reach 500+ emails/day: Need 3-5 domains
- To reach 1000+ emails/day: Need 5-10 domains

**Each new domain = capacity for 150-200 emails/day**

### Adding New Domains (One at a time)

**Timeline for adding domain #2:**
- Week 1: Complete 14-day warmup on domain #1 (reach 150-200/day)
- Week 2-3: Domain #1 running at 150-200/day
- Week 4: Launch domain #2 (start warmup)
- Week 5: Domain #1 at 150-200/day + Domain #2 at 50-100/day = 200-300 total
- Week 6+: Domain #2 reaches 150-200/day = 300-400 total

**Setup for Domain #2:**
1. Register new domain (similar to original domain #1)
2. Add to email provider
3. Configure SPF, DKIM, DMARC (same process)
4. Same warmup schedule (14 days, gradual ramp)
5. Use slightly different email variation (not identical to domain #1)
6. Track separately in CRM

### Managing Multiple Domains in CRM

**Track per domain:**
- Which domain each email sent from (add field in CRM)
- Open rate per domain (should be similar)
- Reply rate per domain
- Bounce rate per domain

**If one domain underperforming:**
- Check bounce rate (if >8%: list quality issue)
- Check open rate (if <70%: deliverability issue)
- Reduce volume, add back list quality, retry

**Scaling from 3-5 domains:**
- Domain 1: 150-200 emails/day
- Domain 2: 150-200 emails/day
- Domain 3: 150-200 emails/day
- etc.
- **Total: 450-1000 emails/day with 3-5 domains**

### Hiring First SDR

**When to hire:** When you have 150+ emails/day and need to handle:
- Follow-ups
- Phone calls
- Objection handling
- Meeting scheduling

**Role: "Outbound SDR" or "Sales Development Representative"**

**Responsibilities:**
- Follow-up emails (days 3, 5, 8 of sequence)
- Phone calls to prospects
- Respond to objections
- Schedule meetings in calendar
- Track activity in CRM

**Not responsible (yet):**
- Copy writing
- List building
- Strategy

**KPI:** 3-5 meetings booked per day

**Training:**
1. Show 5-10 best email sequences (study patterns, not copy)
2. Show 3-5 best phone scripts (understand framework)
3. Show successful follow-up examples
4. Shadow you for 3-5 days (watch how you follow up)
5. Start with 20-30 prospects first week (low volume to build skill)
6. Gradually increase to 100+ prospects by week 4

**Cost:** $2,500-4,000/month (contractor or junior hire)

**Expected ROI:**
- SDR books 3-5 meetings/day = 60-100 meetings/month
- If 20% close to customer = 12-20 customers/month
- If $5K/customer = $60-100K/month revenue
- Cost: $2,500-4,000/month = ROI 15-40x

---

## Phase 4: Team Scale (Weeks 13+)

### Scaling to 2-3 SDRs + Specialized Roles

**Organization at this phase:**

```
Founder (Strategy, Copy, Positioning)
├─ "Copy Lead" (or Founder)
│  └─ Owns email variations, A/B testing
├─ "Phone Lead" SDR
│  └─ Owns phone calls, voicemail drops
├─ "Follow-up Lead" SDR
│  └─ Owns follow-up sequences, objection handling
└─ "List Manager" (or junior)
   └─ Owns list building, validation, segmentation
```

### Copy Specialist

**Responsibility:**
- Write initial email variations
- Run A/B tests (first line, case study, CTA)
- Document winning patterns
- Train other SDRs on best-converting angles

**KPI:** Reply rate across all emails (target: 15%+)

**Training needed:**
- 3C framework (Compliment, Case Study, CTA)
- Understanding target audience per segment
- A/B testing methodology
- Pattern recognition from past wins

### Phone/Calling Lead

**Responsibility:**
- Own all phone calls from initial list
- Record voicemails
- Handle objections on phone
- Book meetings

**KPI:** Meetings booked from phone outreach (target: 5-10/day)

**Required skills:**
- Cold calling script (Sean Longden framework)
- Objection handling ("what's the cost?", "too busy", etc.)
- Qualification framework (BANT: Budget, Authority, Need, Timeline)
- Closing technique (calendar booking)

**Phone technology:**
- RingCentral or Outbound.io (call tracking + recording)
- Voicemail app (HubSpot, Close)

### Follow-up Lead

**Responsibility:**
- Send email follow-ups (day 3, 5, 8, 12 of sequences)
- Monitor replies
- Schedule booked meetings
- Manage CRM data integrity

**KPI:** Meeting bookings from follow-up sequences (target: 5-10/day)

**Not responsible for:**
- Deciding on new angles (that's the copy lead)
- Phone follow-ups (that's the phone lead)

### List Manager / Researcher

**Responsibility:**
- Build prospect lists (Apollo, UpLead, LinkedIn)
- Validate lists in NeverBounce
- Segment lists by role, company size, industry
- Clean and maintain list hygiene
- Add new signals (funding, hiring, product changes)

**KPI:** Valid lead count provided to team (target: 500+/week)

**Skills needed:**
- Apollo.io / LinkedIn navigation
- NeverBounce validation workflow
- Data quality assessment
- Segmentation logic

### Ops/CRM Manager (if team reaches 5+)

**Responsibility:**
- Maintain CRM hygiene
- Generate weekly/monthly reports
- Track KPIs per SDR
- Identify bottlenecks
- Manage domain health and email provider

**KPI:** Data accuracy, report turnaround time

---

## Volume Scaling Economics

### Cost Per Meeting Booked (by phase)

**Phase 1 (Founder only):**
- Cost: $0 + email tool ($39/mo)
- Meetings: 2-4/week
- Cost per meeting: $5-10/week tool cost

**Phase 2 (Refined, single domain):**
- Cost: Email tool ($39/mo)
- Meetings: 5-10/week
- Cost per meeting: $4-8/week

**Phase 3 (Multi-domain, no SDR yet):**
- Cost: 3 email tools ($120/mo) + domains ($15/mo)
- Meetings: 15-30/week
- Cost per meeting: $4-9/week

**Phase 4 (Multi-domain, 2-3 SDRs):**
- Cost: Email tools ($150/mo) + SDRs ($7,500/mo) + tools ($500/mo)
- Meetings: 60-120/week
- Cost per meeting: $60-70 per meeting

**Phase 5 (Enterprise scale, 10+ team):**
- Cost: All tools + 10 people ($50,000+/mo)
- Meetings: 200-500/week
- Cost per meeting: $100-250 per meeting

**Key insight:** Cost per meeting increases as you scale (fixed cost spread). But profit per customer stays same, so unit economics improve overall.

---

## Infrastructure for Scale

### Email Provider for 1000+ emails/day

**MailShake/Lemlist limitations:**
- Max ~500 emails/day per account
- Need separate accounts/providers for scale

**Enterprise options:**
- **Clay + SendGrid:** Unlimited volume, API-based
- **HubSpot Enterprise:** All-in-one CRM + email
- **Outbound.io:** Phone + email platform
- **Klaviyo:** More expensive, but unlimited

**Setup for 1000+ emails/day:**
1. 5 separate email accounts (MailShake/Lemlist): 500 emails/day each
2. OR: Clay + SendGrid (all in one): Unlimited
3. Each domain gets separate account (domain #1 in account A, domain #2 in account B, etc.)
4. CRM integrates with all (HubSpot, Salesforce)

### Domain Infrastructure

**For 1000+ emails/day, need:**
- 5-10 domains (each sending 100-200 emails/day)
- Shared mailbox or dedicated email per domain
- Email provider for each domain
- Separate sender reputation for each domain
- Monthly cost: $10-20 per domain + email tool = $50-200/month

**Domain naming convention:**
- Domain 1: outreach.yourcompany.com
- Domain 2: sales.yourcompany.com
- Domain 3: contact.yourcompany.com
- etc.

**Avoid:** Using random unrelated domains (looks spammy)

### CRM for 1000+ contacts

**Requirements:**
- Store 1000+ contacts
- Track email sends/opens/replies
- Automation for follow-up sequences
- Reporting/analytics

**Options:**
- **HubSpot:** Industry standard, $50-300/mo
- **Salesforce:** Enterprise, $100-300/mo per user
- **Pipedrive:** Affordable, $15-99/mo
- **Outbound.io:** Email + phone + CRM, $99-300/mo

**Recommendation:** HubSpot for teams 2-10, Salesforce for teams 10+

---

## Hiring Playbook

### SDR Job Description Template

**Title:** Sales Development Representative (Cold Outreach)

**Responsibilities:**
- Send 100-200 cold emails per day following templates
- Follow up via email, LinkedIn, phone per sequence
- Book 3-5 qualified meetings per day
- Track all activity in CRM (HubSpot/Pipedrive)
- Handle common objections on phone/email
- Manage calendar and meeting confirmations

**Requirements:**
- Experience: 6+ months in sales or BDR role (or demonstrated cold email success)
- Skills: Excellent written communication, phone confidence, persistence
- Tools: Proficient in CRM, email, spreadsheets
- Traits: Coachable, data-driven, resilient to rejection

**Compensation:**
- Base: $2,000-3,500/month (or $12-21/hour)
- Commission: $50-200 per meeting booked (or 5% of closed deals)
- Bonus: Quarterly bonus for hitting KPIs (e.g., 60+ meetings/month)

**Expected Performance (after 30 days training):**
- Meetings booked: 3+ per day (60+ per month)
- Reply rate: 15%+ on owned emails
- Objection handling: Can handle 5+ common objections

### Where to Hire

**Best sources:**
1. **Upwork** - Quick hire, contractor model, easy to test
2. **LinkedIn Recruiter** - Full-time hires, passive candidates
3. **Your existing contacts** - Referrals are usually best
4. **Sales communities** - Linkedin Sales Development group, Reddit
5. **Agencies** - Pre-trained SDRs, higher cost ($4-6K/mo)

### Training & Onboarding

**Week 1: Pattern Recognition**
- Provide 10-15 successful email sequences
- Have them write down patterns they notice
- Review their observations (Compliment, Case Study, CTA)
- Have them draft 3 first line variations

**Week 2: Shadow & Do**
- Shadow you for phone calls (2-3 hours)
- Review objection handling (provide scripts)
- Have them practice with 20 warm leads (low pressure)
- Review their results together

**Week 3: Independent Action**
- Assign 50-100 cold leads
- Have them send initial emails daily
- Review copy quality (is it following pattern?)
- Track meeting bookings (should be 1-3 by week 3)

**Week 4+: Scale**
- Assign 200-300 leads
- Implement follow-up sequence
- Add phone calls to role
- Scale to 500+ leads by week 6

### Measuring SDR Performance

**Primary KPI: Meetings Booked**
- Daily: 3-5 meetings (15-25 per week)
- Monthly: 60-100 meetings

**Secondary KPIs:**
- Reply rate: 15%+ on emails they send
- Phone contact rate: 40%+ of calls reach someone
- Show-up rate: 75%+ of booked meetings attend

**Bonus KPIs:**
- Customer conversion: 10-20% of meetings close
- Customer value: Average deal size from their bookings
- Retention: Meeting attendees become customers who renew

---

## Cost Structure at Each Phase

### Phase 1 (Weeks 1-2)
- Email tool: $39/month
- Domain: $10/month
- CRM: $0 (free tier) or $50/month
- **Total: $49-100/month**
- Volume: 100 emails/week
- Cost per email: $0.11-0.23

### Phase 2 (Weeks 3-4)
- Email tool: $39/month
- Domain: $10/month
- CRM: $50/month
- **Total: $100/month**
- Volume: 600 emails/week
- Cost per email: $0.03

### Phase 3 (Weeks 5-12)
- Email tools (3): $120/month
- Domains (3): $30/month
- CRM: $50/month
- Validation tools: $50/month
- **Total: $250/month**
- Volume: 2000 emails/week (without SDR)
- Cost per email: $0.03

### Phase 4 (Weeks 13+, 2-3 SDRs)
- Email tools: $150/month
- Domains (5): $50/month
- CRM: $100/month
- Validation tools: $50/month
- SDRs (2): $5,000/month
- Phone/calling: $100/month
- **Total: $5,450/month**
- Volume: 4000+ emails/week
- Cost per email: $0.03
- Cost per meeting: $60-80

### Phase 5 (Enterprise, 10+ team)
- All infrastructure: $500/month
- Team (10 people): $50,000/month
- Tools and management: $2,000/month
- **Total: $52,500+/month**
- Volume: 20,000+ emails/week
- Cost per email: $0.05
- Cost per meeting: $100-150

---

## Scaling Checklist

### Before going from Phase 1 → Phase 2
- [ ] Single domain reaching 150-200 emails/day
- [ ] Open rate: 75%+ (indicating healthy domain)
- [ ] Reply rate: 15%+ (indicating good copy)
- [ ] Meeting book rate: 4-8% (indicating effective sequences)
- [ ] Have documented winning first line angle
- [ ] CRM is tracking all data accurately
- [ ] Ready to scale volume and test variations

### Before going from Phase 2 → Phase 3
- [ ] Single domain sustainability verified (no bounce rate creep)
- [ ] Reply rates stable or improving (messaging validated)
- [ ] A/B testing system established
- [ ] Can identify winning variations
- [ ] Ready to add second domain
- [ ] Have capital for new domain setup ($50-100)

### Before going from Phase 3 → Phase 4
- [ ] 3+ domains running at 150-200 emails/day each
- [ ] Multi-domain metrics consistent with single domain
- [ ] Have validated first line angles + case studies
- [ ] Ready to hire first SDR
- [ ] Have capital for SDR ($2,500-5,000/month)
- [ ] Have documented processes for SDR to follow
- [ ] Have training materials ready (example sequences)

### Before going from Phase 4 → Phase 5
- [ ] 2-3 SDRs producing 60+ meetings/month each
- [ ] Operations running smoothly without founder
- [ ] Processes documented in playbooks
- [ ] Ready to hire specialized roles (copy lead, phone lead)
- [ ] Have capital for team ($8,000-15,000/month)
- [ ] Have infrastructure for 1000+ emails/day

---

## Troubleshooting Scaling Issues

### Problem: Bounce rate increased when scaling

**Likely cause:** List quality degraded as you scaled faster

**Solution:**
1. Check where new leads are coming from
2. Validate new batch in NeverBounce
3. Compare bounce rate per list source
4. Pause sourcing from worst source
5. Add validation step to all new lists

### Problem: Open rates dropped on domain #2

**Likely cause:** Didn't complete full warmup, or sent too much too fast

**Solution:**
1. Reduce volume on domain #2 back to 50/day
2. Extend warmup schedule (add extra week)
3. Check if emails landing in spam (test with new accounts)
4. If spam folder: Add 7 more days low-volume before increasing
5. If primary inbox: Can increase volume more aggressively

### Problem: New SDR not booking meetings

**Likely cause:** Training incomplete or SDR not implementing patterns

**Solution:**
1. Have them show you 10 emails they've sent (are they following 3C structure?)
2. Listen to 2-3 of their phone calls (are they asking qualifying questions?)
3. Review objection handling (are they handling correctly?)
4. Provide 1-on-1 coaching on weaknesses
5. Extend training period if needed (4-6 weeks vs. 4)
6. Consider if SDR is right fit for role

### Problem: Costs too high, need to reduce

**Options:**
1. Consolidate email providers (Clay + SendGrid vs. multiple MailShake)
2. Reduce domain count (fewer domains at higher volume each)
3. Reduce list sourcing cost (manual research vs. Apollo)
4. Hire contractors vs. full-time (lower fixed cost)
5. Focus on highest-ROI audience segment (lower volume but better conversion)
