---
name: A/B Testing & Scaling Plans
description: >
  10/10/80 testing method, per-100-email testing, what to A/B test, volume
  scaling plans, domain rotation rules, send time optimization. Sources:
  Acquisition X (extract_08 section 8), Alex Berman (extract_01 clusters
  12, 14), 30MPC (extract_07 sections 16, 18), Longden (extract_06 sections
  1.18-1.19).
---

# A/B Testing & Scaling Plans

## THE 10/10/80 A/B TESTING METHOD (Acquisition X)

The most structured testing methodology across all sources.

### How It Works
1. Take your total daily send volume
2. Allocate **10%** to Variant A (test version 1)
3. Allocate **10%** to Variant B (test version 2)
4. Keep **80%** on your current best-performing version (the control)
5. Run for a statistically meaningful sample (minimum 100 emails per variant)
6. Winner of A vs B becomes the new challenger against the control
7. Repeat continuously

### Why 80/10/10 Not 50/50
- You never risk your entire volume on unproven copy
- The control keeps producing results while you test
- Losses from failed tests are limited to 20% of volume
- Allows continuous iteration without campaign disruption

### Testing Cadence
- Test one variable at a time (otherwise you cannot attribute results)
- Run each test for at least 100 emails per variant before declaring a winner
- New test every 1-2 weeks depending on volume
- Document every test result in a testing log

---

## WHAT TO A/B TEST (Priority Order)

### Highest Impact Tests

| Variable | Why Test It | How to Test |
|---|---|---|
| **Subject line** | Determines open rate; gate to everything else | Same body, two different subjects |
| **First line / personalization** | Determines if they read past line 1 | Same body, different opening approaches |
| **CTA** | Determines reply rate; the ask matters enormously | Same email, different closing question |
| **Offer** | Interest-based vs. time-ask vs. 1:many vs. 1:1 offer | Same email, different CTA/offer combo |
| **Audience segment** | Same message performs differently by persona | Same email to two different ICP segments |

### Medium Impact Tests

| Variable | Why Test It |
|---|---|
| Email length | Short (3 sentences) vs. medium (5-7 sentences) |
| Problem angle | Problem A from messaging matrix vs. Problem B |
| Social proof type | Case study vs. testimonial vs. data point |
| Spintax variants | Which CTA phrasing converts best |
| Send day | Tuesday vs. Thursday |
| Send time | 8 AM vs. 10 AM in prospect timezone |

### Lower Impact Tests (Only After Big Wins Locked)

| Variable | Why Test It |
|---|---|
| Signature format | Minimal vs. with title/company |
| PS line vs. no PS | Additional personalization hook |
| Preview text optimization | Personalization-first vs. problem-first |
| Paragraph structure | 2 paragraphs vs. 3 paragraphs |

---

## PER-100-EMAIL TESTING (Alex Berman)

A simpler method for smaller-scale operations:

1. Send 100 emails with Version A
2. Send 100 emails with Version B
3. Compare open rates and reply rates
4. Winner becomes the new default
5. Create a new challenger
6. Repeat

### Minimum Sample Size
- 100 emails per variant is the minimum for any testing
- Below 100, random variance makes results meaningless
- For statistically rigorous results, aim for 200-300 per variant

---

## SPINTAX AS FREE A/B TESTING (Acquisition X)

Spintax creates variations automatically:
- "{Let's jump on a call | Are you free today? | Keen for a demo?}"
- Each recipient gets a random variant
- Your cold email tool tracks which variant performs best
- Zero extra effort -- significant deliverability AND testing benefit

### Where to Use Spintax
- CTA (highest impact)
- Subject line variations
- Opening phrase variations
- Closing phrase variations
- NOT on personalized elements (first lines, case studies)

---

## VOLUME SCALING PLAN

### Email Volume Ramp Schedule

| Phase | Timeline | Daily Volume/Domain | Total (5 domains) | Notes |
|---|---|---|---|---|
| Warmup only | Weeks 1-2 | 0 cold + 20-40 warmup | 0 cold emails | Build reputation |
| Soft launch | Week 3 | 5-10 cold + 20 warmup | 25-50 total | Monitor deliverability daily |
| Ramp | Weeks 4-6 | 15-25 cold + 20 warmup | 75-125 total | Increase by 5/week |
| Cruising | Month 2+ | 30 cold + 20 warmup | 150 total | Sustainable volume |
| Scale (add domains) | Month 3+ | 30 cold + 20 warmup x more domains | 300+ total | Pre-warm new domains |

### Domain Rotation Rules
- **30 emails per day per email domain** (+ 20 warmup) -- 30MPC rule of thumb
- Example: 150 emails/day = 5 domains needed
- Use multiple domains: name@company.io, name@company.xyz, firstname.lastname@company.com
- Have backup domains pre-warmed and ready
- Each domain needs independent warmup and monitoring
- NEVER send all volume from one domain

