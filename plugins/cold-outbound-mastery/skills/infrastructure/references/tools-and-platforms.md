# Tools & Platforms: Complete Reference Guide

Comprehensive database of every tool mentioned with exact setup instructions, configurations, and pricing.

---

## Email Hosting & Accounts

### Google Workspace
- **Purpose:** Email hosting for custom domain
- **Cost:** $6-14/month per user (varies by plan)
- **Plans:**
  - Business Starter: $6/month (30 GB storage)
  - Business Standard: $12/month (2 TB storage)
  - Business Plus: $18/month (5 TB storage)
- **Setup:** domains.google.com → Create account → Verify domain → Add users

**For cold email:**
- Use Business Starter ($6/month) minimum
- Create one account per sending domain (firstname@yourdomain.com)
- Enable IMAP for warmup tool integration
- Enable less secure apps (if using warmup/cold email tools)

**Configuration for Cold Email:**
1. Go to admin.google.com
2. Security → Authentication → Enable DKIM signing
3. Set up 2-factor authentication (recommended)
4. Create app passwords (for third-party tools)
5. Enable IMAP (Settings → Forwarding & POP/IMAP)

### Zoho Mail
- **Purpose:** Alternative to Google Workspace (cheaper, more privacy-focused)
- **Cost:** $2/month per user (free tier available)
- **Best for:** Budget-conscious users, privacy
- **Setup:** zoho.com/mail → Create account → Add domain

**For cold email:**
- Works with most warmup tools
- Enable POP/IMAP in settings
- Less common than Google Workspace (some tools may not support)

---

## Email Campaign & Sending Tools

### MailShake
- **Purpose:** Cold email campaigns with personalization
- **Cost:** $59/month (10,000 credit/month = ~10,000 sends)
- **Features:**
  - Easy lead import (CSV)
  - Built-in Mail-Tester integration
  - Follow-up sequences (auto follow-ups)
  - Template library
  - Open/click tracking
  - A/B testing
- **Setup Time:** 30 minutes
- **Best for:** Beginners, all-in-one simplicity

**Setup Steps:**
1. Go to coldemailuniversity.com/mailshake (affiliate link)
2. Sign up with email
3. Verify email
4. Connect email account (Gmail OAuth)
5. Import CSV with leads
6. Create email sequence
7. Test emails before sending
8. Set send parameters:
   - Daily limit: 50-100/day for new accounts
   - Send time window: 9 AM - 5 PM
   - Timezone: Match recipient timezone if available
9. Start campaign

**Configuration Tips:**
- Start with 50/day even if tool allows more (safer warmup)
- Enable open tracking (helps DKIM signing)
- Use native sequences, not smart sequences (more reliable)
- Test 5-10 emails before full send
- Monitor dashboard daily for bounce rate

### LemList
- **Purpose:** Advanced cold email campaigns with personalization
- **Cost:** $99/month (1,500 sends/month, pay-per-send overage)
- **Features:**
  - Advanced personalization (pull dynamic variables)
  - Custom tracking domain (better DKIM signing)
  - Email warm-up built-in
  - A/B testing
  - CRM integration
  - More advanced than MailShake
- **Setup Time:** 45 minutes (more complex)
- **Best for:** Experienced cold emailers, advanced personalization

**Setup Steps:**
1. Go to lemlist.com
2. Sign up with email
3. Connect email account (Gmail OAuth)
4. Setup custom domain:
   - Name: trail
   - Type: CNAME
   - Value: custom.lemlist.com
   - Add to DNS (in your registrar)
5. Verify domain in LemList
6. Create campaign with variables:
   - {{firstName}}
   - {{companyName}}
   - {{custom_field}}
7. Import leads with variables
8. Configure send:
   - Daily limit: 50-150/day
   - Send time: 9 AM - 5 PM
   - Timezone: Auto-adjust by recipient
9. Start campaign

**Configuration Tips:**
- Use custom domain for better deliverability
- Enable activity tracking (opens, clicks)
- Test with 5 emails first
- Use built-in warmup if not using separate tool
- Slower send rate (LemList rate limits) prevents spam folder

### Instantly
- **Purpose:** All-in-one platform (warmup + cold email)
- **Cost:** $29/month (includes warmup + sending)
- **Features:**
  - Built-in warmup (faster ramp)
  - Cold email sending
  - Follow-up sequences
  - Team collaboration
  - CRM-like features
- **Best for:** Teams, all-in-one solution, faster warmup

