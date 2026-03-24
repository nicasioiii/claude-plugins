---
name: Cold Email
description: Write a cold email (body, subject, CTA) for a specific ICP and offer, with 2-3 follow-up variants
argument-hint: "<prospect details, offer, or ICP>"
---

# /cold-email

Write a cold email with subject line, first line, body, CTA, and 2-3 follow-ups. Synthesized from Berman 3-C, 30MPC REPLY Method, Bree Weber Ethical Cold Pitching, Cold Email Wizard, and Acquisition X frameworks.

## Trigger

User runs `/cold-email` or asks to write a cold email, prospecting email, outreach email, pitch email, or email script.

## Skills Activated

- `cold-email-copy` (primary)
- `first-lines` (for personalized opener)

## Gather Context

Before writing, collect or infer these inputs. Check `.claude/product-marketing-context.md` first -- only ask for what is missing:

1. **Who is the prospect?** (industry, company size, job title, specific company name if available)
2. **What are you selling?** (specific offer, not generic service -- "3 newsletters that convert" not "copywriting services")
3. **What is your case study?** (company name + result + timeframe -- or note if you have none)
4. **What is your CTA goal?** (book a call, qualify interest, get a reply)
5. **What context level?** Determines framework:
   - Scale outbound (30-100+ emails/day) → Berman 3-C or Cold Email Wizard One Question
   - Enterprise SDR/AE → 30MPC REPLY Method
   - High-value freelance/consulting (1-5 prospects/week) → Bree Weber 8-Step

## Framework Selection Logic

| Context | Framework | Email Length |
|---|---|---|
| Agency/SaaS scale outbound | Berman 3-C | Ultra-short (3-5 sentences) |
| Tool/service qualification | Cold Email Wizard One Question | 2-3 sentences |
| Enterprise B2B SDR/AE | 30MPC REPLY Method | Short but problem-rich (under 150 words) |
| High-value freelance pitch | Bree Weber 8-Step | Long-form (90%+ about them) |
| No case studies available | Bree Weber (problem-first) or CEW (qualifying question) | Varies |

## Output Format

Deliver the following for each email:

### 1. Subject Line
- Provide 3 options ranked by likely open rate
- Include A/B test recommendation
- Reference `cold-email-copy/references/subject-lines-and-ctas.md` for frameworks

### 2. Email Body
- First line (personalized -- use `first-lines` skill formulas)
- Body (framework-appropriate structure)
- CTA (interest-based, never ask for time unless justified urgency)

### 3. Follow-Up Variants (2-3)
- Follow-up 1: Quick bump (+3 days)
- Follow-up 2: Value-add or new angle (+4-6 days)
- Follow-up 3: Breakup (+3-4 days)

### 4. Technical Compliance Check
Verify against these non-negotiable rules:
- [ ] Under 150 words (for scale frameworks; Bree Weber exempted)
- [ ] No links in initial email
- [ ] No images
- [ ] No spam trigger words
- [ ] Plain text format
- [ ] Spintax suggestions on CTA
- [ ] Unsubscribe note included

### 5. Optimization Notes
- What to A/B test first (subject line, then CTA, then body)
- What signals to watch for (opens, replies, bounces)
- When to escalate to full sequence (hand off to `/campaign-sequence`)

## Example Interaction

**User:** Write a cold email for my agency that does Google Ads for e-commerce brands. We helped a shoe brand go from $50K to $200K/month in 3 months. Targeting DTC brands doing $1M-$10M/year.

**Assistant produces:**
- 3 subject line options
- Full email using Berman 3-C (scale context)
- Spintax variants on CTA
- 3 follow-ups with timing
- Technical compliance check
- A/B testing recommendations