### Cold Call Volume Scaling

| Phase | Weekly Dials | Notes |
|---|---|---|
| Getting started | 50-100 | Focus on quality, practice openers |
| Habit building | 200/week (40/day) | The 200-Dial Challenge: 4 weeks builds permanent habit |
| Sustained | 200-400/week | Quality over quantity; top reps accomplish in 200 what others need 400 for |
| Scaling with SDRs | 800+/month per SDR | Hire experienced SDRs, provide full enablement |

### LinkedIn Volume Scaling

| Phase | Weekly Activity | Notes |
|---|---|---|
| Getting started | 100 connection requests | Manual for best acceptance rate |
| Standard | 200 requests (40/day Mon-Fri) | 10-15 min/day |
| Scaled | 200 requests + Dripify automation | Only automate connection requests, NEVER DMs |
| Add voice messages | After initial DM series | 1 call booked per 3-5 voice messages |

---

## SEND TIMING OPTIMIZATION

### Cold Email: When to Send

| Day | Rating | Data Source |
|---|---|---|
| Tuesday | Best | Multiple sources agree |
| Wednesday | Strong | Second-best across data |
| Thursday | Good | Consistent performer |
| Monday | OK | People catching up; emails get buried |
| Friday | Weak | Winding down |
| Sat/Sun | Avoid | Very low engagement |

**Time of day:**
- 8-10 AM prospect timezone is the consensus best window
- Some evidence for 6-7 AM sends (inbox placement before competition)
- Spread sends throughout the morning (not all at once -- ESP detection)

### Cold Calls: When to Call

- **Best days:** Wednesday and Thursday
- **Best times:** 8-10 AM and 4-5 PM
- **Monday:** People catching up from weekend
- **Friday:** People winding down
- **Dedicated time blocks:** Protect Wed-Thu 8-10 AM and 4-5 PM for calling

### LinkedIn: When to Connect

- **Connection requests:** 8-11 AM prospect timezone, Mon-Thu
- **DMs:** Business hours in prospect timezone
- **Voice messages:** Same as DMs; never as first contact

### Speed of Booking Data (Cold Email Wizard)

The faster you respond to a positive reply, the higher the meeting booking rate:
- Responding within minutes dramatically outperforms responding within hours
- Calendar friction kills conversions -- one link, one click
- If a prospect expresses interest, respond immediately and propose times

---

## SCALING PREREQUISITES CHECKLIST

Before scaling any channel, verify:

- [ ] **Metrics are healthy:** Above benchmark minimums for at least 2 consecutive weeks
- [ ] **Infrastructure is solid:** Domains warmed, DNS authenticated, no blacklists
- [ ] **List quality verified:** <5% bounce, emails validated
- [ ] **Copy is proven:** A/B tested subject, body, CTA with clear winner
- [ ] **Follow-up sequence built:** Minimum 5 touches across channels
- [ ] **Tracking in place:** Can measure open, reply, bounce, spam, meetings booked
- [ ] **Booking mechanics work:** Calendar link tested, confirmation emails sending, show-up rate >70%
- [ ] **Capacity to handle responses:** Can reply within minutes during business hours

### Scaling Red Flags (Stop and Fix)
- Spam rate creeping above 0.2% -- pause and investigate before it hits 0.3%
- Bounce rate increasing week over week -- list quality degrading
- Reply rate declining while volume increases -- personalization dropping
- Show rate declining -- booking too far out or confirmation flow broken
- Positive reply sentiment declining -- copy fatigue or wrong audience

---

## CAMPAIGN MATH

### Cold Email ROI Math
- 1,000 emails sent
- 30% open rate = 300 opens
- 5% reply rate = 50 replies (on total sent) or ~15 replies (on opens)
- 30% positive reply rate = ~5 positive replies
- 50% booking rate from positives = ~2-3 meetings
- 20-30% close rate = 1 new client per ~500-1,000 emails

### Cold Call ROI Math (Top Rep)
- 800 dials/month
- 13.3% connect rate = 106 conversations
- 16.7% set rate = ~18 meetings
- 80% show rate = ~14 meetings attended
- 20-30% close rate = 3-4 new clients/month

### LinkedIn ROI Math
- 200 connection requests/week = 800/month
- 50% acceptance = 400 new connections
- Book 1/10 to 1/15 = 27-40 calls/month
- 20% close rate = 5-8 new clients/month

---

## CTA PERFORMANCE DATA (Gong, 5,000+ Cold Emails)

| CTA Type | Impact on Reply Rate |
|---|---|
| Asking for a meeting/time | **-44%** (worst) |
| Asking about a problem (open-ended) | Slightly negative |
| Asking for interest | **Positive** |
| Making an offer | **+28%** (best) |

Time is the worst thing you could ask for. The prospect thinks: "What am I going to get in return for my time?" Only 3% of your market is in buying mode. To engage the other 97%, they need a reason beyond your solution.
