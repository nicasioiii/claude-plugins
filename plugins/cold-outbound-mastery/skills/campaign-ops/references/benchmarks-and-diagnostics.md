---
name: Benchmarks & Diagnostic Trees
description: >
  Target benchmarks by channel (email, phone, LinkedIn, DM). Diagnostic
  decision trees for underperforming campaigns. Sources: Alex Berman
  (extract_01 clusters 12, 14-15), 30MPC (extract_07 sections 8, 23),
  Acquisition X (extract_08 section 3), Longden (extract_06 section 1.19),
  LinkedIn Client Lab (extract_05 section 1).
---

# Benchmarks & Diagnostic Trees

## COLD EMAIL BENCHMARKS

### Open Rate Targets

| Source | Target | Context |
|---|---|---|
| Alex Berman | 80%+ | High personalization, low volume |
| 30MPC | >30% | Minimum acceptable for healthy campaign |
| Acquisition X | 50-70% | Good range for personalized outreach |

**Interpreting open rates:**
- Open rate tracking may soon be deprecated (Gmail/Outlook flagging tracking pixels)
- Reply rates are the only true sign of deliverability health
- If open rate is high but reply rate is low, the problem is copy -- not deliverability
- If both are low, check deliverability first

### Reply Rate Targets

| Source | Target | Context |
|---|---|---|
| Alex Berman | 15%+ | High personalization, targeted lists |
| 30MPC | >2% | Minimum acceptable; double-digit is excellent |
| Cold Email Wizard | 15-30% | "One Question" angle with good targeting |
| Bree Weber | 50%+ | Ethical cold pitching (extreme personalization, low volume) |
| Acquisition X | 3-5%+ | Scalable volume approach |

**Where instructors disagree on reply rate targets:** Berman and Weber target high reply rates with low volume and extreme personalization. 30MPC and Acquisition X target lower rates at higher volume. Both approaches work -- the math differs. High reply rate at low volume = fewer but warmer leads. Lower reply rate at high volume = more leads but more qualification needed.

### Deliverability Benchmarks

| Metric | Optimal | Acceptable | Danger |
|---|---|---|---|
| Bounce rate | <2% | 2-3% | >5% |
| Spam rate | <0.1% | <0.3% | >0.3% (Google/Yahoo reject) |
| Unsubscribe rate | <1% | <2% | >3% |

### Volume Benchmarks

| Phase | Daily Volume per Domain | Notes |
|---|---|---|
| Warmup only (weeks 1-2) | 0 cold emails + 20-40 warmup | Build reputation first |
| Ramp start | 5-10 cold/day + 20 warmup | Conservative start |
| Ramp middle (month 1) | 25/day/domain | 30MPC recommended start after warmup |
| Ramp increase | +5 per week | Gradual increase, monitor metrics |
| Cruising | 30/day/domain (+ 20 warmup) | 30MPC rule of thumb |
| Maximum | 50/day/domain | Only with healthy metrics and warm domain |

**Domain math:** 150 emails/day = 5 domains needed (at 30/domain)

---

## COLD CALLING BENCHMARKS (The Golden 3)

### Connect Rate / Set Rate / Show Rate

| Metric | Average Rep (50th %ile) | Top Rep (75th %ile) |
|---|---|---|
| Connect Rate | 5.5% | 13.3% |
| Conversations (on 800 dials) | 43 | 106 |
| Set Rate | 4.6% | 16.7% |
| Meetings Booked (on 800 dials) | 2 | ~18 |

**Same number of dials, 13x the results.** The difference is NOT activity -- it is calling the right people at the right time with the right opener.

### Performance Benchmarks (Longden Tracker Data)
- Weekly calling goal: 100 calls
- Weekly contact goal: 50 contacts
- Weekly meeting goal: 5 meetings
- Monthly data: 445 calls, 207 contacts, 46 appointments
- Calls to contacts rate: ~46.5%
- Contacts to appointments rate: ~22.2%
- Overall calls to appointments: ~10.3%

### Maximizing Connect Rate (4 Tactics)
1. **Prioritize mobile and direct lines.** Skip gatekeepers entirely.
2. **Mark your tracks.** Color-code numbers red/yellow/green so you never dial a bad number twice.
3. **Law of diminishing returns.** Max 5 dials in 4 weeks per prospect. Stop after 2 voicemails. Avoid impassable gatekeepers.
4. **Prevent spam tagging:** Register at freecallerregistry.com. Rotate phone numbers. Test your number regularly. Call during business hours only. Do not repeatedly call bad numbers.

### Maximizing Set Rate (Priority Order)
1. People who have a problem NOW (highest conversion)
2. People who have a problem (moderate conversion)
3. Anyone else in your ICP (lowest conversion)

### Maximizing Show Rate
- **Day-before confirmation email:** Send prep research to show goodwill
- **Day-of text:** "Hey [NAME] it's [YOUR NAME] from [COMPANY]. Talk to you soon. [TIME]" -- boosts show-up rate by 10%+
- **No-show protocol:** Email at 2 min, call at 5 min, call again at 8 min
- **If no-show:** NEVER delete the invite. Move 3-4 days out and send backup times with a touch of guilt
- **Rule:** It is far easier to keep a meeting than to find a new one

---

## LINKEDIN BENCHMARKS

### Call Book Rates by Warmth Level (Ty Frankel)

