---
name: Campaign Operations & Optimization
description: >
  MANDATORY TRIGGERS: campaign metrics, campaign benchmarks, diagnose campaign,
  campaign audit, A/B testing, 10/10/80 method, scaling outbound, outbound volume,
  send timing, tool stack, CRM setup, multichannel orchestration, campaign plan,
  low open rate, low reply rate, low meeting rate, high bounce rate, spam rate,
  domain rotation, send volume, scaling cold email, scaling cold calls, SDR hiring,
  performance benchmarks, campaign diagnostics, what tools for outbound, when to
  send emails, how many emails per day, campaign not working.
  FOR: Running, measuring, and optimizing cold outbound campaigns end-to-end.
  Covers campaign metrics and benchmarks by channel, A/B testing methodology
  (10/10/80 method), diagnostic frameworks for underperforming campaigns,
  scaling plans, tool stack selection, CRM setup, send timing optimization,
  multichannel campaign orchestration, SDR hiring, and performance management.
  This is the command center skill that ties all other skills together.
  Do NOT use for: Writing outreach messages (use channel-specific skills),
  infrastructure/DNS setup (use email-infrastructure), detailed list building
  (use list-building), prospect research methodology (use prospect-research).
---

# Campaign Operations & Optimization

## Quick Navigation
- **Benchmarks & diagnostic trees** -> references/benchmarks-and-diagnostics.md
- **A/B testing & scaling plans** -> references/ab-testing-and-scaling.md
- **Tool stack reference** -> references/tool-stack-reference.md

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| Campaign benchmarks, target metrics, low opens/replies/meetings, diagnostic tree, what is a good open rate, why is my campaign not working, spam rate, bounce rate | references/benchmarks-and-diagnostics.md |
| A/B testing, 10/10/80 method, what to test, scaling volume, send timing, domain rotation rules, how many emails per day, scaling plan | references/ab-testing-and-scaling.md |
| Tool recommendations, which tools for cold email/calling/LinkedIn, CRM selection, sending tools, warmup tools, enrichment tools, what does X tool cost | references/tool-stack-reference.md |

---

## THE CAMPAIGN OPERATIONS FRAMEWORK

Campaign ops sits at the top of the outbound pyramid. It does not create the outreach -- it orchestrates, measures, diagnoses, and scales all the other skills.

### The Campaign Lifecycle
1. **Plan:** Define channels, volume, personas, sequences, tools, timelines
2. **Launch:** Start sequences at conservative volume with proper warmup
3. **Measure:** Track benchmarks daily/weekly by channel
4. **Diagnose:** When metrics are below benchmarks, identify the bottleneck
5. **Optimize:** Fix the bottleneck using the appropriate skill
6. **Scale:** Increase volume once metrics are healthy

---

## BENCHMARK QUICK REFERENCE

### Cold Email Benchmarks
| Metric | Target | Danger Zone |
|---|---|---|
| Open rate | >50% (Berman); >30% (30MPC minimum) | <30% |
| Reply rate | >5% (Berman); >2% (30MPC minimum) | <2% |
| Bounce rate | <2% optimal; <5% acceptable | >5% |
| Spam rate | <0.3% (Google/Yahoo requirement) | >0.3% |
| Positive reply rate | >1% | <0.5% |

### Cold Calling Benchmarks (The Golden 3)
| Metric | Average Rep (50th %ile) | Top Rep (75th %ile) |
|---|---|---|
| Connect rate | 5.5% | 13.3% |
| Set rate | 4.6% | 16.7% |
| Show rate | Varies | Target 80%+ |

On 800 dials/month: Average rep books 2 meetings. Top rep books ~18 meetings. Same dials, 13x the results.

### LinkedIn Benchmarks
| Metric | Target |
|---|---|
| Connection acceptance rate | 40-50%+ |
| Call book rate (Level 1 neutral) | 5-10% |
| Call book rate (profile viewers) | 10-20% |
| Call book rate (content engagers) | 15-25% |
| Weekly activity | 200 connection requests, 80-100+ accepted |

### DM Benchmarks (Facebook/Instagram)
| Metric | Target |
|---|---|
| Daily new conversations | 100 new / 50-100 follow-ups (Instagram) |
| Conversation to call rate | Varies by pain level discovered |
| Show-up rate | Target 80%+ with reminder sequences |

---

## THE DIAGNOSTIC FRAMEWORK

When a campaign underperforms, do NOT change everything at once. Diagnose the specific bottleneck:

### Email Diagnostic Tree

```
LOW OPEN RATE (<30%)
  -> Check subject lines (boring? too long? gimmicky?)
  -> Check deliverability (spam folder? blacklisted?)
  -> Check lead quality (right ICP? valid emails?)
  -> Check send timing (sending at midnight?)
  -> Action: Fix subject lines first, then deliverability

LOW REPLY RATE (>30% opens but <2% replies)
  -> Check email copy (too long? too generic? no problem language?)
  -> Check case study/social proof (missing? irrelevant?)
  -> Check CTA (asking for time? too aggressive?)
  -> Check personalization (template-obvious? stale data?)
  -> Action: Fix copy and CTA first, test new angles

LOW MEETING RATE (replies but no meetings)
  -> Check follow-up speed (responding within minutes?)
  -> Check follow-up sequence (only one follow-up?)
  -> Check CTA in replies (still not asking clearly?)
  -> Check calendar friction (too many steps to book?)
  -> Action: Fix follow-up and booking mechanics

HIGH BOUNCE RATE (>5%)
  -> Check list quality (verified emails? recent data?)
  -> Check targeting (job changers? stale list?)
  -> Action: Verify emails with NeverBounce before sending

HIGH SPAM RATE (>0.3%)
  -> Check content (spam words? HTML? images? links?)
  -> Check authentication (SPF/DKIM/DMARC configured?)
  -> Check warmup (did you skip warmup? volume too high?)
  -> Check domain reputation (blacklisted? new domain?)
  -> Action: Pause campaign, fix infrastructure first
```

