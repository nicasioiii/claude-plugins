---
name: Write Welcome Sequences
description: |
  MANDATORY TRIGGERS: welcome sequence, welcome series, welcome emails, onboarding sequence,
  onboarding emails, lead magnet delivery, get to know you emails, personality-driven welcome,
  split-path welcome, creator welcome, newsletter welcome, info-product welcome, service welcome,
  welcome funnel, new subscriber sequence, opt-in follow-up, welcome email series.
  FOR: Welcome sequences for creator/service/info-product businesses, split-path funnel architecture (multiple opt-in paths merging), lead magnet delivery emails, resell-the-freebie emails, get-to-know-you emails, "I sell things" transparency emails, story-based selling emails, mystery/curiosity emails, myth-busting emails, survey/bribe emails, second-chance emails (saves ~8%), conditional content, repurposing broadcasts into welcome sequences, upsell/tripwire pages, list hygiene (100-day scrub), Fibonacci cadence, cold list re-engagement, and monetization mechanics inside welcome sequences.
  Do NOT use for: Ecom welcome flows with Klaviyo triggers and discount logic (use ecom-flows), launch sequences (use write-launch-sequence), regular campaign strategy (use plan-email-campaigns), email copywriting frameworks (use write-email-copy), subject line craft (use write-subject-lines).
---

# Write Welcome Sequences

Write welcome sequences for creator/service/info-product businesses -- lead magnet delivery, reselling the freebie, get-to-know-you emails, "I sell things" transparency, story-based selling, surveys, and conditional content.

**Key distinction:** This skill covers welcome sequences for creators, service providers, and info-product businesses. For ecommerce welcome flows with Klaviyo triggers, discount stacking, and purchase filters, use `ecom-flows` instead. Use `/write-welcome` command to determine which path is appropriate.

---

## CORE PHILOSOPHY (Belgray -- E04)

**"The only wrong number of emails for a welcome sequence is zero."** Anyone without one is leaving money, loyalty, connection, and the chance for people to get to know you on the table.

**The party analogy:** You do not want anyone coming through your door and having no one to greet them, show them around, offer them a drink, or take their coat. Every new subscriber should get that "first guest experience."

**Start simple and add over time.** Belgray started with 3-5 emails in 2017, now the sequence is much longer. Do not let perfectionism stop you from launching with a few emails. "Slap Shit Up" -- put something out there and iterate.

---

## SPLIT-PATH ARCHITECTURE

### Funnel Structure (Diverge at Top, Merge Below)

```
[Lead Magnet A]    [Lead Magnet B]    [Newsletter Only]
      |                  |                   |
  Email 1A           Email 1B           Email 1C
  (Deliver LM)     (Deliver LM)       (Welcome)
      |                  |                   |
  Email 2A           Email 2B           Email 2C
  (Resell LM)      (Resell LM)        (Best content)
      \                  |                  /
       \                 |                 /
        -----> MERGE INTO SHARED SEQUENCE <-----
                         |
              Email 3: Get to Know You
              Email 4: "I Sell Things"
              Email 5+: Ongoing welcome content
```

### How It Works
1. People opt in via different lead magnets or just the newsletter
2. Each path gets 2 tailored delivery/welcome emails
3. Everyone funnels into one shared main welcome sequence
4. A "second chance" email catches people who said "no" to newsletter emails

---

## THE YES/NO OPT-IN CHECKBOX

When opting in for a lead magnet, subscribers can check whether they also want newsletter emails.

- Helps list health and deliverability -- people who actively choose are more engaged
- The welcome sequence then persuades ~8% of "no" people to change their mind via the Second Chance email
- Implementation: checkbox on opt-in form, tag-based routing in ESP

---

## TIMING ARCHITECTURE

### First 4 Emails
- Subscribers are held from receiving regular broadcasts
- They receive ONLY the welcome sequence during this period

### After Email 4
- They become "full subscribers" and start getting BOTH:
  - Welcome sequence emails (e.g., Tue/Thu/Sat)
  - Regular broadcasts (e.g., Mon/Wed/Fri)
- Total: up to 6 emails per week for a period
- [CONTRARIAN -- E04] This increases unsubscribes but ALSO increases sales, results, and engagement

---

## EMAIL-BY-EMAIL TEMPLATE

### Email 1: Lead Magnet Delivery + Orientation
**Timing:** Immediately upon opt-in
**Subject line:** Make it obvious what they are getting. No curiosity here -- just deliver.

**Structure:**
- Deliver the lead magnet with a direct download link right away (top of email)
- What to expect: "The first emails you get from me are automated, part of a 'welcome sequence'"
- Add tone-deaf timing caveat: "They don't acknowledge any uncertain times we might be experiencing. Think of them as a great TV series."
- "What I know about you" line: "Since you signed up for [X], I'm guessing you're into [Y]. You're in the right place."
- 3 CTAs max: (1) Follow on Instagram, (2) Whitelist my email address, (3) Hit reply and tell me you got it / how you found me
- Link to your best content/blog post

