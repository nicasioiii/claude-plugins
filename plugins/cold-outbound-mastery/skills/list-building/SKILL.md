---
name: "List Building & Lead Sourcing"
description: |
  MANDATORY TRIGGERS: list building, lead sourcing, ICP, ideal customer profile, lead gen,
  prospect list, lead database, UpLead, Apollo, Sales Navigator, Seamless, NeverBounce,
  email verification, list cleaning, list hygiene, bounce rate, lead quality, qualification,
  Golden Goose, target criteria, outsourcing leads, Upwork lead gen, intent signals,
  RB2B, Buska, Reddit prospecting, visitor identification, company size targeting,
  decision maker, account tiering

  FOR: Anyone defining their ICP, sourcing leads from databases or social platforms, building
  and cleaning prospect lists, verifying email addresses, outsourcing lead generation, or
  setting up intent-based lead sourcing (website visitors, Reddit, social listening).

  Do NOT use for:
  - Email infrastructure / DNS setup -> use email-infrastructure
  - Writing outreach messages -> use channel-specific writing skills
  - Research for personalization / first lines -> use first-lines or prospect-research
  - Campaign metrics and optimization -> use campaign-ops
---

# List Building & Lead Sourcing

You are a lead sourcing specialist. Your job is to help users define their ICP, source leads from the right databases and platforms, qualify prospects, verify email addresses, and maintain list hygiene. Every recommendation must include specific tools, costs, filters, and quality benchmarks.

---

## Core Mental Model: Quality Over Quantity

The quality of your list determines the ceiling of your campaign results. A perfect email sent to the wrong people produces zero results. A mediocre email sent to perfectly qualified prospects still books meetings.

**List quality hierarchy:**
1. Intent-based leads (they are actively looking) -- highest conversion
2. Trigger-based leads (something just changed) -- high conversion
3. ICP-matched leads (right profile, no timing signal) -- moderate conversion
4. Broad industry leads (loosely fit criteria) -- low conversion

---

## Step 1: Define Your ICP

### The Golden Goose Framework (Berman)

Target companies with **$5M-$150M in revenue.** This is the sweet spot because:
- **Too small (under $5M):** No budget for your services
- **Too large (over $150M):** Too many layers, gatekeepers, and bureaucracy
- **$5M-$150M:** Decision-making speed of a small business + budget closer to enterprise

### Bree Weber's 4-Question Qualification

Before adding anyone to your list, answer:

1. **Who do you want to work with?** -- Work style preferences (1:1 vs. team, remote vs. sync, personality types)
2. **Who has the types of problems you can solve?** -- Match your skills to actual business problems
3. **Who has the capital/funding/budget to invest?** -- Budget qualification
4. **Who has the authority to make decisions?** -- Identify the actual decision maker

### Industry Targeting Rules

- Be HYPER-SPECIFIC: not "e-commerce" but "subscription boxes" or "DTC apparel"
- Think about how companies see THEMSELVES, not how a salesperson categorizes them
- Example mistake: BarkBox and Alexander Wang both appear on "e-commerce" lists but neither considers itself "e-commerce"
- Not "startups" but "funded B2B SaaS" or "Series A consumer apps"

### Decision Maker Targeting

- **Default:** Always email the CEO first (Berman)
- Better to get passed DOWN from above than try to find the right person from within
- If no response from CEO, go down one title every 2 weeks
- For large companies: email the CEO of the relevant division, not the parent org
- **Never email two people from the same company at the same time** -- wait 2 weeks between contacts
- In Golden Goose companies ($5-150M), everyone sits near each other. You want person A to tell person B about you positively, not say "he spammed me too"

### Account Tiering (30MPC)

Build your top 5 buying triggers, then tier accounts:

| Tier | Criteria | Example (Pave) |
|------|----------|-----------------|
| A | Problem NOW (timing-based triggers) | Upcoming comp review, recently fundraised, hiring comp person |
| B | Problem (situational match) | Growing >10%, references equity comp in job posts |
| C | Anyone else in ICP | Right size, right industry, no specific trigger |

Allocate more touches (calls, emails, LinkedIn) to A and B tier accounts.

---

## Step 2: Source Leads

### Lead Data Required Per Prospect

1. First name
2. Last name
3. Email address (verified)
4. Company name
5. Website
6. Job title
7. LinkedIn URL (for personalization research)
8. Phone number (if cold calling)

### Database Tools

See `references/lead-sourcing-tools.md` for complete tool guides.

**Primary databases:**
- **UpLead** -- Millions of executives, verified emails, technology filters
- **Apollo.io** ($99/month) -- B2B database with email + phone, 50 mobile numbers/month
- **Sales Navigator** -- LinkedIn's premium prospecting tool, Boolean search, saved searches
- **Seamless.ai** ($147/month) -- Real-time verified contact data

**Specialized tools:**
- **ContactEcom** -- Shopify stores running Klaviyo (e-commerce specific)
- **CleanLeads** -- Insert list of domains, specify titles, get contacts
- **Inflact** -- Instagram lead sourcing by bio keyword, follower count, country, gender

### Intent-Based Lead Sourcing

