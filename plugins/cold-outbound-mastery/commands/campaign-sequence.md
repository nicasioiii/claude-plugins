---
name: Campaign Sequence
description: Design a complete multi-touch follow-up sequence with timing, channels, and templates
argument-hint: "<campaign context, channels, or duration>"
---

# /campaign-sequence

Design a full multi-touch outbound sequence integrating email, LinkedIn, phone, and voicemail with specific timing, templates, and channel integration.

## Trigger

User runs `/campaign-sequence` or asks to design a follow-up sequence, outbound cadence, multi-touch sequence, drip sequence, or campaign sequence.

## Skills Activated

- `follow-up-sequences` (primary)
- `cold-email-copy` (for email content)

## Gather Context

Before designing, collect or infer these inputs. Check `.claude/product-marketing-context.md` first:

1. **What channels are available?** (email, LinkedIn, phone, voicemail, DM)
2. **What is the target persona?** (title level: C-suite, VP, Director, Manager)
3. **Is this high-effort or low-effort?** (personalized A-tier or templated B/C-tier)
4. **How many problem angles do you have?** (ideally 2 from messaging matrix)
5. **What is the initial email?** (already written, or need to create it first → route to `/cold-email`)
6. **What tools/platform are you using?** (Mailshake, Lemlist, Outreach, Apollo, manual)

## Sequence Tier Selection

| Account Tier | Effort Level | Duration | Channels | Touches |
|---|---|---|---|---|
| A-Tier (strong triggers) | High effort | 21-28 days | Email + Phone + LinkedIn | 7 emails + 3-4 calls + 3 LinkedIn |
| B-Tier (ICP match) | Standard | 14-21 days | Email + Phone + LinkedIn | 5-7 emails + 2 calls + 2 LinkedIn |
| C-Tier (broad ICP) | Low effort | 7-14 days | Email only (+ call openers) | 4-5 automated emails |

## Output Format

### 1. Sequence Calendar

Deliver a day-by-day calendar showing:
- Day number
- Channel(s) used
- Action type (triple tap, double tap, single)
- Content summary
- Subject line (new thread or reply)

### 2. Email Templates

For each email in the sequence:
- Subject line (or "reply to previous")
- Full email body
- Timing relative to previous touch
- Problem angle (1 or 2)

### 3. LinkedIn Messages (If Applicable)

- Connection request strategy (blank vs. note)
- DM templates for each LinkedIn touch
- Timing relative to email sequence

### 4. Phone/Voicemail Scripts (If Applicable)

- When to call in relation to email sends
- Voicemail script (15-30 seconds max, point to email)
- What to say if they pick up (route to `cold-calling` skill)

### 5. No-Show Prevention Protocol

- Day-before confirmation email template
- Day-of text/LinkedIn message
- 2/5/8 minute escalation protocol
- Rescheduling email template

### 6. Metrics to Track

- Target open rate: >30% (email)
- Target reply rate: >2% (email)
- Target connect rate: 5-13% (phone)
- Target set rate: 5-17% (phone)
- Target show rate: tracked via calendar confirmations
- Bounce rate: <5%
- Spam rate: <0.3%

## Sequence Architecture Templates

### High-Effort A-Tier (30MPC K.I.S.S.)

**Week 1 -- Problem #1:**
- Day 1 (Tue): TRIPLE TAP -- Email 1 (personalized REPLY method) + Call + VM + LinkedIn connect
- Day 3 (Thu): DOUBLE TAP -- Email 2 (bubble-up bump) + Call

**Week 2 -- Problem #2:**
- Day 8 (Tue): TRIPLE TAP -- Email 4 (new subject, new problem) + Call + VM + LinkedIn DM 1
- Day 10 (Thu): DOUBLE TAP -- Email 5 (pushaway bump) + LinkedIn DM 2

**Week 3 -- Get the Truth:**
- Day 15 (Tue): Email 6 (get the truth) + LinkedIn DM 3 (video)
- Day 17 (Thu): Email 7 (final pushaway)

### Standard B-Tier (Berman + Cold Email Wizard Hybrid)

- Day 1: Email 1 (initial cold email)
- Day 4: Email 2 (quick bump)
- Day 8: Email 3 (value-add / two ideas)
- Day 12: Email 4 (case study or new angle)
- Day 16: Email 5 (breakup)
- Day 4 + Day 8: Optional phone calls to openers

### Low-Effort C-Tier (Acquisition X)

- Day 1: Email 1 (4C formula email)
- Day 4: Email 2 (gentle reminder, same thread)
- Day 9: Email 3 (new angle + value)
- Day 16: Email 4 (social proof / case study)

## Post-Sequence Actions

After the sequence completes:
- **No response:** Add to 30-day reconnect cadence
- **Opened but no reply:** Mark warm, re-engage in 2-4 weeks with new angle
- **Replied with objection:** Route to `cold-email-copy/references/objection-handling-email.md`
- **Booked meeting:** Trigger no-show prevention protocol from `references/meeting-booking-mechanics.md`
- **Bounced/unsubscribed:** Remove immediately, update DNC list