**Comparison:** All-in-one (warmup + sending) vs. separate tools

---

## Email Warmup Tools

### WarmupInbox (Recommended)
- **Purpose:** Warm up new inboxes for cold email
- **Cost:** Free or $9/month (paid recommended)
- **Duration:** 2-3 weeks
- **Features:**
  - Auto ramp schedule
  - Natural replies
  - Analytics dashboard
  - Multiple inbox support (separate accounts)
- **Setup Time:** 2 hours
- **Best for:** Beginners, cost-effective

**Setup:** See warmup-protocols.md for complete guide

### Hunter Warmup
- **Purpose:** Premium warmup with detailed control
- **Cost:** $20/month
- **Duration:** 2-3 weeks
- **Features:**
  - More control over warmup behavior
  - Detailed analytics
  - Multiple inbox management
- **Best for:** More technical users, custom warmup behavior

### RocketReach Warmup
- **Purpose:** Warmup integrated with lead database
- **Cost:** $50/month+ (includes RocketReach database)
- **Duration:** 2-3 weeks
- **Features:**
  - Lead database (250M+ contacts)
  - Warmup integrated
  - One-stop solution
- **Best for:** If already using RocketReach for leads

---

## Lead Generation & Data Tools

### UpLead
- **Purpose:** Lead generation (B2B executive contacts)
- **Cost:** Pay-per-lead (~$0.50-2.00/lead depending on data)
- **Database:** 250M+ business executives
- **Features:**
  - Real-time verification
  - Fresh data (updated regularly)
  - Industry/role filters
  - Self-service platform
- **Setup Time:** 20 minutes
- **Best for:** Quick lead acquisition, verified data

**How to Use:**
1. Go to coldemailuniversity.com/uplead
2. Sign up or log in
3. Search filters:
   - Company name or industry
   - Job title
   - Location
   - Company size
   - etc.
4. Review results (shows quality score)
5. Export CSV
6. Upload to email tool (MailShake, LemList, etc.)

**Cost Calculation:**
- 100 leads at $1.50/lead = $150
- Cold email benchmark: 15% response rate
- 100 leads × 15% = 15 responses
- Cost per response: $150 / 15 = $10

### Clearbit (Alternative)
- **Purpose:** B2B data enrichment
- **Cost:** API pricing (~$0.50/lookup)
- **Best for:** Enriching existing leads with company/role data

### Hunter (Email Finder)
- **Purpose:** Find business email addresses
- **Cost:** Free tier available, $49+/month paid
- **Features:**
  - Domain email format finder
  - Email verification
  - Bulk search
- **Best for:** If you have names but not emails

### LinkedIn Sales Navigator (Data Source)
- **Purpose:** Identify prospects (not direct lead export, but sourcing)
- **Cost:** $65+/month
- **Best for:** B2B prospecting, building custom lists
- **Note:** Manual process; requires exporting names to other tools for email finding

---

## List Validation & Cleaning

### NeverBounce
- **Purpose:** Clean email lists, remove invalid/spam trap addresses
- **Cost:** $25-100/month depending on volume, or pay-per-email
- **Features:**
  - Identifies invalid emails
  - Detects spam traps
  - Removes duplicates
  - Classifies: Valid / Invalid / Risky
- **Setup Time:** 15 minutes

**How to Use:**
1. Export list from email tool (CSV format)
2. Go to neverbounceto.com
3. Upload CSV file
4. Run validation
5. Download cleaned list (valid emails only)
6. Remove risky/invalid from tool
7. Import cleaned list back

**Expected Results:**
- 2-10% of list typically classified as risky/invalid
- Immediate bounce rate improvement
- Better inbox placement

**Cleaning Process:**
1. Before first campaign: Full list cleaning
2. During campaigns: Clean bounces immediately (hard bounces)
3. Monthly: Re-clean engaged segments

### Email List Validation Services
- **Verify-Email.org:** API-based validation
- **ZeroBounce:** Similar to NeverBounce, $19-75/month
- **BriteVerify:** Enterprise option, higher cost

**Recommendation:** NeverBounce for simplicity and accuracy

---

## Testing & Diagnostics

### Mail-Tester (Recommended)
- **Purpose:** Check email spamminess score
- **Cost:** Free
- **Use:** Check spam score of cold email template
- **Target:** 9+/10 score for optimal deliverability

