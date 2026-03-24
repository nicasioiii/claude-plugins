# Deliverability Troubleshooting & Diagnostics

Step-by-step guide to diagnosing and fixing deliverability issues.

---

## Diagnostic Flowchart

```
PROBLEM: Emails not arriving in inbox
│
├─→ Step 1: Verify it's really a deliverability problem
│   ├─ Test: Send to fresh accounts (Gmail, Yahoo, Outlook, iCloud)
│   ├─ If arrives in primary inbox: NOT a deliverability issue
│   └─ If arrives in spam/promo: YES, continue troubleshooting
│
├─→ Step 2: Check authentication
│   ├─ SPF: Run MX Toolbox SPF check (should show ✓ valid)
│   ├─ DKIM: Check email headers (should show "DKIM: pass with yourdomain.com")
│   ├─ DMARC: Run MX Toolbox DMARC check (should show ✓ valid)
│   └─ If any fail: Fix authentication (see dns-setup.md)
│
├─→ Step 3: Check email content
│   ├─ Run through Mail-Tester (should be 9+/10)
│   ├─ Common issues: Spammy words, too many links, HTML errors
│   └─ If score <8: Fix content issues (see Content Audit section)
│
├─→ Step 4: Check list quality
│   ├─ Run through NeverBounce
│   ├─ Remove invalid/risky addresses
│   ├─ If bounce rate >2%: List is problem
│   └─ If bounce rate <2%: List is okay
│
├─→ Step 5: Check volume strategy
│   ├─ Are you ramping gradually?
│   ├─ Did you warm up inbox first (2-3 weeks)?
│   ├─ If no: Start over with warmup
│   └─ If yes: Reduce volume and test
│
└─→ Step 6: Check sender reputation
    ├─ Check Sender Score (senderscore.org)
    ├─ Check blacklist status (MX Toolbox)
    ├─ If on blacklist: Request delisting
    └─ If reputation poor: Implement recovery plan
```

---

## Common Issues & Solutions

### Issue 1: Emails Going to PROMO Tab (Gmail)

**Symptoms:**
- Emails arrive in "Promotions" tab instead of "Primary" inbox
- High volume of emails to unengaged recipients
- Promotional/salesy language dominance

**Root Causes:**
1. Content too promotional (too many CTAs, links)
2. Sending to non-engaged segment (inactive list)
3. High link density
4. Lacks personal, conversational tone

**Solutions (In Order of Impact):**

**1. Segment List (MOST IMPORTANT)**
- Don't send to entire list at once
- Identify engaged segment (recent openers, clickers)
- Send ONLY to engaged segment
- Non-engaged: Archive or soft-delete

**2. Reduce Link Density**
- Remove unnecessary links
- Target: 0-1 links per email (cold email benchmark is 0 links)
- Every link signals: "This is promotional"

**3. Increase Value Content**
- 60% educational/value emails
- 40% sales/CTA emails
- Ratio: 6 value emails, then 4 CTAs

**4. Soften Sales Language**
- Avoid: "Limited time", "Act now", "Don't miss out", "Exclusive"
- Use: Conversational, question-based, consultative tone
- Example: "Would love to chat about..."
- Avoid: "You need to do X to succeed"

**5. Improve Email Authentication**
- Verify DKIM is passing with your domain (not provider domain)
- Ensure DMARC p=reject is set
- Gmail respects authentication as signal of legitimacy

**Testing:**
1. Make changes to content/segmentation
2. Send 10 test emails to Gmail accounts
3. Check actual folder placement (not just "arrived")
4. If now in Primary: Increase volume and monitor
5. If still in Promo: Review changes, identify what worked

**Timeline:** 2-3 weeks to see improvement after changes

---

### Issue 2: High Bounce Rate

**Symptoms:**
- Bounce rate >2% (unacceptable)
- Many "address not found" errors
- Sudden spike in bounces

**Types of Bounces:**

**Hard Bounce (Permanent):**
- Invalid email format: john@example (missing .com)
- Domain doesn't exist: @fakebusiness.com
- User doesn't exist: john@realdomain.com (but John never had account)
- Mailbox closed: User deleted their email account
- **Action:** Remove immediately, never send again

