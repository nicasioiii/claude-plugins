# Reference: Welcome Sequence Tactics -- Advanced Strategies

## CONDITIONAL CONTENT DEEP DIVE (E04)

### What It Is
Dynamic content blocks within a single email that show different text/offers to different subscriber segments.

### Implementation by ESP
| ESP | Feature Name | Complexity |
|-----|-------------|------------|
| Active Campaign | Conditional Content | Powerful but glitchy |
| ConvertKit | Conditional Content / Liquid Tags | Moderate |
| Klaviyo | Show/Hide Blocks + Template Tags | Moderate |
| Mailchimp | Merge Tags + Conditional Logic | Basic |

### Use Cases in Welcome Sequences
1. **Lead magnet vs. newsletter opt-ins:** Show different intro paragraph based on how they found you
2. **Product owners vs. non-owners:** Show different offers (upgrade vs. first purchase)
3. **Active promotion vs. no promotion:** If a launch is happening, acknowledge it; if not, standard content
4. **Geographic segmentation:** Show different testimonials or product recommendations based on location

### Example Block
```
{% if subscriber.tag contains "lead-magnet-A" %}
  Since you grabbed my [Lead Magnet A], I'm guessing you're working on [Topic A].
{% elsif subscriber.tag contains "newsletter-only" %}
  Since you signed up for my emails, you're clearly someone who values [Topic].
{% endif %}
```

---

## REPURPOSING BROADCASTS INTO WELCOME SEQUENCES (E04)

### The System
1. Track performance of every regular broadcast email
2. When one performs exceptionally well (high opens, clicks, replies, sales), flag it
3. Add it into the welcome sequence at an appropriate position
4. Adjust any time-sensitive references ("this week," specific dates)

### What Qualifies as "Exceptional"
- Open rate 50%+ above your average
- Click-through rate 2x+ your average
- Reply rate above 3%
- Generated sales or bookings directly

### Placement Logic
- High-engagement/fun emails: earlier in the sequence (emails 5-7)
- Sales-heavy emails: later in the sequence (emails 8+)
- Teaching/value emails: middle positions (emails 6-8)
- Myth-busting or contrarian emails: later when trust is established

### Growth Pattern
This is how welcome sequences naturally grow over time:
- Year 1: 5-7 emails
- Year 2: 10-15 emails
- Year 3: 15-25 emails
- Each addition is battle-tested from live broadcast performance

---

## SUBJECT LINE FORMULAS FOR WELCOME SEQUENCES (E04)

### Delivery Emails (Be Clear, Not Clever)
- "Get it: Your [Lead Magnet Name] from [Brand]"
- "Here's your [thing] + what to expect"
- "[First Name], your [download/guide/template] is ready"

### Resell / Engagement Emails (Curiosity + Personality)
- "Ooh, it's nice in here, [First Name]"
- "3 humiliating mistakes"
- "Let's not fake it, [First Name]"

### Transparency / Selling Emails (Tension + Honesty)
- "Too soon?"
- "I sell things. There, I said it."
- "Is this it for us? I don't wanna say goodbye"

### Value / Teaching Emails (Curiosity + Benefit)
- "These 5 words are a huge turnoff (you've been warned)"
- "My #1 favorite writing trick (any guesses?)"
- "What if it IS about you?"

### Survey / Engagement Emails (Intrigue + Fun)
- "Bribe you" (65% open rate)
- "Quick Q -- need to know this about you"
- "I'll trade you"

### Subject Line Patterns That Work (E04)
| Pattern | Example | Why It Works |
|---------|---------|-------------|
| Vague + emotional | "Too soon?" | Creates curiosity gap with emotional tension |
| Personal/intimate | "Come to my room?" | Feels private, irresistible to open |
| Numbered + curiosity | "You're one of these 5 kinds of people" | Self-classification is compelling |
| Taboo/tension | "Brag" | Bragging is taboo -- we need to know what about |
| Misleading-but-fun | "have a few left -- want this?" | "A few minutes" not items |

---

## THE SECOND CHANCE EMAIL DEEP DIVE (E04)

### Why It Exists
~8% of people who check "no" to newsletter emails on a lead magnet opt-in form will change their mind when asked directly with personality and humor.

### Timing
- Send 1-2 days after lead magnet delivery
- Only to subscribers tagged as "opted-out-of-newsletter"

### Structure
1. "Wanted to make extra sure you don't want my newsletter emails"
2. Acknowledge their choice: "You checked the 'No' box"
3. Playful guilt: "I'll be OK with it... in time. But will you?"
4. Single CTA: "YES, [Name], keep raining genius upon my inbox!"
5. Clear outcome: "If not, this is the last you'll hear from me"

### Key: Do Not Be Aggressive
- Respect the "no" -- this is a gentle one-time ask
- Humor and personality do the work, not pressure
- One email only. Never follow up on the second chance.

---

## UPSELL / TRIPWIRE PAGE STRATEGY (E04)