### Cold Call Diagnostic Tree

```
LOW CONNECT RATE (<5%)
  -> Calling mobile or direct lines? (gatekeepers kill connect rate)
  -> Data quality? (bad numbers, wrong contacts)
  -> Calling at right times? (8-10 AM or 4-5 PM best)
  -> Phone number spam-tagged? (check at freecallerregistry.com)

LOW SET RATE (connecting but <5% meetings)
  -> Opener working? (using canned "bad time?" opener?)
  -> Problem proposition specific enough? (Hairy Lollipop Test)
  -> Handling objections or arguing? (use Miyagi method)
  -> Calling right persona? (too junior = no authority)
  -> Calling right timing? (A-tier triggers vs C-tier?)

LOW SHOW RATE (<70%)
  -> Sending day-before confirmation?
  -> Sending day-of text?
  -> Using no-show protocol? (2-min, 5-min, 8-min escalation)
  -> Booking too far out? (>5 days = show rate drops)
```

---

## SEND TIMING OPTIMIZATION

### Cold Email
| Day | Rating | Notes |
|---|---|---|
| Tuesday | Best | Most data supports Tuesday sends |
| Wednesday | Strong | Second-best day across sources |
| Thursday | Good | Consistent performer |
| Monday | Acceptable | People catching up; emails buried |
| Friday | Weak | Winding down, lower engagement |
| Saturday/Sunday | Avoid | Very low open/reply rates |

**Best times:** 8-10 AM in the prospect's timezone. Some data supports 6-7 AM for early inbox placement.

### Cold Calls
- **Best days:** Wednesday and Thursday
- **Best times:** 8-10 AM and 4-5 PM
- **Block these windows** in your calendar and protect them for calling only

### LinkedIn DMs
- **Send connection requests:** 8 AM - 11 AM prospect's timezone, Mon-Thu
- **Send DMs:** Business hours in prospect's timezone
- **Separate searches by geography** to send during appropriate time zones

---

## MULTICHANNEL ORCHESTRATION

### The K.I.S.S. Weekly Touch Pattern (30MPC)

**Week 1:**
- Day 1 (Tuesday): Triple tap -- Call + voicemail + email + social touch
- Day 3 (Thursday): Double tap -- Call + email

**Week 2:**
- Day 1 (Tuesday): Triple tap with new problem angle, new email subject
- Day 3 (Thursday): Double tap

**Week 3-4:**
- "Get the truth" / breakup emails
- Phase out calls, keep email + LinkedIn

### Key Sequencing Stats
- 70% of replies come from emails sent AFTER the first email
- One-off emails have <1% chance of reply
- Adding phone calls nearly doubles reply rate
- Phone + voicemail = 3.24x increase in reply rate
- Triple taps = 3.1x increase in contact rates

### Two Tiers of Sequences

**High Effort (A/B-tier accounts):**
- Manual phone calls
- Personalized emails
- LinkedIn touches
- Full triple/double tap pattern
- Two deeply personalized long emails per sequence

**Low Effort (C-tier accounts):**
- Automated/templated emails OR automated + call people who open
- Pervasive problems instead of personalized triggers
- Same structure but templated
- "Not sure if you're running into this, but..." language

---

## SDR HIRING AND MANAGEMENT

### Hiring Criteria
- Experienced only: $5K-10K+ earned on Upwork, 90-95%+ job success
- Native to target country (timezone, language, accent match)
- Filter question in job post: "First words of cover letter should be: umbrella-avocado"
- Problem-solving question: "What would you do if you called a prospect and it was the wrong number?"
- 1-2 week trial basis, renew based on performance

### SDR Commission Structure (Tiered)
| Appointments/Month | Commission |
|---|---|
| 1-25 | 15% |
| 25-50 | 20% |
| 50-75 | 25% |
| 75-100 | 30% |
| 100+ | 40% |

### SDR Management
- Provide: value prop, case studies, offer, CTA, decks/slides
- Set KPIs: expected calls per hour/day, expected appointments per hour/day
- End-of-day reports: calls made, calls booked, follow-up notes
- Training: review 3-5 random recorded calls per week; provide feedback

---

## CROSS-REFERENCES

| Situation | Go To |
|---|---|
| Deliverability issues diagnosed | `email-infrastructure` skill |
| Copy/subject lines need improvement | `cold-email-copy` skill |
| First lines are too generic | `first-lines` skill |
| List quality is the bottleneck | `list-building` skill |
| Call framework needs work | `cold-calling` skill |
| LinkedIn DMs underperforming | `linkedin-outreach` skill |
| DM conversations not converting | `dm-outreach` skill |
| Follow-up cadence problems | `follow-up-sequences` skill |
| Research angles are weak | `prospect-research` skill |
| Team morale/fear issues | `outbound-psychology` skill |

---

## KEY DATA POINTS

- 80% of B2B buyers prefer email contact (Ring Group)
- 58% of meetings buyers take with reps are a complete waste of time
- Only 3% of your market is in active buying mode at any time
- 80% of successful cold email sales happen after 5+ follow-ups
- Only 8-10% of people have a proper structure of 5+ emails
- 8 seconds is the time a prospect spends reading an email after opening
- Voicemails have 90%+ open rate (prospect at least sees transcription)