| Warmth Level | % of Prospects | Call Book Rate |
|---|---|---|
| Level 1: Neutral (connected, no engagement) | 70-95% | 5-10% |
| Level 2: Profile Viewers | 5-15% | 10-20% |
| Level 3: Content Engagers | 5-10% | 15-25% |
| Level 4: Lead Magnet Engagers | 5-30% | 10-30% |
| Level 5: Inbound Leads | 1-10% | Highest (but lowest volume) |
| Level 6: Referrals/Warm Intros | Rare | Highest close rate |

### Activity Targets
- 200 hyper-targeted connection requests per week (40/day Mon-Fri)
- 80-100+ accepted per week (40-50%+ acceptance rate)
- 320-400 new people to DM each month
- Book 1/10 to 1/15 into a sales call
- Equals 20-40+ sales calls/month
- 20-50% of calls can come from follow-ups alone

---

## DM BENCHMARKS (Facebook/Instagram)

### Instagram Cold DM
- Daily volume: 100 new conversations + 50-100 follow-ups
- Target follower range for prospects: 500-4,000 (sweet spot)
- Profile optimization: 3 pinned posts, belief-shifting carousels

### Facebook DM
- Warm leads (group members): higher conversion than cold
- Cold leads (old connections, content engagers): moderate conversion
- Book calls only after Level 2 pain identified

---

## DIAGNOSTIC DECISION TREES

### Email Campaign Diagnostic

**Symptom: Low Open Rate (<30%)**

| Check | What to Look For | Fix |
|---|---|---|
| Subject line | >5 words? Capitalized? Gimmicky? Uses first name? | Rewrite: 5 words or less, internal camouflage, no gimmicks |
| Deliverability | Blacklisted? SPF/DKIM/DMARC misconfigured? | Run deliverability audit -> `email-infrastructure` skill |
| Warmup status | Skipped warmup? Not enough warmup volume? | Pause, warmup 2+ weeks, restart at lower volume |
| Lead quality | Wrong ICP? Unverified emails? Stale list? | Clean list with NeverBounce -> `list-building` skill |
| Send timing | Sending on weekends? Wrong timezone? | Shift to Tue-Thu, 8-10 AM prospect timezone |
| Spam words | "Free," "guarantee," "limited time" in copy? | Remove spam triggers, use built-in spam checker |

**Symptom: Low Reply Rate (Good opens, <2% replies)**

| Check | What to Look For | Fix |
|---|---|---|
| Email length | >150 words? Wall of text? | Cut to under 150 words, 2-3 short paragraphs |
| Problem language | Using buzzwords? Product voice? Generic problems? | Rewrite using messaging matrix -> `prospect-research` |
| Case study | Missing? Irrelevant to prospect? Too vague? | Add one-sentence case study formula -> `cold-email-copy` |
| CTA | Asking for time? Too aggressive? Open-ended? | Switch to interest-based CTA. Offers outperform time asks by 72% |
| Personalization | Template-obvious? Stale data? No first line? | Add god-level first lines -> `first-lines` skill |
| Links/images | Links in first email? Images? HTML formatting? | Strip to plain text, no links except tracking domain |

**Symptom: Low Meeting Rate (Replies but no meetings)**

| Check | What to Look For | Fix |
|---|---|---|
| Follow-up speed | Responding hours/days later? | Reply within minutes; speed of booking = close rate |
| Follow-up volume | Only 1-2 follow-ups? | Build 5-7 touch sequence -> `follow-up-sequences` |
| Booking friction | Calendar link buried? Too many steps? | Simplify: one link, one click |
| CTA clarity | Not actually asking for the meeting in replies? | After positive reply, propose specific times |

### Cold Call Diagnostic

**Low Connect Rate (<5%)**
1. Check data quality: Are numbers valid? Mobile vs. landline?
2. Check timing: Calling Wed-Thu, 8-10 AM or 4-5 PM?
3. Check spam status: Number registered? Rotating numbers?
4. Check targeting: Calling right persona level?

**Low Set Rate (<5% of conversations)**
1. Check opener: Using canned opener? "Bad time?" or "How's your day?"
2. Check problem proposition: Specific enough? (Hairy Lollipop Test)
3. Check objection handling: Arguing or using Miyagi?
4. Check persona: Too junior (no authority) or too senior (wrong problem frame)?
5. Check trigger quality: A-tier accounts vs. C-tier?

**Low Show Rate (<70%)**
1. Check confirmation: Day-before email sent?
2. Check day-of: Text reminder sent?
3. Check booking distance: More than 5 days out?
4. Check no-show protocol: Using 2/5/8-minute escalation?

---

## CAMPAIGN HEALTH SCORECARD

Use this weekly to track campaign health:

| Metric | This Week | Target | Status |
|---|---|---|---|
| Emails sent | ___ | Per volume plan | |
| Open rate | ___% | >30% | |
| Reply rate | ___% | >2% | |
| Bounce rate | ___% | <5% | |
| Spam rate | ___% | <0.3% | |
| Calls made | ___ | Per dial plan | |
| Connect rate | ___% | >5% | |
| Set rate | ___% | >5% | |
| Show rate | ___% | >80% | |
| LinkedIn requests sent | ___ | 200/week | |
| Acceptance rate | ___% | >40% | |
| Calls booked (all channels) | ___ | Per target | |

Red flags that require immediate action:
- Spam rate >0.3% -> PAUSE campaign, fix infrastructure
- Bounce rate >5% -> STOP sending, clean list
- Open rate <20% -> Deliverability crisis, audit immediately
- Show rate <50% -> Booking mechanics broken, fix confirmation flow
