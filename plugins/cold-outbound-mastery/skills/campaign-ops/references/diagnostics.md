# Campaign Diagnostics: Troubleshooting Decision Trees

## Email Campaign Diagnostics

### Problem: Campaign Metrics Are Low (All channels)

**FIRST STEP - Verify Product Context**
Before any technical troubleshooting: Do you understand your product positioning?
- Can you clearly articulate the problem you solve?
- Who is your ideal customer profile (ICP)?
- What specific outcome/metric do you deliver?
- What's the price point and deal size?

If NO → Your campaign will underperform regardless of execution. Clarify ICP and positioning first.

If YES → Continue to specific metric diagnostics below.

---

### Diagnostic: Low Open Rates (Below 70%)

**Decision Point 1: Is this a subject line problem or deliverability problem?**

**Action: Run Deliverability Test**
1. Create BRAND NEW email accounts on 4+ providers (never used before)
   - Gmail
   - Yahoo/AOL
   - Outlook/Hotmail
   - iCloud
2. Have someone send 5 test emails to each account using your domain
3. DO NOT use your own accounts (you've whitelisted your domain, results invalid)
4. Check where emails land: Primary Inbox, Promotions, or Spam?

**If emails land in SPAM/PROMOTIONS folder:**
→ You have a DELIVERABILITY problem (not subject line)
→ Go to Deliverability Diagnostics section below

**If emails land in PRIMARY INBOX:**
→ You have a SUBJECT LINE problem (not deliverability)
→ Go to Subject Line Diagnostics section below

---

### Diagnostic: Deliverability Issues (Emails in Spam)

**Root Cause Checklist:**

**1. Domain Authentication Issues (CRITICAL)**
- [ ] SPF record configured? (Check: your domain SPF record includes mail provider)
- [ ] DKIM enabled? (Check: mail provider shows DKIM status as "signing")
- [ ] DMARC configured? (Check: your domain has DMARC policy, ideally p=quarantine)
- [ ] Domain age: How old is the domain?
  - New domain (<14 days): Expect spam folder initially. DO 14-day warmup
  - Old domain (>30 days): Should not be spam folder issue

**Action if authentication broken:**
1. Contact your email provider (MailShake, Lemlist, etc.)
2. Verify SPF record in domain DNS
3. Enable DKIM signing
4. Set up DMARC policy (start with p=none, move to p=quarantine)
5. Wait 48 hours for DNS propagation
6. Re-test with new accounts

**2. Domain Warmup Issues**
- [ ] Is this a brand new domain?
- [ ] Did you start with 50+ emails on day 1?
- [ ] Are you sending to high-volume lists immediately?

**Action if warmup incomplete:**
1. Pause campaign
2. For next 14 days: Send 10-20 emails/day only
3. Send to responsive people (clients, colleagues, warm lists)
4. Gradually increase volume (day 5: 30/day, day 10: 50/day, day 14: 100/day)
5. After 14 days, resume full campaign

**3. List Quality Issues**
- [ ] What's your bounce rate? (Check email platform dashboard)
- [ ] If >8% bounce: Your list is bad quality
- [ ] Where did the list come from? (Random scraping? Old list? API error?)

**Action if list quality poor:**
1. Upload list to NeverBounce
2. Remove all invalid/risky emails (NeverBounce labels these)
3. Start with top 100 highest-quality leads
4. If new batch: Validate before sending
5. Going forward: Only use verified sources (UpLead, Apollo, Seamless) or validate first

**4. Volume Issues**
- [ ] Are you sending >100 emails/day from single domain?
- [ ] Are you sending to same ISP (Gmail) >50 times/day?

**Action if volume too high:**
1. Reduce to 50-70 emails/day from this domain
2. Space emails across different times of day
3. Add second domain if you need higher volume
4. Monitor bounce rate - should drop within 2-3 days

**5. Content Issues**
- [ ] Are you using spam trigger words? (FREE, CONGRATULATIONS, GUARANTEE, URGENT, etc.)
- [ ] Does email have multiple links? (Reduces open rate AND meeting bookings)
- [ ] Does email have attachments? (Reduces deliverability)

**Action if content problematic:**
1. Remove all links except calendar booking link (if any)
2. Remove spam trigger words
3. Remove attachments (use Google Drive link or email as plain text)
4. Simplify email structure: 3-4 short paragraphs max
5. A/B test clean version vs. previous version

---

### Diagnostic: Subject Line Issues (Emails reaching Inbox but not opened)

**Root Cause: Subject Line Is Not Compelling Enough**

Your subject line should:
- [ ] Be personalized (mention something about THEM, not your company)
- [ ] Be specific (avoid generic praise like "interested in a conversation?")
- [ ] Be under 50 characters (shorter = better mobile performance)
- [ ] Create curiosity without clickbait (should be truthful)
- [ ] Avoid ALL CAPS (triggers spam filters + feels aggressive)

**Examples:**
- ✗ Bad: "Quick question about your marketing"
- ✓ Good: "Saw your SaaS Conf 2024 talk about churn"

- ✗ Bad: "Let's grow your business together!"
- ✓ Good: "Your recent $5M round in marketing automation"

- ✗ Bad: "RE: Partnership Opportunity"
- ✓ Good: "5 ecommerce brands + [your solution] = 34% ROAS lift"

**Action: A/B Test Subject Lines**
1. Write 3-5 new subject line variations (each takes different angle)
2. Send to 100-150 people with each variation
3. Track open rate per variation after 5 days
4. Winning variation = highest open rate (target 80%+)
5. Next batch: Use winning variation as template for more testing
6. Never send same subject line twice to same person

---

### Diagnostic: Low Reply Rates (Below 15%)

**Root Cause Analysis:**

**Decision Point: Are opens good (>70%) but replies low (<15%)?**

**If YES:** Your copy is weak, not your subject line
- First line is not personalized enough
- Case study/social proof is weak or irrelevant
- Offer is not clear or compelling
- Call to action is too big an ask

**If NO (low opens + low replies):** Combination of subject line + copy + deliverability issues
- Go back to "Low Open Rates" diagnostic

---

### Diagnostic: Copy/Email Body Issues

**The 3C Framework Issues (Alex Berman)**

**Issue 1: First Line (Compliment) - Is It Actually Personalized?**

RED FLAGS:
- [ ] You copy-pasted the first line for multiple people
- [ ] The compliment is generic ("Your company looks great")
- [ ] You researched them but didn't mention specifics
- [ ] The first line doesn't match ANY research on them

EXAMPLE OF BAD FIRST LINES:
- "Hi Sarah, hope this email finds you well" ← Generic, no research
- "I saw you work at Acme Corp" ← Obvious from company email
- "You seem like a visionary leader" ← Flattery without specifics

EXAMPLE OF GOOD FIRST LINES:
- "Saw your keynote at MarketingProfs 2024 about iOS privacy" ← Specific event
- "Your recent LinkedIn post on churn got 2K reactions" ← Specific achievement
- "Noticed you're hiring for [role] - growing team?" ← Specific business signal

**Action if first line weak:**
1. Spend 5-10 minutes researching EACH person before emailing
2. Find 1 specific thing about them (speech, article, job change, achievement)
3. Mention that specific thing in opening line
4. Test new version: should see 2-3x reply increase within 50-100 emails

**Issue 2: Case Study (Proof) - Is It Relevant to THEIR Situation?**

RED FLAGS:
- [ ] Case study is about your business, not about results you delivered
- [ ] Case study is too long (more than 1 sentence)
- [ ] Case study mentions metric that doesn't matter to this prospect
- [ ] Case study is generic (could apply to anyone)

EXAMPLE OF BAD CASE STUDIES:
- "We work with marketing teams to improve their campaigns" ← Not a case study
- "One client saw 100% growth in followers" ← Vague metric, no context
- "We helped improve performance" ← No number, no timeline

EXAMPLE OF GOOD CASE STUDIES:
- "Helped 12 ecommerce brands increase ROAS by 34% in 60 days using [specific tactic]"
- "Took failing SaaS company from 2% MoM churn to 95% net dollar retention in 4 months"
- "Generated $2.3M pipeline for mid-market software company in Q1 using [specific process]"

**Action if case study weak:**
1. Pick ONE recent win with real metric + timeline
2. Make sure metric is relevant to THIS prospect's role/industry
3. Keep it to 1 sentence max
4. Test new version against old version

**Issue 3: Call to Action - Is the Ask Too Big?**

RED FLAGS:
- [ ] CTA is a button ("Schedule a Call" button)
- [ ] CTA is asking for 30-60 min call directly
- [ ] CTA is asking them to fill out form or watch video
- [ ] CTA mentions price or product details (should not)

EXAMPLE OF BAD CTAs:
- "Let's schedule a 30-minute call to discuss your needs" ← Too big ask
- "Click here to book a call on my calendar" ← Button, too formal
- "What's your annual marketing budget?" ← Asking too much info too early
- "Watch this 5-minute demo video" ← They won't, too much friction

EXAMPLE OF GOOD CTAs:
- "Quick question - are you open to exploring if we could add a similar result?" ← Yes/no
- "Does that sound relevant to what you're working on?" ← Casual, yes/no
- "Worth a 15-min conversation to see if there's fit?" ← Small commitment

**Action if CTA too big:**
1. Change to yes/no question (not calendar link, not button)
2. Make ask small and casual (15 min call, not 30-60)
3. Don't mention product/price/details yet
4. Test new version: should see 3-5x reply increase within 50-100 emails

---

### Diagnostic: Follow-Up Sequence Issues

**Problem: People reply but don't book meetings**

**Root Cause Checklist:**

**1. Follow-Up Cadence Issues**
- [ ] Are you following up at all? (70% of conversions happen in follow-ups)
- [ ] What's your follow-up timeline? (Recommended: Day 3, Day 5, Day 8, Day 12)
- [ ] Are follow-ups spaced properly? (Too fast = annoying; too slow = forgotten)

**Action if follow-ups missing or poorly timed:**
1. Map follow-up sequence:
   - Day 0: Initial email
   - Day 3: Follow-up 1 (reference previous, add new angle)
   - Day 5: Follow-up 2 (different hook or social proof)
   - Day 8: Follow-up 3 (final attempt, shift angle completely)
   - Day 12: Follow-up 4 (last attempt before sunset)
2. Set calendar reminders for each follow-up
3. Each follow-up should reference the previous message

**2. Follow-Up Content Issues**
- [ ] Does follow-up reference the previous email? ("Wanted to follow up on my last email...")
- [ ] Does follow-up add NEW value? (New angle, new case study, new social proof)
- [ ] Or is it just "checking in?" (Weakest follow-up possible)

EXAMPLES OF STRONG FOLLOW-UPS:
- "Wanted to follow up on my last email. I also noticed [new discovery about them]. Thought it was relevant given [your use case]"
- "Know you're probably busy. Sent this case study to a similar [role] at [company type]. See attached. Thought you might find it useful."
- "Just got off a call with [similar company] who's facing the exact problem I mentioned. If you're in a similar boat, worth a quick conversation?"

EXAMPLES OF WEAK FOLLOW-UPS:
- "Just following up on my previous email. Let me know if you're interested!"
- "Checking in to see if you got my email and if you'd like to chat"
- "Any interest? Would love to chat about this"

**Action if follow-ups weak:**
1. Rewrite each follow-up to add new value or angle
2. Each follow-up gets a new case study or hook (don't repeat the same message)
3. Test new sequence: should see 30-50% increase in conversions within 2 weeks

**3. Objection Handling Issues**
- [ ] When they say "Too expensive," do you respond with price? (TRAP - don't answer)
- [ ] When they ask "What's the cost?", do you explain why you can't quote via email?
- [ ] When they say "Not interested," do you give up? (50% of converts come after "no")

**Specific Objection: "What's the cost?"**
Response: "I'm happy to discuss pricing with you. I'd be wasting both our time if I threw a random number at you via email. Our work is custom enough that a quick call would help us understand what you need first. Sound fair?"

**Specific Objection: "Too expensive" / "Out of budget"**
Response: "Totally understand budget constraints. Most of my clients said similar thing initially. Worth asking - if we could show [specific ROI], would timing/budget shift? If not, no worries. I'll remove you from follow-ups."

**Specific Objection: "Not interested"**
Response: "No problem. Just a heads up - most companies I've worked with said the same thing initially but ended up in [relevant conversation after 3-4 touch points]. I'll check back in [specific time]. Fair?"

---

### Diagnostic: Segment-Level Issues

**Problem: One segment has 80% open rate, another has 30%**

**Root Cause: Lack of Segmentation or Poor Segmentation**

**Action: Segment by:**
1. **Job Title:** CEO/VP/Manager (different copy for each)
2. **Company Size:** 10 people vs. 1000 people (different pain points)
3. **Industry:** Healthcare copy ≠ SaaS copy ≠ Ecommerce copy
4. **Engagement Level:** Cold (never interacted) vs. Warm (opened previous emails)
5. **Geographic:** Different regulations, business hours, holidays
6. **Source:** Leads from API ≠ leads from manual research (different quality)

**Action per segment:**
1. Create separate email variation for each segment
2. Reference segment-specific context in first line
3. Track open/reply rate per segment
4. Winning segment: Use as template for other segments
5. Losing segment: Either improve copy or remove from list

---

## Cold Calling Diagnostics

### Problem: Low Contact Rate (Below 46.5%)

**Root Cause Analysis:**

**1. Calling at Wrong Time**
- [ ] Are you calling outside 8 AM - 9 PM?
- [ ] Are you calling on Sunday/Monday (lower answer rates)?
- [ ] Are you calling during 12-1 PM lunch time?

**Action if timing wrong:**
- Call Wednesday-Thursday, 8-10 AM and 4-5 PM only
- Avoid Monday (people catching up), Friday (people leaving)
- Avoid 12-1 PM lunch window
- Summer (June-Aug): Call earlier (8-9 AM) before people leave

**2. Wrong Number List Quality**
- [ ] Are numbers current? (Sourced recently or old database?)
- [ ] Are numbers valid phone numbers? (Proper format, business numbers)
- [ ] Are you reaching decision makers or gatekeepers?

**Action if list quality poor:**
- Use Apollo.io or LinkedIn Sales Navigator to get fresh numbers
- Only call people with specific role (not "founder" - too vague)
- Validate number format before dialing
- Expect 40-50% to be wrong/disconnected

**3. Call Opening/Script Issues**
- [ ] Are you leading with your company name? (They don't care yet)
- [ ] Are you asking permission? ("Do you have 30 seconds?")
- [ ] Are you immediately pitching? (Too early)

**ACTION: Use Sean Longden Opening Framework**
1. Lead with their name and company (acknowledge them)
2. Give reason for call in 1 sentence (context)
3. Ask permission briefly ("Do you have 30 seconds?")
4. Skip the pitch - go to qualifying question
5. Example: "Hi [Name], I'm calling because [specific reason] - do you have 30 seconds?"

**4. Voicemail Issues**
- [ ] Are you leaving voicemails? (You need to)
- [ ] Are voicemails too long? (Keep to 20-25 seconds)
- [ ] Are voicemails just your name/number? (No context)

**ACTION: Voicemail Strategy**
- Leave voicemail on every call (even if wrong person)
- Content: "Hi [Name], this is [Your Name] from [Company]. Reason for call [1 sentence]. My number is [number]. Thanks."
- Length: 20-25 seconds max
- Drop 3-5 voicemails over 2 weeks before moving on
- Follow-up voicemail with email 1 day later

---

### Problem: Low Contact-to-Appointment Rate (Below 22%)

**Root Cause: Script/Qualifying Issues**

**1. You're Pitching Too Early**
- [ ] First thing you do after reaching them: Pitch your service?
- [ ] Are you immediately asking if they want to meet?
- [ ] Are you not qualifying at all - just booking everyone?

**ACTION: Use Qualifying Questions Instead**
Do NOT pitch. Instead:
1. Name + reason for call (1 sentence)
2. Qualifying question: "Quick question - are you currently responsible for [problem area]?"
3. If YES → "Worth a 15-minute call to see if there's fit?" (NOW you ask for meeting)
4. If NO → "No problem, who would be a better person to talk to?" (Get referral)

**2. You're Not Handling Objections**
- [ ] When they say "I'm not interested," do you give up?
- [ ] When they say "Too busy right now," do you accept it?
- [ ] When they ask "What's this about?", do you pitch immediately?

**ACTION: Objection Responses**
- "Not interested" → "I get it. Just out of curiosity - is it the timing or the concept that doesn't resonate?"
- "Too busy" → "Totally understand. Is Thursday or Friday better to talk for 15 minutes?"
- "What's this about?" → "Quick context - I was calling because [specific reason]. Quick question - [qualifying question]?"

**3. You're Not Confirming Details**
- [ ] Are you assuming they want to meet?
- [ ] Are you not sending calendar link after call?
- [ ] Are you not confirming time/date before hanging up?

**ACTION: Booking Call Process**
1. After they say yes to meeting: "Does Thursday at 2pm work for you?"
2. Get specific time confirmation on the call
3. Say: "I'll send you a calendar invite with the Zoom link"
4. Send calendar invite within 5 minutes of hanging up
5. Follow up 24 hours before call: "Looking forward to tomorrow at 2pm. Here's the Zoom link"

---

## DM Campaign Diagnostics

### Problem: Not Getting DM Replies

**Root Cause Analysis:**

**1. You're Sending Cold DMs to Non-Engaged Audience**
- [ ] Are you DMing people who've never engaged with your content?
- [ ] Are you DMing cold (no prior interaction)?

**Action if cold audience:**
- Build audience first (post 2-3 weeks of content first)
- Let them engage with your content
- THEN DM engaged followers (10-20x better response)
- Or use multi-channel: Email first → wait 3 days → LinkedIn → then DM (warmer path)

**2. Your First Message Is a Pitch**
- [ ] Do you lead with business ask?
- [ ] Do you mention your product/service in first message?
- [ ] Do you ask them to click a link or book a call immediately?

**ACTION: Rapport-First Messaging**
- Message 1: Comment on something they posted or reference shared interest (no business ask)
- Message 2: Share relevant value or insight (no pitch)
- Message 3: Introduce yourself + business context (now you can soften pitch)
- Message 4-5: Call to action (after 5-7 message sequence)

**3. Timing Issues**
- [ ] Are you messaging during off-hours? (Time zones matter)
- [ ] Are you messaging at same time every day? (Vary it)
- [ ] Are you waiting long enough between messages? (Should be 2-5 hours min)

**ACTION: DM Cadence**
- Don't send all DMs at once (looks automated)
- Space out: Message 1 → wait 3-6 hours → Message 2 → wait 6-12 hours → Message 3
- Best times: 10 AM, 2 PM, 8 PM (varies by timezone/platform)
- Platform variations: Facebook = more daytime; Instagram = more evening

**4. Segment Wrong (Cold vs. Warm)**
- [ ] Treating all DMs same (cold + warm)
- [ ] Not recognizing warm audience converts 5x better

**ACTION: Segment DM Strategy**
- Cold audience (never engaged): 2-5% conversion, longer sequence, lower daily volume
- Warm audience (engaged with content): 10-20% conversion, shorter sequence, higher volume
- Build warm audience pool first (2-4 weeks content)
- Then DM warm first, cold second

---

### Problem: Getting Replies But No Meetings Booked

**Root Cause: Follow-Up Sequence Broken**

**1. You're Pitching Too Early in DM Sequence**
- [ ] Do you mention your offer before message 5-7?
- [ ] Are they interested in you as a person yet?

**ACTION: Rapport Phase (Messages 1-3)**
- Build genuine connection around shared interest
- Ask questions about THEM
- Show you understand their world/content
- Zero business talk

**Warm Phase (Messages 4-7)**
- Now mention your background/business
- Share 1-2 relevant insights or stories
- Soft intro to what you do
- Still mostly about them

**Close Phase (Messages 8+)**
- Now move to call/Zoom booking
- Example: "This would be better discussed on a quick call. You free Thursday at 2?"

**2. Wrong Call-to-Action**
- [ ] Are you asking for Zoom/call link to be clicked in DM?
- [ ] Or are you asking them to book directly via calendar?

**ACTION: DM CTA Framework**
- Don't ask them to click external link in DM (they won't)
- Instead: "Quick call worth having?" (get yes)
- Then: "Cool. I'll send you a Zoom link on [platform]" or "Share your calendar?"
- Never push them off-platform until they're warm

**3. No Follow-Up System**
- [ ] When someone doesn't reply to Message 3, do you send Message 4?
- [ ] Or do you give up?

**ACTION: DM Follow-Up Sequence**
- Message 1: Initial rapport
- Message 2: Value add (wait 6 hours)
- Message 3: Soft business intro (wait 8 hours)
- Message 4 (if no reply): Bump message ("Not sure if you saw my last message")
- Message 5 (wait 2 days): Different angle ("Thought of you because...")
- Message 6 (wait 3 days): Final attempt or move on

---

## Multi-Channel Diagnostics

### Problem: Low Conversion Despite Multiple Channels

**Root Cause: Channels Not Coordinated**

**1. Timing Issues Between Channels**
- [ ] Are you sending email + LinkedIn + phone same day? (Overwhelming)
- [ ] Are you sending all on weekday mornings? (Annoying)
- [ ] Is there no spacing between touches?

**ACTION: Proper Multi-Channel Sequencing**
- Day 0: Email initial (8 AM)
- Day 1: Nothing (let them read)
- Day 2: LinkedIn connection/message (2 PM)
- Day 3: Email follow-up (9 AM)
- Day 5: Phone call (4 PM)
- Day 6: Voicemail (wait 4 PM)
- Day 7: Email with case study (10 AM)
- Day 9: Final phone attempt (8:30 AM)

**2. Inconsistent Messaging Across Channels**
- [ ] Email says one thing, LinkedIn says another?
- [ ] Phone script contradicts email?

**ACTION: Unified Message**
- Email opening line → LinkedIn message should reference same insight
- Phone script should reference previous email/LinkedIn touch
- All channels telling same story, different format

**3. Missing the "Warm Handoff"**
- [ ] Email gets reply, then what? Do you call them?
- [ ] Or do you wait for next sequence touch?

**ACTION: Warm Handoff Process**
- Email reply = Signal they're interested
- Immediate action: Send calendar link in email
- Wait 2 hours, if no calendar click: Send LinkedIn message saying "Saw your reply, easiest to chat on Zoom [link]"
- Wait 3 hours, if still no action: Phone call saying "Got your email, great to hear. Quick 15 minute call?"

---

## General Troubleshooting Tree

```
Campaign metrics bad?
│
├─→ ALL metrics low (opens, replies, meetings)
│   └─→ Is product/ICP/positioning clear?
│       ├─→ NO: Fix positioning first, THEN relaunch campaign
│       └─→ YES: Check specific metrics below
│
├─→ Opens low, replies/meetings low
│   └─→ Deliverability test: Check spam folder status
│       ├─→ Spam folder: Fix authentication + warmup + list quality
│       └─→ Primary inbox: Fix subject line (A/B test)
│
├─→ Opens good (80%+), replies low (< 10%)
│   └─→ Copy issue: First line + case study + CTA
│       └─→ A/B test each element, win rate must improve
│
├─→ Opens + replies good, meetings low (< 4%)
│   └─→ Follow-up sequence issue
│       └─→ Map follow-up cadence + objection responses
│
├─→ Metrics vary by segment (some good, some bad)
│   └─→ Segment differently: job title, industry, company size
│       └─→ Write segment-specific copy
│
└─→ One channel working, others not
    └─→ Check platform-specific settings + timing
        └─→ Multi-channel requires specific sequencing
```

---

## Quick Diagnostic Checklist Before Changing Anything

Before you change your campaign:
- [ ] Sample size: Are you testing with at least 100-200 people?
- [ ] Time: Have you let it run 5+ days to get full follow-up sequence?
- [ ] Segment: Are you mixing different audience types (cold + warm, CEO + manager)?
- [ ] One variable: Did you change only ONE thing (not multiple)?
- [ ] Documentation: Are you tracking which version is which?

If you haven't checked all of these, your diagnostics are unreliable. Run again with proper controls.
