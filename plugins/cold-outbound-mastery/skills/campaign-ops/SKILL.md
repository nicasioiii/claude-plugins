---
name: campaign-ops
description: Manage, measure, and optimize cold outbound campaigns across all channels. Use when the user needs to track metrics, diagnose underperforming campaigns, build prospect lists, scale outbound operations, or orchestrate multi-channel outbound sequences. Covers KPIs, diagnostics, lead generation, list building, and campaign scaling. MANDATORY TRIGGERS: campaign metrics, reply rate, open rate, conversion rate, campaign performance, lead generation, list building, prospect list, outbound metrics, campaign optimization, scale outbound, multi-channel, campaign management, outbound KPIs, campaign diagnostics, deliverability, bounce rate, contact rate, DM conversion.
---

# Campaign Operations & Optimization

## Quick Start: Channel Benchmarks & KPI Targets

### Email Campaigns
- **Open Rate Target:** 80%
- **Reply Rate Target:** 15%
- **Meeting Book Rate:** 4-8% (per 100 emails)
- **Bounce Rate:** <8%
- **Volume per domain:** 50-100 emails/day (start conservative, scale gradually)

### Cold Calling / Phone Outreach
- **Contact Rate:** 46.5% (207 contacts from 445 calls)
- **Contact-to-Appointment Rate:** 22.2% (46 appointments from 207 contacts)
- **Overall Call-to-Meeting Rate:** ~10%
- **Calling hours:** 8 AM - 9 PM (Monday-Saturday only, not Sunday/holidays)
- **Target:** 3 qualified calls per day minimum

### Direct Messages (DMs)
- **Daily New Conversations:** 20-50
- **Daily Follow-ups:** 100+
- **Qualified Calls Target:** 3 per day
- **Cold DM Conversion to Calls:** 2-5%
- **Warm DM Conversion to Calls:** 10-20%
- **Platform recommendations:** Primary (Facebook/Instagram), Secondary (LinkedIn/Twitter)

---

## Campaign Diagnostics: Decision Trees

### Low Email Open Rates (Below 70%)
**Step 1: Identify the root cause**
- Low opens = deliverability issue OR subject line issue
- **Test:** Send to new test email accounts on Gmail, Yahoo, Outlook, iCloud, Zoho
- If emails land in SPAM/PROMO folders → Deliverability problem
- If emails land in Primary Inbox → Subject line problem

**Step 2: If deliverability issue**
- Domain authentication: Check SPF, DKIM, DMARC records
- Domain age/warmup: New domains need warmup (low volume first 30 days)
- Volume check: Sending too many emails/domain? Scale back to 50-100/day max
- List quality: High bounce rate = bad list quality. Validate with NeverBounce
- Frequency: Are you sending too often to same list? Space out by 3+ days

**Step 3: If subject line issue**
- A/B test subject lines weekly
- Benchmark: 80% open rate targets high-quality, personalized first lines
- Common failures: Generic subject, too salesy, too long (>50 chars)

### Low Reply Rates (Below 15%)
**Step 1: Identify the root cause**
- 80% of performance = email copy quality (not subject line, not opens)
- Low replies despite good opens = your offer/copy is weak
- No opens + no replies = deliverability + copy issues combined

**Step 2: Review email copy**
- **First line:** Is it a custom, personalized compliment? (NOT generic flattery)
  - Good: "Saw you speaking at SaaS Conf 2024 about product-market fit"
  - Bad: "Hi, your company looks great"
- **Case study:** One-sentence proof of results for similar prospect
  - Example: "Helped 12 ecommerce brands increase ROAS by 34% through [specific tactic]"
- **Call to Action:** Yes/no question requesting meeting
  - Good: "Quick question - are you open to exploring if we could add a similar result?"
  - Bad: "Would you like to schedule a call?" (too much ask for cold)

**Step 3: A/B test framework**
- Test 1 variable per week (first line OR case study OR CTA)
- Track replies per 100 emails sent
- Winning variation gets rolled into next campaign
- Never copy-paste winning emails; use as pattern reference only

### Low Conversion Rate (Below 4-8% meetings booked)
**Step 1: Are meetings happening?**
- If people reply but don't book → Follow-up issue
- If no one replies → Copy issue (see Low Reply Rates above)

**Step 2: Follow-up sequences**
- 70% of conversions happen in follow-ups, not initial email
- Recommended sequence: Day 0 (initial) → Day 3 (follow-up 1) → Day 5 (follow-up 2) → Day 8 (follow-up 3)
- Each follow-up should reference previous message, add new value, or shift angle
- Example: "Were you able to see the case study I sent?" (reference) OR provide different angle/proof