**Soft Bounce (Temporary):**
- Mailbox full: User's quota exceeded
- Server down: Temporary connectivity issue
- Message too large: Email size exceeds limit
- **Action:** Retry after 24 hours, then remove if persists

**Root Causes:**
1. Purchased email list (contains invalid addresses)
2. Old list (addresses have closed accounts)
3. Bot-filled forms (fake addresses submitted)
4. Data entry errors (manual list building)

**Solutions:**

**Immediate Actions:**
1. Remove hard bounces from list immediately
2. Don't retry hard bounces
3. Soft bounces: Retry in 24 hours, then remove

**Prevention:**
1. Clean list BEFORE sending:
   - Use NeverBounce before first campaign
   - Upload to NeverBounce, download cleaned version
   - Expected cleanup: 2-10% invalid addresses

2. Source list quality:
   - Use UpLead (verified contacts)
   - LinkedIn Sales Navigator (manual list)
   - Never buy pre-made lists
   - Research manually (slower, but cleaner)

3. Form validation (if collecting emails):
   - Verify email format on form submission
   - Send verification email to confirm address
   - Use double opt-in (requires confirmation)

**Cleanup Process:**
1. Export current list from email tool
2. Upload to NeverBounce
3. Run validation
4. Download cleaned list
5. Import cleaned list back
6. Remove invalid addresses from tool
7. Resume sending

**Expected Results:**
- Bounce rate drops from 3-5% to <1%
- Improved deliverability immediately
- Better sender reputation

---

### Issue 3: Blacklist (RBL) Listing

**Symptoms:**
- MX Toolbox blacklist check shows RED
- Emails rejected by major providers
- Getting "IP/domain on blacklist" rejections

**Major Blacklists (In Order of Importance):**
1. **Spamhaus ZEN** (most important)
2. **Spamcop** (medium importance)
3. **SORBS** (less critical for major providers)

**Root Causes:**
1. High spam complaint rate
2. Sending to spam trap addresses
3. Previous owner used domain for spam
4. Shared IP address (standard ESP plan) has bad reputation

**Solutions:**

**If You're Listed (Emergency Protocol):**

1. **Stop all sends immediately** (this is important)
   - Don't send another email until resolved
   - Continued sends worsen reputation

2. **Investigate root cause:**
   - Review recent list: Any new acquisitions?
   - Review recent content: Too spammy?
   - Review complaints: Any spike?
   - Check if you purchased list recently

3. **Fix the issue:**
   - Clean list with NeverBounce (remove spam traps)
   - Reduce sending volume by 50%
   - Review email content (Mail-Tester score)
   - Segment to engaged only

4. **Request delisting:**
   - Spamhaus: spamhaus.org/lookup → Delisting request
   - Spamcop: spamcop.net → Reporting system
   - Provide description of issue and how you fixed it

5. **Monitor removal:**
   - Check MX Toolbox daily (every 24 hours)
   - Takes 24-72 hours typically (can take week in some cases)
   - Once removed, monitor for re-listing

6. **Resume sending carefully:**
   - Start with 50 emails/day (half normal)
   - Monitor bounce/complaint rate
   - If healthy, ramp back to normal
   - If issues return, investigate again

**Prevention:**
1. Monitor blacklist status monthly
2. Keep bounce rate <2% and complaints <0.1%
3. Don't purchase email lists
4. Clean list before large sends
5. Use engaged segment only

**Timeline:** 24-72 hours to delisting (sometimes longer)

---

### Issue 4: DKIM Signing Failures

**Symptoms:**
- Email headers show: "DKIM: pass with domain ac-emsrv.com" (not your domain)
- DKIM passing with provider domain, not your domain
- MX Toolbox shows DKIM failing

**Root Causes:**
1. DKIM record not set up in DNS
2. DKIM record set up for wrong platform
3. Platform not configured to sign with your domain
4. DKIM record has typo or is incomplete

**Solutions:**

**Step 1: Verify DKIM Record in DNS**
1. Use MX Toolbox: mxtoolbox.com/dkim.aspx
2. Enter selector and domain: `default._domainkey.yourdomain.com`
3. Should show: ✓ DKIM record is valid
4. If shows: ✗ Not found
   - Record may not be added to DNS yet (24-48 hour propagation)
   - Record may be added to wrong registrar
   - Record selector name may be wrong

