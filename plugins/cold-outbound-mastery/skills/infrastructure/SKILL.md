---
name: infrastructure
description: Set up and maintain cold email sending infrastructure. Use when the user needs to configure domains, DNS records (SPF/DKIM/DMARC), email warmup, sending tools, or diagnose deliverability issues. Also use for scaling email infrastructure and domain management. MANDATORY TRIGGERS: deliverability, DNS, SPF, DKIM, DMARC, warmup, email setup, domain setup, inbox placement, spam, blacklist, sender reputation, email infrastructure.
---

# Email Infrastructure & Deliverability

**CHECK FOR PRODUCT MARKETING CONTEXT:** If user mentions testing/demoing a tool or comparing solutions, root advice in data and frameworks rather than product positioning.

---

## Core Philosophy

**Deliverability = Reputation** built on two pillars:
- **TRUST:** Authentication (SPF/DKIM/DMARC), domain age, sending volume strategy, technical correctness
- **VALUE:** Engagement metrics, list quality, content relevance, segmentation discipline

This is NOT a "hack" system—it's sustainable infrastructure built on email provider algorithms and authentication protocols. Expect 30-90 days for full results depending on starting reputation.

---

## Quick Diagnosis: Is This Really a Deliverability Problem?

Low open rates ≠ always deliverability. **Test first to confirm.**

