---
name: "DNS Authentication Setup"
description: "Step-by-step SPF, DKIM, DMARC setup procedures for all major ESPs, record formats, verification steps, and MXToolbox workflows."
---

# DNS Authentication Setup

## SPF Record Setup -- Step by Step

### Step 1: Inventory Every Platform Sending Email As Your Domain

Create a list of EVERY platform that sends email from your domain:
- Marketing ESP (ActiveCampaign, Klaviyo, Mailchimp)
- Cold email tool (Lemlist, Mailshake, Instantly)
- Corporate email (Google Workspace, Zoho)
- Transactional email (SendGrid, SocketLabs, Mailgun)
- CRM notifications (HubSpot, Close)
- Website/ecommerce (Shopify, WordPress contact forms)

### Step 2: Build the SPF Record

**Using MXToolbox SPF Record Generator:**
1. Go to mxtoolbox.com/spf
2. Walk through the survey -- add each sending platform
3. Generator produces the complete TXT record

**Manual construction:**
```
v=spf1 include:_spf.google.com include:emsd1.com include:sendgrid.net ~all
```

**Common include statements:**
| Platform | Include Statement |
|----------|------------------|
| Google Workspace | `include:_spf.google.com` |
| ActiveCampaign | `include:emsd1.com` |
| SendGrid | `include:sendgrid.net` |
| Mailchimp | `include:servers.mcsv.net` |
| Klaviyo | `include:send.klaviyo.com` |
| HubSpot | `include:hubspot.com` |
| Lemlist | `include:_spf.lemlist.com` |

**Rules:**
- One SPF record per domain (multiple records cause failures)
- Order of includes does not matter
- No commas in the actual TXT record
- Use `~all` (soft fail) as default enforcement
- Only use `-all` (strict) when 100% confident everything is correct

### Step 3: Add SPF Record in DNS

1. Log into your DNS host (Cloudflare, GoDaddy, Namecheap)
2. Navigate to DNS management for your domain
3. Add a TXT record:
   - **Host/Name:** `@`
   - **Type:** TXT
   - **Value:** Your complete SPF record
   - **TTL:** Auto or 3600

### Step 4: Verify SPF

1. Go to MXToolbox SPF Record Lookup
2. Enter your domain
3. Confirm: record found, all includes resolve, enforcement policy present
4. Send a test email to Gmail, open "Show Original," confirm SPF: PASS

---

## DKIM Record Setup -- Step by Step

Unlike SPF (one record), DKIM requires a separate TXT record for each sending platform.

### Google Workspace DKIM

1. Go to admin.google.com
2. Navigate to: Apps > Google Workspace > Gmail > Authenticate email
3. Select your domain
4. Click "Generate new record"
5. Copy the selector name (usually `google`) and the DKIM value
6. Add TXT record in DNS:
   - **Host/Name:** `google._domainkey`
   - **Type:** TXT
   - **Value:** (paste the generated value exactly)
7. Return to Google Admin and click "Start authentication"

### ActiveCampaign DKIM

1. Go to Settings > Advanced
2. Select "I will manage my own email authentication"
3. Enter your domain
4. Click "Generate"
5. Copy the DNS record values (selector is `dk`)
6. Add TXT record in DNS:
   - **Host/Name:** `dk._domainkey`
   - **Type:** TXT
   - **Value:** (paste exactly)
7. Return to ActiveCampaign and click "Verify"

### SendGrid / Klaviyo DKIM

These platforms use CNAME records instead of TXT records (allows dynamic key rotation):
1. Follow platform-specific instructions to generate DKIM
2. Add CNAME records (not TXT) in DNS
3. Platform handles key rotation automatically

### DKIM Verification

1. MXToolbox DKIM Lookup: enter `yourdomain.com:selector` (e.g., `acme.com:google`)
2. Confirm: key found, valid, correct length
3. Send test email to Gmail, "Show Original" should show DKIM: PASS
4. Critically: "Authenticated as" must show YOUR domain, not the provider's

**If it shows "via [provider-domain.com]":** Your DKIM is authenticating as the provider. This means the DKIM record for that platform is missing or incorrect in your DNS. Fix immediately.

---

## DMARC Record Setup -- Step by Step

### Prerequisites

- SPF must be fully set up and PASSING
- DKIM must be fully set up and PASSING for every sending platform
- Do NOT add DMARC until both are confirmed

### Step 1: Start with Reporting Mode

Add TXT record in DNS:
- **Host/Name:** `_dmarc`
- **Type:** TXT
- **Value:** `v=DMARC1; p=none; fo=1; rua=mailto:dmarc@yourdomain.com; pct=100`

**Parameter breakdown:**
- `p=none` -- reporting only (no enforcement yet)
- `fo=1` -- report if anything fails (recommended)
- `rua` -- email address for aggregate reports
- `pct=100` -- apply to 100% of emails

### Step 2: Monitor Reports (2-4 Weeks)

- Use MXToolbox to aggregate DMARC reports
- Verify 100% SPF and DKIM pass rate across all sending platforms
- Identify any platforms you missed in SPF/DKIM setup

### Step 3: Escalate to Enforcement

Once 100% pass rate confirmed, update the record:
- **Moderate:** `v=DMARC1; p=quarantine; fo=1; rua=mailto:dmarc@yourdomain.com; pct=100`
- **Strict:** `v=DMARC1; p=reject; fo=1; rua=mailto:dmarc@yourdomain.com; pct=100`

### Alignment Settings

- **Relaxed (default):** Recommended for most setups
- **Strict:** Only needed if you have a custom mail server domain (enterprise-level ESP plans)

**Key insight:** You do NOT need a dedicated sending server for DMARC to pass -- works on shared/base plans at any ESP.

---

## Maildoso Automated DNS Setup

If using Maildoso, all four DNS records (MX, SPF, DKIM, DMARC) are configured automatically. No manual DNS setup required.

**What Maildoso handles:**
- MX records for mail delivery
- SPF record with correct includes
- DKIM signing and record creation
- DMARC policy configuration

**What you still need to do:**
- Set up custom tracking domain (CNAME record)
- Configure redirect from secondary domains to primary domain
- Connect mailboxes to your cold email sending tool

---

## Custom Tracking Domain Setup

### For Lemlist:
1. Add CNAME record in DNS:
   - **Host/Name:** `trail`
   - **Value:** `custom.lemlist.com`
2. In Lemlist: Settings > My custom domain > Configure

### For Other Tools:
1. Check your tool's documentation for the tracking domain value
2. Add CNAME record with your chosen subdomain (e.g., `c`, `track`, `go`)
3. Enable global custom tracking domain in tool settings

---

## Verification Workflow (Post-Setup)

After completing all DNS setup, run this verification sequence:

1. **MXToolbox SPF Lookup** -- Confirm record found, all includes resolve
2. **MXToolbox DKIM Lookup** -- Test each platform's selector
3. **MXToolbox DMARC Lookup** -- Confirm record found, policy set
4. **MXToolbox Blacklist Check** -- Check both domain AND sending IP
5. **Mail-Tester.com** -- Send test email, target 9+/10 score
6. **Gmail "Show Original"** -- Verify SPF PASS, DKIM PASS, DMARC PASS, authenticated as self
7. **Send to all providers** -- Test inbox placement on Gmail, Outlook, Yahoo, Zoho, iCloud

**Expected Mail-Tester scores:**
- 9.3+/10 = Good (most deductions from tracking pixel alt tags)
- Below 8/10 = Investigate authentication or content issues
- Mail-Tester always subtracts 1 point for DKIM check then gives it back (plus bonus) if fully self-authenticated