**How to Use:**
1. Go to mail-tester.com
2. It shows a unique email address (copy it)
3. Send your test email to that address
4. Wait 1 minute
5. Return to Mail-Tester
6. Click "Check Results"
7. See spamminess score and issues
8. Common issues:
   - Missing SPF/DKIM/DMARC
   - Spammy words (avoid: "free", "limited time", "act now", etc.)
   - Too many links
   - HTML errors
   - Missing unsubscribe link

**Target Score:** 9-10/10
**Acceptable:** 8/10
**Needs Work:** <8/10

### MX Toolbox (SPF/DKIM/DMARC Validation)
- **Purpose:** Validate authentication records
- **Cost:** Free
- **Use:** Verify SPF, DKIM, DMARC before sending
- **Tools:**
  - SPF checker: mxtoolbox.com/spf.aspx
  - DKIM checker: mxtoolbox.com/dkim.aspx
  - DMARC checker: mxtoolbox.com/dmarc.aspx
  - Blacklist checker: mxtoolbox.com/blacklist.aspx

**How to Use SPF:**
1. Go to mxtoolbox.com/spf.aspx
2. Enter domain: yourdomain.com
3. Click "Check SPF"
4. Should show: ✓ SPF record is valid
5. Verify all platforms listed are included

### GlockApps
- **Purpose:** Detailed email content analysis
- **Cost:** Free tier, paid plans available
- **Features:**
  - Deeper analysis than Mail-Tester
  - Rendering preview
  - Detailed spam assessment
- **Best for:** Detailed diagnostics

### Sender Score
- **Purpose:** Monitor overall domain reputation
- **Cost:** Free
- **Website:** senderscore.org
- **Scale:** 0-100 (100 is best)
- **What It Shows:**
  - Domain reputation
  - Bounce rate
  - Complaint rate
- **Target:** 80+ is good, 70+ acceptable

**Check Weekly During Campaigns:**
1. Go to senderscore.org
2. Enter domain: yourdomain.com
3. See reputation score (0-100)
4. Review bounce/complaint rates
5. If score declining, review sending practices

### Gmail Postmaster Tools
- **Purpose:** Google-specific deliverability metrics
- **Cost:** Free (requires setup)
- **Setup:** Must authenticate domain
- **Shows:**
  - Bounce rate (Gmail users)
  - Complaint rate (Gmail users)
  - Authentication pass rates (SPF/DKIM/DMARC)
  - IP reputation (if applicable)
- **Access:** postmaster.google.com

**Setup:**
1. Go to postmaster.google.com
2. Add domain (will require auth token)
3. Verify ownership
4. Wait 24 hours for data to appear
5. Monitor bounce/complaint rates

---

## Domain & DNS Services

### Google Domains
- **Purpose:** Domain registrar + DNS hosting
- **Cost:** $12-15/year per domain
- **Features:**
  - Easy DNS management
  - Privacy protection included
  - Auto-renewal
- **Best for:** Simplicity, integrated with Google ecosystem

**Setup:**
1. Go to domains.google.com
2. Search for domain
3. Purchase (.com, .io, etc.)
4. Create email accounts with Google Workspace
5. Manage DNS from Google Domains dashboard

### Cloudflare
- **Purpose:** DNS hosting (better performance, more features)
- **Cost:** Free tier, $20+/month paid (but free usually sufficient)
- **Features:**
  - Faster DNS propagation
  - Email forwarding
  - Security features
  - Global CDN
- **Best for:** Performance-focused, advanced DNS features

**Setup:**
1. Go to cloudflare.com
2. Sign up
3. Add domain (point nameservers from registrar to Cloudflare)
4. Import DNS records
5. Manage SPF/DKIM/DMARC from Cloudflare dashboard

### GoDaddy
- **Purpose:** Domain registrar + DNS hosting (less technical)
- **Cost:** Varies, typically $8-12/year domain
- **Best for:** Beginners, all-in-one with hosting
- **Note:** More expensive than Google Domains, slower support

### Namecheap
- **Purpose:** Budget domain registrar + DNS hosting
- **Cost:** ~$8/year domains, no WHOIS privacy upsell (included)
- **Best for:** Budget-conscious
- **Note:** Good value, reliable DNS

---

## Content Planning & Calendar

### Google Calendar (Free)
- **Purpose:** Content calendar
- **Cost:** Free
- **Use:** Plan email send dates, content themes
- **Setup:** Create calendar → Share with team

### Google Sheets (Free)
- **Purpose:** Email content planning spreadsheet
- **Cost:** Free
- **Use:** Track subject lines, body copy, send dates, results
- **Setup:** Create sheet → Add columns for planning