### Proper Testing Protocol
1. Create **brand new email accounts** on 4+ providers (Gmail, Yahoo/AOL, Outlook, iCloud, Zoho Mail, Mail.com)
   - NEVER use your own email (you've whitelisted yourself)
2. Send test emails to these accounts (sample 10+ emails across email types)
3. Check **actual inbox placement**, not just if they arrived
4. Verify **authentication headers** (SPF, DKIM, DMARC status)

### If Not Deliverability, The Real Problem Is:
- **Content quality:** Spammy language, too many links, poor segmentation
- **Engagement:** Sending to non-engaged lists, wrong audience targeting
- **List quality:** Purchased lists, spam traps, invalid addresses, bot-filled forms

---

## Authentication: The 3-Pillar System

All three must be in place for optimal deliverability. Setup takes 1-2 hours total.

### SPF (Sender Policy Framework)
- **What it does:** Proves you own the domain via DNS text record
- **Setup:** Single DNS TXT record per domain
- **Must include:** All platforms sending as your domain (Gmail, Active Campaign, SendGrid, etc.)
- **Tool:** MX Toolbox SPF Record Generator

**Example SPF Record:**
```
v=spf1 include:_spf.google.com include:sendgrid.net include:ac-emsrv.com ~all
```

**Common includes by platform:**
- Google Workspace: `include:_spf.google.com`
- Active Campaign: `include:ac-emsrv.com`
- SendGrid: `include:sendgrid.net`
- MailChimp: `include:servers.mcsv.net`
- Klaviyo: `include:klaviyo.com`

### DKIM (DomainKeys Identified Mail)
- **What it does:** Digitally signs emails with your domain (cryptographic verification)
- **Critical difference from SPF:** One DKIM record per sending platform (not one per domain)
  - Gmail gets one DKIM selector, Active Campaign gets another, SendGrid gets another
- **Record format:** `[selector]._domainkey.yourdomain.com`
- **Tool:** Platform-specific setup (each platform provides DKIM records)

**Common platforms and selectors:**
- **Active Campaign:** Selector from dashboard → Add TXT record to DNS
- **Google Workspace:** Selector from admin console → Add TXT record
- **SendGrid:** Use CNAME setup (easier than TXT) → Add CNAME to DNS
- **Klaviyo:** Selector from account settings → Add TXT record

**DKIM Verification:**
- Gmail: Open email → Show Original → Find `DKIM: pass with domain yourdomain.com`
- Bad result: `DKIM: pass with domain ac-emsrv.com` (passing with provider domain, not yours—PROBLEM)

### DMARC (Domain-based Message Authentication, Reporting & Conformance)
- **What it does:** Combines SPF and DKIM, sets enforcement policy
- **REQUIREMENT:** Must have SPF and DKIM fully working BEFORE setting up DMARC
- **Setup:** Single DNS TXT record at `_dmarc.yourdomain.com`
- **Tool:** MX Toolbox DMARC Record Generator

**Policy Options:**
- `p=none` (monitoring only): Tells receivers "I'm monitoring but not enforcing yet"
- `p=quarantine` (cautious enforcement): Move suspicious emails to spam folder
- `p=reject` (strict enforcement): Reject emails that don't pass SPF/DKIM

**Recommended progression:**
1. Start with `p=none` for 1-2 weeks (monitor reports, verify 100% pass rate)
2. Move to `p=quarantine` for 1-2 weeks
3. Upgrade to `p=reject` once confident all legitimate emails pass

**Example DMARC Records:**

*Monitoring phase:*
```
v=DMARC1;p=none;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;
```

*Enforcement phase:*
```
v=DMARC1;p=reject;rua=mailto:dmarc-reports@yourdomain.com;fo=1;pct=100;aspf=relaxed;adkim=relaxed;
```

**DMARC Parameters:**
- `v=DMARC1` - Version (always this)
- `p=` - Policy (none, quarantine, or reject)
- `rua=` - Email address for aggregate reports
- `fo=1` - Report if anything fails (0=report only if all fail; 1=report if any fails)
- `pct=100` - % of emails to apply policy to (100=all)
- `aspf=relaxed` - SPF alignment (relaxed=domain matches somewhere; strict=exact match)
- `adkim=relaxed` - DKIM alignment (relaxed=domain matches somewhere; strict=exact match)

**DMARC Alignment Concept:**
- Relaxed: Email passes SPF OR DKIM with your domain (email passes if either one succeeds)
- Strict: Email passes SPF AND DKIM with your domain (both must succeed)
- Use relaxed unless you have 100% control over all sending sources

---

## Email Warmup: Mandatory Pre-Step

**Why it's critical:** New inboxes sending immediate cold email campaigns = spam folder. Legitimate senders build history gradually.

### WarmupInbox (Recommended)
- **Cost:** Free or $9/month (paid recommended for faster ramp)
- **Setup time:** ~2 hours
- **Warmup duration:** 2-3 weeks minimum before campaigns
- **What it does:** Automatically sends emails between your inbox and other real inboxes to build sender reputation with Google

### Warmup Schedule
**Starting emails:** 15 emails on day 1
**Daily ramp:** Increase by 5-10 emails per day
**Maintenance:** Keep running during campaigns
**Maximum:** Don't exceed 30-40 emails/day total (including warmup + campaigns)

### Setup Steps
1. Create WarmupInbox account with your new email
2. Enable Gmail settings: Allow less secure apps, Allow per-user outbound gateways, Enable IMAP
3. **WAIT 1 HOUR** before connecting warmup tool (critical for IMAP sync)
4. Connect WarmupInbox to Gmail via OAuth
5. Configure schedule: Start 15/day, ramp 5-10/day increase
6. Monitor dashboard until you maintain max capacity for 1-2 weeks with zero spam complaints

---

## Sending Volume Ramp (New Domain or IP)

**Use when:** Starting new domain, new sending IP, or recovering from deliverability damage

**30-Day Progressive Ramp Formula:**
- Week 1 (days 1-7): 50-100 emails/day (engaged segment only)
- Week 2 (days 8-14): 150-250 emails/day
- Week 3 (days 15-21): 300-500 emails/day
- Week 4 (days 22-30): 500-1000 emails/day
- Post-week 4: Can increase volume further if metrics healthy

**Rules:**
- Only send to engaged lists (high open rate, recent activity)
- Never skip this for new domains—damages reputation permanently
- Monitor bounce rate and spam complaints daily
- If bounce rate exceeds 2%, pause volume increase and clean list

---

## Tools & Platforms Reference

**See references/tools-and-platforms.md for:**
- Complete tool matrix with pricing and configs
- Platform-specific DKIM/SPF setup instructions
- Warmup tool comparisons
- Lead generation tools
- List validation tools
- Testing/diagnostics tools

**Essential baseline setup cost:** ~$200-300/month
- Domain: $12-15/year
- Google Workspace: $6-14/month/user
- Warmup tool: $9/month
- Email campaign tool (MailShake/LemList): $59-99/month
- Lead generation/validation: Variable

---

## Critical Mistakes to Avoid

1. **Buying email lists**
   - High spam trap probability
   - Instant reputation damage
   - Not worth any short-term gains

2. **Sending to non-engaged at scale**
   - Signals to providers that people aren't interested
   - Damages domain reputation
   - Better to have 5,000 engaged than 100,000 disengaged

3. **Relying on platform reputation instead of domain reputation**
   - You're responsible for your domain reputation
   - Poor list building or segmentation = your problem, not platform's
   - High-deliverability platforms won't save bad practices

4. **Not warming up new inboxes**
   - Sending 500 cold emails day 1 = spam folder
   - Warmup isn't optional—it's mandatory infrastructure

5. **Ignoring engagement signals**
   - If open rate is legitimately low AND list is engaged, that's a content problem
   - If open rate is low AND list is disengaged, archive that segment

6. **Failing to test authentication**
   - Set up SPF/DKIM/DMARC but never verify it works
   - Test with MX Toolbox and check headers before sending
   - Don't assume it's correct because you added the records

---

## Deliverability Testing & Diagnosis

**See references/troubleshooting.md for:**
- Detailed diagnostic flowchart
- Common issues and solutions (PROMO tab placement, bounces, unsubscribes)
- Blacklist recovery procedures
- Content analysis with Mail-Tester
- Sender reputation monitoring
- Domain rehabilitation options

---

## Monitoring & Maintenance

**Weekly:**
- Check bounce rate (should be <2%)
- Monitor spam complaints (should be <0.1%)
- Verify warmup running smoothly (if applicable)

**Monthly:**
- Review engagement metrics (open, click, unsubscribe rates)
- Check Sender Score (senderscore.org, 0-100 scale)
- Segment non-engaged people and remove them
- Validate authentication records still working

**Quarterly:**
- Send 10 test emails to fresh accounts (same as initial audit)
- Run through Mail-Tester (aim for 9+/10)
- Check blacklist status (MX Toolbox)
- Clean list with NeverBounce
- Run NeverBounce on entire list

**Annually:**
- Full deliverability audit (same as initial protocol)
- Review all authentication records
- Assess domain age and reputation trajectory

---

## Key Benchmarks

| Metric | Target |
|--------|--------|
| Bounce Rate | <2% |
| Spam Complaint Rate | <0.1% |
| Unsubscribe Rate | 0.2-0.5% |
| Deliverability Rate | >95% |
| Authentication Pass Rate | 100% SPF + 100% DKIM |
| Warmup Spam Complaints | 0 |

**Open rate varies by industry:**
- B2B SaaS: 15-25%
- E-commerce high-ticket: 10-20%
- E-commerce consumable: 5-15%
- Info products/memberships: 20-30%+

---

## Pre-Campaign Infrastructure Checklist

Before sending any cold email campaign:

- [ ] Domain registered and domain age at least 1-2 weeks (if new)
- [ ] SPF record created and validated with MX Toolbox
- [ ] DKIM record created for each sending platform and validated
- [ ] DMARC record created (start with p=none)
- [ ] Test emails sent to 4+ providers and inbox-verified
- [ ] Authentication headers checked (SPF pass, DKIM pass, DMARC pass expected)
- [ ] Email content tested through Mail-Tester (9+/10 score)
- [ ] List cleaned with NeverBounce (remove invalid/risky/trap addresses)
- [ ] Warmup tool active and running for 2-3+ weeks
- [ ] Email signature created and footer included
- [ ] Unsubscribe link verified functional
- [ ] Welcome sequence drafted (5-7 emails minimum)

---

## When to Use This Skill

**Exact trigger scenarios:**

✓ User asks: "How do I set up SPF/DKIM/DMARC?"
✓ User asks: "Why are my emails going to spam?"
✓ User asks: "What's email warmup and why do I need it?"
✓ User asks: "How do I configure my domain for cold email?"
✓ User asks: "What tools do I need for email infrastructure?"
✓ User asks: "How long does it take to warm up an inbox?"
✓ User asks: "I'm getting bounces—how do I fix it?"
✓ User asks: "Am I blacklisted? How do I recover?"
✓ User asks: "What's my sender score and why does it matter?"
✓ User mentions scaling email volume or setting up multiple domains

---

## Reference Files

- **dns-setup.md** - Complete SPF, DKIM, DMARC configuration guides with exact record values
- **warmup-protocols.md** - Warmup schedules, tools, settings, volume ramp formulas
- **tools-and-platforms.md** - Every tool mentioned with configs, setup instructions, and pricing
- **troubleshooting.md** - Deliverability diagnostics, blacklist recovery, spam avoidance strategies
