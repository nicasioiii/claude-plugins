---
name: "Domain Reputation Recovery"
description: "Nuclear option (new domain + warmup service), ESP migration best practices, postmaster tools monitoring, and content calendar strategy for reputation."
---

# Domain Reputation Recovery

## When to Consider Recovery

You have done everything in the deliverability audit checklist, given it 2-4 weeks, and either:
- Reputation is still not improving
- Reputation is so damaged that gradual recovery is too slow
- You are landing in spam on Gmail and Outlook consistently
- Your domain appears on major blacklists (especially Spamcop)

---

## The Nuclear Option: New Domain Reset

### Four-Step Protocol (Orzechowski)

**Step 1: Register a New (But Related) Domain**

- Must have branding relevance but be different enough to be treated as a separate domain
- Example: main domain is `theemailcopywriter.com` --> register `tecmail.com`
- Example: main domain is `acme.com` --> register `getacme.com` or `acme.io`
- Do NOT use a random unrelated domain -- recipients need to recognize the connection

**Step 2: Apply the Full Checklist to the New Domain**

- Set up all DNS authentication (SPF, DKIM, DMARC) from scratch
- Configure custom tracking domain
- Set up email signature (plain text)
- Set up inbox with real profile picture, name, backup email, phone
- Change all from-email addresses to the new domain

**Step 3: Start with Ultra-Low Volume**

- Begin with warmup only -- no cold campaigns
- Target only your most engaged/qualified leads first
- Follow the 30-day ramp protocol (see warmup-and-ramp-protocol.md)
- Be patient -- rushing this step defeats the entire purpose

**Step 4: Sign Up for a Warmup Service**

- **Recommended:** Lemwarm ($30-40/month) for rehabilitation specifically
- Lemwarm is most effective when you are sending minimal real email (better warmup-to-real ratio)
- Dashboard shows red/yellow/green meter for readiness
- Let it run 30-60-90 days before full cold campaign launch
- Gradually reintroduce campaigns as the meter turns green

### What to Do with the Old Domain

- Do NOT abandon it immediately -- keep forwarding active
- Reduce volume gradually over 2-4 weeks
- Eventually use it only for receiving replies to existing threads
- Do not delete it -- domain age has value if you ever want to rehabilitate it later

---

## ESP Migration Best Practices

### Switching Email Platforms Without Losing Reputation

The authenticated domain carries reputation through the transition -- this is why authentication must be perfect before migrating.

**Pre-Migration Checklist:**

1. Get SPF and DKIM set up for the NEW provider in DNS **before migrating**
2. Ideally, have 30 days of clean sending history with proper authentication on the old platform first
3. Add the new provider's include statements to SPF record before the cutover
4. Add the new provider's DKIM record before the cutover
5. Update DMARC reporting email if needed

**Migration Strategies:**

**Option 1: Gradual Migration (Recommended)**
- Move automations to new platform first, keep campaigns on old platform
- OR move campaigns first, keep automations on old platform
- Run both in parallel for 2-4 weeks
- Complete the switch once new platform is stable

**Option 2: Clean Cutover**
- Set up everything on new platform
- Verify all authentication passing
- Switch all sending in one move
- Only recommended when moving between two well-established ESPs

### Migration Direction Impact

| Migration Direction | Expected Impact |
|---------------------|-----------------|
| Reputable ESP to reputable ESP | Minimal impact if authentication is clean |
| Custom/homegrown SMTP to reputable ESP | Likely improvement |
| Reputable ESP to custom SMTP | Likely decline |
| Free/shared plan to dedicated plan | Likely improvement |

---

## Postmaster Tools Monitoring

### Google Postmaster Tools (Primary)

**What you see:**
- IP reputation (High/Medium/Low/Bad) -- daily, weekly, monthly, quarterly
- Spam complaint rates
- Bounce rates
- DMARC pass rates
- Encryption rates

**How to use:**
1. Register your domains and sending IPs
2. Check weekly for trends
3. Look for correlation between reputation dips and sending changes
4. If reputation drops from High to Medium: investigate immediately
5. If reputation drops to Low: pause cold campaigns, increase warmup

**Key metric:** If your spam complaint rate exceeds 0.3%, you are in danger territory.

### Yahoo Feedback Loop

- Different format from Google -- more raw data, harder to parse
- Registers for feedback on spam complaints
- Set up once, review monthly

### Microsoft SNDS

- Monitor Outlook/Hotmail delivery specifically
- Important because Microsoft handles a large share of business email
- Less granular than Google Postmaster but still valuable

### MXToolbox Monitoring (Paid)

- Aggregates all feedback loops into one dashboard
- Creates unified quality score across all providers
- Sends alerts when reputation changes
- Worth the investment at 10+ domains

---

## Content Strategy for Reputation Rebuilding

During reputation recovery, every email must maximize engagement signals.

### The Content Calendar Approach (Orzechowski)

**Problem:** Only emailing when you want something (sales, promotions) creates a purely promotional pattern that ISPs penalize.

**Solution:** Build a content calendar with balanced content:

| Content Type | Purpose | Frequency |
|-------------|---------|-----------|
| Educational | Builds trust, demonstrates expertise | 2-3x/week |
| Conversational | Invites replies (strongest engagement signal) | 1x/week |
| Promotional | Drives revenue | 1x/week max during recovery |

### Nine-Word Email Strategy (During Ramp-Up)

Send a short question (~9 words) that invites a literal reply:
- "Are you still looking for help with [topic]?"
- "Hey [name], is [problem] still on your plate?"
- Replies are the strongest engagement signal to ISPs
- Use periodically to boost bidirectional email flow

### Setting Expectations

During ramp-up, clearly state in early emails:
- What kind of content you will send
- How frequently you will email
- What they should expect
- Meeting expectations = high engagement = great deliverability

---

## Recovery Timeline Expectations

| Scenario | Expected Recovery Time |
|----------|----------------------|
| Missing authentication (fix DNS records) | 1-2 weeks |
| New domain + warmup | 2-4 weeks |
| Moderate reputation damage + fixes | 4-8 weeks |
| Severe reputation damage (nuclear option) | 60-90 days |
| Blacklist removal (Spamcop) | Varies -- 24 hours to 2 weeks depending on list |

### Signs of Recovery

- Google Postmaster reputation improving from Low/Medium to High
- Mail-Tester scores consistently above 9/10
- Cold email open rates returning to 50%+
- Spam folder placement decreasing
- Reply rates improving

### When to Resume Full Cold Campaigns

Only resume full-volume cold campaigns when ALL of the following are true:
1. Warmup dashboard shows green/ready
2. Google Postmaster shows Medium or High reputation
3. Test emails land in inbox (not spam/promo) across all major providers
4. At least 2 weeks of warmup-only sends completed
5. Mail-Tester score above 9/10

Resume at 50% previous volume, ramp back to full over 2 weeks.
