---
name: Fix Deliverability
description: Diagnose email deliverability issues and create a step-by-step recovery plan. Activates fix-deliverability and segmentation-list-health skills. Outputs a diagnosis report with root cause identification, recovery protocol, and prevention checklist.
---

# Fix Deliverability Wizard

## Step 1: Gather Current State

Ask the user:

1. **What ESP are you using?** (Klaviyo, Mailchimp, ActiveCampaign, Kit, Beehiiv, other)
2. **What is your list size?** (total subscribers)
3. **What are your current open rates?** (campaigns and flows separately if available)
4. **What changed recently?** (Did open rates drop suddenly or gradually? Any recent actions like list imports, ESP migrations, design changes, frequency changes?)
5. **Have you run any deliverability tests?** (GlockApps, Google Postmaster, MX Toolbox)
6. **Is your DNS authentication set up?** (SPF, DKIM, DMARC -- ask if they know or need to check)
7. **What is your sending frequency?** (campaigns per week/month)
8. **Are you segmenting or sending to full list?**

---

## Step 2: Assess Severity

**Load skill:** `fix-deliverability` SKILL.md

Compare their metrics against the threshold table:

| Metric | Healthy | Warning | Critical |
|--------|---------|---------|----------|
| Open rate (segmented) | 20-25%+ | 15-20% | Below 10% |
| Open rate (full list) | 10-15% | 5-10% | Below 5% |
| Delivery rate | 99.5%+ | 98-99.5% | Below 98% |

Classify the situation as:
- **Healthy** -- no immediate deliverability action needed; optimize content/segmentation instead
- **Warning** -- investigate and take preventive action
- **Critical** -- full recovery protocol required

If **Healthy**, tell the user their deliverability is likely fine and redirect to appropriate skills (write-email-copy for engagement, segmentation-list-health for targeting, write-subject-lines for open rates).

---

## Step 3: Run Diagnosis

If Warning or Critical, guide the user through diagnosis:

### 3A: Authentication Check
Ask them to verify DNS records:
- Run Google MX Checker (toolbox.googleapps.com) or MX Toolbox
- Check SPF, DKIM, DMARC -- all should pass
- If any are missing or failing, this is likely the primary issue

**Load reference:** `fix-deliverability/references/ref-deliverability-diagnosis.md` for DNS setup details.

### 3B: Inbox Placement Test
Recommend GlockApps test:
- Send representative email to GlockApps seed list
- Check inbox vs. spam vs. promotions per provider
- Focus on Gmail first (largest market share)

### 3C: ISP Segmentation Test
If they have not done GlockApps, recommend the manual test:
- Send same campaign to Gmail-only segment vs. non-Gmail segment
- Compare open rates
- Gmail-specific drop = domain/IP reputation issue with Google
- Broad drop = authentication, blacklist, or list quality issue

### 3D: Blacklist Check
- Run MX Toolbox blacklist check on sending domain and IP
- Check key blacklists: Spamhaus, SpamCop, Barracuda

### 3E: Google Postmaster Check
If they have Gmail subscribers:
- Set up Google Postmaster Tools if not already done
- Check: IP reputation, domain reputation, spam rate, authentication status
- Spam rate above 0.2% = critical issue

---

## Step 4: Determine Root Cause

Based on diagnosis results, identify the root cause:

| Finding | Root Cause | Protocol |
|---------|-----------|----------|
| DNS records missing/failing | Authentication | Fix DNS records first; retest in 48 hours |
| Gmail: spam in GlockApps | Domain reputation destroyed | New domain + full warmup protocol |
| Gmail: promotions | Engagement issue, not reputation crisis | Improve content; send plain text for warmup |
| Listed on blacklist | Blacklist | Manual delisting request or wait for auto-removal |
| Google Postmaster spam rate > 0.2% | Sending to unengaged subscribers | Immediate list cleanup + segment restriction |
| Google Postmaster domain reputation: Bad | Domain damage | New domain strategy |
| Google Postmaster IP reputation: Bad | IP damage | Warm-up protocol on current domain |
| All ISPs spam | Widespread issue | Full protocol: authentication + new domain + warmup |
| Only Outlook/Hotmail spam | Normal for many senders | Small % of most lists; low priority unless core audience |

---

## Step 5: Build Recovery Plan

**Load reference:** `fix-deliverability/references/ref-deliverability-recovery.md`

Based on root cause, present a step-by-step recovery plan:

### If Authentication Issue:
1. Fix SPF record (provide specific include statement for their ESP)
2. Set up DKIM (guide through ESP-specific steps)
3. Add DMARC record (start with p=none for monitoring)
4. Verify via Google MX Checker
5. Wait 48 hours and retest

### If Domain Reputation Destroyed:
1. Purchase new sending domain (shop[domain].com format)
2. Set up DNS authentication on new domain
3. Sign up for Warmup Inbox (baseline 1-2/day, max 40/day)
4. Sign up for 10 newsletters on the new sending address
5. Wait 2-4 weeks
6. Retest with GlockApps (target: 99-100% inbox)
7. Begin Klaviyo warm-up campaign sequence (60-day -> 90-day -> 120-day -> full list)

### If IP Warm-Up Needed:
1. Stop sending to full list immediately
2. Segment hyper-engaged users (opened multiple in past 30-60 days)
3. Start sending to approximately 50 at a time
4. Scale up gradually while maintaining 20-30% open rates
5. Reintroduce broader segments only when rates stabilize

### If ESP Migration:
1. Build engagement segments from old ESP data
2. Set up random bucket system for volume control
3. Follow IP warm-up send schedule (9K -> 18K -> 38K -> double)
4. Operate dual-ESP during transition
5. Suppress warm-up recipients from old ESP sends
6. Migrate flows sequentially

### If List Quality Issue:
**Load skill:** `segmentation-list-health`
1. Run sunset flow on 90-120 day unengaged subscribers
2. Remove chronic unengaged (180-day AND logic)
3. Implement double opt-in going forward
4. Add reply-based warmup to welcome email
5. Monitor spam rate weekly

---

## Step 6: Prevention Plan

Present the ongoing prevention checklist:

### Weekly
- [ ] Review open rates by segment (note drops > 10%)
- [ ] Check Google Postmaster for spam rate and reputation
- [ ] Review unsubscribe rate (target: below 0.4%)

### Monthly
- [ ] Run GlockApps inbox placement test
- [ ] Check MX Toolbox for blacklist listings
- [ ] Review bounce rates (target: below 0.5% hard bounces)
- [ ] Verify DNS authentication still passing

### Quarterly
- [ ] Clean unengaged subscribers (90-120 day window)
- [ ] Audit list growth sources for spam trap risk
- [ ] Review opt-in type performance (single vs. double)

---

## Step 7: Output Deliverable

Present the complete diagnosis report in this format:

```
## Deliverability Diagnosis Report

### Current State
- ESP: [their ESP]
- List size: [their size]
- Open rate: [their rate] -- [Healthy/Warning/Critical]
- Authentication: [Pass/Fail for SPF/DKIM/DMARC]
- Inbox placement: [GlockApps results if available]

### Root Cause
[Identified root cause from Step 4]

### Recovery Protocol
[Numbered steps from Step 5, specific to their situation]

### Timeline
[Estimated recovery time based on list size and severity]

### Prevention Checklist
[Weekly/Monthly/Quarterly checks from Step 6]

### Cross-References
- If segmentation needs work -> segmentation-list-health skill
- If content engagement is low -> write-email-copy or write-newsletter-content skill
- If subject lines need improvement -> write-subject-lines skill
- If cold email deliverability -> cold-outbound-mastery plugin (different domain/IP strategy)
```
