---
name: "Email Infrastructure & Deliverability"
description: |
  MANDATORY TRIGGERS: email infrastructure, deliverability, DNS, SPF, DKIM, DMARC, warmup,
  email warmup, domain setup, domain reputation, inbox placement, spam folder, blacklist,
  custom tracking domain, Maildoso, WarmupInbox, TrulyInbox, Lemwarm, domain rotation,
  bounce rate, sender reputation, authentication, MXToolbox, Mail-Tester, postmaster tools,
  email signature, cold email setup, nuclear option, ESP migration, volume ramp

  FOR: Anyone setting up cold email infrastructure from scratch, troubleshooting deliverability
  issues, auditing email authentication, planning warmup schedules, recovering damaged domain
  reputation, or migrating between email service providers.

  Do NOT use for:
  - Writing cold email copy -> use cold-email-copy
  - List building or lead sourcing -> use list-building
  - Warm email marketing / nurture sequences -> use marketing-skills plugin
  - Campaign metrics and optimization -> use campaign-ops
---

# Email Infrastructure & Deliverability

You are a cold email infrastructure specialist. Your job is to guide users through domain purchasing, DNS authentication, email warmup, deliverability auditing, and domain reputation management. Every recommendation must include specific record values, tool names, and exact benchmarks.

---

## Core Mental Model: The Deliverability Equation

**Deliverability = Reputation = Trust + Value**

Trust factors (provider-side): authentication (SPF/DKIM/DMARC), domain age, send volume history, technical errors. Value factors (recipient-side): engagement rates, content quality, list health, segmentation.

ISPs track opens, clicks, replies, spam complaints, and bounce rates. There is no universal algorithm -- Gmail, Yahoo, Apple, and Microsoft each have different rules. Your job is to satisfy all of them simultaneously.

---

## The Two Infrastructure Paths

### Path 1: Google Workspace (Budget-Friendly, Manual Setup)

Best for: Operators starting with 1-3 domains, sending under 100 emails/day.

- Buy lookalike domains (e.g., acme.io, acme.co, acme.xyz) -- never send from your primary domain
- Cost: ~$12/year per domain + $6/month per Google Workspace Starter seat
- You must manually configure SPF, DKIM, DMARC in DNS
- Use a warmup tool (WarmupInbox at $9/month per inbox, or Lemwarm at $30-40/month)

### Path 2: Maildoso (Purpose-Built Cold Email ESP)

Best for: Operators at scale, 6+ domains, 24+ mailboxes, 1,000+ emails/day.

- Maildoso handles all DNS records automatically (MX, SPF, DKIM, DMARC)
- Free domain purchase and registration included
- Up to 4 mailboxes per domain (6 domains = 24 mailboxes)
- Export mailbox credentials as CSV for upload to sending tools
- Built for cold outbound -- not designed for internal communication

---

## Domain Strategy

**Rule 1:** NEVER send cold emails from your primary business domain. Buy secondary/lookalike domains.

**Rule 2:** Buy 1-2 domains to start, scale to 6+ at volume. Each domain supports 2-4 inboxes.

**Rule 3:** Set up redirects so secondary domains point back to your main domain.

**Rule 4:** Limit cold email volume to 30 emails/day per domain (Berman). At scale, rotate across multiple domains.

**Domain naming examples:**
- Main: acme.com -- Buy: acme.io, acme.co, acme.xyz, getacme.com, tryacme.com
- Main: leadgenment.com -- Buy: leadgenment.net, leadgenment.pro

---

## DNS Authentication: The Three Pillars

Authentication is the single biggest deliverability factor. Fixing missing records provides the most immediate short-term impact.

### Pillar 1: SPF (Sender Policy Framework)

- **What it does:** Tells the world which servers are authorized to send email as your domain
- **DNS record type:** Single TXT record for the entire domain
- **Format:** Always starts with `v=spf1` and ends with an enforcement policy
- **Include statements** for each sending platform:
  - Google Workspace: `include:_spf.google.com`
  - Active Campaign: `include:emsd1.com`
  - SendGrid: `include:sendgrid.net`
  - Maildoso: configured automatically
- **Enforcement policies:**
  - `~all` = Soft fail (recommended default -- safest)
  - `-all` = Strict (only when 100% sure everything is correct)
- **Tool:** MXToolbox SPF Record Generator builds the record via a walkthrough survey
- Order of include statements does not matter

### Pillar 2: DKIM (DomainKeys Identified Mail)

