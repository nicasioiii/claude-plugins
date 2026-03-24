# Complete DNS Setup Guide: SPF, DKIM, DMARC

This reference provides exact DNS record configurations for all major platforms.

---

## SPF Record Setup

### SPF Record Basics
- **Record Type:** TXT
- **Record Name:** @ (or leave blank, depending on registrar)
- **Value:** `v=spf1 [includes] ~all` or `v=spf1 [includes] -all`

### SPF Syntax
| Component | Meaning |
|-----------|---------|
| `v=spf1` | SPF version (always required first) |
| `include:[domain]` | Include SPF records from another domain |
| `~all` | Soft fail (accepts, but marks suspicious) |
| `-all` | Hard fail (rejects outright) |

**Recommendation:** Use `~all` unless you have 100% control of all sending sources.

### Complete SPF Examples

**Minimal (Gmail Workspace only):**
```
v=spf1 include:_spf.google.com ~all
```

**Standard (Gmail + Email Marketing + Transactional):**
```
v=spf1 include:_spf.google.com include:sendgrid.net include:ac-emsrv.com include:servers.mcsv.net ~all
```

**Full featured (All platforms):**
```
v=spf1 include:_spf.google.com include:sendgrid.net include:ac-emsrv.com include:servers.mcsv.net include:klaviyo.com include:sparkpost.com include:mandrillapp.com ~all
```

### Platform-Specific SPF Includes

| Platform | SPF Include | Use Case |
|----------|-------------|----------|
| Google Workspace | `include:_spf.google.com` | Email hosting |
| SendGrid | `include:sendgrid.net` | Transactional emails, high volume |
| Active Campaign | `include:ac-emsrv.com` | Marketing automation |
| MailChimp | `include:servers.mcsv.net` | Email campaigns |
| Klaviyo | `include:klaviyo.com` | E-commerce marketing |
| SparkPost | `include:sparkpost.com` | Transactional email |
| Mandrill | `include:mandrillapp.com` | Transactional email |
| Amazon SES | `ip4:[IP]` | Direct IP (get from AWS console) |
| LemList | `include:lemlist.com` | Cold email campaigns |

### How to Add SPF Record

**Cloudflare:**
1. Log in to Cloudflare dashboard
2. Select domain
3. Go to DNS
4. Click "Add Record"
5. Type: TXT
6. Name: @ (or leave blank)
7. Content: `v=spf1 include:_spf.google.com ~all` (your SPF record)
8. TTL: Auto
9. Save

**Google Domains:**
1. Log in to domains.google.com
2. Select domain
3. Click DNS (left sidebar)
4. Scroll to "Custom records"
5. Click "Add" in TXT row
6. Subdomain: (leave blank for @)
7. Value: `v=spf1 include:_spf.google.com ~all`
8. Click "Add"

**GoDaddy:**
1. Log in to GoDaddy
2. Go to My Products → Domains
3. Select domain
4. Click "Manage DNS"
5. Find TXT Records section
6. Click "Add" (or Edit if exists)
7. Name: @ or leave blank
8. Value: `v=spf1 include:_spf.google.com ~all`
9. Save

**Namecheap:**
1. Log in to Namecheap
2. Go to Manage Domains
3. Select domain
4. Click "Advanced DNS"
5. Find TXT Records
6. Click "Add New Record"
7. Type: TXT
8. Host: @ (or leave blank)
9. Value: `v=spf1 include:_spf.google.com ~all`
10. Save

### SPF Validation

**Using MX Toolbox:**
1. Go to mxtoolbox.com/spf.aspx
2. Enter domain: yourdomain.com
3. Click Check SPF
4. Results should show: ✓ SPF record is valid
5. Verify all platforms listed are included

---

## DKIM Record Setup

### DKIM Record Basics
- **Record Type:** TXT or CNAME (depending on platform)
- **Record Name:** `[selector]._domainkey.yourdomain.com`
- **Value:** Public key provided by each platform

### Critical Concept: One DKIM per Platform
You need SEPARATE DKIM records for each platform sending as your domain:
- Gmail Workspace gets 1 DKIM selector
- Active Campaign gets 1 DKIM selector
- SendGrid gets 1 DKIM selector
- Etc.

