---
name: Objection Handle
description: Handle a specific outreach objection across any channel (phone, email, LinkedIn DM, Facebook/Instagram DM). Activates outbound-psychology for the psychological framework, then routes to channel-specific skill for scripts. Outputs a complete response with psychological reasoning.
---

# Objection Handler

## Step 1: Gather Context

Ask the user:

1. **What channel?** (phone call, cold email reply, LinkedIn DM, Facebook/Instagram DM)
2. **What did the prospect say?** (exact words if possible)
3. **What stage of the conversation?** (first contact, follow-up, after interest shown, after call booked)
4. **What do you sell?** (one sentence -- needed for relevant reframing)
5. **Any context about the prospect?** (their role, company, previous engagement)

---

## Step 2: Classify the Objection

**Load skill:** `outbound-psychology` > references/persuasion-psychology.md

All objections reduce to 3 categories:

| Category | Examples | Core Fear |
|---|---|---|
| **Financial** | "Too expensive," "No budget," "Not in the budget this quarter" | Loss of money |
| **Trust** | "Never heard of you," "Send me information," "How did you get my number?" | Risk of wasting time with unknown entity |
| **Hesitation** | "Not interested," "Not a priority," "Call me in 6 months," "Need to think about it" | Fear of commitment / change |

### Key Psychological Principle
Most objections are NOT objections to your product. They are reactions to the interruption itself. You must handle the reaction before you can handle the objection. When you counter with a pitch, you increase resistance.

---

## Step 3: Apply Channel-Specific Framework

### For Phone Objections
**Load skill:** `cold-calling` (Mr. Miyagi Method + AREQ)

**Mr. Miyagi 3-Step Framework:**
1. **Agree** with the objection (removes all pressure, disarms the reaction)
2. **Incentivize conversation** (promise no more calls, use multiple-choice questions to get them talking)
3. **Sell the test drive, not the car** (what they get from a meeting even if they never buy)

Generate a response using this structure with the user's specific offer and objection.

### For Email Objections
**Load skill:** `cold-email-copy`

Email objection handling is more about the REPLY strategy:
- Acknowledge their concern
- Reframe the value (not your product -- the insight/outcome)
- Offer a lower-friction next step
- Use referral strategy if appropriate (near 100% booking rate when asking for the right person)

### For LinkedIn DM Objections
**Load skill:** `linkedin-outreach`

LinkedIn objection handling stays grounded and non-needy:
- Stay positive, come from a grounded state
- Do not get fearful or prideful
- Foreshadow value FIRST (controls frame)
- Then address the objection casually
- If they decline a call: leave with genuine value ("Let me know if there's any way I can help")
- Follow up in 1-2 weeks with rope-throwing (foreshadow intros, send free resources)

### For Facebook/Instagram DM Objections
**Load skill:** `dm-outreach`

DM objection handling focuses on pain discovery:
- Have you reached Level 2 pain? If not, the objection is premature -- go deeper before proposing a call
- Use the 4-step consulting framework (Awareness > Cold > Warm > Hot)
- No pain, no next step -- only book when Level 2+ pain identified

---

## Step 4: Deliver the Response

Output:

1. **Objection category:** Financial / Trust / Hesitation
2. **Why they said this:** The psychological reason behind the objection (not face value)
3. **Recommended response:** Channel-appropriate script using the relevant framework
4. **Tone guidance:** How to deliver it (speed, energy, confidence level)
5. **If they push back again:** Second-level response
6. **The exit strategy:** What to do if they are truly not interested (graceful exit that leaves door open)

### Tone Rules by Channel
- **Phone:** Slow down when hit with an objection. Laugh to dispel tension. Curious tone when incentivizing. Low pressure when selling the test drive.
- **Email:** Keep it short. One reframe. One new angle or offer. Never argue.
- **LinkedIn DM:** Restrained. "100%" as a separate message (gives it room to breathe). "Just a chat" framing. Outcome independent.
- **Facebook/Instagram DM:** Empathetic. Go deeper into pain. Genuine curiosity about their situation.

---

## Common Objection Quick Reference

| Objection | Channel | Quick Response Direction |
|---|---|---|
| "Not interested" | Any | Agree -> find the real reason -> sell the test drive |
| "No budget" | Any | Agree -> is it fiscal year or approval process? -> value of preparation |
| "Send me info" | Phone/Email | Trade info for calendar hold (The Dart) OR be disarmingly blunt |
| "We use a competitor" | Phone/Email | Agree (never badmouth) -> trap question to find gap -> test drive |
| "Call me in 6 months" | Phone | Is there something specific in 6 months? (9/10 times: no) -> blunt line |
| "Too expensive" | Phone/Email | ROI math -> lifetime value -> guarantee if available |
| "Are you trying to sell me?" | LinkedIn | "Not trying to sell you. Just want to see if I can help, genuinely." |
| "Not looking for coaching/services" | LinkedIn | "100%. Down for just a chat where I get under the hood & find blind spots" |
| Ghost (no response) | Any | Follow-up sequence with rope-throwing, NOT guilt trips |
| Hung up on you | Phone | Note the date/time/last words. Call back ONE WEEK later referencing all three |