### CoSchedule
- **Purpose:** Professional content calendar
- **Cost:** $29/month
- **Features:**
  - Team collaboration
  - Auto-optimization
  - Calendar view
- **Best for:** Teams wanting professional planning tool

---

## Reporting & Analytics

### MX Toolbox DMARC Reporter
- **Purpose:** Aggregate DMARC reports
- **Cost:** Varies (dmarcian, agari are alternatives)
- **Features:**
  - Aggregates weekly DMARC reports
  - Visual breakdown
  - Failure analysis
- **Best for:** DMARC monitoring

### Dmarcian (Alternative)
- **Purpose:** Advanced DMARC reporting
- **Cost:** $15+/month
- **Features:**
  - Detailed failure analysis
  - Alignment insights
  - Threat analysis

---

## Complete Tool Stack: Budget-Friendly Setup

**Minimum viable cost (~$200-300/month):**

| Tool | Cost | Purpose |
|------|------|---------|
| Google Workspace (1 user) | $6/month | Email hosting |
| Google Domains | $1/month (annual) | Domain registration |
| WarmupInbox | $9/month | Email warmup |
| MailShake | $59/month | Cold email sending |
| UpLead (20 leads/month) | $40/month avg | Lead generation |
| NeverBounce | $25/month | List cleaning |
| **Total** | **~$140/month** | Complete system |

**Optional additions:**
- LemList ($99/month): More advanced alternative to MailShake
- Instantly ($29/month): All-in-one (replaces MailShake + WarmupInbox)
- Hunter ($49/month): Email finding (if not using UpLead)

---

## Tool Selection Decision Tree

**Question 1: Budget?**
- Limited: WarmupInbox ($9) + MailShake ($59) = $68/month
- Moderate: Add NeverBounce ($25) + UpLead (~$40) = $132/month
- Higher: Add LemList ($99) + premium services

**Question 2: Needs?**
- Beginner: MailShake (simple, all-in-one)
- Advanced personalization: LemList
- All-in-one with warmup: Instantly
- Maximum simplicity: Instantly

**Question 3: Volume?**
- 0-1,000 emails/month: MailShake free tier or Instantly
- 1,000-10,000 emails/month: MailShake standard ($59)
- 10,000+ emails/month: LemList + dedicated warmup

---

## Configuration Checklist: Complete Setup

**Before First Campaign:**

Infrastructure:
- [ ] Domain registered (1-2 weeks old minimum)
- [ ] Google Workspace account created
- [ ] SPF record added to DNS and validated
- [ ] DKIM records added for each sending platform
- [ ] DMARC record added (start with p=none)
- [ ] All records verified with MX Toolbox

Warmup:
- [ ] WarmupInbox account created
- [ ] Gmail IMAP enabled (waited 1 hour)
- [ ] WarmupInbox connected to Gmail
- [ ] Warmup schedule configured
- [ ] Dashboard monitoring 2-3 weeks

Email Tool:
- [ ] MailShake/LemList account created
- [ ] Email account connected
- [ ] Test email sent and verified delivery
- [ ] Email content tested through Mail-Tester (9+/10)

Leads:
- [ ] Lead list source identified (UpLead, manual research, LinkedIn, etc.)
- [ ] Leads exported to CSV
- [ ] List cleaned with NeverBounce
- [ ] 100-500 leads imported to email tool
- [ ] Leads have email addresses and basic info

Content:
- [ ] Email template created
- [ ] 3-5 follow-up emails written
- [ ] Subject lines tested (A/B)
- [ ] Unsubscribe link verified
- [ ] Email signature created

Monitoring:
- [ ] Sender Score bookmarked (senderscore.org)
- [ ] MX Toolbox bookmarked
- [ ] Mail-Tester bookmarked
- [ ] Gmail Postmaster Tools set up
- [ ] Daily monitoring routine established

---

## Quick Reference: Essential URLs

| Service | URL |
|---------|-----|
| MailShake | mailshake.com (or affiliate link) |
| LemList | lemlist.com |
| WarmupInbox | warmupinbox.com |
| UpLead | uplead.com |
| NeverBounce | neverbounceto.com |
| Mail-Tester | mail-tester.com |
| MX Toolbox | mxtoolbox.com |
| Sender Score | senderscore.org |
| Gmail Postmaster | postmaster.google.com |
| Google Domains | domains.google.com |
| Google Workspace | workspace.google.com |
| Cloudflare | cloudflare.com |