Each platform provides its own selector and public key. You add all of them to DNS.

---

## DKIM Setup by Platform

### Active Campaign DKIM Setup

**Steps:**
1. Log in to Active Campaign
2. Go to Settings → Domains
3. Click on your domain
4. In "Sender Domain" section, you'll see a table with:
   - Host (selector: e.g., `acmailing._domainkey`)
   - Type: TXT
   - Value: (long DKIM public key)

5. Copy the host, type, and value
6. Go to your DNS registrar (Cloudflare, GoDaddy, etc.)
7. Add TXT record:
   - Name: `acmailing._domainkey`
   - Type: TXT
   - Value: (the long key from Active Campaign)
8. Save

**DKIM Verification:**
- Open an email sent from Active Campaign
- Click Show Original (Gmail)
- Search for "DKIM: pass"
- Should show: `DKIM: pass with domain yourdomain.com`
- If shows: `DKIM: pass with domain ac-emsrv.com` = NOT PASSING (problem to fix)

### Google Workspace DKIM Setup

**Steps:**
1. Go to admin.google.com
2. Security → Authentication
3. Scroll to "Domain Verification"
4. Under "DKIM signing," click "Add DKIM signing for yourdomain.com"
5. In dialog: Select domain, confirm DKIM configuration
6. Google will generate selectors: `google`, `google2`, `google3` (usually)
7. For each selector, you get a TXT record:
   - Name: `[selector]._domainkey.yourdomain.com`
   - Type: TXT
   - Value: (public key)

8. Add all to DNS (can take 24-48 hours to fully authenticate)

**DKIM Verification:**
- Google will show status in admin console (check mark when authenticated)
- Open email → Show Original → Look for `DKIM: pass with domain yourdomain.com`

### SendGrid DKIM Setup (Recommended: CNAME Method)

SendGrid supports both TXT and CNAME. CNAME is easier and cleaner.

**Steps:**
1. Log in to SendGrid
2. Settings → Sender Authentication
3. Click "Authenticate Your Domain"
4. Enter domain: yourdomain.com
5. Click "Next"
6. SendGrid generates CNAMEs (usually 3):
   - Name: `c1.[yourdomain.com]`, Value: `sendgrid.net`
   - Name: `c2.[yourdomain.com]`, Value: `sendgrid.net`
   - Name: `c3.[yourdomain.com]`, Value: `sendgrid.net`

7. Add these to DNS as CNAME records
8. Return to SendGrid and verify

**Using TXT Instead (if CNAME not available):**
SendGrid will provide TXT records with DKIM selectors. Add as:
- Name: `[selector]._domainkey.yourdomain.com`
- Type: TXT
- Value: (public key)

**DKIM Verification:**
- SendGrid dashboard will show "authenticated" checkmark
- Email header check: `DKIM: pass with domain yourdomain.com`

### MailChimp DKIM Setup

**Steps:**
1. Log in to MailChimp
2. Account → Domains
3. Click "Authenticate Domain"
4. MailChimp generates a DKIM record:
   - Host: `default._domainkey.yourdomain.com`
   - Type: TXT
   - Value: (public key)

5. Add to DNS
6. Verify in MailChimp dashboard

### Klaviyo DKIM Setup

**Steps:**
1. Log in to Klaviyo
2. Account → Email Settings → Sender Domain
3. Click "Add Verified Domain"
4. Klaviyo generates:
   - Host: `klaviyo._domainkey.yourdomain.com`
   - Type: TXT
   - Value: (public key)

5. Add to DNS
6. Verify in Klaviyo

### LemList DKIM Setup (with Custom Tracking Domain)

**Steps:**
1. Log in to LemList
2. Settings → Email Configuration
3. Add Custom Tracking Domain: `trail.yourdomain.com` (or similar)
4. LemList shows DKIM record:
   - Host: `lemlist._domainkey.yourdomain.com`
   - Type: TXT
   - Value: (public key)

