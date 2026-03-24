---
name: "Warmup & Ramp Protocol"
description: "Warmup tool configurations, ramp schedules, volume scaling plans, and benchmarks for WarmupInbox, TrulyInbox, and Lemwarm."
---

# Warmup & Ramp Protocol

## Why Warmup Is Non-Negotiable

When you buy a new mailbox, you have ZERO reputation with your ESP. ESPs treat unknown senders as suspicious by default. Warmup gradually establishes positive sender reputation by simulating organic email behavior.

**Without warmup:** 3-6 months to build good reputation organically.
**With warmup:** 2-3 weeks to achieve good reputation.

Skipping warmup is the single most common infrastructure mistake in cold email.

---

## Warmup Tool Comparison

### WarmupInbox ($9/month per inbox)

**Recommended by:** Alex Berman
**Setup:**
1. Gmail settings: Enable IMAP, allow less secure apps, allow per-user outbound gateways
2. Wait 1 hour after enabling IMAP
3. Connect inbox in WarmupInbox dashboard

**Configuration:**
- Start at 15 warmup emails/day
- Increase by 1 per day
- Never go below 20-30 warmup emails/day
- Keep running forever -- even while sending cold campaigns

**Readiness indicators:**
- Dashboard shows maxed emails
- At least 1-2 weeks have passed
- No spam complaints

### TrulyInbox (Free -- Unlimited)

**Recommended by:** Manthan Patel (Acquisition X)
**Setup:** Click the warmup button, everything runs automatically

**What it does automatically:**
- Sends emails to other TrulyInbox users
- Marks emails as important
- Stars emails
- Scrolls/reads like a human
- Replies to emails

**Configuration schedule:**

| Phase | Emails/Day | Reply Rate Target | Duration |
|-------|-----------|-------------------|----------|
| Start | 4-8 | 30% | Weeks 1-2 |
| Ramp | 20-30 | 40-50% | Weeks 2-4 |
| Maximum | 50 | 60% (cap here) | Ongoing |

**Ramp rate:** Increase by 3-5 emails per day.
**Critical:** Randomize the number of warmup emails daily to appear natural.

### Lemwarm ($30-40/month)

**Recommended by:** Chris Orzechowski (for reputation rehabilitation)
**Best for:** Domain recovery/nuclear option scenarios

**How it works:**
- Logs into your email account
- Sends emails as you to other Lemwarm users
- Opens and replies to emails from other Lemwarm users to your account
- Artificially inflates engagement metrics that ISPs track

**Dashboard:** Red/yellow/green meter indicating when you can start sending real campaigns.

**Key insight:** More effective the less email you are sending (better ratio of warmup to real sends). This is why it is particularly effective for domain rehabilitation.

**Custom tracking domain setup for Lemlist/Lemwarm:**
- CNAME record: `c.yourdomain.com` pointed to `custom.lemlist.com`

### Tool Comparison Summary

| Feature | WarmupInbox | TrulyInbox | Lemwarm |
|---------|------------|------------|---------|
| Cost | $9/mo/inbox | Free | $30-40/mo |
| Setup complexity | Medium (IMAP config) | Low (one click) | Low |
| Best for | Standard warmup | Budget-conscious / high inbox count | Domain rehabilitation |
| Reply simulation | Yes | Yes (with scrolling/reading) | Yes |
| Ramp automation | Manual increase | Manual increase | Automatic |
| Readiness indicator | Dashboard metrics | Manual monitoring | Red/yellow/green meter |
| Keep running during campaigns | Yes (mandatory) | Yes (mandatory) | Yes (most effective with low real sends) |

### Choosing the Right Tool

- **New to cold email, tight budget:** Start with TrulyInbox. It is free and unlimited. Upgrade to WarmupInbox if you need more granular control.
- **Running 5-20 inboxes at scale:** WarmupInbox at $9/inbox gives the best balance of cost and control.
- **Rehabilitating a burned domain:** Lemwarm is the strongest option -- its engagement simulation is more aggressive, and it works best when real send volume is near zero.
- **Multiple tools simultaneously:** You CAN run TrulyInbox + WarmupInbox on the same inbox for extra warmup volume, but monitor for unusual sending patterns.

---

## Volume Ramp-Up Protocol (For New or Rehabilitated Domains)

### When to Use This Protocol

- Brand new domain with no sending history
- Rehabilitating a domain with damaged reputation
- Migrating to a new ESP
- Returning after a long period of no sends

### The 30-Day Minimum Ramp Formula (Orzechowski)

1. Export your **engaged recipients only** (for warm email) or your **warmest leads** (for cold email)
2. Create a new list in your ESP
3. **Day 1:** Send to 5-10 leads
4. **Day 2:** Send to 10-20 leads
5. **Day 3:** Send to 20-40 leads
6. **Double the send size each day**
7. If doubling reaches your full list before 30 days, **slow down** -- skip days, add only 5-10/day
8. Stretch this to **at least 30 days** before reaching full volume
9. **Only send to your most engaged or qualified leads** during ramp-up
10. **No other campaigns** during the 30-day ramp-up