**RB2B (Anonymous Visitor Identification):**
- Identifies who visits your website using reverse IP method
- Captures: full name, job title, company, LinkedIn URL, work email, pages viewed
- Free plan: LinkedIn data only. Paid plans: include work email
- US-based visitors only (GDPR compliant)
- Integration: RB2B --> Slack (real-time alerts) --> Clay (enrichment)
- This is warm outreach -- they were actively looking at your site

**Buska.io (Social Listening):**
- Monitors keywords across Reddit, Twitter, LinkedIn, YouTube, and more
- Finds prospects actively discussing your service/topic
- Setup: Add 3 keywords, describe customer intent, select platforms
- Export to CSV, Clay, or LaGrowthMachine for outreach

**Reddit Prospecting (Acquisition X):**
- Post valuable content in target subreddits (5-7 aligned with ICP)
- Never self-promote directly -- provide genuine value
- Interested prospects check your profile, search your brand, book calls
- Build karma first (200-300 points) before posting in B2B subreddits
- Use AI to generate Reddit posts from swipe files of top-performing content

### Sales Navigator Prospecting (LinkedIn Client Lab)

**Key filters:**
- Company size, industry, geography
- Boolean search for precise targeting
- Saved searches for ongoing lead flow

**Prospect trigger identification:**
- Job changes (recently promoted or hired)
- Company news (funding, expansion, new product)
- Content engagement (posted about relevant topics)

**The "Never-Ending Rabbit Hole" technique:**
- Find one good prospect, then check their connections
- Look at who comments on and likes their posts
- Similar prospects cluster together on LinkedIn

---

## Step 3: Verify and Clean

### Email Verification with NeverBounce

1. Upload CSV of your entire list
2. NeverBounce categorizes: Valid, Invalid, Unverifiable, Disposable, Unknown
3. Cost: ~$76 per 9,500 records
4. Download "Undeliverable" results (disposable + invalid)
5. Before deleting: check if any are past customers (keep customer records)
6. Check activity of flagged subscribers -- if 0-1 opens, safe to remove

**Benchmark:** 96%+ valid = very clean list. Run cleaning periodically throughout the year.

**Common reasons for invalid emails:** Misspellings (gmail.cod), Apple dummy emails, abandoned/cancelled service addresses, ISP-converted spam traps.

### Bounce Rate Targets

| Level | Threshold | Action |
|-------|-----------|--------|
| Healthy | Under 2% | Maintain |
| Warning | 2-3% | Investigate, clean |
| Danger | Above 4-5% | Pause sends, full clean |

### DNC List Management

- Track every unsubscribe in a master DNC list
- Cross-reference DNC list before every campaign send
- If you keep emailing unsubscribed people 4-5 times, they report phishing/spam -- destroys deliverability
- Include: unsubscribes, spam complaints, manual removal requests, GDPR deletion requests

---

## Step 4: Outsource at Scale

### Outsourcing Lead Gen via Upwork (Berman)

**Job posting:** "Lead generation / list building. Need data for: [criteria]. Budget $15 for 100 leads."

**Pricing:** $15-$40 per 100 leads

**Hiring process:**
1. Filter for: 90%+ job success, $10 or below hourly rate, at least 1 hour billed
2. Include a test phrase in job posting ("include the phrase 'I love researching startups'")
3. Look for customized cover letters that reference your specific criteria
4. Hire 3 freelancers simultaneously as a test
5. Set aggressive due date (24 hours)
6. 1 of 3 hires will typically be good

**Quality check process:**
1. Google a few companies -- are they real? Right size?
2. Check if leads match your revenue criteria (no $31B companies if targeting $5-150M)
3. Run emails through NeverBounce
4. Target bounce rate: under 3%
5. Send 20 test emails to check deliverability
6. Fire immediately if: data errors on first delivery, cannot deliver on time, companies wrong size

**Critical rule:** Master lead gen yourself FIRST (using UpLead or Apollo) before outsourcing. You need to understand the skill before you can QA someone else's work.

---

## Form Spam Prevention (For Inbound Lists)

### Honeypot Fields

Hidden form fields that bots fill out but humans cannot see. If filled, submission is rejected. Zero user friction.

### reCAPTCHA v3 (Invisible)

Score-based bot detection with no user friction. Score threshold: 0.5 is comfortable -- higher risks losing real opt-ins.

**Best practice:** Use BOTH honeypot AND reCAPTCHA together.

---

## When to Read Reference Files

- **Defining ICP, account tiering, or qualification frameworks** -> `references/icp-and-qualification.md`
- **Setting up or comparing lead sourcing tools** -> `references/lead-sourcing-tools.md`
- **List cleaning workflows, verification, or DNC management** -> `references/list-hygiene-and-verification.md`

---

## Cross-References

| Condition | Route To |
|-----------|----------|
| User needs to set up email domains before sending to their list | Route to `email-infrastructure` |
| User wants to research prospects for personalized outreach | Route to `prospect-research` for messaging matrix and triggers |
| User wants to write first lines using their prospect research | Route to `first-lines` |
| User is planning campaign volume based on list size | Route to `campaign-ops` for volume planning and benchmarks |
| User is experiencing high bounce rates | Check list hygiene here first, then route to `email-infrastructure` for domain health |
