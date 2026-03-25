---
name: "Deliverability Diagnosis"
description: "When to investigate, GlockApps interpretation, Google Postmaster setup, ISP-specific diagnosis, spam thresholds, blacklist detection, and authentication DNS setup."
---

# Deliverability Diagnosis Reference

## Detection Threshold Table

| Metric | Healthy | Warning | Critical |
|--------|---------|---------|----------|
| Open rate (segmented, Klaviyo) | 20-25%+ | 15-20% | Below 10% |
| Open rate (full list) | 10-15% | 5-10% | Below 5% |
| Email delivery rate | 99.5%+ | 98-99.5% | Below 98% |
| Spam rate (Google Postmaster) | Below 0.05% | 0.05-0.2% | Above 0.2% |
| Unsubscribe rate | Below 0.2% | 0.2-0.4% | Above 0.4% |
| Welcome flow Email 1 open rate | 50%+ | 30-50% | Below 30% |
| Abandon checkout Email 1 open rate | 50%+ | 35-50% | Below 35% |

Source: E02 (Ecom Email School), E03 (MuteSix)

---

## GlockApps Testing Protocol

### How to Run a Test
1. Create account at GlockApps
2. Set up a test (choose "regular email test")
3. Copy the seed email list provided by GlockApps
4. Send a representative email (same design/content as your typical campaign) to the seed list from your ESP
5. Wait for results (usually 5-15 minutes)

### Reading Results

GlockApps shows inbox placement per provider:

| Provider | Inbox | Promotions | Spam | Missing |
|----------|-------|------------|------|---------|
| Gmail | Target: 100% | Acceptable | Problem | Problem |
| Yahoo | Target: 100% | N/A | Problem | Problem |
| Outlook/Hotmail | Target: 100% | N/A (Focused vs Other) | Problem | Problem |
| Apple/iCloud | Target: 100% | N/A | Problem | Problem |

**Interpretation rules:**
- Gmail spam = sender reputation destroyed; requires new domain [E02]
- Gmail promotions = not ideal but domain is not a write-off; improve engagement [E02]
- Outlook spam = very tight filters; small % of most lists (e.g., 724 out of 30,000); do not panic unless core audience uses Outlook [E02]
- Multiple providers spam = likely authentication issue or blacklist

### When to Retest
- After completing warmup protocol (minimum 1 week for existing domains, 2-4 weeks for new)
- Target: 99-100% inbox delivery across Gmail, Yahoo, Apple [E02]
- Retest monthly as part of prevention routine

---

## Google Postmaster Tools Setup

### What It Monitors [E03]
- **IP reputation:** How Google views your sending IP
- **Domain reputation:** How Google views your sending domain
- **Authentication status:** SPF, DKIM, DMARC pass rates
- **Spam rate:** Percentage of emails marked as spam by Gmail users

### Setup Steps
1. Go to postmaster.google.com
2. Add and verify your sending domain (TXT record or CNAME verification)
3. Data appears after sending sufficient volume to Gmail addresses (minimum approximately 100/day)
4. Dashboard shows daily reputation scores: High / Medium / Low / Bad

### Reputation Interpretation
- **High:** Excellent standing; maintain current practices
- **Medium-Low:** Authentication or engagement issues; investigate segmentation and list quality
- **Low-Bad:** Immediate action required; begin warmup protocol; consider new domain

---

## DNS Authentication Setup (DMARC, DKIM, SPF)

### SPF (Sender Policy Framework)
- **What it does:** Declares which mail servers are authorized to send email on behalf of your domain
- **Record type:** TXT record on root domain
- **Format:** `v=spf1 include:[esp-specific] ~all`
- **Common ESP includes:**
  - Klaviyo: `include:send.klaviyo.com`
  - Google Workspace: `include:_spf.google.com`
  - Mailchimp: `include:servers.mcsv.net`
  - ActiveCampaign: `include:emsd1.com`
  - SendGrid: `include:sendgrid.net`
- **Rules:** One SPF record per domain; multiple records cause failures; use `~all` (soft fail) as default [E02, cold-outbound-mastery cross-ref]

### DKIM (DomainKeys Identified Mail)
- **What it does:** Adds a cryptographic signature to outgoing emails proving they were not altered in transit
- **Setup:** Generate in your ESP or Google Workspace (Admin > Apps > Gmail > Authenticate Email)
- **Key size:** Use 1024-bit key minimum
- **Record type:** Copy DNS hostname provided by ESP to domain DNS records [E02]

### DMARC (Domain-based Message Authentication, Reporting & Conformance)
- **What it does:** Tells receiving servers what to do when SPF or DKIM fails; also provides reporting
- **Record type:** TXT record with `_dmarc` hostname
- **Starting policy:** `v=DMARC1; p=none; rua=mailto:dmarc@yourdomain.com` (monitor only)
- **Graduated enforcement:** Move from `p=none` to `p=quarantine` to `p=reject` as confidence grows
- **Verification:** Google MX Checker (toolbox.googleapps.com) -- all three should show green checkmarks [E02]

---

## ISP-Specific Diagnosis [E03]

### The Segmentation Test
1. Create a segment of Gmail-only subscribers
2. Create a segment of non-Gmail subscribers
3. Send the same campaign to each segment separately
4. Compare open rates

| Result Pattern | Diagnosis | Fix |
|----------------|-----------|-----|
| Gmail low, others normal | Gmail-specific; check Google Postmaster | Domain or IP reputation with Google |
| Gmail normal, others low | ISP-specific; check authentication | Likely SPF/DKIM issue for non-Gmail providers |
| All low | Broad issue | List quality, authentication, or blacklist |
| All normal | Not a deliverability issue | Check content, segmentation, or send timing |

---

## Blacklist Detection and Recovery [E03]

### Key Blacklists to Monitor
- Spamhaus (most impactful)
- SpamCop
- Barracuda
- SORBS
- URIBL

### Detection
- Use MX Toolbox (free) blacklist check
- Enter your sending domain or IP address
- Check results for any listings

### Recovery
- **Manual blacklist:** Research the specific blacklist's removal process; submit delisting request with evidence of corrective action
- **Automatic blacklist:** Continue sending only to highly engaged users following best practices; auto-removal typically occurs within days to weeks once sending behavior improves [E03]

---

## Spam Rate Analysis [E03]

### Thresholds
- **Target:** Below 0.05%
- **Warning:** 0.05-0.2%
- **Danger zone:** Above 0.2% (Google Postmaster)
- **Note:** Rates as low as 0.08% can affect Gmail deliverability [E03]

### Common Causes of High Spam Rate
1. Sending to unengaged subscribers who forgot they opted in
2. Purchased or scraped email lists
3. Missing or hard-to-find unsubscribe link
4. Misleading subject lines that do not match email content
5. No double opt-in for new subscribers
6. Stale list with dormant addresses becoming spam traps [E03]

### Spam Trap Types
- **Recycled traps:** Old email addresses abandoned by original owners, repurposed by ISPs as spam traps (e.g., unused Yahoo address for 2-3 years) [E03]
- **Pristine traps:** Addresses created solely to catch spammers; never opted into anything
- **Typo traps:** Common misspellings of real domains (gmial.com, yaho.com)

**Prevention:** Regular list cleaning removes addresses that have become traps. Run sunset flows to remove subscribers who have not engaged in 90-120+ days.
