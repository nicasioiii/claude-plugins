---
name: Tool Stack Reference
description: >
  Consolidated tool reference across all 8 sources. Categories: sending,
  warmup, lead gen, verification, calling, CRM, LinkedIn automation,
  enrichment, testing. Costs and best-for-whom. Sources: All 8 extraction
  files consolidated.
---

# Tool Stack Reference

## EMAIL SENDING TOOLS

| Tool | Cost | Best For | Source |
|---|---|---|---|
| **Maildoso** | Varies (includes domains) | Purpose-built for cold email; auto DNS setup, free domain purchase, up to 4 mailboxes/domain | Acquisition X |
| **Lemlist** | ~$59-99/month | Cold email with personalization features, custom tracking domains, A/B testing | Alex Berman |
| **Mailshake** | ~$59/month | Simple cold email campaigns, LinkedIn integration | Alex Berman |
| **Sales engagement platforms** (generic) | Varies | Look for: domain rotation, auto warmup, delayed sending, A/B testing, one-click unsubscribe | 30MPC |

### Maildoso Advantages (Acquisition X)
- Handles all DNS configuration automatically (SPF, DKIM, DMARC, MX)
- Free domain purchase and registration
- Up to 4 mailboxes per domain (6 domains = 24 mailboxes)
- Export credentials as CSV for easy upload to cold email tools
- Built specifically for cold outbound (unlike Google/Outlook)

### Sales Engagement Platform Requirements (30MPC)
- Rotating email domains
- Automated email warmup
- Delayed email sending (spread throughout day, not 500 at once)
- A/B testing with synonymous word substitution
- One-click unsubscribe (Google/Yahoo requirement, must process within 2 days)

---

## EMAIL WARMUP TOOLS

| Tool | Cost | Notes | Source |
|---|---|---|---|
| **TrulyInbox** | Free (unlimited warmup) | Fully automated: sends, marks important, stars, scrolls, replies | Acquisition X |
| **WarmupInbox** | ~$9/month/inbox | Reliable; start at 15/day, increase by 1/day | Alex Berman |
| **Lemwarm** | Included with Lemlist | Convenient if already using Lemlist | Alex Berman |

### Warmup Configuration (Acquisition X Schedule)

| Phase | Emails/Day/Account | Target Reply Rate | Duration |
|---|---|---|---|
| Start | 4-8 | 30% | Weeks 1-2 |
| Ramp | 20-30 | 40-50% | Weeks 2-4 |
| Maximum | 50 | 60% (max) | Ongoing |

### Warmup Rules
- Randomize number of warmup emails daily (appear natural)
- Never start cold campaigns without warming up first
- Without warmup: 3-6 months to build reputation; with warmup: 2-3 weeks
- Keep warmup running FOREVER alongside cold campaigns
- After warmup, drop to 10-20 warmup emails/day alongside cold outreach

---

## LEAD GENERATION TOOLS

| Tool | Cost | Best For | Source |
|---|---|---|---|
| **UpLead** | ~$99/month | B2B contact data with high accuracy | Alex Berman |
| **Apollo.io** | ~$99/month (includes 50 mobiles) | Email + phone data, built-in sequencing | Longden |
| **Sales Navigator** | ~$99/month | LinkedIn prospecting, Boolean search, trigger detection | LinkedIn Client Lab |
| **Seamless.ai** | ~$147/month | Phone number enrichment, contact data | Longden |
| **Inflact** | Varies | Instagram lead sourcing by follower count/engagement | Jason C Fox |
| **RB2B** | Varies | Anonymous website visitor identification (name + LinkedIn of visitors) | Acquisition X |
| **Buska.io** | Varies | Reddit/social keyword monitoring for intent signals | Acquisition X |
| **ContactEcom / CleanLeads** | Varies | E-commerce lead sourcing | Acquisition X |

### Sales Navigator Search Setup (Ty Frankel)
1. Company headcount (e.g., 1-50 employees)
2. Job titles (Founder, Co-Founder, CEO)
3. Geography (e.g., US only)
4. Profile language: English
5. **Critical:** "Posted on LinkedIn" filter (removes inactive profiles)
6. Connection degree: 2nd and 3rd
7. Optional: Years in current company (filter rigid thinkers with 5+ years)

### Boolean Search for Refinement
- Use "NOT" to exclude irrelevant profiles
- Multi-word exclusions: NOT "affiliate marketing"
- Exclude irrelevant job titles one by one
- Save refined searches for reuse

---

## EMAIL VERIFICATION TOOLS

| Tool | Cost | Best For | Source |
|---|---|---|---|
| **NeverBounce** | Pay per verification | Email list cleaning, bounce prevention | Chris Orzechowski |
| **Built-in verification** (Apollo, etc.) | Included | First-pass verification on sourced contacts | Multiple |

### Verification Rules
- Verify ALL emails before sending (non-negotiable)
- Target <2% bounce rate (optimal), <5% (acceptable)
- Re-verify lists older than 30 days
- Maintain DNC (Do Not Contact) list for unsubscribers

---

## COLD CALLING TOOLS