**Step 3: Meeting booking friction**
- Is calendar link obvious? Add direct calendar booking link in first follow-up
- Is timing objection blocking? ("Too busy now, maybe later") → Offer 2-3 specific dates
- Is price objection blocking? (See Cold Email Wizard objection handling in references)

---

## Core Frameworks

### The 3C Email Structure (Alex Berman)
1. **Compliment** - Personalized opening line (researched, specific to them)
2. **Case Study** - One-sentence proof of results for similar buyer
3. **Call to Action** - Yes/no question (no links, no CTA buttons)

### Product Marketing Context Check
BEFORE running any outbound campaign: Confirm you understand the product's positioning
- What problem does your product solve?
- Who is the ideal customer profile (ICP)?
- What specific metric/outcome do you deliver?
- What's the price point / what deal size are we targeting?
- Are we selling a new service or expanding existing relationships?

If you can't clearly articulate these, the campaign will underperform regardless of execution.

### A/B Testing Methodology
- **Test Cadence:** Weekly (every 50-100 emails sent)
- **One Variable:** Change only subject line, first line, case study, OR CTA (not multiple)
- **Sample Size:** Minimum 100 emails per variation to achieve statistical significance
- **Metric:** Track reply rate (replies / emails sent)
- **Winning Variation:** Gets 50%+ of next batch; losing variation retired
- **Pattern, Not Template:** Use winning framework to inform next test, don't copy-paste

### List Segmentation Rules (Chris Orzechowski)
Segmentation is how you maintain good deliverability and high engagement:
- **Segment by engagement:** Cold prospects (never interacted) vs. warm (engaged before)
- **Segment by source:** Different lists get different warmup timelines
- **Segment by job title/industry:** Tailor copy to each segment
- **Frequency:** Cold lists = lower frequency (2x/week max); warm lists = higher frequency
- **Test results:** Never send the same email to a list that previously rejected it

---

## Campaign Scaling Checklist

### Phase 1: Foundation (Weeks 1-2)
- [ ] Define ICP clearly (company size, industry, role, pain point)
- [ ] Build initial list of 100-200 leads manually (use Apollo.io or Seamless.ai)
- [ ] Write 3-5 variations of first lines (test different angles)
- [ ] Validate domain authentication (SPF, DKIM, DMARC records configured)
- [ ] Warm domain: Send 10-20 emails/day for first 3 days
- [ ] Track: opens, replies, meetings booked in simple spreadsheet or CRM

### Phase 2: Optimization (Weeks 3-4)
- [ ] A/B test subject lines and first lines (sample size: 100+ each)
- [ ] Identify winning first line angle
- [ ] Review follow-up sequences (expecting 70% of replies in follow-ups)
- [ ] Scale volume to 50-100 emails/day if opens > 70% and bounce < 8%
- [ ] Segment list: cold vs. warm; A/B test separately

### Phase 3: Scale (Weeks 5+)
- [ ] Add second domain (repeat Phase 1 warmup)
- [ ] Expand list: Apollo.io, Seamless.ai, UpLead, or manual LinkedIn research
- [ ] Implement multi-channel: Email → LinkedIn (day 3) → Phone (day 5)
- [ ] Hire SDR: For follow-ups, phone calls, and objection handling
- [ ] Track KPIs: Meetings booked per 1000 emails, cost per meeting, show-up rate

### Adding Domains for Scale
- First domain: 50-100 emails/day (sustainable long-term)
- Second domain: New domain = repeat warmup process (low volume first 14 days)
- Each domain adds 50-100 email capacity
- To scale to 500+ emails/day: Need 5-10 domains

### Hiring First SDR
- **First SDR focus:** Follow-ups and objection handling (phone/email)
- **KPI:** 3 qualified calls per day minimum
- **Training:** Provide 5-10 successful email threads as pattern reference
- **System:** Use shared CRM; SDR works from CRM, not email
- **Measurement:** Show-up rate to scheduled calls (target: 80%+)

---

## Quick Reference: When to Use This Skill

✓ Campaign is underperforming (low open rate, reply rate, meetings)
✓ Want to scale from 100 to 1000+ emails/day
✓ Need to add new channels (LinkedIn, phone, DMs) to email
✓ Building prospect list and need tool recommendations
✓ List quality issues (bounces, low engagement)
✓ Setting up KPI tracking and analytics
✓ Hiring SDR team for outbound
✓ Infrastructure setup (domains, email, CRM)
✓ Creating A/B testing plan for campaign
✓ Objection handling during follow-ups

See the references directory for:
- **metrics-benchmarks.md** - All metrics by channel
- **diagnostics.md** - Detailed troubleshooting trees
- **list-building.md** - Lead gen tools and processes
- **multi-channel.md** - Email + LinkedIn + Phone + DMs sequencing
- **scaling.md** - How to scale operations and hire