5. Go to DNS, add:
   - Name: `trail`
   - Type: CNAME
   - Value: `custom.lemlist.com`

6. Also add DKIM record from step 4

---

## Multiple DKIM Records Example

If using Gmail + Active Campaign + SendGrid, your DNS should have:

```
default._domainkey.yourdomain.com    TXT    google_spf_key_here
acmailing._domainkey.yourdomain.com  TXT    active_campaign_key_here
s1._domainkey.yourdomain.com         TXT    sendgrid_key_here
```

All three must show "PASS" when you check headers.

---

## DMARC Record Setup

### DMARC Record Basics
- **Record Type:** TXT
- **Record Name:** `_dmarc.yourdomain.com`
- **Value:** Policy string with configuration options

### DMARC Prerequisites
- Must have SPF record working (validate with MX Toolbox)
- Must have DKIM records working (validate with MX Toolbox)
- Do NOT proceed with DMARC until both SPF and DKIM pass 100%

### DMARC Policy Progression

**Phase 1: Monitoring (Weeks 1-2)**
```
v=DMARC1;p=none;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;
```
- Tells receivers: "Monitor failures but don't enforce"
- You receive weekly reports showing pass/fail rates
- Goal: Verify 100% SPF and DKIM pass rates

**Phase 2: Cautious Enforcement (Weeks 3-4)**
```
v=DMARC1;p=quarantine;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;aspf=relaxed;adkim=relaxed;
```
- Tells receivers: "Move suspicious emails to spam folder"
- Less aggressive than reject
- Safe if you're confident most legitimate emails pass

**Phase 3: Full Enforcement (Week 5+)**
```
v=DMARC1;p=reject;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;aspf=relaxed;adkim=relaxed;
```
- Tells receivers: "Reject emails that don't pass SPF or DKIM"
- Most aggressive
- Only use after confirming 100% pass rate for at least 2 weeks

### DMARC Parameters Explained

| Parameter | Options | Recommended |
|-----------|---------|-------------|
| `v=DMARC1` | DMARC1 only | Always DMARC1 |
| `p=` | none, quarantine, reject | Start with none, progress to reject |
| `rua=` | Email address | dmarc-reports@yourdomain.com |
| `ruf=` | Email address | dmarc-failures@yourdomain.com |
| `fo=` | 0, 1, d, s | 1 (report if anything fails) |
| `pct=` | 1-100 | 100 (apply to all emails) |
| `aspf=` | relaxed, strict | relaxed (more forgiving) |
| `adkim=` | relaxed, strict | relaxed (more forgiving) |

**Alignment Modes Explained:**
- `aspf=relaxed`: Email passes if SPF domain matches anywhere in chain (domain match is enough)
- `aspf=strict`: Email passes only if SPF aligns exactly with sending domain (stricter)
- `adkim=relaxed`: Email passes if DKIM domain matches anywhere (domain match is enough)
- `adkim=strict`: Email passes only if DKIM aligns exactly with sending domain (stricter)

Most use `relaxed` for both unless they have 100% control of all sending sources.

### Complete DMARC Examples

**Startup/New Domain (Monitoring):**
```
v=DMARC1;p=none;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;
```

**Established (Enforcement):**
```
v=DMARC1;p=reject;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;aspf=relaxed;adkim=relaxed;
```

**With Failure Reporting:**
```
v=DMARC1;p=reject;rua=mailto:dmarc-reports@yourdomain.com;ruf=mailto:dmarc-failures@yourdomain.com;fo=1;pct=100;aspf=relaxed;adkim=relaxed;
```

### How to Add DMARC Record

**Cloudflare:**
1. Log in to Cloudflare
2. Select domain
3. Go to DNS
4. Click "Add Record"
5. Type: TXT
6. Name: `_dmarc`
7. Content: `v=DMARC1;p=none;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;`
8. TTL: Auto
9. Save

**Google Domains:**
1. Log in to domains.google.com
2. Select domain
3. Click DNS
4. Scroll to Custom Records
5. Click Add in TXT row
6. Subdomain: `_dmarc`
7. Value: `v=DMARC1;p=none;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;`
8. Save