**Step 2: Verify Platform Configuration**
1. Go to sending platform (Active Campaign, SendGrid, etc.)
2. Check domain authentication settings
3. Verify domain is set to yours (not platform domain)
4. Verify DKIM selector matches what's in DNS

**Step 3: Check Email Headers**
1. Open test email in Gmail
2. Click menu → Show Original
3. Search for: "DKIM: pass"
4. Should show: `DKIM: pass with domain yourdomain.com`
5. If shows: `DKIM: pass with domain sendgrid.net` = WRONG (using provider domain)

**How to Fix:**

**For Active Campaign:**
1. Go to Settings → Domains
2. Click your domain
3. Verify DKIM is enabled
4. Copy exact DKIM record values
5. Go to DNS registrar
6. Add TXT record with exact values
7. Wait 24-48 hours
8. Verify with MX Toolbox

**For SendGrid:**
1. Go to Settings → Sender Authentication
2. Click "Authenticate Domain"
3. Ensure domain is your domain (not subdomain)
4. Copy CNAME values
5. Add to DNS
6. Return to SendGrid and verify
7. Wait 24-48 hours for full authentication

**For Google Workspace:**
1. Go to admin.google.com
2. Security → Authenticate Domain
3. Enable DKIM signing
4. Copy selectors and keys
5. Add to DNS
6. Wait 24-48 hours for authentication

**Test Verification:**
1. Send test email from platform
2. Check headers (Gmail: Show Original)
3. Verify DKIM passes with yourdomain.com
4. Run Mail-Tester to confirm score improves

---

### Issue 5: SPF Alignment Issues

**Symptoms:**
- MX Toolbox shows SPF failing
- Email marked as failing SPF check
- Too many includes (SPF limit: 10 lookups)

**Root Causes:**
1. SPF record has typo
2. Too many includes (exceeds 10 DNS lookups)
3. Circular includes (platform A includes platform B includes A)

**Solutions:**

**Too Many Includes (Most Common):**
- SPF has hard limit: 10 DNS lookups maximum
- Adding 12+ platforms = exceeds limit
- Includes that count: Each `include:` statement

**How to Fix SPF Limit:**
1. Count your includes:
   ```
   v=spf1 include:_spf.google.com include:sendgrid.net
   include:ac-emsrv.com include:servers.mcsv.net
   include:klaviyo.com ~all
   ```
   = 5 includes (within limit)

2. If exceeds 10:
   - Remove unused platforms (are you still sending via MailChimp?)
   - Use CNAME instead of include (some platforms allow this)
   - Consolidate platforms (SendGrid handles transactional + marketing)
   - Create subdomain for additional platforms

3. Update SPF record with fewer includes
4. Verify with MX Toolbox

**SPF Typo Fix:**
1. Check for common mistakes:
   - Missing `v=spf1` at start
   - Wrong platform include name
   - Extra spaces or formatting
2. Use MX Toolbox SPF Generator to rebuild record
3. Replace record in DNS
4. Verify with MX Toolbox

---

### Issue 6: Low Open Rate (Content Problem, Not Deliverability)

**Symptoms:**
- Open rate <5% (much lower than expected)
- BUT emails arrive in inbox (not spam)
- Bounces are normal (<2%)

**This Is NOT a Deliverability Problem:**
- Emails are being delivered
- Inbox placement is correct
- Problem is: Recipients aren't opening emails