### Cold Email Volume Ramp (Berman)

| Week | Volume Per Domain |
|------|-------------------|
| Week 1 | 5-10 emails/day |
| Week 2-3 | 15-20 emails/day |
| Month 1+ | 30-40 emails/day |
| Scale (multiple domains) | 30/day/domain |

**Domain rotation rule at scale:** Maximum 30 emails per day per domain. To send 300/day, you need 10 domains.

### Content During Ramp-Up

- Send an email every day (or every ramp day)
- Does not need to be long/complex content
- Lightweight, engaging content that invites replies is ideal
- If your ESP supports suppressing previous recipients, you can send the same email each day
- The nine-word email strategy works well during ramp-up (a short question that invites a reply)

---

## Maintaining Warmup After Launch

Once you begin cold email campaigns, maintain warmup to protect reputation:

**Ratio guideline:** Keep warmup volume at least equal to your cold send volume.
- Sending 30 cold emails/day? Keep 30+ warmup emails/day running.
- At higher volumes, warmup ratio can be lower but never zero.

**What to monitor:**
- Warmup reply rates staying above 30-40%
- No increase in spam complaints
- Open rates on cold campaigns staying above 50%
- Bounce rates staying below 2%

---

## When to Pause and Reassess

Stop cold campaigns and increase warmup volume if you see:

- Open rates dropping below 30% (check authentication first)
- Bounce rates exceeding 3%
- Spam complaints increasing
- Domain appears on blacklists (check via MXToolbox)
- Mail-Tester score dropping below 7/10

**Recovery protocol:**
1. Pause all cold campaigns
2. Max out warmup volume
3. Run full deliverability audit (see deliverability-audit-checklist.md)
4. Fix identified issues
5. Wait 1-2 weeks of warmup-only sends
6. Resume cold campaigns at 50% previous volume, ramp back up over 2 weeks

---

## Monitoring Benchmarks by Phase

### Phase 1: Warmup Only (Weeks 1-2)

| Metric | Healthy | Warning | Critical |
|--------|---------|---------|----------|
| Warmup reply rate | 40%+ | 20-40% | Below 20% |
| Warmup emails landing in inbox | 90%+ | 70-90% | Below 70% |
| Mail-Tester score | 9-10/10 | 7-8/10 | Below 7/10 |
| Blacklist status | Clean | -- | Any listing |

### Phase 2: Ramp (Weeks 2-4)

| Metric | Healthy | Warning | Critical |
|--------|---------|---------|----------|
| Cold email open rate | 50%+ | 30-50% | Below 30% |
| Bounce rate | Below 2% | 2-3% | Above 3% |
| Spam complaints | 0 | 1-2 | 3+ |
| Warmup reply rate (concurrent) | 30%+ | 20-30% | Below 20% |

### Phase 3: Full Volume (Month 1+)

| Metric | Healthy | Warning | Critical |
|--------|---------|---------|----------|
| Cold email open rate | 50%+ | 40-50% | Below 40% |
| Reply rate | 5%+ | 2-5% | Below 2% |
| Bounce rate | Below 1% | 1-2% | Above 2% |
| Unsubscribe rate | Below 1% | 1-2% | Above 2% |
| Domain reputation (Google Postmaster) | High | Medium | Low/Bad |

---

## Ramp Schedule Variations

### Conservative Ramp (Safest -- For Premium Domains)

Use this when the domain is your brand domain or you cannot afford any reputation risk.

| Day | Warmup Emails | Cold Emails | Total |
|-----|--------------|-------------|-------|
| 1-7 | 15-20 | 0 | 15-20 |
| 8-10 | 25 | 3-5 | 28-30 |
| 11-14 | 30 | 5-10 | 35-40 |
| 15-21 | 30 | 10-15 | 40-45 |
| 22-30 | 30 | 15-25 | 45-55 |
| 30+ | 30 | 25-30 | 55-60 |

### Aggressive Ramp (For Disposable Domains at Scale)

Use this only with secondary domains you can afford to burn. Typically paired with Maildoso or similar bulk inbox providers.

| Day | Warmup Emails | Cold Emails | Total |
|-----|--------------|-------------|-------|
| 1-7 | 20-30 | 0 | 20-30 |
| 8-10 | 30 | 10 | 40 |
| 11-14 | 30 | 20 | 50 |
| 15-21 | 30 | 30 | 60 |
| 22+ | 30 | 30 (cap) | 60 |

**Important:** Even with aggressive ramp, NEVER exceed 30 cold emails per day per domain. Scale by adding more domains, not by increasing per-domain volume.