**GoDaddy:**
1. Log in and go to Manage Domains
2. Select domain → Manage DNS
3. Find TXT Records
4. Click Add
5. Name: `_dmarc`
6. Value: `v=DMARC1;p=none;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;`
7. Save

**Namecheap:**
1. Log in → Manage Domains
2. Select domain → Advanced DNS
3. Find TXT Records
4. Add New Record
5. Type: TXT
6. Host: `_dmarc`
7. Value: `v=DMARC1;p=none;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;`
8. Save

### DMARC Reporting & Monitoring

**Report Frequency:**
- Weekly aggregate reports (detailed breakdown from receivers)
- Daily summaries if using a DMARC aggregator

**What to Monitor:**
- SPF pass rate: Should be 100%
- DKIM pass rate: Should be 100%
- DMARC alignment: Should be 100%

**Tools for Reading Reports:**
- Gmail (look for emails from dmarc-reports@yourdomain.com)
- MX Toolbox DMARC Reporter (aggregates reports)
- DMARC visualization dashboards (Dmarcian, Agari, etc.)

**Expected Timeline:**
1. Days 1-7: Add DMARC p=none, watch reports
2. Days 8-14: Verify 100% pass rate consistently
3. Week 3: Upgrade to p=quarantine, monitor for 5-7 days
4. Week 4: Upgrade to p=reject if still at 100%

---

## Complete DNS Setup Example

### Full Configuration (New Domain)

```
@ (blank)          TXT  v=spf1 include:_spf.google.com include:sendgrid.net ~all
default._domainkey TXT  v=DKIM1; k=rsa; p=[google_public_key]
sendgrid._domainkey TXT  v=DKIM1; k=rsa; p=[sendgrid_public_key]
_dmarc             TXT  v=DMARC1;p=none;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;
```

### Verification Checklist

- [ ] SPF record added to DNS
- [ ] SPF validated with MX Toolbox (green checkmark)
- [ ] DKIM records added for each platform (Gmail, SendGrid, Active Campaign, etc.)
- [ ] DKIM validated with MX Toolbox (all green)
- [ ] Test email headers show "DKIM: pass with domain yourdomain.com"
- [ ] DMARC record added (start with p=none)
- [ ] DMARC validated with MX Toolbox
- [ ] Test emails sent to 4+ providers (Gmail, Yahoo, Outlook, iCloud)
- [ ] All test emails arrived in primary inbox (not spam)
- [ ] Authentication headers show SPF pass, DKIM pass, DMARC pass

---

## Propagation & Timing

- SPF/DKIM/DMARC records: Can take 24-48 hours to fully propagate
- Don't wait—you can start sending emails after adding records
- But they'll authenticate better once propagated
- Monitor with MX Toolbox; re-check every 6 hours

---

## Troubleshooting DNS Setup

**SPF not validating:**
- Syntax error in record (extra spaces, missing "v=spf1")
- Too many includes (SPF limit is 10 DNS lookups)
- Platform include wrong (verify with platform docs)

**DKIM not validating:**
- Selector name wrong (must match exactly what platform provides)
- Public key truncated (full key not copied)
- DKIM signature not sent by platform (check email headers)
- Platform not configured to sign with your domain

**DMARC not validating:**
- _dmarc prefix missing
- SPF or DKIM not working first (required prerequisite)
- P= policy has typo (should be "none", "quarantine", or "reject")

---

## Quick Reference: Validation Commands

**Check SPF in Terminal:**
```
nslookup -type=TXT yourdomain.com
```
Look for: `v=spf1 include:...`

**Check DKIM:**
```
nslookup -type=TXT [selector]._domainkey.yourdomain.com
```
Look for: `v=DKIM1; k=rsa; p=...`

**Check DMARC:**
```
nslookup -type=TXT _dmarc.yourdomain.com
```
Look for: `v=DMARC1; p=...`

**Or use MX Toolbox (easier):**
- mxtoolbox.com/spf.aspx
- mxtoolbox.com/dkim.aspx
- mxtoolbox.com/dmarc.aspx