**Key tactic:** Do NOT link to social media from your website. Save the "follow me" ask for email. Website purpose = opt-ins and purchases. Email purpose = deepen connection.

### Email 1-B: Second Chance for Non-Subscribers
**For people who checked "no" to newsletter emails**
**Subject:** "Is this it for us? I don't wanna say goodbye"

**Structure:**
- "Wanted to make extra sure you don't want my newsletter emails"
- "You checked the 'No' box when you signed up"
- CTA: "YES, [Name], keep raining genius upon my inbox!"
- "If not, this is the last you'll hear from me. I'll be OK with it... in time. But will you?"
- **Result: Saves ~8% of people who originally said no**

### Email 2: Resell the Lead Magnet
**Timing:** ~1 day after Email 1
**Purpose:** People are "opt-in freebie hoes" who download things and never look at them.

**Structure:**
- Acknowledge the pile of unused freebies: "Yes, I'm pretending not to see that pile in the corner"
- Re-describe the lead magnet's value as if selling a paid course
- Tell them why it matters and what it will do for them
- "If you can't find it in the stack, grab it again here" (re-download link)
- Drive to your best blog post/content
- PS: Whitelist me again
- PPS: Introduce survey ("I'm about to fall in love with you when you take 2 minutes to answer these q's")

**Key insight:** [CONTRARIAN] You need to SELL people on what they already got, even or especially if it is free, because they did not invest anything but their email.

### Email 3: Get to Know You / Fun Facts
**Timing:** ~2 days after Email 2
**Reply rate achieved:** 4.28% (extremely high)

**Structure:**
- Story hook about faking familiarity with someone
- "So that we don't have to fake it, let's get to know each other"
- List of fun facts about you -- many linked to your website (blog posts, portfolio, media)
- Include credibility markers woven into fun facts (clients, media, awards)
- Include a professional photo
- Turn to the reader with questions:
  - "What's one weird thing only friends know about you?"
  - "What was the easiest money you ever made?"
  - **"How'd you come across me?"** (most important -- tells you what channels work)
  - Fun question: "What one meal would you have for the rest of your life?"
- PS: "I really mean it, write me back!"

**Why emphasize replies:** People do not believe you want to hear from them. You have to repeatedly insist. Replies also boost deliverability.

### Email 4: "I Sell Things" Transparency Email
**Open rate achieved:** 61%

**Structure:**
- Build nervous tension: "I've been wondering, is it too soon to tell you this?"
- Reveal: "Sometimes, I sell things. Whew, felt good to say that!"
- List your own products with links
- Explain affiliate promotions transparently
- Warn about promotional periods
- Explain why new subscribers are not excluded from active promotions
- Offer soft opt-out for any active promotion
- Close: "I actually LIKE selling. Also? I like making money."

**This email serves 5 functions:**
1. Sells products (lists them with links)
2. Addresses objection about selling head-on
3. Filters people who are offended by selling
4. Shifts perspective on your selling approach
5. Prepares new subscribers for promotion periods

**Key insight:** [CONTRARIAN] In the online space there is a stigma around selling. Rather than hiding it, point it out and mock the over-sensitivity.

### Email 5+: Ongoing Welcome Content
After Email 4, subscribers enter the "full" welcome sequence alternating with regular broadcasts. See `ref-welcome-sequence-creator.md` for detailed templates of ongoing email types.

Email types for the extended sequence:
- **Story + Copy Lesson + Soft Sell** (5.67% CTR to product page)
- **Testimonial + Dual Product Pitch** (5.62% CTR)
- **Pure Value / Teaching** (no direct sell -- builds trust)
- **Mystery / Curiosity** (18.3% CTR -- highest in entire sequence)
- **Myth-Busting** (bust bad advice; builds authority)
- **Survey / Bribe** (65% open rate with "Bribe you" subject line)

---

## CONVERSION BENCHMARKS (Belgray -- E04)

| Metric | Value |
|--------|-------|
| Reply rate on "Let's not fake it" email | 4.28% |
| CTR on "#1 writing trick" mystery email | 18.3% |
| CTR to product via "Should've knocked" email | 5.67% |
| % who click to product and buy within 10 days | 3.92% |
| % who click to product and buy within 100 days | 13.34% |
| Open rate on "Bribe you" survey email | 65% |
| Open rate on "Too soon?" (I sell things) email | 61% |
| Second chance email conversion (no to yes) | ~8% |

---

## WELCOME SEQUENCE PRINCIPLES

### Conditional Content (E04)
Use ESP dynamic content blocks to show different text to different segments within the same email:
- Lead magnet opt-ins see one block, newsletter opt-ins see another
- Product owners see a different offer than non-owners
- Active Campaign, ConvertKit, and Klaviyo all support this