**Root Causes:**
1. Poor subject line (not compelling)
2. Wrong audience (list doesn't match offer)
3. Sending at wrong time (off-hours)
4. Email content doesn't match subject
5. From name not recognizable

**Solutions:**

**1. Improve Subject Line**
- Test variations (A/B test)
- Make it personalized: "John, I found this on [Company] website"
- Avoid: Spam trigger words ("Free", "Limited time", "Click here")
- Length: 30-50 characters optimal

**2. Right Audience**
- Review lead source: Are these right prospects?
- Check targeting: Does prospect match your offer?
- Test with 20 leads first before 200

**3. Optimize Send Time**
- Send during recipient's business hours
- Use timezone feature in email tool
- Test different times (9 AM vs 2 PM vs 4 PM)

**4. Strengthen From Name**
- Use: "John Smith" (personal) instead of "Marketing Team"
- Recipients are more likely to open personal emails
- Avoid company names in From line for cold email

**5. Test Content**
- Subject: Does email match subject line?
- Length: 50-100 words optimal
- Call to action: Clear yes/no question
- Personalization: 2-3 custom elements per email

**Testing Process:**
1. Keep everything the same except subject line
2. Send 20 emails with subject A
3. Send 20 emails with subject B
4. Compare open rates
5. Use winner in next batch

**Timeline:** 3-5 days to get statistically significant data

---

### Issue 7: High Unsubscribe Rate

**Symptoms:**
- Unsubscribe rate >0.5% (excessive)
- Many people clicking unsubscribe
- Spike in unsubscribes after certain sends

**Root Causes:**
1. Not setting expectations in welcome email
2. Sending too frequently
3. Content not matching what was promised
4. Wrong audience (ads promised something different)

**Solutions:**

**1. Improve Welcome Email**
- Set clear expectations: "You'll receive X per week"
- Example: "I send cold email tips every Tuesday"
- Explain value: "Each email is personalized for your business"
- Segment: "What are you interested in?" (let them choose)

**2. Control Frequency**
- Standard: 1 email per week (sustainable)
- Maximum: 2-3 per week (only for highly engaged)
- Minimum: 1 per 2 weeks (too slow, people forget)
- Test what resonates

**3. Match Content to Promise**
- If you promised "cold email strategies", deliver strategies
- Don't surprise with: Sales pitch, product promotion, etc.
- Keep ratio: 80% value, 20% asks

**4. Review Ad Copy**
- If advertising via ads: Does copy match email content?
- Example: Ad says "Learn 5 cold email hacks"
  → Email should deliver that, not just sell product
- Build trust first, sell later

**5. Create Preference Center**
- Let people choose email frequency
- Let people choose topics
- Reduces hard unsubscribes (people leave if can't customize)

**Acceptable Unsubscribe Rate:** 0.2-0.5% is normal and healthy

---

### Issue 8: Domain Age/History Problem

**Symptoms:**
- Brand new domain (days old)
- Emails going to spam despite good authentication
- All metrics look good but deliverability poor

**Root Cause:**
- Email providers don't trust domains with 0 history
- Domain reputation takes time to build
- New domains = higher spam filter scrutiny

**Solutions:**

**If Domain Is Very New (Days Old):**
1. Wait 1-2 weeks before sending (let domain age slightly)
2. Focus on warmup during this period (2-3 weeks is minimum anyway)
3. Start volume ramp small (50-100 emails day 1)
4. Increase slowly (5-10% per day)
5. Build positive history (engagement, low complaints, etc.)

**If Domain Has History But It's Bad:**
- Previous owner used for spam
- Domain is "burned" in email provider databases
- Recovery is slow or impossible

**Options:**
1. **Rehabilitation (30-day ramp):**
   - Implement full authentication
   - Clean list (NeverBounce)
   - Segment to highly engaged only
   - Send 50-100/day for 2 weeks
   - Increase volume gradually over 30 days
   - Monitor bounce/complaint/engagement carefully
   - Success rate: 50-70% (domain salvageable)
   - Timeline: 30 days

2. **Start Fresh (New Domain):**
   - Register new domain
   - Move to new sending IP (if possible)
   - Set up authentication (SPF/DKIM/DMARC)
   - Start warmup (2-3 weeks)
   - Begin sending from fresh domain
   - Redirect old domain email to new one
   - Success rate: 95%+ (clean slate)
   - Timeline: 3-4 weeks to full volume
   - Cost: Domain registration ($1-15/year)

**Recommendation:** If rehabilitation not working after 2 weeks, start fresh domain

---

### Issue 9: Provider-Specific Issues

#### Gmail Promo Folder
**Cause:** Content-driven (too promotional)
**Solution:** Reduce links, increase value content, segment to engaged

#### Yahoo/AOL Spam Folder
**Cause:** Often stricter filtering than Gmail
**Solution:** Ensure DKIM passing with your domain, clean list, reduce volume

#### Outlook/Hotmail Strict
**Cause:** Suspicious of new senders
**Solution:** Build history, increase domain age, verify DMARC

#### iCloud Private Relay
**Cause:** iCloud hides user engagement metrics (intentional)
**Note:** Can't track opens/clicks from iCloud users (privacy feature)
**Solution:** Focus on other metrics (Gmail, Yahoo, Outlook responses)

---

## Content Audit (Mail-Tester)

### How to Run Complete Audit

1. **Get your test email address from Mail-Tester**
2. **Send your template email to it**
3. **Wait 1 minute**
4. **View results (score out of 10)**

### Common Issues & Fixes

| Issue | Problem | Fix |
|-------|---------|-----|
| Spam words | Contains: "Free", "Limited time", "Act now", "Click here" | Remove trigger words, use consultative language |
| No DKIM | Not signed with your domain | Set up DKIM (see dns-setup.md) |
| No SPF | Missing or invalid SPF record | Add SPF record (see dns-setup.md) |
| No DMARC | Missing DMARC record | Add DMARC record (see dns-setup.md) |
| Too many links | >2 links per email | Remove unnecessary links (cold email: 0 links ideal) |
| HTML errors | Broken HTML/CSS | Use email templates, avoid custom HTML |
| No unsubscribe | Missing unsubscribe link | Add unsubscribe footer |
| Image-only | Email is just images | Include text content, images secondary |
| Large file size | Email >100KB | Compress images, reduce attachments |

### Target Scores
- **9-10/10:** Optimal (send with confidence)
- **8/10:** Acceptable (can send but room to improve)
- **7/10:** Risky (fix issues before sending at scale)
- **<7/10:** Send with caution (fix major issues first)

---

## Sender Reputation Monitoring

### Monthly Check-In

| Metric | Target | Where to Check |
|--------|--------|-----------------|
| Sender Score | 80+ | senderscore.org |
| Bounce Rate | <2% | Email tool dashboard |
| Complaint Rate | <0.1% | Gmail Postmaster Tools |
| Open Rate | 30-80% (varies) | Email tool dashboard |
| Blacklist Status | Not listed | mxtoolbox.com/blacklist.aspx |

### Dashboard Setup
1. Bookmark these pages:
   - senderscore.org
   - mxtoolbox.com
   - mail-tester.com
   - Gmail Postmaster Tools (postmaster.google.com)

2. Weekly routine (5 minutes):
   - Check Sender Score (any decline = investigate)
   - Review bounce rate (should be <2%)
   - Check blacklist (should be green)

3. Monthly review:
   - Run test emails to multiple providers
   - Run Mail-Tester on current template
   - Review engagement metrics
   - Assess list health (remove non-engaged)

---

## Recovery Roadmap

### If Deliverability is Severely Damaged

**Week 1-2: Emergency Response**
- [ ] Stop all sends
- [ ] If blacklisted: Request immediate delisting
- [ ] Clean entire list with NeverBounce
- [ ] Review email content (Mail-Tester)
- [ ] Audit authentication (SPF/DKIM/DMARC)

**Week 3-4: Rehabilitation Start**
- [ ] Implement any fixes identified
- [ ] Warm up inbox (2-3 weeks)
- [ ] Segment to highly engaged segment only
- [ ] Prepare 30-day volume ramp

**Week 5-8: Volume Ramp**
- [ ] Start at 50-100 emails/day
- [ ] Increase 5-10% per day
- [ ] Monitor metrics daily
- [ ] Stop at first sign of problems

**Week 9+: Maintenance & Monitoring**
- [ ] Monitor reputation continuously
- [ ] Keep warmup running (10-15/day maintenance)
- [ ] Maintain segmentation discipline
- [ ] Plan future growth carefully

**Alternative: Start Fresh**
- Register new domain (takes 1-2 weeks)
- Set up cleanly from start
- Faster path to deliverability
- Cost: ~$15/year + time

---

## Escalation: When to Get Help

**Reach out for professional help if:**
- Recovery plan not working after 4+ weeks
- Domain has long history of spam (previous owner)
- Multiple provider issues (not just Gmail)
- Blacklist listing won't remove
- Complex multi-sending-source infrastructure

**Resources:**
- Email deliverability consultants
- ESP support (if using major platform)
- DMARC analyzer services (dmarcian, agari)

**Cost:** $500-2000+ for consultation, worth it if valuable domain worth saving