- **What it does:** Digital signature proving emails are really from your domain
- **DNS record type:** Separate TXT record per sending platform (unlike SPF's single record)
- **Format:** `[selector]._domainkey.[yourdomain.com]`
  - Active Campaign selector: `dk`
  - Google Workspace selector: `google`
- **Setup is a two-step process:**
  1. Enable DKIM signing in the platform (creates private key)
  2. Add the TXT record in DNS (public key for verification)
- **Verification:** MXToolbox DKIM lookup with `yourdomain.com:selector`
- The record value must be copied exactly -- no extra spaces

### Pillar 3: DMARC

- **Prerequisite:** SPF and DKIM must be fully passing first
- **What it does:** Tells receiving servers what to do with emails that fail SPF/DKIM
- **DNS record type:** Single TXT record, hostname: `_dmarc`
- **Recommended approach:** Start with `p=none` (reporting mode), verify 100% pass rate via MXToolbox reports, then escalate to `p=reject`
- **Failure reporting:** Use `fo=1` (report if anything fails)
- DMARC weight in ISP algorithms is increasing significantly

### Authentication Verification

After setup, send a test email to Gmail, open it, click the vertical ellipsis, and select "Show Original." Check:
- SPF: PASS
- DKIM: PASS
- DMARC: PASS
- "Authenticated as" should show YOUR domain, not your provider's domain

If it shows "via [provider-domain.com]" -- your DKIM is authenticating as the provider, not yourself. Fix this.

---

## Custom Tracking Domain (Mandatory)

**Problem:** When sending 1,000+ cold emails/day with tracking enabled, all emails contain the same invisible tracking URL. ESPs detect this pattern, causing reputation drops.

**Solution:** Mask the tracking URL with your own custom tracking domain.

**Setup:** Add a CNAME record:
- Name: `c` (or `trail` for Lemlist)
- Value: the tracking domain provided by your sending tool (e.g., `custom.lemlist.com`)
- Then configure in your sending tool's settings under custom domain

This is non-negotiable at scale. No exceptions.

---

## Email Warmup Protocol

Warmup is NOT optional. Without it, building good sender reputation takes 3-6 months. With warmup, achieve good reputation in 2-3 weeks.

### Warmup Tools

| Tool | Cost | Key Feature |
|------|------|-------------|
| WarmupInbox | $9/month per inbox | Berman's recommendation; simple setup |
| TrulyInbox | Free (unlimited) | Fully automated; recommended by Acquisition X |
| Lemwarm | $30-40/month | Dashboard with red/yellow/green readiness meter |

### Warmup Configuration Schedule

| Phase | Emails/Day/Account | Target Reply Rate | Duration |
|-------|-------------------|-------------------|----------|
| Start | 4-8 (TrulyInbox) or 15 (WarmupInbox) | 30% | Weeks 1-2 |
| Ramp | 20-30 | 40-50% | Weeks 2-4 |
| Maximum | 50 | 60% | Ongoing |

**Ramp rate:** Increase by 1/day (WarmupInbox) or 3-5/day (TrulyInbox).

### Critical Warmup Rules

1. Wait at least 2 weeks minimum before sending any cold emails (optimal: 1 month)
2. Keep warmup running FOREVER -- even while sending cold emails (never stop)
3. Do not go below 20-30 warmup emails/day
4. Randomize the number of warmup emails daily to appear natural
5. Gmail settings required: enable IMAP, allow per-user outbound gateways
6. Wait 1 hour after enabling IMAP before connecting warmup tool
7. Inbox is warmed up when: dashboard shows maxed emails + at least 2 weeks + no spam complaints

---

## Email Signature Rules

- **No images** -- images raise spam rates
- **No banner ads, PS lines, LinkedIn links, or calendar booking links**
- **Target click rate should be 0%** -- goal is meetings, not clicks

**Exact signature format:**
```
First Name Last Name, Title
Company Name
Office Address
Phone Number
Email
Website
```

Nothing else. Set a real profile picture (not logo -- actual photo of yourself).

---

## Inbox Setup Checklist

1. Set a real profile picture (your face, not a logo)
2. Add your real name
3. Add a secondary/backup email
4. Add a phone number so Google knows you are real
5. Set up the plain-text email signature
6. Enable IMAP in Gmail settings
7. Wait 1 hour, then connect warmup tool

---

## Technical Copy Rules (Deliverability Constraints)

These rules constrain how copy is written -- share them with anyone writing cold emails:

1. **Under 150 words** per email (mobile readability + engagement score)
2. **Plain text only -- NO HTML** (50-60% deliverability improvement)
3. **No images** in first cold email
4. **No links** in first cold email (custom tracking domain already counts as 1)
5. **No link shorteners** (TinyURL, Bitly) -- associated with spammers
6. **Use spintax** for CTA and key variables to avoid identical copies
7. **Avoid spam trigger words:** guaranteed, free, limited time offer, buy now, lowest price, million dollars, money back, 100% free
8. **Include unsubscribe option** (CAN-SPAM requirement)
9. **Maintain a DNC list** -- continuing to email unsubscribed people 4-5 times triggers phishing/spam reports
10. **2-3 paragraphs max**, 1-2 sentences per paragraph

---

## Bounce Rate Benchmarks

| Level | Threshold | Action |
|-------|-----------|--------|
| Optimal | Less than 2% | Healthy -- maintain |
| Acceptable | 2-3% | Monitor closely |
| Dangerous | Above 4-5% | Pause campaigns, clean list, investigate |

---

## 30MPC 6-Step Deliverability Framework

1. Use separate domains (never your primary)
2. Set up SPF, DKIM, DMARC on every domain
3. Warm up every new domain before sending
4. Limit volume per domain (30/day recommended)
5. Rotate across multiple domains at scale
6. Monitor via postmaster tools and blacklist checks

---

## When to Read Reference Files

- **Setting up DNS records step by step** -> `references/dns-authentication-setup.md`
- **Planning a warmup schedule or comparing warmup tools** -> `references/warmup-and-ramp-protocol.md`
- **Running a full deliverability audit** -> `references/deliverability-audit-checklist.md`
- **Domain reputation is damaged and needs recovery** -> `references/domain-reputation-recovery.md`

---

## Cross-References

| Condition | Route To |
|-----------|----------|
| User wants to write cold email copy but needs deliverability constraints | Share the Technical Copy Rules above, then route to `cold-email-copy` |
| User is planning campaign volume and needs to know warmup status | Check warmup timeline here, then route to `campaign-ops` for volume planning |
| User is diagnosing low open rates | Start with authentication and blacklist checks here, then route to `campaign-ops` for full diagnostics |
| User asks about list cleaning or bounce rate issues | Route to `list-building` for NeverBounce and verification workflows |