| Tool | Cost | Best For | Source |
|---|---|---|---|
| **Twilio + Go High Level** | Twilio: <$0.01/min; GHL: $97-297/month | Power dialer, SMS, ringless voicemail, local area codes | Longden |
| **RingCentral** | Varies | Alternative to Twilio stack | Longden |
| **Vonage** | Varies | Alternative calling platform | Longden |

### Twilio + GHL Power Dialer Setup
1. Create campaign with Manual Call + Voicemail events
2. Upload pre-recorded voicemail MP3
3. Configure: "Allow multiple" OFF, "Stop on response" ON
4. Add contacts via tags
5. Click Start -- auto-dials sequentially

### Local Area Code Advantage
Twilio provides local area code numbers (appear to call from same area as prospect). Described as a "game changer" for connect rates.

### Missed Call Automation (GHL)
1. Pipeline with "Called Me" stage
2. Zapier: New Twilio call -> Update tracking + GHL opportunity
3. Auto-SMS trigger: "Hi, sorry missed your call. Here's my calendar link"

---

## CRM TOOLS

| Tool | Cost | Best For | Source |
|---|---|---|---|
| **Close** | Varies | Best CRM per Ty Frankel; built for outbound sales teams | LinkedIn Client Lab |
| **PipeDrive** | ~$14-99/month | Pipeline management, visual deal tracking | Multiple |
| **Go High Level** | $97-297/month | All-in-one: CRM + dialer + SMS + automation + funnels | Longden, Acquisition X |

### CRM Requirements for Outbound
- Contact tracking with engagement history
- Pipeline/stage management
- Integration with email sending tools
- Call logging and recording
- Lead scoring capability
- Tag-based segmentation
- Automated follow-up triggers

---

## LINKEDIN TOOLS

| Tool | Cost | Best For | Source |
|---|---|---|---|
| **Dripify** | Varies (code FRANKEL10MO for 10% off) | Connection request automation ONLY (never DMs) | LinkedIn Client Lab |
| **Kondo** | Varies (code TY10 for 10% off) | LinkedIn inbox management | LinkedIn Client Lab |
| **Prosp (prosp.ai)** | Varies (code TY20 for 20% off) | AI lead magnet distribution | LinkedIn Client Lab |

### Dripify Rules (Ty Frankel)
- 100% optional -- manual outperforms by 10-20% on acceptance
- ONLY automate connection requests
- NEVER automate DMs (kills authenticity)
- If not getting 40%+ acceptance with Dripify, switch to manual
- Send Mon-Fri, 8 AM - 1 PM prospect timezone

---

## ENRICHMENT AND RESEARCH TOOLS

| Tool | Cost | Best For | Source |
|---|---|---|---|
| **Clay** | Varies | Data enrichment, multi-source aggregation | 30MPC |
| **RB2B** | Varies | Anonymous visitor ID (name + LinkedIn of site visitors) | Acquisition X |
| **Buska.io** | Varies | Reddit/social keyword monitoring | Acquisition X |
| **hunter.io** | Freemium | Email finding with transparent data policy | Bree Weber |
| **Spokeo** | Varies | Background check for phone numbers (last resort) | Longden |

---

## DELIVERABILITY AND TESTING TOOLS

| Tool | Cost | Best For | Source |
|---|---|---|---|
| **Google Postmaster** | Free | Spam rate monitoring for Gmail | 30MPC |
| **MailReach** | Varies | Inbox placement testing | 30MPC |
| **MX Toolbox** | Free/Paid | Blacklist checking, DNS verification | 30MPC, Chris Orzechowski |
| **Mail-Tester** | Free (limited) | Email spam score testing | Chris Orzechowski |
| **SendForensics** | Varies | Advanced deliverability analysis | Chris Orzechowski |

---

## CONTENT AND PRODUCTIVITY

| Tool | Cost | Best For | Source |
|---|---|---|---|
| **Notion** | Free/Paid | Project management, results database, CRM supplement | LinkedIn Client Lab |
| **Calendly** | Free/Paid | Call booking with questionnaire | LinkedIn Client Lab |
| **Loom** | Free/Paid | Video follow-ups, proof of concept | Bree Weber |
| **Manus (AI)** | Varies | AI assistant for research and content | LinkedIn Client Lab |

---

## TOOL SELECTION DECISION GUIDE

### Solo Operator (Just Starting)
- **Sending:** Maildoso (domains + mailboxes) + Lemlist or Mailshake
- **Warmup:** TrulyInbox (free)
- **Leads:** UpLead or Apollo
- **Verification:** NeverBounce
- **CRM:** Close or PipeDrive
- **LinkedIn:** Manual (no automation yet)
- **Estimated cost:** ~$250-400/month

### Small Team (2-5 people)
- Add: Go High Level ($297/month for unlimited sub-accounts)
- Add: Twilio for power dialing
- Add: Sales Navigator ($99/month)
- Add: Dripify for LinkedIn automation
- **Estimated cost:** ~$700-1,000/month

### Scaled Operation (SDR team)
- Add: Clay for enrichment at scale
- Add: RB2B for visitor identification
- Add: Multiple sending domains (10+)
- Add: MailReach for deliverability monitoring
- **Estimated cost:** ~$1,500-3,000/month