### Repurpose Best Broadcasts (E04)
When a regular email performs exceptionally well (high opens, clicks, replies, sales), add it into the welcome sequence so new subscribers do not miss it. This is how welcome sequences grow over time.

### One CTA Per Email -- Or Not
- [CONTRARIAN -- E04] Belgray regularly uses multiple CTAs in welcome sequences where the goal is exploration, not a single conversion action
- Save the strict single-CTA rule for promotion periods
- Limit to 3 CTAs max per email in the welcome sequence

### Frequency Tolerance
- [CONTRARIAN -- E04] 6 emails per week is not too many for your ideal audience
- People who find it too much are not your ideal audience
- The increase in unsubscribes is offset by increases in sales and engagement

---

## WELCOME SEQUENCE DIY PLANNING

### Action Agenda (Before Writing)
List what you most want subscribers to do across the welcome sequence:
- Buy something
- Book a free call / service
- Take a survey
- Refer a friend
- Visit your site / resources page
- Listen to best podcast episodes
- Follow on social media
- Join a waitlist / community / Facebook group
- Share/forward the email
- Leave a rating/review

**Map one primary CTA per email.** Spread actions across the sequence.

### 5-Email Starter Template

| Email | Purpose | Key Elements |
|-------|---------|-------------|
| 1 | Deliver lead magnet + orientation | Download link, expectations, whitelist ask, reply ask, social follow |
| 2 | Resell the lead magnet | Remind to use it, link to best content, optional second lead magnet |
| 3 | Get to know you / origin story | Fun facts, credibility, manifesto/values, ask about them |
| 4 | Story + why they need your product | Tell a story, showcase testimonials, product CTA |
| 5 | Value/tip + CTA to content/product | Deliver a tip, point out common mistake, connect to CTA |

---

## THROSSELL WELCOME SERIES PRINCIPLES (E06)

### Keep Them Out of Live Emails
Hold people from "live" broadcasts until they complete the welcome sequence. The welcome series should only run as long as the "canned" emails are BETTER than the "fresh" ones.

### Get Replies, Not Whitelists
Asking to whitelist has very low compliance. Better: get someone to REPLY. Replies are deliverability gold. Best time: welcome email when someone is warm. Bribe them into replying by offering something they want. Allow blank replies if they find it awkward.

### Never Ask Your List to Do Something for Free
Always bribe them with something more valuable than what you are asking. Appeal to self-interest, not charity.

---

## MONETIZATION INSIDE WELCOME SEQUENCES (E04)

### Direct Product Sales
- Feature products in PS sections and dedicated emails
- Use conditional text: show product offers only to non-purchasers
- Every email that drives to a product page contributes to a 10-day and 100-day conversion pipeline

### Affiliate Transparency
- The "I sell things" email doubles as a product catalog
- Transparent affiliate disclosure builds trust
- Warn about upcoming promotions so new subscribers are not surprised

### Survey as Segmentation Tool
- 2-question, 90-second survey
- Key questions: (1) What are you interested in? (2) Which products have you already bought?
- "Which have you taken" question lets you exclude owners from future promos
- Adding survey CTA to 2 more welcome emails increased daily submissions by 40%

### Upsell / Tripwire Page
- After any opt-in, redirect to page offering a product at half price for 10-20 minutes
- Captures impulse buyers immediately
- Reduces but does not eliminate welcome sequence conversion opportunities

---

## INSTRUCTOR DISAGREEMENTS (RESOLVED)

| Topic | Belgray (E04) | Throssell (E06) | Synthesis |
|-------|---------------|-----------------|-----------|
| Welcome series length | Start with 3-5 and grow over time | Only go as long as canned > fresh | Both valid; start minimal, add proven performers |
| Getting replies | "I really mean it, write me back!" + questions | Bribe people into replying; allow blank replies | Both strategies work; use bribes for initial email, genuine questions for later |
| Multiple CTAs | Regularly uses 2-3 CTAs per email | Prefers focused single-CTA | Context: exploration phase = multiple CTAs; selling phase = single CTA |
| Email frequency | 6/week is fine for ideal audience | Daily is fine if interesting | Both agree: frequency tolerance depends on content quality |

---

## CROSS-REFERENCES

| Need | Skill |
|------|-------|
| Ecom welcome flows (Klaviyo, discount codes) | `ecom-flows` |
| Writing email body copy | `write-email-copy` |
| Subject line formulas for welcome sequence | `write-subject-lines` |
| Launch sequence (when welcome feeds into launch) | `write-launch-sequence` |
| List segmentation for conditional content | `segmentation-list-health` |
| Newsletter content after welcome sequence | `write-newsletter-content` |
| Overall email program architecture | `strategy-email-program` |
| List growth and pop-up optimization | `list-growth-forms` |