### What It Is
After any opt-in, redirect the thank-you page to offer a product at half price with a countdown timer (10-20 minutes).

### Implementation
1. Subscriber completes opt-in form
2. Thank-you page loads with countdown timer and discounted offer
3. If they buy: tag as purchaser, exclude from welcome sequence product pitches
4. If they do not buy: normal welcome sequence continues

### Impact on Welcome Sequence
- Because many buy via the tripwire, fewer warm prospects remain for the welcome sequence
- BUT the welcome sequence still adds meaningful incremental sales
- Adjust product mentions: use conditional content to show different offers to tripwire buyers

### What to Offer
- Your most popular/accessible product at 50% off
- A mini-course or template that is a natural next step from the lead magnet
- A consultation or call at a reduced rate

---

## MONETIZATION MECHANICS IN WELCOME SEQUENCES (E04)

### The 10-Day and 100-Day Pipeline
Every email that drives to a product page contributes to TWO conversion windows:
- **10-day pipeline:** 3.92% of clickers buy within 10 days (impulse + immediate need)
- **100-day pipeline:** 13.34% of clickers buy within 100 days (nurture + eventual need)

This means even emails that seem to "fail" at driving immediate sales are planting seeds.

### Direct Product Sales Tactics
- Feature products in PS sections (low-pressure, high-visibility)
- Dedicate specific emails to product pitches (story + sell format)
- Use conditional text: show product offers only to those who have not purchased
- Track which welcome email positions drive the most revenue and optimize those

### Affiliate Transparency Framework
1. The "I sell things" email serves as the initial disclosure
2. "I get a commission, which I like to call 'thank-you money'"
3. Warn about upcoming promotional periods in advance
4. Explain why new subscribers are not excluded from active promotions
5. Always offer soft opt-out for promotions

### Survey as Segmentation for Monetization
- **Question 1:** "What are you interested in?" -- routes to relevant content and offers
- **Question 2:** "Which of my products have you already bought?" -- excludes from irrelevant promos
- **People who answer "none / not buying":** Still valuable for content engagement; exclude from promos but keep for newsletter

---

## FREQUENCY AND CADENCE DETAILS (E04)

### Welcome Sequence Cadence Options

**Conservative (New Email Marketer):**
| Email | Day |
|-------|-----|
| 1 (Deliver) | 0 |
| 2 (Resell) | 2 |
| 3 (Get to know) | 5 |
| 4 (I sell things) | 8 |
| 5+ (Ongoing) | Every 3-4 days |

**Moderate (Established List):**
| Email | Day |
|-------|-----|
| 1 (Deliver) | 0 |
| 2 (Resell) | 1 |
| 3 (Get to know) | 3 |
| 4 (I sell things) | 5 |
| 5+ (Ongoing) | Every 2-3 days |

**Aggressive (Belgray Model):**
| Email | Day |
|-------|-----|
| 1 (Deliver) | 0 |
| 2 (Resell) | 1 |
| 3 (Get to know) | 2 |
| 4 (I sell things) | 3 |
| 5+ (Ongoing) | Tue/Thu/Sat + broadcasts Mon/Wed/Fri = up to 6/week |

### Transition to Regular Broadcasting
- After the core welcome sequence (4-8 emails), transition subscribers to regular broadcast list
- Options: (a) Add to broadcast list immediately, (b) Continue welcome sequence alongside broadcasts, (c) Wait until welcome sequence completes
- Belgray's approach: overlap starts at Email 4 -- both welcome and broadcasts run simultaneously

---

## COLD LIST RE-ENGAGEMENT PROTOCOL (E04)

### When to Use
- You have not emailed your list in 30+ days
- A significant portion of subscribers have never received a broadcast from you
- You inherited or purchased a list (with proper permission)

### The Re-Engagement Sequence

**Email 1: Re-Introduction (Day 0)**
- Remind them how they got on your list
- Give something valuable immediately (re-provide lead magnet, exclusive content)
- Do NOT sell in this email
- Ask for a reply: "Are you still interested in [topic]? Just hit reply and let me know."

**Email 2: Value + Connection (Day 2-3)**
- Share your best piece of content (blog post, video, podcast episode)
- "I've got some great stuff planned for you"
- Ask a question to prompt engagement

**Email 3: Soft Sell + Choice (Day 5-7)**
- "Now that we're reacquainted, I wanted to let you know about [products/services]"
- List offers casually in PS
- Give opt-out option: "If you're not interested in hearing from me, no hard feelings. Click here to unsubscribe."

**Email 4: Engagement Test (Day 10-14)**
- Send value-forward content
- Track opens/clicks
- Anyone who has not engaged with any of the 4 emails: suppress or remove

### Critical Warning
- Sending to a cold list without re-engagement risks severe deliverability damage
- Start with your most engaged segment (most recent opt-ins)
- Gradually expand to older segments as deliverability holds
